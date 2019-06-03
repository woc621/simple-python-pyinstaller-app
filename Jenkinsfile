pipeline {
  agent {
    docker {
      image 'qnib/pytest'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'python -m py_compile sources/add2vals.py sources/calc.py'
      }
    }
    stage('Test') {
      steps {
        sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py'
      }
    }
  }
}