pipeline {
    agent any

            stage('Install Dependicies') {
            steps {
                echo 'Dependencies'
                script{
                    if(isUnix()){
                        sh 'npm install'
                    }else{
                        bat 'npm install'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Test'
                script{
                    if(isUnix()){
                        sh 'npm test'
                    }else{
                        bat 'npm test'
                    }
                }
            }
        }
        stage('Reports') {
            steps {
                echo 'Reports'
               script{
                    if(isUnix()){
                        sh 'npm run report'
                    }else{
                        bat 'npm run report'
                    }
                }
            }
        }
        stage('Publish Reports') {
            steps {
                echo 'Publish Report'
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: '', reportFiles: 'cucumber_report.html', reportName: 'cucumber Report', reportTitles: ''])
            }
        }
    }
}
