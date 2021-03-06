# UtilBox README

> `utilbox` is a collection of Python utility packages to help you save time and avoid writing code for commonly
required tasks.

[![Build Status](https://travis-ci.org/jensonjose/utilbox.svg?branch=master)](https://travis-ci.org/jensonjose/utilbox) [![Coverage Status](https://coveralls.io/repos/github/jensonjose/utilbox/badge.svg?branch=master)](https://coveralls.io/github/jensonjose/utilbox?branch=master)

The current set of capabilities cover the following areas:

*   Encryption
*   JSON manipulation
*   Sending Email
*   Number manipulations
*   File, directory manipulations
*   System interaction
*   Spreadsheet (Excel, CSV) manipulation
*   String and multi-line text manipulation
  
An overview of the available packages is tabulated as below.

Package | Class | Description
--- | --- | ---
crypt_utils | CryptUtils | Encrypt data with AES-128/192/256-bit encryption
json_utils | JsonUtils | Convert data to `JSON` formatted string
mail_utils | MailUtils | Send a plain-text or HTML-formatted email using Python `smtplib` or external mail application (CLI)
number_utils | NumberUtils | Perform various operations with numbers and numeric lists
os_utils | SysUtils, FileUtils, DirUtils | Manipulate files, directories and interact with the underlying OS
spreadsheet_utils | ExcelUtils, CsvUtils | Work with spreadsheets and CSV files
string_utils | StringUtils, TextUtils | Manipulate strings and multi-line text

For detailed documentation, refer the [UtilBox wiki](https://github.com/jensonjose/utilbox/wiki).

## Installation

### Install using `pip`

Make sure you have `pip` installed on your system, and then run:

```pip install utilbox```

### Install from sources

*   Download the [latest release](https://github.com/jensonjose/utilbox/releases/latest) from `GitHub` and extract it to a temporary location
*   Open your terminal and `cd` to the extracted archive directory
*   Run `python setup.py install`

### Dependencies

Package dependencies are listed in `requirements.txt`.

## Usage

The below rule should be applied in general when trying to use a utility class,

> from utilbox.*<package_name>* import *<class_name>*

For example to use the `FileUtils` class from `os_utils` package,

> from utilbox.*os_utils* import *FileUtils*

Here are some real-world scenarios where `utilbox` can serve your purposes,

### Example 1
Let's say you want to fetch only the last line of some text file. To do this,

```python
from utilbox.os_utils import FileUtils

last_line = FileUtils.get_file_last_line("path/to/file.ext")
print last_line
```

### Example 2
What if you wanted the epoch time? No worries,

```python
from utilbox.os_utils import SysUtils

epoch_time = SysUtils.get_epoch_time()
print epoch_time
```

### Example 3
You can send an email just as easily,

```python
from utilbox.mail_utils import MailUtils

smtp_server = "192.168.0.1"
sender_email_id = "someguy@example.com"

mailer = MailUtils(smtp_server, sender_email_id)

# send a plain-text message
mailer.send_mail_plain("receiver@example2.com", "This is a test mail", sender_email_id, "This message was brought to you by 'utilbox'!")

# send an HTML message
mailer.send_mail_plain("receiver@example2.com", "This is a test mail", sender_email_id, "This message was brought to you by <b>'utilbox'<b>!")
```

To use the latest *bleeding-edge*, but possibly unstable version of the code, clone the `master` branch.  
To use the latest *stable* code, download the latest release from the [releases](https://github.com/jensonjose/utilbox/releases) page. 

`utilbox` is being continuously developed and upgraded to be as comprehensive as possible, and any suggestions are most welcome.

## Release history

Release history is available in `CHANGELOG.md`.

## License

See `LICENSE.txt` for license information.

## Author

[Jenson Jose](https://www.jensonjose.com)  
Follow me [@JoseJenson](https://twitter.com/JoseJenson)  
Send your suggestions / feedback at `jensonjose@live.in`

### How to contribute

To contribute, simply:

*   Fork the project
*   Create your feature branch
*   Commit your changes
*   Push committed changes to your branch
*   If you're happy and you know it, create a new `PULL` request
