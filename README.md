# Домашнє завдання #11
___Мета цього домашнього завдання___ — створити REST API для зберігання та управління контактами. API повинен бути побудований з використанням інфраструктури FastAPI та використовувати SQLAlchemy для управління базою даних.

_Контакти повинні зберігатися в базі даних та містити в собі наступну інформацію:_

* Ім'я
* Прізвище
* Електронна адреса
* Номер телефону
* День народження
* Додаткові дані (необов'язково)

### API повинен мати можливість виконувати наступні дії:

* Створити новий контакт
* Отримати список всіх контактів
* Отримати один контакт за ідентифікатором
* Оновити існуючий контакт
* Видалити контакт 

_На придачу до базового функціоналу CRUD API також повинен мати наступні функції:_

* Контакти повинні бути доступні для пошуку за іменем, прізвищем чи адресою електронної пошти (Query).
* API повинен мати змогу отримати список контактів з днями народження на найближчі 7 днів.

### Загальні вимоги

* Використання фреймворку FastAPI для створення API
* Використання ORM SQLAlchemy для роботи з базою даних
* В якості бази даних слід використовувати PostgreSQL.
* Підтримка CRUD операцій для контактів
* Підтримка зберігання дати народження контакту
* Надання документів для API
* Використання модуля перевірки достовірності даних Pydantic



# Домашнє завдання #12

_У цьому домашньому завданні ми продовжуємо допрацьовувати наш REST API застосунок із домашнього завдання 11._

## Завдання

* Реалізуйте механізм аутентифікації в застосунку;
* Реалізуйте механізм авторизації за допомогою JWT токенів, щоб усі операції з контактами проводились лише зареєстрованими користувачами;
* Користувач має доступ лише до своїх операцій з контактами;

### Загальні вимоги

* При реєстрації, якщо користувач вже існує з таким email, сервер поверне помилку HTTP 409 Conflict;
* Сервер хешує пароль і не зберігає його у відкритому вигляді в базі даних;
* У разі успішної реєстрації користувача сервер повинен повернути HTTP статус відповіді 201 Created та дані нового користувача;
* Для всіх операцій POST створення нового ресурсу, сервер повертає статус 201 Created;
* При операції POST - аутентифікація користувача, сервер приймає запит із даними користувача (email, пароль) у тілі запиту;
* Якщо користувач не існує або пароль не співпадає, повертається помилка HTTP 401 Unauthorized;
* Механізм авторизації за допомогою JWT токенів реалізований парою токенів: токена доступу access_token і токен оновлення refresh_token;