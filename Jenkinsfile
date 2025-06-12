/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'python:3.13.4-alpine3.22' } }
    stages {
        stage('build') {
            steps {
                sh 'pip --version'
            }
        }
        stage('test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('sanity') {
            steps {
                input {
                    message 'Do you want to continue?'
                }
            }
        }
        stage('deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}