pipeline {
    agent any        
    stages { 
	 stage('build') {
            when {
                branch 'dev'
            }
            steps {
                ansiblePlaybook credentialsId: 'ssh_id', disableHostKeyChecking: true, inventory: '/etc/ansible/hosts', playbook: '/etc/ansible/git-test.yml'
            }
        }
         stage('Test for production') {
            when {
                branch 'qa'
            }
            steps {
                sh 'echo "Hello world!"'
            }
        }	
   }
    } 
