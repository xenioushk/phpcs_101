# PHPCS Setup

A comprehensive guideline to setup phpcs for a WordPress theme or plugin.

## Requirements

You need to install the following softwares on your machine.

- [composer](https://getcomposer.org/)
- [npm](https://www.npmjs.com/)
- [node](https://nodejs.org/en)

## Steps

1. Navigate to the project root directory.
2. Open composer.json file and add/update the codes.

```json
"require": {
  "php": ">=7.4|^8.0",
  "composer/installers": "^1.0.12"
},
```

```json
"require-dev": {
  "wp-coding-standards/wpcs": "^3.1",
  "phpcompatibility/phpcompatibility-wp": "2.1",
  "dealerdirect/phpcodesniffer-composer-installer": "^1.0",
  "squizlabs/php_codesniffer": "^3.10"
},
```

```json
"config": {
  "allow-plugins": {
    "composer/installers": true,
    "dealerdirect/phpcodesniffer-composer-installer": true,
    "johnpbloch/wordpress-core-installer": true
  }
}
```

3. Run the command to install composer packages.

```bash
composer update
```

4. You will now see a bin folder inside the `vendor` directory.

![phpcs bin directory](/previews/composer/phpcs_bin_folder.jpg)

5. Next, open the `package.json` file and add this code.

```json
"lint:php": "vendor/bin/phpcs",
"lint:php:fix": "vendor/bin/phpcbf",
```

![Update package.json file](/previews/npm/phplintcode.jpg)

6. Now, copy/download the `phpcs.xml` file from this [link](phpcs.xml) and paste it to the project root directory.

![Update package.json file](/previews/npm/phplintcode.jpg)

7. All done. Now, we can run this command to check the php linting errors and fix them.

```bash
npm run lint:php
npm run lint:php:fix
```

**Output:**

![PHPCS linting report](/previews/phpcs/phpcs_log.jpg)

### Acknowledgement

- [bluewindlab.net](https://bluewindlab.net)
- [composer](https://getcomposer.org/)
- [npm](https://www.npmjs.com/)
