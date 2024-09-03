pipeline {
    agent any
    environment {
        registry = 'docker.io'  
        registryCredential = 'docker' 
    }
 
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/santoshPagire/ecommerce_web.git', branch: 'main'
            }
        }

        stage('build image') {
            steps{
                script{
                    docker.withRegistry('', registryCredential){
                        def customImage = docker.build("santoshpagire/ecommerce-app")
                        customImage.push()
                        

                    }
                    
                }
            }
        }

        // stage('Deploy Container') {
        //     steps {
                
        //         script {
        //             docker.withRegistry('', registryCredential) {
        //                 def runContainer = docker.image("santoshpagire/myjava-app:${env.BUILD_ID}").run('--name mynew-container -d')
        //                 echo "Container ID: ${runContainer.id}"
        //             }
        //         }
        //     }
        // }
        
    }
 
  
}
