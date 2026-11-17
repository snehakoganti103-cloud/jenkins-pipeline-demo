pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Starting Jenkins build'
                bat 'java -version'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Jenkins pipeline'
                bat 'echo Test completed successfully'
            }
        }
    }

    post {
        always {
            script {
                def result = currentBuild.currentResult

                def reason = result == 'SUCCESS'
                    ? 'Jenkins build passed'
                    : 'Jenkins build failed'

                echo "Notification: ${reason}"
            }
        }
    }
}
