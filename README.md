# branching-django-example

From this repo, you can learn:

- How to connect to TiDB Serverless in Django.
- How to use branching GitHub integration.

## About this repo

This repo is a Django crud example. it consists of 3 small applications:

- books_cbv: Implement CRUD using CBV (Class Based Views).
- books_fbv: Implement CRUD using FBV (Function Based Views).
- books_fbv_user: add user interaction to books_fbv example.

> The repo is based on the [django_crud](https://github.com/rayed/django_crud). Thanks for the author's excellent work.

## Connect to TiDB Serverless in Django

1. clone the code

```
git clone git@github.com:tidbcloud/branching-django-exmaple.git
cd apps
```

2. active virtual environment (Mac)

```
python3 -m venv env
source env/bin/activate
```

For Windows, use env/Scripts/activate.

3. Install the dependencies

```
pip install -r ../requirements.txt
```

4. Fill in the .env file with your TiDB Serverless connection information. You can find the information in the TiDB Serverless console.

```
DB_DATABASE=
DB_USER=
DB_PASSWORD=
DB_HOST=
SSL_CA=
```

5. Migrate the schema

> make sure you have already created the database in TiDB Serverless before running the migrate command.

```
./manage.py migrate
```

6. Run the server

```
./manage.py runserver
```

## Use branching GitHub integration

Assume that you have run the Django project on a TiDB Serverless. Next, you can use the [Branching GitHub integration](https://docs.pingcap.com/tidbcloud/branch-github-integration) to connect the TiDB Serverless to this repo. Then a database branch will be created for every pull request to test the changes before merging the code to the master branch.

This repo has already connected to a TiDB Serverless. Check this [pull request](https://github.com/tidbcloud/branching-django-exmaple/pull/1) to see how we check the migration changes!


