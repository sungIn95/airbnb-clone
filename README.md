1.0 정리 
pip을 쓰지 않는 이유는 이렇게 설치하면 모든 곳에 설치가 된다. 이것의 문제점이 장고 버전 2을 쓰다가 3으로 바꾸고 싶을 때, 모든 곳에 영향을 주기 떄문에 서로에게 영향을 미친다. 
1.1 pip install 
 1.pip install --user pipenv
 이렇게 설치 하고 보니 
 pipenv
 zsh: command not found: pipenv 에로가 났다. 

 2.그 후에 https://www.nemonein.xyz/2018/03/355/ 에서 설치 해 봤지만 실패.
 wget https://bootstrap.pypa.io/get-pip.py -O /tmp/get-pip.py
 pip3 --version
 re: pip 22.1.2 from /home/dlrkehrud/.local/lib/python3.8/site-packages/pip (python 3.8)
 를 하고 여전히 안되서 

 3.pip list 에서 virtualenv 이 설치되어있는지 확인 해주시고
pip uninstall virtualenv
pip uninstall pipenv
pip install pipenv 이 방법 시도 후 다시 실패. 

 4. https://blog.naver.com/youngsiphone/221857231923 에서  <---해결 방법
 echo $PATH
 PYTHON_BIN_PATH="$(python3 -m site --user-base)/bin"
 PATH="$PATH:$PYTHON_BIN_PATH"
 sudo pip3 install pipenv

 and clear!!! 너무 행복하다. 

1.2 정리
내가 쓸려는 폴더에 pipenv --three 를 설치 해 준다. (pipfile)
그리고 pipenv shell 을 입력한다. (pipenv --three은 버블 생성 하지만 나의 위치는 버블 밖, 버블 안으로 들어가기 위해 입력하는것.)
pipenv install Django==2.2.5 장고 설치 pipenv install Django게 설치하면 최신버전. 
django-admin 로 제대로 깔렸는지 확인~!!!

1.3 