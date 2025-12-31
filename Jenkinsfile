pipeline {
    agent any   // روی هر نودی اجرا شود

    environment {
        // اگر نیاز به متغیر محیطی داری اینجا می‌تونی اضافه کنی
        GREETING = "Hello from Jenkins Pipeline!"
    }

    stages {
        stage('Checkout') {
            steps {
                echo "Cloning repository from GitHub..."
                git branch: 'main', url: 'https://github.com/USERNAME/REPO.git'
            }
        }

        stage('Prepare Script') {
            steps {
                echo "Making bash.sh executable..."
                sh 'chmod +x bash.sh'
            }
        }

        stage('Run Script') {
            steps {
                echo "Running bash.sh..."
                sh './bash.sh'
            }
        }

        stage('Post Actions') {
            steps {
                echo "Pipeline finished successfully!"
            }
        }
    }

    post {
        success {
            echo "✅ Build completed successfully!"
        }
        failure {
            echo "❌ Build failed!"
        }
        always {
            echo "This always runs, cleanup or notifications can go here."
        }
    }
}
