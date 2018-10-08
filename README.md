# php-composer-practice
Here is a practicing project of appling php composer. 

## how to include packages/files
        require 'vendor/autoload.php';

## about the composer.json
This file is the config for composer which lists all the packages (with version) or user-defined files.
1.   Edit your .json file
-   "require" key stands for package
-   "autoload" key means user-defined files. Using "classmap" as sub-key to include all the files in the folder list, while "files" sub-key lists the files (with complete path) to be included.

-   composer.json:

        {
          "require": {
            "monolog/monolog": "^1.23"
          },
          "autoload": {
            "classmap": [
              "math"
            ]
          }
        }
2.   The composition of version num: the major version number. the minor version number. the revision number. Users can specify package version with 3 way:
-   Fixed version, e.g., 1.0.0
-   Specify a lower bound, e.g., > =1.0.0
-   Specify upper and lower bound, e.g., > =1.0.0, <2.0.0
-   Other symbal, e.g., ^1.2.3 is equivalent to >=1.2.3 <2.0.0

3.   Install package if need
-   [Terminal] Download and install packages:

        > composer update
-   The command will install the avaliable latest version packages according to composer.json and then update the packages' details into composer.lock file like name, version, reqired packages, source and so on.
-   If you are ensure that your project should update to another new version or your project is first created and install package, the command can be helpful, otherwise, using command install is better.

## about the composer.lock
The file involves the information of all packages inclouded and will be update when command composer update/install occurs.

        > command install
-   The command will install specific version packages descripted in composer.lock.
-   For the stable purpose, use command install to get packages from remote project which provides composer.lock.
