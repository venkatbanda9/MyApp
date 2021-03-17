pipeline{
    agent any
    stages{
    stage('CDownload_Master'){
        steps{
            script{
            try{
                git 'https://github.com/venkat18396/sample9.git'
            }
            catch(Exception e){
                mail bcc: '', body: 'Jenkins job failed to download git at stage "CDownload"', cc: '', from: '', replyTo: '', subject: 'JENKINS JOB CDownload', to: 'venkat.18396@gmail.com'
                abort(1)
                
            }
        }
        }
    }
    stage('CBuild_Master'){
        steps{
            script{
            try{
                sh 'mvn package'
            }
            catch(Exception e){
                mail bcc: '', body: 'Jenkins job failed to at stage "CBuild"', cc: '', from: '', replyTo: '', subject: 'JENKINS JOB CBuild', to: 'venkat.18396@gmail.com'
                exit(1)
            }
            }
            }
        }
	}
	}
