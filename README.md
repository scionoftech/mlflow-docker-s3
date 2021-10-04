# MLflow-Docker-S3


# Features
 - MLflow in Docker container
 - Mysql Docker container for MLflow tracking data
 - Minio browser(https://min.io/) Docker container for artifacts.
 - Nginx proxy Docker container for MLflow UI

## How to setup

1. Clone the Repo 

2. Update `.env` file with required details

3. Start the Setup by this one line:
   
   ```shell
   $ docker-compose up -d
   ```

4. Open up http://localhost:5000 for MlFlow, and http://localhost:9000 for S3 bucket (MLflow artifacts) with credentials from `.env` file

5. Configure MLflow client-side

For running mlflow files we need various environment variables set on the client side. To generate them use the script `./bashrc_install.sh`, which installs it on your system.

> $ ./bashrc_install.sh   
> [ OK ] Successfully installed environment variables into your .bashrc!

The script installs this variables: AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, MLFLOW_S3_ENDPOINT_URL, MLFLOW_TRACKING_URI. All of them are needed to use mlflow from the client-side.

6. Test the MLflow setup for tracking and Artifacts in S3

```shell
python mlflow_tracking.py
```

### References

- mlflow-docker - [Production ready docker-compose configuration for ML Flow with Mysql and Minio S3 Topics](https://github.com/Toumash/mlflow-docker)
- deploy-mlflow-with-docker-compose - [Track your machine learning experiences with MLflow easily deployed thanks to docker-compose](https://towardsdatascience.com/deploy-mlflow-with-docker-compose-8059f16b6039)

