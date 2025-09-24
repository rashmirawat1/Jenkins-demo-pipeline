pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the Docker image...'
                sh 'docker build -t my-python-app .'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'docker run --rm my-python-app pytest test_app.py'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the app...'
                sh 'docker run -d -p 8000:8000 --name my-running-app my-python-app'
            }
        }
    }
}