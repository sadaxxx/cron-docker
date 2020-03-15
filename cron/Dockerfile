FROM alpine:3.11.3

# timezone
RUN apk --update add tzdata
RUN cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
RUN apk del tzdata
RUN rm -rf /var/cache/apk/*

# 実行shell
COPY crontask.sh /usr/local/bin
COPY crontab_root /var/spool/cron/crontabs/root
RUN chmod 644 /usr/local/bin/crontask.sh

# cron起動
CMD crond -l 2 -f