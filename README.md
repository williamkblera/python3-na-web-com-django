# python3-na-web-com-django
Implementação dos exemplos do curso https://www.udemy.com/python-3-na-web-com-django-basico-intermediario/

#  Seção: 1 - Introdução e Conceitos Básicos
## 001 Apresentação do Curso
## 002 Apresentação do Projeto
## 003 Ambiente Virtual

Dicas:
- Para diminuir o caminho no prompt digite o seguinte comando

    $ PS1="(`basename \"$VIRTUAL_ENV\"`):/\W$ "

- Para sair do virtualenv use o comando

    $ deactivate

## 004 Configurando o Django
- Instalei a versão Django==1.10.5, mais atual no dia de estudo.

## 005 Configurando o Banco de Dados

- Aproveite para alterar o **settings.py** para colocar o idioma em pt-br e na timezone correta. Busque seu **timezone** aqui https://en.wikipedia.org/wiki/List_of_tz_database_time_zones

        LANGUAGE_CODE = 'pt-br'

        TIME_ZONE = 'America/Campo_Grande'

- Em vez do comando **./manager.py syncdb** utilize o comando **./manage.py migrate** para sincronizar e migrar o banco de dados.
 - Para criar o usuário administrador do sistema utilize o comando **./manage.py createsuperuser**
        ./manage.py createsuperuser
        Username (leave blank to use 'william'): admin
        Email address: admin@admin.com
        Password:
        Password (again):
        Superuser created successfully.

- Na definição da função home edite o arquivo **simplemooc/urls.py** da seguinte forma:

        from django.conf.urls import url
        from django.contrib import admin

        from simplemooc.core import views as core_views

        urlpatterns = [
            url(r'^$', core_views.home, name='home'),
            url(r'^admin/', admin.site.urls),
        ]
