# 02-3 개발 편의를 제공하는 장고 Admin
------------
## 장고 Admin 사용하기
1. 슈퍼 유저 생성
```
$ python manage.py createsuperuser
```
2. 장고 Admin에서 모델 관리하기
```
# admin.py

from django.contrib import admin
from .models import Question

admin.site.register(Question)
```
3. 장고 Admin에 데이터 검색 기능 추가
```
# admin.py

from django.contrib import admin
from .models import Question

class QuestionAdmin(admin.ModelAdmin):
    search_fields = ['subject']

admin.site.register(Question, QuestionAdmin)
```
4. 장고 Admin 커스텀   
장고 공식 문서 (장고 Admin 기능) : https://docs.djangoproject.com/ko/4.0/ref/contrib/admin/