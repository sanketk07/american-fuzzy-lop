# american-fuzzy-lop

## Setup

Download the latest release 
```
$ wget http://lcamtuf.coredump.cx/afl/releases/afl-latest.tgz
```

Unzip the downloaded tar file
```
$ tar -xvf alf-latest.tgz
```

Navigate to the afl directory
```
$ cd afl-2.52b/
```

Compile afl using make command
```
$ make
```

Install afl using make install
```
$ sudo make install - install afl
```

## Fuzzing source files

```
afl-gcc -fno-stack-protector -z execstack filename.c -o outputfile
```
<dl>
  <dt></dt>
  <dd><h6>afl-gcc: AFL compiler</h6></dd>
  <dd><h6>-fno-stack-protector: Argument that tells the compiler to remove any stack protection such as canaries.</h6></dd>
  <dd><h6>-z execstack: It says that we can execute code from the stack</h6></dd>
  <dd><h6>filename.c: Source file</h6></dd>
  <dd><h6>-o outputfile: Output file</h6></dd>
</dl>

## Checking results
```
afl-fuzz -i ./testcases -o ./results ./outputfile
```
<dl>
  <dt></dt>
  <dd><h6>testcases: Input directory for test cases</h6></dd>
  <dd><h6>results: Output directory for results/crashes</h6></dd>
  <dd><h6>outputfile: The executable file generated after running previous compilation command</h6></dd>
</dl>
