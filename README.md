
## Description

This is a simple utility to generate an SSL private key and Certificate Signing request.

It requires `ruby` and `openssl` to already be installed to run.

It automatically removes the passphrase on the private key, which is generally
want you want on web servers, so that they can rebooted without requiring the
SSL passwords to start up the web server each time.

The keys generated are 2048 bits, and the key and CSR are verified after they are generated.

After running the program, the following files will be produced in the current directory, with
the names updated to match the current year and the domain name of your choice:

    2014-example.com.csr
    2014-example.com.key

## Usage

Here's what it looks like to actually run the script:


```
 ./generate_csr
Enter the domain name: (i.e. something.com): 
example.com
** Generating private key and CSR
Generating a 2048 bit RSA private key
...................................................................................................+++
........................................................................................................+++
writing new private key to '2014-example.com.key.protected'
-----
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [AU]:US
State or Province Name (full name) [Some-State]:Indiana
Locality Name (eg, city) []:Bloomington
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Bloomingfoods
Organizational Unit Name (eg, section) []:
Common Name (e.g. server FQDN or YOUR name) []:example.com
Email Address []:devnull@example.com

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:
An optional company name []:

** Removing passphrase
writing RSA key

** Verifying key
writing RSA key
RSA key ok
[... private key snipped from output ...]
** Verifying CSR
verify OK
[... verify details snipped from output ...]
```
