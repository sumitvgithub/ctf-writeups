### Solved by historypeats

This was a web challenge that required us to send a special HTTP Method to the web application to both start, and stop, the "brewing". This was solved with the following quick script:

```bash 
#!/bin/bash

echo "Starting Brew..."
curl --request BREW http://brew.p.tjctf.org/flag --header "Content-Type: message/teapot" --header "Accept-Additions: sugar" --data "start" --proxy "localhost:8080" --header "Type: message/teapot"
sleep 59
curl --request BREW http://brew.p.tjctf.org/flag --header "Content-Type: message/teapot" --header "Accept-Additions: sugar" --data "stop" --proxy "localhost:8080" --header "Type: message/teapot"
```

Running it yields the following results:
```bash
historypeats@vulnhub $ ./exploit.sh
Starting Brew...
Brewing...Ahh! That was a marvelous cup of tea!<br>Oh, I found this flag at the bottom of the cup: h4v3-a-n1c3-cup-0f-t3a!
```

Key: h4v3-a-n1c3-cup-0f-t3a!
