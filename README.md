# A convenient utility for managing configurations.

## Installation

```bash
python3 -m pip install config-kit
```

## Usage

### Use in Python

```python
from config_kit.core import ConfigKit

# Intialize a ConfigKit instance
config = ConfigKit(config_file='config.ini', section='common')

# Set configuration items
config.username = 'admin'
config.password = '123456'

# Remove configuration items
del config.username

# Save configuration items
config.save()

# Retrieve configuration items
print(config.username)
print(config.password)


# Use a context manager to automatically save changes
with ConfigKit(config_file='config.ini') as config:
    config.host = 'localhost'
    config.port = 8080
```

### Use in Shell

```bash
config-kit --help

config-kit -c config.ini -s common sub-command [arguments]

# Set configuration items
config-kit set username admin
config-kit set password 123456

# Remove configuration items
config-kit remove username

# Retrieve configuration items
config-kit get username
config-kit get password
```

## Configuration File Format

The configuration file is in the INI format, with sections and key-value pairs. For example:

```ini
[common]
username = admin
password = 123456

[database]
host = localhost
port = 3306
```
