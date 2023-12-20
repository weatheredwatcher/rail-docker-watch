## Ruby on Rails Dev With Docker Compose Watch

### Use Cases

#### Create a New Rails Application

To create a new Rails Application, first fork this repository and use it as the basis of your application.

```git clone <your-fork>```

Next you will want to initialize your new Rails application

```docker compose run --no-deps web rails new . --force --database=postgresql```

This will generate a new rails application and install the required Gems.  Your application will be in the folder root and docker watch
will sync the changes you make to your code to the container.  If you update the Gemfile, it will rebuild the app container and use Bundle
to install the added Gems.

#### Add this to you existing application

If you already have a rails application and you want to use this setup to run you app, you can just copy the files into your application root.

  * compose.yml
  * Dockerfile
  * entrypoint.sh

You should keep your Gemfile and Gemfile.lock file from your project. You will need to run your migrations to setup your database in the new container
or you can change the compose.yml to point to an existing db container?
