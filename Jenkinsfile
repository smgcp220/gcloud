pipeline {
  agent any
  environment {
      CLOUDSDK_CORE_PROJECT='gcp-learn-413221'
      GCLOUD_CREDS=credentials('gcloud-creds')
  }
  stages {
    stage('Run gcloud') {
      steps {
          withEnv(['GCLOUD_PATH=/usr/local/bin']) {
          sh '''
             $GCLOUD_PATH/gcloud auth activate-service-account --key-file="$GCLOUD_CREDS"
             $GCLOUD_PATH/gcloud version
             $GCLOUD_PATH/gcloud compute zones list
         '''
          }
      }
    }
  }
}
