pipeline {
    agent any 
    stages {
        stage('sonarqubeanalysis') {
            agent {
                docker{
                    image 'openjdk:11'
                }
            }
            steps {
                script{
                    withSonarQubeEnv(credentialsId: 'sonartocken') {
                         sh 'chmod +x gradlew'
                         sh './gradlew sonarqube'
                         }

                }
            }
        }
    }
}