# Задания зачёта (в процессе...)

[![Travis build][travis-badge]][travis-page]

Каждое задание находится в отдельной папке.

Структура файлов для каждого задания:

 * `README.md` - описание задания
 * `credit.c` или `credit.lua` - заготовка решения
 * `spec.lua` - тесты, которые должно проходить решение

## Подготовка окружения (SSH на kodomo)

Чтобы Lua "видел" установленные модули, в том числе решения
задач, надо изменить переменные окружения `PATH`, `LUA_PATH` и
`LUA_CPATH`. Для этого выполните команду:

```bash
$ eval `luarocks path`
$ export PATH=$PATH:~/.luarocks/bin
```

Для локальной проверки тестов потребуется пакет `busted`:

```bash
$ luarocks install --local busted
```

Собрать задачи (в корневой папке проекта):

```bash
$ luarocks make --local
```

## Как сдавать задачи

 * сделать форк этого репозитория
 * склонировать к себе в папку
 * решить задачу (изменить файл credit.c или credit.lua)
 * собрать локально (luarocks make --local)
 * в файле `spec.lua` заменить "pending" на "it"
 * запустить команду `busted ваша-задача/spec.lua`
 * убедиться, что все тесты пройдены и нет pending
 * сделать коммит, push'нуть на гитхаб и создать pull-реквест
 * отслеживать статус решения на [Travis][travis-pulls]

## Задачи

Есть две группы задач:

 1. Решить задачу на C в форме расширения для Lua.
    Названия начинаются с "c-".
 2. Составить юнит-тесты на Lua.
    Названия начинаются с "lua-".

Для зачёта нужно справиться хотя бы с одной задачей из
каждой группы.

[travis-page]: https://travis-ci.org/LuaAndC/credits
[travis-badge]: https://travis-ci.org/LuaAndC/credits.png
[travis-pulls]: https://travis-ci.org/LuaAndC/credits/pull_requests
