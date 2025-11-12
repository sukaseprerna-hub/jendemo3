pipeline {
    agent any

    environment {
        PYTHON = 'C:\\Program Files\\Python314\\python.exe'

    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '''
                %PYTHON% -m pip install -r requirements.txt
                '''
            }
        }

        stage('Run API ETL Script') {
            steps {
                bat '%PYTHON% extract_data.py'
            }
        }
    }
}
