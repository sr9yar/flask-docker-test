FROM ubuntu:bionic


RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y python-virtualenv virtualenv ca-certificates git nano net-tools wget 

RUN \
  apt-get install -y python3 python3-pip python3-dev python3-setuptools python3-virtualenv 
  
RUN \
  cp /usr/bin/python3.6 /usr/bin/python && \
  cp /usr/bin/pip3 /usr/bin/pip

RUN \
  python -m pip install --upgrade pip &&\
  cp /usr/local/bin/pip3.6 /usr/bin/pip





ADD ./  /project

# RUN  virtualenv /venv --python=python3.6 && source /venv/bin/activate

WORKDIR /project




# #  ------------------- installing PyAV END  -------------------


# #  ------------------- installing requirements  -------------------
RUN pip install --trusted-host pypi.python.org -r requirements.txt 
# --force-reinstall
# #  ------------------- installing requirements END -------------





ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8
ENV FLASK_APP=run.py 
ENV APP_CONFIG_FILE=development.py



# EXPOSE 5000
CMD ["flask", "run"]

# CMD ["python", "run.py"]
# CMD ["tail", "-f", "/dev/null"]

