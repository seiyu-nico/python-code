FROM python:3.11.2-alpine
# 環境変数 PYTHONUNBUFFEREDを設定
ENV PYTHONUNBUFFERED 1
RUN mkdir /src
# mkdirコマンドの実行
# 作業ディレクトリの設定
WORKDIR /src
# requirements.txtを/codeに追加する
COPY requirements.txt ./
# Pythonのパッケージ管理ツールのpipをアップグレード
RUN pip install --upgrade pip
# pipでrequirements.txtに指定されているパッケージを追加する
RUN pip install -r requirements.txt

ENV user tech
RUN useradd -u 1000 -m -d /home/${user} -g staff ${user} \
  && chown -R ${user} /home/${user}
USER ${user}
