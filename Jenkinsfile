@Library('jenkins-shared-libraries')_
pipeline{
    agent any
    stages{
        stage("Code Cloning"){
            steps{
                script{
                clone("https://github.com/sarvajeetnarkhede/django-notes-app.git","main")
                }
            }
        }
        stage("Code Build"){
            steps{
                script{
                docker_build("notes-app","latest","sarvajeet123")
                }
            }
        }
        stage("Push to Dockerhub"){
            steps{
                script{
                docker_push("notes-app","latest","sarvajeet123")
                }
            }
        }
        stage("Deploy"){
            steps{
                script{
                    docker_compose()
                }
            }
        }
    }
}
