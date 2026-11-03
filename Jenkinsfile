
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                sh 'whoami'
                sh 'pwd'
            }
        }

        stage('Build') {
            steps {
                echo 'Building application'

                sh '''
                    mkdir -p build
                    echo "Hello from GitHub and Jenkins" > build/app.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'cat build/app.txt'
            }
        }
    }

    post {
        success {
            echo 'GitHub integration successful!'
            echo 'Building application'
        }

        failure {
            echo 'GitHub integration failed!'
        }
    }
}
