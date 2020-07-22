pipeline {
  agent any
  stages {
    stage('') {
      steps {
        sh '''pwd
ls
sudo rm -f report.log && sudo rm -rf report/
sudo cp -r /var/lib/jmeter-scenarios/* $WORKSPACE
docker run --name jmeter --net=host --rm --volumes-from=jenkins -e SCENARIO=$WORKSPACE/$SCENARIO -e WORKSPACE=$WORKSPACE -e USERS=$USERS -e RAMPUP=$RAMPUP -e DURATION=$DURATION -e BUILD_NUMBER=$BUILD_NUMBER -e BUILD_URL=$BUILD_URL java:8-jdk 
'''
      }
    }

  }
}