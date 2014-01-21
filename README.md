This repository is a proof of concept of packaging SQLCipher for
Android as an AAR Maven artifact via Gradle for Android.

This is totally unofficial and exists solely as a vehicle for potentially
helping the SQLCipher for Android project start making their binaries
available for consumption via Gradle, such as for Android Studio.

The `build.gradle` file is hereby released to the public domain.
Everything else in this repository is from
[the SQLCipher for Android project](https://github.com/sqlcipher/android-database-sqlcipher)
and is subject to that project's license terms.

The `build.gradle` file uses an
[unofficial `android-maven` plugin](https://github.com/dcendents/android-maven-plugin)
that is AAR-aware. Running `gradle install` will install this to
your local Maven repository for consumption in another project. That
project would need stuff like this in its `build.gradle`:

To use that, add the following
blocks to your `build.gradle` file:

```groovy
repositories {
    mavenLocal()
    // note: use url "${System.env.HOME}/.m2/repository" if mavenLocal() does not work for you due to bug in Gradle 1.9
}

dependencies {
    compile 'net.sqlcipher:sqlcipher-gradle:3.0.1'
}
```

