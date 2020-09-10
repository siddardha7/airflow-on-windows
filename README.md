
# Usage

## sequential executor with SQL lite

    By default, docker-airflow runs Airflow with **SequentialExecutor** :

    docker run -p 8080:8080 -it --entrypoint /bin/bash apache/airflow:1.10.10-python3.6

    > airflow initdb
    > airflow scheduler
    > airflow webserver

## Local executor with RBAC UI

    docker-compose -f docker-compose-local-executor.yml up -d


    Once the container is up and running 

    > docker exec -it <container_id> /bin/bash

    > airflow initdb
    > airflow create_user -r Admin -u admin -e admin@example.com -f firstname -l lastname -p admin
    > airflow scheduler &
    > airflow webserver

Goto <http://localhost:8080> and signin using the credentials created above

See <https://airflow.apache.org/docs/stable/configurations-ref.html> for configurations
