# Zip Packager

This repository creates zip archives for the IDE to serve to users.

This version of the utility is intended for use with post SR2022 kit, which
uses the [astoria][astoria] robot management system and the associated [usercode format][astoria-format].

[astoria]: https://github.com/srobo/astoria
[astoria-format]: https://srobo.github.io/astoria/design/code_format.html

## Requirements

- Python 3.6+
- `toml` library

## Usage

```
$ ./make-zip --help
usage: make-zip [-h] [-p PSK] [-r REGION] [team_tla] usercode [output]

Pack a robot.zip from user code.

positional arguments:
  team_tla              The TLA of the team the zip is being created for
  usercode              user code source directory, containing a robot.py
  output                output zip file

optional arguments:
  -h, --help            show this help message and exit
  -p PSK, --psk PSK     WiFi PSK used to secure robot hotspot
  -r REGION, --region REGION
                        Region information for the WiFi hotspot
```

## Development

This project uses [poetry](https://python-poetry.org/) to manage it's development dependencies.

GNU Make is used to handle running the test suite.

- Install dependencies to virtualenv: `poetry install`
- Run type checking and linting: `make`
