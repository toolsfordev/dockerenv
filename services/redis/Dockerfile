FROM redis

MAINTAINER inhere<cloud798@126.com>

# 更换(debian 8)软件源
RUN mv /etc/apt/sources.list /etc/apt/sources.list.bak
ADD data/resources/debian8.sources   /etc/apt/sources.list

# create redis config directory.
# e.g /etc/redis/comm.conf /etc/redis/6379.conf /etc/redis/6380.conf
RUN mkdir /etc/redis

VOLUME [ "/data", "/etc/redis" ]

# add a slave redis
CMD [ "redis-server", "&& redis-server --port 6380 --slaveof 127.0.0.1 6379" ]