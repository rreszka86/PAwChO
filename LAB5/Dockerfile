FROM scratch
ADD alpine-minirootfs-3.19.1-x86_64.tar /

RUN apk update && apk add nodejs npm

WORKDIR /usr/app

COPY ./web/package.json ./
RUN npm install

COPY ./web/index.js ./

EXPOSE 8080

ARG VERSION
ENV APP_VERSION=${VERSION:-test_build}

CMD ["npm", "start"]