pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven"
    }
    environment {
        SETTINGS = '/var/lib/jenkins/settings.xml'
    }

    stages {
        stage('Build') {
            steps{
               sh 'mvn clean install'
            }
        }
        stage('Test'){
            steps{

                sh 'mvn test'
                

                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}