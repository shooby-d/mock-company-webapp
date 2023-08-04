pipeline {
  
  agent any

    stages {
        stage('Build') {
            steps {
                // TODO: Build the application using Gradle
                sh './gradlew assemble'
            }
        }

        stage('Test') {
            steps {
                // TODO: Run tests using Gradle
                sh './gradlew test'
            }
        }
    }

    post {
        always {
            // TODO: Archive the build artifacts
            archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true
        }

        success {
            // TODO: Send a notification on successful build
            echo 'Build and test succeeded!'
        }

        failure {
            // TODO: Send a notification on build failure
            echo 'Build and test failed!'
        }
    }
}
