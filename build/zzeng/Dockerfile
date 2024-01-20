# use python img
FROM python:3.8-slim

ARG SOME_CONDITION

# set /app
WORKDIR /app

# copy
COPY . /app

# install necessary ones
RUN pip install --no-cache-dir -r requirements.txt

# expose 80
EXPOSE 80

# set env
ENV NAME World

# run with condition app.py
RUN if [ "${USE_SVN}" = "1" ]; then \
        echo "ここに1だったときのコマンド"; \
    else \
        echo "ここに1じゃなかったときのコマンド"; \
fi

RUN if [ "${SOME_CONDITION}" = "true" ]; then \
        echo "ここに1だったときのコマンド"; \
        cp app02.py / ; \
    else \
        echo "ここに1じゃなかったときのコマンド"; \
fi

RUN if [ "$SOME_CONDITION" = "true" ]; then \
        cp app.py run.py; \
    else \
        cp app02.py run.py; \
    fi

CMD ["python", "run.py"]

