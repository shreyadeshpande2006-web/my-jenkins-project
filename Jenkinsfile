pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building project...'

                bat 'if exist index.html echo HTML file found'
                bat 'if exist style.css echo CSS file found'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing project...'

                bat 'if exist index.html (echo Test Passed) else (exit /b 1)'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying project...'
                echo 'Website deployment completed successfully!'
            }
        }
    }

    post {

        success {
            echo '✅ Jenkins Pipeline completed successfully!'
        }

        failure {
            echo '❌ Jenkins Pipeline failed!'
        }
    }
}
