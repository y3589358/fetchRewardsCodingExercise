## Fetch Rewards Points Project

Fetch Rewards Coding Exercise - Backend Software Engineering

To Installing dependency and run project:

```bash
# Installing the project's dependency packages
# python 3.x, Django 4.1.2, djangorestframework 3.14
pip install -r requirements.txt
# Run the project and start the Django service
python manage.py runserver
```

run server at `http://localhost:8000/`


path of logic code:

```bash
- app
  - utils.py
  - views.py
- testCase
```

## API

Example input/output
from [https://fetch-hiring.s3.us-east-1.amazonaws.com/points.pdf](https://fetch-hiring.s3.us-east-1.amazonaws.com/points.pdf):

Accepts the following HTTP requests:

| Method | API                        | Desc                                          | request                                                                    | response                                                                                                                     |
|--------|----------------------------|-----------------------------------------------|----------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|
| POST   | localhost:8000/api/trans/  | add transaction route                         | { "payer": "DANNON", "points": 1000, "timestamp": "2020-11-02T14:00:00Z" } | {'code': 200, 'msg': 'add transaction successfully'}                                                                         | 
| GET    | localhost:8000/api/trans/  | get transactions route                        | null                                                                       | [[{"payer": "DANNON","points": 300,"unused_points": 0,"timestamp": "2020-10-31T10:00:00Z","is_credit": true}]                                                                                                                           | 
| POST   | localhost:8000/api/spend/  | spend points route                            | { "points": 5000 }                                                         | [{ "payer": "DANNON", "points": -100 },{ "payer": "UNILEVER", "points": -200 },{ "payer": "MILLER COORS", "points": -4,700}] |
| POST   | localhost:8000/api/points/ | A subsequent call to the points balance route | null                                                                       | {"DANNON": 1000,”UNILEVER” : 0, ,"MILLER COORS": 5300}                                                                       |                                                                                                                            |

