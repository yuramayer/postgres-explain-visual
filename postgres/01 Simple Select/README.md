# Простой Select 

## SQL Код

```sql
explain (analyze, format json)
select *
from dwh.calendar c 
;
```

## План запроса

```
[
  {
    "Plan": {
      "Node Type": "Seq Scan",
      "Parallel Aware": false,
      "Async Capable": false,
      "Relation Name": "calendar",
      "Alias": "c",
      "Startup Cost": 0.00,
      "Total Cost": 1.10,
      "Plan Rows": 10,
      "Plan Width": 4,
      "Actual Startup Time": 0.006,
      "Actual Total Time": 0.021,
      "Actual Rows": 10,
      "Actual Loops": 1
    },
    "Planning Time": 0.047,
    "Triggers": [
    ],
    "Execution Time": 0.057
  }
]
```

## Ключевые строки

### `Node Type`

```JSON
"Node Type": "Seq Scan"
```

Seq Scan - полный проход таблицы

### `Relation Name`

```JSON
"Relation Name": "calendar"
```

Табличка, по которой мы провели экшн

### `Actual Rows`

```JSON
"Actual Rows": 10
```

Реальное количество строк на узле

### `Actual Total Time`

```JSON
"Actual Total Time": 0.021
```

Реальное время, которое узел занял

### `Plan Rows`

```JSON
"Plan Rows": 10
```

Ожидания оптимизатора, сколько он думал что будет строк

### `Loops`

```JSON
"Actual Loops": 1
```
Скольо раз постгрес выполнял узел
