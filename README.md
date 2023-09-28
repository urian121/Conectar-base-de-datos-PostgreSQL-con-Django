### APRENDIENDO A CONECTAR DJANGO CON PostgreSQL PASO A PASO

1.  Crear un entorno virtual, hay muchas formas

        Opción 1: Crear entorno virtual con el paquete virtualenv
        Si no tienes instalado virtualenv puedes instalarlo de forma global en el sistema atraves de https://pypi.org/project/virtualenv/
        pip install virtualenv ->Instalar de forma global
        virtualenv env ->Crear entorno
        virtualenv --version ->Ver la versión de virtualenv

        Opción 2: Crear un entorno virtual con el paquete que ya viene por defecto en las ultimas versiones de Python
        python -m venv env

2.  Activar entorno virtual

        . env/Script/activate ->para Windows
        . env/bin/activate -> Para Mac
        deactivate -->Para desactivar mi entorno virtual

3.  Instalar Djando desde el manejador de paquete de Python Pip, ya dentro del entorno virtual.

        python -m pip install Django
        pip install Django
        Nota: para instalar Django en una version especifica
        pip install Django==4.2.4

4.  Ver la versión de Djando instalada en el proyecto

        python -m django --version

5.  Instalar Driver `psycopg2` (paquete - libreria - modulo) para conectar Gestor de BD PostgreSQL con Django

        pip install psycopg2-binary

6.  Crear el proyecto con Djando

        django-admin startproject project_django_postgreSQL .
        El punto . es crucial porque le dice al script que instale Django en el directorio actual.

        Ya en este punto se puede correr el proyecto que a creado Django,
        python manage.py runserver

7.  Crear el archivo requirements.txt para tener todos los paquetes del proyecto a la mano

        pip freeze > requirements.txt

        Nota: para instalar los paquetes solo basta ejecutar
        pip install -r requirements.txt

8.  Editar el archivo settings.py del proyecto, cambiando los parametros de conexión para PostgreSQL

        `
        DATABASES = {
                'default': {
                        'ENGINE': 'django.db.backends.postgresql_psycopg2',  # ENGINE es motor de BD
                        'NAME': 'bd_django_postgresql',
                        'USER': 'postgres',
                        'PASSWORD': '4825',
                        'HOST': 'localhost',
                        'PORT': '5432'
                }
        }
        `

9.  Crear la Base de Datos en PostgreSQL ((bd_django_mysql))

10. Correr migraciones

        python manage.py migrate

11. Correr el proyecto de Django

        python manage.py runserver
        Revisar la consola y visitar la URL http://127.0.0.1:8000

#### Ejecutando las Migraciones `python manage.py migrate` y corriendo el proyecto de Django `python manage.py runserver`

![](https://raw.githubusercontent.com/urian121/imagenes-proyectos-github/master/servidor-corriendo-django-postgresql.png)

#### Resultado final, ya las tablas están creadas en el motor de BD PostgreSQL

![](https://raw.githubusercontent.com/urian121/imagenes-proyectos-github/master/conexion-postresql-django.png)

#### COMANDO ADICIONALES:

1.  ver todo el historial de migraciones:

        python manage.py showmigrations

2.  listar paquetes del instalador en el proyecto

        pip list
        pip freeze

3.  Correr archivo requirement.txt

        pip install -r requirements.txt


### Expresiones de Gratitud 🎁

    Comenta a otros sobre este proyecto 📢
    Invita una cerveza 🍺 o un café ☕
    Paypal iamdeveloper86@gmail.com
    Da las gracias públicamente 🤓.

## No olvides SUSCRIBIRTE 👍

