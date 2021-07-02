# CommandProcessor
Command Processor<br>
It processes your command<br>
your commands will be processed<br>
processing will occur upon your commads<br>
you can put it however you want <br>

Its very very simple

it breaks down the command(the whole line) into three parts:<br>
&bull; command<br>
&bull; args<br>
&bull; flags

Description:
- command is basically the first word in line
- args are the words that come after the command
- flags are the ones that have that little "-" before them and theyre usually followed by another word (or a whole expression in quotes) as their attribute...

Example:
`Open file -f "C:\Users\Richard\penis profile\ee.txt" -readonly -o LOCK_EX`

now in java:
```java
CommandProcessor cp = new CommandProcessor(true);// true for case insesitive, false or nothing for case sesitive
String commandLine = scanner.nextLine(); // grab the whole line
cp.process(commandLine);

String command = cp.getCommand(); // command = "open" ( case insensitive! so everything becomes lowercase )
int argCount = cp.getArgCount(); // argCount = 1
String arg1 = cp.getArg(0); //arg1 = "file"
if(cp.hasFlag("-f")){ // true
  String filePath = cp.getFlag("-f"); // filePath = "c:\users\richard\penis profile\ee.txt" (everything inside the quotes, basically)
  // if you're a hardcore linux user, you might've just noticed the problem here. well.... 
  // yes, thats a huge bug but be patient im gonna patch it up real quick!
  // ofcourse the problem could be avoided by using the case sesitive option but still, that sucks.
  if(cp.hasFlag("-readonly")) readOnly = true;
  String dummy = cp.getFlag("-readonly"); // dummy = "" (the -readonly flag basically doesnt have any attributes *shrug*)
  String openOptions = cp.getFlag("-o"); // openOptions = "LOCK_EX" 
}else nag();

```

The internal structure of the cp object in our little example is:
* command = "open"
* args:
  * "file"
* flags:
  * "-f" : "C:\Users\Richard\penis profile\ee.txt"
  * "-readonly" : ""
  * "-o" : "LOCK_EX"



For contributions, bug reports and other stuff email `hiradcodes@yahoo.com`

Or truth ...
