cwwwd -- a handy web server
============================
 
About
-----

cwwwd starts a web server using your current working directory as the
server's default document root and also provides automatic directory
listings.

The application was created to simplify file sharing with network
devices and computers.


Installation
------------

1. In a terminal, go to the folder where cwwwd is downloaded

::

    $ cd ~/Downloads
    
2. Copy cwwwd to a directory in your path

::

    $ sudo cp cwwwd /usr/local/bin

3. Make cwwwd executable

::

    $ sudo chmod a+x /usr/local/bin/cwwwd


Usage
-----

1. In a terminal, go to the folder you want to make available over HTTP
2. Type cwwwd and hit return

Example::

    $ cd Movies
    $ cwwwd
    Starting server on port 8080

    -- Press Enter To Stop Server --


Options
-------

Server Type
~~~~~~~~~~~
By default, cwwwd uses the Apache2 HTTP server.  If you don't have Apache
installed on your computer, no fear!  cwwwd comes with its own internal 
HTTP server.

Specify which server to use with the the ``-s`` option, providing it either
``internal`` or ``apache2`` values.


Listen Port
~~~~~~~~~~~
cwwwd attempts to listen for traffic on the first free port between 8080
and 8179.  To change this range, use the options ``-p``, the start port,
and ``-m``, the maximum number of ports to search.


Access Control
~~~~~~~~~~~~~~
By default only localhost may access server.  Use the ``-a`` and ``-d``
options to provide lists of client IPs that are allowed and denied access
to the server.  Use ``-a all`` to allow access to all clients.

The denied client list overrides the allowed client list.


Example
~~~~~~~
Start cwwwd using:

1. the internal server, 
2. the first free port between 9001 to 9010,
3. your home directory as the document root,
4. allowing access to everyone with IP address starting with 192.168 or
   the specific IP, 64.202.189.170
5. but denying access to IP addresses 192.168.0.10 and 192.168.0.11

::

    $ cwwwd -s internal                  \
            -p 9001 -m 10                \
            -r ~/                        \
            -a 192.168,64.202.189.170    \
            -d 192.168.0.10,192.168.0.11


Contact
-------

Stephen Norum (stephen@mybunnyhug.org)
