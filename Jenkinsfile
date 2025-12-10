pipeline {
    agent any

    stages {

        stage('Initialize') {
            steps {
                echo "Starting CI pipeline..."
            }
        }

        stage('Run Tests in Parallel') {
            parallel {

                stage('API Tests') {
                    steps {
                        echo "Running API tests..."
                        sh """
                           sleep 20
                           echo 'API tests completed'
                        """
                    }
                }

                stage('UI Tests') {
                    steps {
                        echo "Running UI tests..."
                        sh """
                           sleep 20
                           echo 'UI tests completed'
                        """
                    }
                }

                stage('3rd step added---4th change') {
                            steps {
                                echo "Running DB migration..."
                                sh """
                                   sleep 20
                                   echo 'Migration completed'
                                """
                            }
                        }

                stage('DB Tests') {
                    stages {

                        stage('DB Backup') {
                            steps {
                                echo "Taking DB backup..."
                                sh """
                                   sleep 20
                                   echo 'Backup completed'
                                """
                            }
                        }

                        stage('Run Migration') {
                            steps {
                                echo "Running DB migration..."
                                sh """
                                   sleep 20
                                   echo 'Migration completed'
                                """
                            }
                        }
                    }
                }
            }
        }

        stage('Summary') {
            steps {
                echo "All tests finished. Pipeline complete."
            }
        }
    }
}
