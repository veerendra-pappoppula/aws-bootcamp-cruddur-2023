FROM python:3.10-slim-buster

#docker run --rm -p 4567:4567 -it -e FRONTEND_URL='*' -e BACKEND_URL='*' backend-flask

#changing working directory of inside container
WORKDIR /backend-flask
#copying requirements file from outside container to inside container
COPY requirements.txt requirements.txt
#installing python libraries from requirements file
RUN pip3 install -r requirements.txt
#copy all the files from the current folder outside container to insider container
COPY . .
#setting env variable inside container which stays set inside container
ENV FLASK_ENV=development

EXPOSE ${PORT}
#starting flask
#python3 -m flask run --host=0.0.0.0 --port=4567
#using "Attach Shell" is the same as running a docker exec -it <containerid> bash - you're inside the container and we're checking the environment variables
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
