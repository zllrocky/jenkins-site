pipeline {
    agent any

    environment {
        // Указываем путь к Node.js на твоей Windows
        NODE_PATH = 'C:\\Program Files\\nodejs'
        // Добавляем Node в PATH (синтаксис Windows использует ; вместо :)
        PATH = "${env.NODE_PATH};${env.PATH}"
    }

    stages {
        stage('Prepare Workspace') {
            steps {
                // Переходим в твою реальную папку проекта
                dir('C:\\Users\\Acer\\GIT Traning\\jenkins-site') {
                    // В Windows вместо sh используем bat
                    bat 'npm install'
                    bat 'npm run build'
                }
            }
        }

        stage('Run Tests') {
            steps {
                dir('C:\\Users\\Acer\\GIT Traning\\jenkins-site') {
                    // Запускаем тесты
                    bat 'npm test'
                }
            }
        }
    }

    post {
        always {
            echo 'Билд завершен. На Windows сервер обычно закрывается сам после выполнения bat-команд.'
        }
    }
}