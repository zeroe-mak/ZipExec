ZipExec - это инструмент Proof-of-Concept (POC) для упаковки двоичных инструментов в
защищенный паролем zip-файл. Затем этот zip-файл кодируется в кодировке base64 в строку,
которая перестраивается на диск. Затем эта закодированная строка загружается в файл JScript,
который при выполнении восстанавливает защищенный паролем zip-файл на диске и выполняет его.
Это делается программно, используя COM-объекты для доступа к функциям на основе графического
интерфейса в Windows через сгенерированный загрузчик JScript, выполняя загрузчик внутри
защищенного паролем zip-архива без необходимости его предварительно распаковывать.
Защищая zip-файл паролем, он защищает двоичный файл от EDR и механизмов сканирования диска
или вредоносных программ.

https://github.com/Tylous/ZipExec

https://research.swtch.com/zip


# ZipExec
ZipExec is a Proof-of-Concept (POC) tool to wrap binary-based tools into a password-protected zip file. This zip file is then base64 encoded into a string that is rebuilt on disk. This encoded string is then loaded into a JScript file that when executed, would rebuild the password-protected zip file on disk and execute it. This is done programmatically by using COM objects to access the GUI-based functions in Windows via the generated JScript loader, executing the loader inside the password-protected zip without having to unzip it first. By password protecting the zip file, it protects the binary from EDRs and disk-based or anti-malware scanning mechanisms.


<img src="1.gif" alt="https://media.giphy.com/media/Ykm4xp5NnMlz9ohJbC/giphy.gif">


## Installation

The first step as always is to clone the repo. Before you compile ZipExec you'll need to install the dependencies. To install them, run following commands:
```
go get github.com/yeka/zip
```


Then build it

```
go build ZipExec.go
``` 
  
 or 
  
```go get github.com/Tylous/ZipExec  ```

## Help
```
./ZipExec -h

__________.__      ___________                     
\____    /|__|_____\_   _____/__  ___ ____   ____  
  /     / |  \____ \|    __)_\  \/  // __ \_/ ___\ 
 /     /_ |  |  |_> >        \>    <\  ___/\  \___ 
/_______ \|__|   __/_______  /__/\_ \\___  >\___  >
        \/   |__|          \/      \/    \/     \/ 
                (@Tyl0us)

Usage of ./ZipExec:
  -I string
        Path to the file containing binary to zip.
  -O string
        Name of output file (e.g. loader.js)
  -sandbox
        Enables sandbox evasion using IsDomainedJoined.
```



