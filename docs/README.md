# Explain

[![Build Status](https://gitlab.com/sanpi/explain/badges/master/pipeline.svg)](https://gitlab.com/sanpi/explain/commits/master)

Transform postgresql explain to a graph.

[<img title="Explain plan 1" src="https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_1.png" width="200px" />](https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_1.png)
[<img title="Explain plan 2" src="https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_2.png" width="200px" />](https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_2.png)
[<img title="Explain plan 3" src="https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_3.png" width="200px" />](https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_3.png)
[<img title="Explain plan 4" src="https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_4.png" width="200px" />](https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_4.png)
[<img title="Explain plan 5" src="https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_5.png" width="200px" />](https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_5.png)
[<img title="Explain plan large" src="https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_large.png" width="300px" />](https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_large.png)
[<img title="Explain plan parallel" src="https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_parallel.png" height="250px" />](https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_parallel.png)
[<img title="Explain plan trigger" src="https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_trigger.png" width="200px" />](https://raw.githubusercontent.com/sanpii/explain/master/examples/plan_trigger.png)

## Install

If you use Arch Linux, explain is available in
[AUR](https://aur.archlinux.org/packages/explain/).

### Manually

```bash
git clone https://github.com/sanpii/explain
cd explain
make
sudo make install
```

## Launch

Launch this program like `psql` and use `dot` to generate image:

```
$ explain --command 'select 1' database | dot -Tpng > explain.png
```

```
$ explain --help
explain 1.0.0

USAGE:
    explain [FLAGS] [OPTIONS] [dbname]

FLAGS:
        --analyse     this option executes explain analyse /!\ Be carful, that executes the query!
    -n, --dry-run     Don’t execute the query, the input is already an explain plan in JSON
        --help        Prints help information
    -W, --password    Prompt for a password before connecting to a database
    -V, --version     Prints version information

OPTIONS:
    -c, --command <command>    Specifies the command to execute
    -f, --file <file>          Read commands from the file, rather than standard input
    -h, --host <host>          Specifies the host name of the machine on which the server is running
    -o, --output <output>      Put output into file
    -p, --port <port>          Specifies the TCP port on which the server is listening for connections
    -U, --user <user>          Connect to the database as the user

ARGS:
    <dbname>    Specifies the name of the database to connect to
```
