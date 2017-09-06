# Задача к лекции «Основы Javascript» – «Телефонная книга»

:sos: [Как создать Pull Request](https://github.com/urfu-2015/guides/blob/master/how-to-pull-request.md)
:warning: При создании PullRequest'а не забудьте указать ваши имя и фамилию.

### Общие требования

Мы очень хотим, чтобы код вы написали сами, а не пользовались внешними библиотеками.

Прежде чем отправлять ПР, проверьте на соответствие codestyle. Для этого в корне выполните:

```js
// Устанавливаем проверяльщик
npm install

// Проверяем
npm run lint

// В результате выведутся ошибки, если они есть
// Если какие-либо ошибки будут не понятны – смело спрашиваем у ментора
```

### Задача

Как известно, каждый уважающий себя разработчик должен в жизни сделать три вещи:
посадить DOM дерево, построить абстракцию и ~~вырастить~~ написать телефонную книгу.

В репозитории, изнемогая от нетерпения, вас ожидают два файла:

- __phone-book.js__ – здесь будет ваш код. В нём 3 метода, которые вы должны реализовать:
    - `add(name, phone, email)` – добавляет запись в телефонную книгу, если какое-либо из полей не валидно,
      то запись не добавляется;

       Примеры номеров:
       ```text
       // Валидные
       +7 (111) 777-2-222
       +7 (111) 777 2 222
       +7 111 777-2-222
       7 111 777-2-222
       111 777-2-222
       71117772222
       +34 111 777-2-222

       // Не валидные
       777-2-222
       АБС-6666
       +7 (111) 777%2%222
       +7 (111 777-2-222
       7+ (111) 777-2-222
       -7 (111) 777-2-222
       ```

       Примеры электронной почты:
       ```text
       // Валидные
       info@example.com
       info@example.com.ru
       info@инфо.рф

       // Не валидные
       info@yandex
       info@yandex@ya.ru
       info.yandex.ru
       ```

    - `find(query)` – находит записи в телефонной книге по запросу `query`
      (и при этом ищет во всех полях), выводит построчно (а поля через запятую);
      __если запрос не указан – выводит все записи__;

      Примеры запросов: «Сергей», «+7», «@gmail.com».

      Пример вывода:
      ```text
      Сергей, +7 (999) 666-7-778, gogolef@yandex-team.ru
      Олег, +7 (999) 777-7-777, just7@yandex-team.ru
      ```

    - `remove(query)` – удаляет запись из телефонной книги по запросу;

- __index.js__ - пример скрипта, который работает с вашей телефонной книгой.

### Не обязательные задания (+1 в вашу карму, +2 к мудрости)

Будет нереально круто, если вы реализуете методы:

- `import(filename)` – добавляет запись в телефонную книгу из CSV файла; пример файла в
   репозитории __backup.csv__; читаем файл, добавляем валидные записи в книгу;

- `showTable()` – выводит записи в виде красивой таблички;
   Пример того, как предложил сделать Олег Семичев:
    ```text
    ┌─────────────┬────────────────────╥──────────────────┐
    │ Имя         │ Телефон            ║ email            │
    ├─────────────┼────────────────────╫──────────────────┤
    │ Уася        │ +7 (456) 234-40-50 ║ vasya@gmail.com  │
    │ Ашот        │ +7 (456) 234-40-50 ║ ashot@ya.ru      │
    │ Мария       │ +7 (456) 234-40-50 ║ maria@heaven.ru  │
    └─────────────┴────────────────────╨──────────────────┘
    ```
    :warning: Но он хочет, чтобы вы сделали лучше! :warning:
