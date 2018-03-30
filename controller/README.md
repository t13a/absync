
absync-controller
=================

Usage
-----

    $ docker run --rm --name absync-controller \
    -e ACTIVE_SNAPSHOT_CMD=/usr/local/bin/absync-active-snapshot \
    -e ACTIVE_SSH_USER=storage-admin \
    -e ACTIVE_SSH_HOST=a.example.com \
    -e ACTIVE_SSH_PORT=8873 \
    -e ACTIVE_SSH_IDENTITY=/identity \
    -e BACKUP_CMD=/usr/local/bin/absync-backup \
    -e BACKUP_SSH_USER=storage-admin \
    -e BACKUP_SSH_HOST=b.example.com \
    -e BACKUP_SSH_PORT=9873 \
    -e BACKUP_SSH_IDENTITY=/identity \
    -e PROMETHEUS_ENABLED=yes \
    -e PROMETHEUS_JOB=absync \
    -e PROMETHEUS_INSTANCE=c.example.com \
    -e PROMETHEUS_CONTROLLER=a-b \
    -e PROMETHEUS_PUSHGATEWAY_URL=https://pushgateway.d.t13a.net \
    -e PROMETHEUS_PUSHGATEWAY_CA_CERT=/ca.crt \
    -v $(pwd)/crontab:/var/spool/cron/crontabs/root:ro \
    -v $(pwd)/identity:/identity:ro \
    -v $(pwd)/ca.crt:/ca.crt:ro \
    t13a/absync-controller

