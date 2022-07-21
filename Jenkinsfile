pipeline {
    agent any

    stages {
        stage('Setup') {
            steps {
                
                sh "./install_driver.sh"

            }
        }

         stage('Build') {
            steps {
                
                sh "mvn compile"

            }
        }

        stage('Test') {
            steps {
                
                sh "mvn test"

            }

            post {
                always {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }

     
        
    }
}
