@Library('mylibrary')_

pipeline
{
    agent any
    stages
    {
        stage('Download_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('Build_Master')
        {
            steps
            {
                script
                {
                    cicd.buildartifact()
                }
            }
        }
        stage('Deployment_Master')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("Sharedlibrary","172.31.10.172","testapp")
                }
            }
        }
        stage('Testing_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("FunctionalTesting")
                    cicd.runSelenium("Sharedlibrary")
                }
            }
        }
        stage('Delivery_Master')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("Sharedlibrary","172.31.3.113","myprod")
                }
            }
        }
    }
}
