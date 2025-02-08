FROM python:3.9
WORKDIR /src
# 必要なシステムライブラリーをインストール
RUN apt-get update && apt-get install -y \
    gcc \
    libpq-dev \
    gdal-bin \
    libgdal-dev \
    netcat-openbsd \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ADD requirements.txt /src/
RUN pip install -r requirements.txt

# GDALのライブラリパスを設定（環境変数を設定）
ENV GDAL_LIBRARY_PATH=/usr/lib/libgdal.so

# RUN cd ./src
# CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]