# java init

## 事前準備
### sdkman
```
$ curl -s "https://get.sdkman.io" | bash
$ source "$HOME/.sdkman/bin/sdkman-init.sh"
$ sdk version
```

### springboot
```
$ sdk install springboot
```

### gradle
```
$ brew update
$ brew install gradle
```

## springbootプロジェクトを作成する
```
$ spring init -d=web --build=gradle java-practice
```

## build
```
$ ./gradlew bootRun
```
下記にアクセスするとhello worldと出力される
http://localhost:8080/

## jibを使ってdocker imageをbuildする
```
$ gradle jibDockerBuild
$ docker images | grep java-practice
```

## dockerにコンテナ立ち上げる
```
$ docker run -p 8080:8080 -it java-practice:0.0.1-SNAPSHOT
```

## 参考
- [GitHub - GoogleContainerTools/jib: Build container images for your Java applications.](https://github.com/GoogleContainerTools/jib)
