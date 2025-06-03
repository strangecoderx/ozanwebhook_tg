Установите Python и библиотеки
Убедитесь, что у вас установлен Python 3.10+
Проверьте командой: python --version

Установите зависимости
Запуск сервера
В терминале, находясь в папке со скриптом:
python ozan_webhook_telegram.py

Увидите примерно:
* Running on http://127.0.0.1:5000

✅ Шаг 1: Скачай и установи ngrok
Перейди на сайт: https://ngrok.com/download

Скачай версию для Windows.

Распакуй архив (например, в C:\ngrok\ngrok.exe).

Добавь папку с ngrok.exe в PATH или просто используй абсолютный путь.

✅ Шаг 2: Зарегистрируйся и получи токен
Создай аккаунт на ngrok.com

Перейди на страницу Auth Tokens

Скопируй команду авторизации вида:

ngrok config add-authtoken ТВОЙ_ТОКЕН
Выполни эту команду в PowerShell или CMD.

Убедись, что твой Python-скрипт ozan_webhook_telegram.py запущен:

И слушает http://127.0.0.1:5000

✅ Шаг 4: Проброс порта через ngrok
Открой новое окно PowerShell или CMD и выполни: ngrok http 5000

Ты увидишь что-то вроде: Forwarding  https://abc12345.ngrok.io -> http://localhost:5000

✅ Шаг 5: Укажи Webhook в Ozan

Теперь ты можешь использовать ссылку вроде: https://abc12345.ngrok.io/webhook/ozan
в качестве webhook URL в Ozan SuperApp.

🔄 Автоматизация (опционально)
Можно создать bat-файл run_ngrok.bat:

@echo off
start "" "C:\ngrok\ngrok.exe" http 5000

