---
- hosts: all
  connection: ssh


  tasks:
     - name: create a httpd server
       yum: name=httpd state=present

     - name: restarted a web server
       service: name=httpd state=restarted

     - name: create a file /var/www/html/index.html
       file:
         path: "/var/www/html/index.html"
         state: touch


     - name: add some data in the file
       copy:
         dest: "/var/www/html/index.html"
         content:
           MY NAME IS SAMANA SIVASAI
            IAM STARTING THE HTTPD SERVER
           THANKS FOR YOUR SUPPORT ENJOY PANDAGO
~                                 
