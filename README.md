<p align="center">
    <a href="https://github.com/yiiboot" target="_blank">
        <img src="https://avatars.githubusercontent.com/u/118281946?s=600&u=b16475d97095b69a8f500ec2f29b8d05c3d02b3a&v=4" height="100px">
    </a>
    <h1 align="center">Yii Boot Actions</h1>
    <br>
</p>


## General usage

This package allows us to reuse GitHub actions, which simplifies version management.

### Using [Composer require checker](https://github.com/maglnet/ComposerRequireChecker)

```yml
on:
  pull_request:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'phpunit.xml.dist'

  push:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'phpunit.xml.dist'

name: composer require checker

jobs:
  composer-require-checker:
    uses: yiiboot/actions/.github/workflows/composer-require-checker.yml@master
    with:
      os: >-
        ['ubuntu-latest']
      php: >-
        ['8.0']
```

### Example of use of the action [PHPBench](https://github.com/phpbench/phpbench)

```yml
on:
  pull_request:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'

  push:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'
  
name: benchmark

jobs:
  phpunit:
    uses: yiiboot/actions/.github/workflows/phpbench.yml@master
    with:
      # coverage: pcov / coverage: xdebug / coverage: xdebug2 / coverage: none 
      # extensions: pdo, pdo_pgsql
      # ini-values: date.timezone='UTC'      
      os: >-
        ['ubuntu-latest']
      php: >-
        ['8.0']
      #tools: composer:v2 
```

### Example of use of the action [PHPUnit](https://github.com/sebastianbergmann/phpunit)

```yml
on:
  pull_request:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'

  push:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'
  
name: build

jobs:
  phpunit:
    uses: yiiboot/actions/.github/workflows/phpunit.yml@master
    with:
      # coverage: pcov / coverage: xdebug / coverage: xdebug2 / coverage: none 
      # extensions: pdo, pdo_pgsql
      # ini-values: date.timezone='UTC'      
      os: >-
        ['ubuntu-latest', 'windows-latest']
      php: >-
        ['8.0', '8.1']
      #tools: composer:v2 
```

### Example of use of the action [PSALM](https://github.com/vimeo/psalm)

```yml
on:
  pull_request:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'

  push:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'

name: static analysis

jobs:
  psalm:
    uses: yiiboot/actions/.github/workflows/psalm.yml@master
    with:
      os: >-
        ['ubuntu-latest']
      php: >-
        ['7.4', '8.0', '8.1']
```

### Example of use of the action [RECTOR](https://github.com/rectorphp/rector)

```yml
on:
  pull_request:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'

  push:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'

name: rector

jobs:
  rector:
    uses: yiiboot/actions/.github/workflows/rector.yml@master
    with:
      os: >-
        ['ubuntu-latest']
      php: >-
        ['8.0']
```

### Example of use of the action [ROAVE-INFECTION](https://github.com/roave/infection-static-analysis-plugin)

```yml
  pull_request:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'

  push:
    paths-ignore:
      - 'docs/**'
      - 'README.md'
      - 'CHANGELOG.md'
      - '.gitignore'
      - '.gitattributes'
      - 'infection.json.dist'
      - 'psalm.xml'

name: mutation test

jobs:
  mutation:
    uses: yiiboot/actions/.github/workflows/roave-infection.yml@master
    with:
      os: >-
        ['ubuntu-latest']
      php: >-
        ['8.1']
    secrets:
      STRYKER_DASHBOARD_API_KEY: ${{ secrets.STRYKER_DASHBOARD_API_KEY }}
```

### Support the project

[![Open Collective](https://img.shields.io/badge/Open%20Collective-sponsor-7eadf1?logo=open%20collective&logoColor=7eadf1&labelColor=555555)](https://opencollective.com/yiiboot)

## License

The Yii Boot Actions is free software. It is released under the terms of the Apache-2.0 License.
Please see [`LICENSE`](./LICENSE.md) for more information.

Maintained by [Yii Boot](https://github.com/yiiboot).

## Inspired && Thanks

- [Yii Software Actions](https://github.com/yiisoft/actions)
