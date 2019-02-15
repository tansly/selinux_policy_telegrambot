# selinux_policy_telegrambot
A SELinux policy module for my [Telegram bot](https://github.com/tansly/telegram_notifier).

## Types
* `telegrambot_t`: Domain of the daemon.
* `telegrambot_exec_t`: Type of the executable file of the daemon.
* `telegrambot_conf_t`: Type of the config file.
* `telegrambot_port_t`: Type of the port the daemon binds to.
Label TCP 6666 (or whatever you choose the service to bind to) with this type.

## Paths
* `/usr/local/sbin/telegrambotd`: The executable.
* `/etc/telegrambotd.conf`: The config file.

## Permissions
Nothing interesting. We need to read `telegrambot_conf_t`, bind to `telegrambot_port_t`,
create sockets, connect to HTTP ports and use DNS.
