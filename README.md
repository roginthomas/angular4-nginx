Configure angular in AWS ec2 Ubuntu

Run "npm install"

## Build

Run `ng build --prod` to build the project in production. 

It will generate a folder dist/ contain index.html 


Then install Nginx and create a file server.conf in given location

sudo vi /etc/nginx/conf.d/server.conf

# paste the text in server.conf

        server {
          listen 80;

          server_name mysite.com www.mysite.com;
          root /opt/apps/angular/dist;
          index index.html;
           location / {
                try_files $uri $uri/ /index.html =404;
          }
        }







