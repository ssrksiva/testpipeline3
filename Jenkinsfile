pipeline {
  agent any
  stages {
    stage('Pull') {
      steps {
        git(url: 'https://github.com/ssrksiva/testpipeline3.git', branch: 'develop', poll: true)
      }
    }

    stage('Check Java') {
      steps {
        sh 'java -version'
      }
    }

    stage('Deliver for development') {
      when {
        branch 'develop'
      }
      steps {
        sh 'git config --global user.name "ssrksiva"'
        sh 'git config --global user.email "sssrkbsc@gmail.com"'
        sh 'git tag -a tagName5 -m "test-admin5"'
        sh 'git commit -am "Merged develop branch to master1"'
        sh 'git merge -s ours develop --allow-unrelated-histories'
        sh 'git config --global credential.username ssrksiva'
        sh 'git config --global credential.helper !echo password=14Dec@1991; echo'
        sh 'git push origin master --tags'
      }
    }

  }
}