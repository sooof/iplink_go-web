---
root: true
name: Введение в BeeGo
sort: 0
---

# Что такое BeeGo?

BeeGo - это HTTP фреймворк для быстрой разработки Go приложений. Он может быть использован для разработки API, веб-приложений и разных бэкэнд сервисов. BeeGo является RESTful фреймворком. Он вдохновлен Tornado, Sinatra и Flask и имеет некоторые специфичные только для Go возможности вроде интерфейсов и структур.

## Архитектура BeeGo

Это и есть вся архитектура BeeGo:

![](../images/architecture.png)

BeeGo построен на 8 слабосвязанных модулях.

BeeGo спроектирован для модульной разработки. Вы можете использовать любой из восьми модулей без логики веб-сервера BeeGo. Для примера: вы можете использовать модуль `cache` для создания своего кэша или модуль `logs` для логгирования, а модуль `config` для обработки различных форматов конфигурационных файлов. Так что вы можете использовать все эти модули не только в BeeGo, но еще и в множестве различных приложений, вроде сетевых игр. Это одна из причин почему BeeGo стал популярен. Если вы знаете Лего, то вы должны знать, что все игрушки Лего сделаны из множества маленьких кусочков. В философии BeeGo модули являются маленькими кусочками Лего для построения блоков и приложений в BeeGo. Мы поговорим подробней о модулях в BeeGo немного позже.

## Логика работы BeeGo

BeeGo основан на модулях, но как он работает? Логика его работы похожа на любой типичный MVC фреймворк.
Вот схема:

![](../images/flow.png)

## Структура проекта на BeeGo

Это типичная иерархия папок для проекта на BeeGo:

```
├── conf
│   └── app.conf
├── controllers
│   ├── admin
│   └── default.go
├── main.go
├── models
│   └── models.go
├── static
│   ├── css
│   ├── ico
│   ├── img
│   └── js
└── views
    ├── admin
    └── index.tpl
```

Здесь мы можем видеть M (модели), V (представления), C (контроллеры) (прим. пер.: Model View Controller).
И `main.go` как точку входа.

>Вы можете использовать [bee tool для создания нового проекта](../install/bee.md).