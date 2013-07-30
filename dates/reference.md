Python Dates
============

Date Calculations and Timedelta
-------------------------------

```python
from datetime import timedelta

week_later = dt + timedelta(days=7)
last_week = dt - timedelta(days=7)
in_five_minutes = dt + timedelta(minutes=5)
```

valid `timedelta` properties are:
*weeks*, *days*, *hours*, *minutes*, *seconds*, *microseconds*, *milliseconds*


```python
dt1 = datetime(year=2012, month=8, day=23)
dt2 = datetime(year=2012, month=8, day=28)
td = dt2 - dt1
td.days
>> 5
```


Last Day of the Month
---------------------
```python
from datetime import timedelta
now = datetime.now()
next_month = datetime(year=now.year, month=now.month+1, day=1)
last_day_month = next_month - timedelta(days=1)
```

Another solution, using the `calendar` object:

```python
import calendar
now = datetime.now()
range = calendar.monthrange(now.year, now.month)
last_day_month = now.replace(day=range[1])
```

Next Thursday
-------------
```python
today = datetime.now()
thursday_dow = 4
today_dow = first_day_of_month.strftime("%w")
adjustment = ( 7 + thursday_dow - int(today_dow)) % 7
next_thursday = today + timedelta(days=adjustment)
```


First Monday of the Month
-------------------------
```python
today = datetime.now()
first_day_of_month = today.replace(day=1)
day_of_week = first_day_of_month.strftime("%w")
adjustment = (8 - int(day_of_week) ) % 7
first_monday = first_day_of_month + timedelta(days=adjustment)
```

