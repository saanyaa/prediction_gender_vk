# Прогнозирование пола пользователя VK
## Цель проекта
1. Собрать данные о пользователях VK, используя VK API (https://vk.com/dev/users).
2. Привести данные к пригодному виду, пригодному для анализа.
3. Создать линейную модель, обучить ее и посмотреть на вектор весов, чтобы оценить важность признаков.

## Используемые инструменты
1. `jupiter notebook` - написание и отладка кода.
2. `pandas`, `numpy` - работа с датафреймами.
3. `matplotlib`, `seaborn` - визуализация данных.
4. `yaml` - хранение конфигурационных файлов и словарей.
5. `sklearn` - построение моделей.
6. `requests` - запросы к VK API.

## Результат
1. Удалось выполнить сбор данных и проанализировать их.
2. Удалось создать линейную модель - LogisticRegression, с accuracy = 0.57. Невысокая точность обусловлена ограниченым набором признаков.
3. Была оценена значимость признаков.

## Проблемы
1. Метод VK API users.search позволил бы сразу получить пользователей, удовлетворяющих условию поиска, но этот метод возвращает не более 1000 пользователей.
2. Метод VK API users.get в пакетном режиме позволяет получить информацию сразу о множестве пользователей, но в таком режиме возрващается ограниченный набор информации. Единичный режим метода работает слишком медленно. Поэтому было принято решение использовать метод в пакетном режиме и ограничить набор используемых признаков.
