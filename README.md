# libraries

Repository for my libraries

- [x] [Published pub.dev packages](https://pub.dev/packages?q=publisher%3Aiipekolict.infinityfreeapp.com)
- [x] [Published Maven Central packages](https://central.sonatype.com/search?smo=true&q=io.github.evgenii-shcherbakov)

---

### Repository secrets

- `KEYSTORE_HOST` keystore project API url
- `KEYSTORE_ACCESS_TOKEN` keystore API JWT access token

---

### Requirements

Platform:

- Dart 3
- Java 19

---

### Bootstrap project

```shell
git clone git@github.com:yauheni-shcharbakou/libraries.git
cd libraries
```

---

### Dart

##### Bootstrap new dart library

```shell
chmod +x scripts/helpers/new.sh
scripts/helpers/new.sh --dart $LIBRARY_NAME
cd dart/$LIBRARY_NAME
```

##### Build all changed dart libs

```shell
chmod +x scripts/main.sh
scripts/main.sh dart build $KEYSTORE_HOST $KEYSTORE_ACCESS_TOKEN
```

##### Build and publish all changed dart libs

```shell
chmod +x scripts/main.sh
scripts/main.sh dart publish $KEYSTORE_HOST $KEYSTORE_ACCESS_TOKEN
```

---

### Kotlin

##### Bootstrap new kotlin library

```shell
chmod +x scripts/helpers/new.sh
scripts/helpers/new.sh --android $LIBRARY_NAME # for android library
scripts/helpers/new.sh --jvm $LIBRARY_NAME # for jvm library
cd kotlin/$LIBRARY_NAME
```

##### Build all changed kotlin libs

```shell
chmod +x scripts/main.sh
scripts/main.sh kotlin build $KEYSTORE_HOST $KEYSTORE_ACCESS_TOKEN
```

##### Build and publish all changed kotlin libs

```shell
chmod +x scripts/main.sh
scripts/main.sh kotlin publish $KEYSTORE_HOST $KEYSTORE_ACCESS_TOKEN
```

---

### Test GitHub Actions workflow

Requirements:
- Docker
- Act utility
- secrets.env file with repository secrets

```shell
act --secret-file secrets.env
```
