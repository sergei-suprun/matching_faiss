# Мэтчинг товаров с применением библиотеки FAISS

## Описание проекта
Личный проект

## Задача
Разработка алгоритма, который для всех товаров из `validation.csv` найдет 5 похожих из `base.csv`

## Данные
 - __base.csv__ словарь с векторами товаров
 - __train.csv__ тренировочная выборка с правильным соответствием запроса и ответа из словаря
 - __validation.csv__ тестовая выборка, для которой надо найти соответствие
 - __validation_answer.csv__ образец предсказаний, необходимо для каждого запроса предоставить 10 ответов, объединенных в строку
 
## Методология
- Загрузка и знакомство с данными
  - Исследовательский анализ данных:
    - Проверка на пропуски и дубликаты
    - Анализ распределения признаков и наличия выбросов
    - Анализ корреляции признаков
    - Проверка признаков на дискретность
  - Построение алгоритма с использованием FAISS 
    - Тестирование с разными наборами признаков
    - Тестирование разных вариантов масштабирования признаков
    - Тестирование с разным количеством кластеров
  - Выбор оптимального алгоритма и тестирование ее на валидационной аыборке

**Использумые библиотеки: Numpy, Sklearn, Seaborn, Matplotlib, FAISS**

## Результат
Разработан алгоритм, который для всех товаров из `validation.csv` находит 5 похожих из `base.csv`. Значение целевой метрики `accuracy@5` _70.584_ на валидационной выборке было достигнуто при следующих параметрах:
  - алгоритм FAISS;
  - кол-во кластеров 50;
  - индекс `IndexIVFFlat`;
  - масштабирование данных с помощью `RobustScaler`;
  - с удалением признаков, распределённых ненормально.
 
