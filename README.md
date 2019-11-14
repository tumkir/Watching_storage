# Пульт охраны банка

Это внутренний репозиторий для сотрудников банка «Сияние». Если вы попали в этот репозиторий случайно, то вы не сможете его запустить, т.к. у вас нет доступа к БД, но можете свободно использовать код вёрстки или посмотреть как реализованы запросы к БД.

Пульт охраны — это сайт, который можно подключить к удалённой базе данных с визитами и карточками пропуска сотрудников нашего банка.

### Как установить

Запросите доступ к БД у менеджера вашего банка.

Перед запуском в корневой папке необходимо создать `.env` файл и прописать там:
* Данные для доступа к базе данных. Вам понадобятся хост, порт, название базы данных, логин и пароль для доступа к ней
* [Секретный ключ](https://djbook.ru/rel1.9/ref/settings.html#secret-key) для Django. Сгенерировать его самостоятельно можно, например, [тут](https://djecrety.ir/)
* Параметр `DEBUG` установить в `True` или `False` в зависимости от того, нужен ли вам [режим отладки](https://djbook.ru/rel1.9/ref/settings.html#debug) или нет


Пример заполнения `.env` файла:
```.env
DB_HOST=127.0.0.1
DB_PORT=5432
DB_NAME=database_name
DB_USER=admin
DB_PASSWORD=password
SECRET_KEY=^kxee!4e!$bpn(jv*0xy4wcze1&8w47f8$rgjg6c1k(9iev0qp
DEBUG=False
```


Python3 должен быть уже установлен.
Затем используйте `pip` (или `pip3`, есть конфликт с Python2) для установки зависимостей:

```
pip install -r requirements.txt
```

После установки зависимостей запустите сайт командой
```
python manage.py runserver 0.0.0.0:8000
```

В терминале выведется адрес `http://0.0.0.0:8000/`, откройте его в браузере и увидите сайт.

### Цель проекта

Код написан в образовательных целях на онлайн-курсе для веб-разработчиков [dvmn.org](https://dvmn.org/).