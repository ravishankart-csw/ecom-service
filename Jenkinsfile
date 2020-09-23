pipeline {
   agent any

   tools {
      maven "M3"
   }

   stages {
      stage('Build') {
         steps {
            git 'https://github.com/ravishankart-csw/ecom-service.git'

            // Run Maven
            sh "mvn -Dmaven.test.failure.ignore=true clean package"
         }
      }


      stage('Checkpoint') {
          steps {
              echo "Analyze if all scan-results are within threshold"
              //sh "python3 /opt/tools/custom/checkpoint.py"
          }
      }

      stage('Publish Artifacts') {
         steps {
            sh "echo 'Pushing to Nexus'"
            sh "sleep 30"
            //sh "echo 'Pushing Docker .. ' "
            //sh "docker push kmasani/myapp:${DOCKER_RELEASE_TAG}"
         }
      }

         

   }
}
