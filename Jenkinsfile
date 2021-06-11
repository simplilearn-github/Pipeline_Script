pipeline {
    agent none
    
    stages {
        stage('Non-Parallel Step') {
            agent {
                label "master"
            }
            steps {
                echo 'This stage will executed first'
            }
        } 
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "CentOSNode1"
                    }
                    steps {
                        echo "Task1 on Agent"
                    }            
                }
                stage('Test on Master') {
                    agent {
                        label "master"
                    }
                    steps {
                        echo "Task1 on Master"
                    }            
                }        
            }        
        }
    }
}
