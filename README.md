# Ragnarok Game Installation

Ragnarok is browser base game which is made top on robrowser game clien. Html, css, javascirpt, and webGL this game client created

# Setup the remote client

- Install apache web server and run the index.html under the server
- Put the Grf files and DATA.INI files in the ‘client/resources/’ folder.
- Configure the DATA.INI file
  - add the grf file into the DATA.INI file, example
    [Data]
    0=data.grf
    1=new.grf
- Extract your mp3 file into the ‘client/BGM/’ folder.
- Now delete the ‘data/’ directory, We will put data later if any needed.
- Now configure the client .htaccess file:

  - Put ErrorDocument top of the file, example
    #ex : myroserver.com/client/
    ErrorDocument 404 /client/index.php

    #ex : myroserver.com/low/client/
    ErrorDocument 404 /low/client/index.php

    #ex : client.myroserver.com/
    ErrorDocument 404 /index.php

- Open the 'client/config.php' file. Make this changes
  'DEBUG' => true,
  'CLIENT_RESPATH' => 'resources/',
  'CLIENT_DATAINI' => 'DATA.INI',
  'CLIENT_AUTOEXTRACT' => false,
  'CLIENT_ENABLESEARCH' => true,
- Configure doen, Now let’s check the server. Go to this url 'http://{yourDomain}/client/'
  If get Debug Trace and list of grf file, you are on the right track.
- Now click on the data/clientinfo.xml link. if your htaccess configure right way you get this message
  data/clientinfo.xml not found, loading grf file.

  \*\*\*Note: if you get any php error upgrade your php version 7.3 and install php-xml extentions.

- Go to the 'client/config.php' file and turn off debug mode.
  'DEBUG' => false,
- Your client server is configured, now you can put extra data on the ‘client/data/’ folder.

# index.html setup

- set your, remoteClient: 'http://{yourDomain}/client/',
- set websocket list, servers: [],

# Setup done run the index.html file
