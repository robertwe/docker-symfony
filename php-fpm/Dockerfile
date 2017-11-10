FROM debian:jessie

MAINTAINER Robert Weclawski <robert.weclawski@mykolab.com>

COPY sources.list /etc/apt/sources.list

RUN \
  apt-get clean all
RUN \
  apt-get update
RUN \
  apt-get install -y \
    php5-common \
    php5-cli \
    php5-fpm \
    php5-mcrypt \
    php5-mysqlnd \
    php5-gd \
    php5-imagick \
    php5-curl \
    php5-intl \
    php5-curl

COPY symfony.ini /etc/php5/fpm/conf.d/
COPY symfony.ini /etc/php5/cli/conf.d/
COPY symfony.pool.conf /etc/php5/fpm/pool.d/

RUN usermod -u 1000 www-data

CMD ["php5-fpm", "-F"]
EXPOSE 9000
