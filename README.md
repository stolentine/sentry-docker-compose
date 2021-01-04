
1. Скопировать образец файла *.env*.
    ```cp sentry-variables.env.example sentry-variables.env``` 

1. Создать секретный ключ:

    ```docker-compose run --rm sentry config generate-secret-key```

1. Скопировать ключ в `SENTRY_SECRET_KEY` параметр в sentry-variables.env.

1. Если вы хотите чтоб Sentry отправлял email-письма с уведомлениями укажите email настройки.

1. Если это первый запуск контейнера Sentry, синхронизируййте БД выполнив:

    ```docker-compose run sentry upgrade```

1. При выполнении команды будет придложенно создать аккаунт - создайте это будет суперпользователь.

    ```Would you like to create a user account now? [Y/n]:
    Email:
    Password:
    Repeat for confirmation:
    ```

1. Запуск Sentry:

    ```docker-compose up -d```
    Sentry доступен на 8088 порту, вы можете это изменить в docker-compose.yml.

1. Откройте Sentry, авторизуйтесь, создайте проект и слдуйте инструкции по установке в проект.

Использованы Sentry образы: https://hub.docker.com/_/sentry/
