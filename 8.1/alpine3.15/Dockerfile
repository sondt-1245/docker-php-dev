# NOTE: This file was generated via generate.sh. Don't edit it directly

FROM sunasteriskrnd/php:8.1.9-nginx-alpine3.15

ENV COMPOSER_VERSION=2.4.1

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version="$COMPOSER_VERSION"

COPY docker-php-ext-disable /usr/local/bin
RUN apk add --no-cache git

RUN apk add --no-cache --virtual .ext-deps autoconf gcc musl-dev make \
    && pecl install xdebug pcov \
    && docker-php-ext-enable xdebug pcov \
    && apk del .ext-deps
