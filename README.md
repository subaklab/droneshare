# Droneshare

빌드 상태 :

[![Codeship Status for diydrones/droneshare](https://codeship.io/projects/1d6b0730-e382-0131-36da-0e6774a12e5d/status)](https://codeship.io/projects/25456)

droneshare의 새로운 버전 - built upon the [DroneKit](http://www.dronekit.io/).  Please see our [welcome letter](WELCOME.md).

## 개발자 가이드

이 어플리케이션은 AngularJS와 [coffeescript](http://coffeescript.org/)를 이용해서 개발되었다.


### 요구사항

진행하기 전에 시스템이 아래 패키지의 최신 버전에서 동작하는지 확인하라.

- [Nodejs](http://nodejs.org/)
- [npm](https://www.npmjs.org/)
- [grunt](http://gruntjs.com/) (Install globaly: ```npm install -g grunt-cli```)

### 소스 구하기
최신 버전을 다운받기를 원하거나 git을 이용해서 얻거나 프로젝트를 fork한다.

repository 얻기

```
git clone https://github.com/diydrones/droneshare.git
```

fork 얻기

```
git clone git@github.com:YOUR-USERNAME/droneshare.git
```

아니면 마지막으로 최신버전의 zip 파일로 다운 받기

[Download Zip](https://github.com/diydrones/droneshare/archive/master.zip)



### 설치

앱을 설치하기 위해서 이 프로젝트를 위해서 필요한 패키지를 설치해야한다. 이 앱은 Node 패키지와 Bower라이브러리 패키지가 필요하다.

아래 패키지 내에서 npm 패키지의 리스트를 찾을 수 있다. 
[packages.js](https://github.com/diydrones/droneshare/blob/master/package.json) 파일

bower 리스는 아래 링크 내부에서 찾을 수 있다. [bower.json](https://github.com/diydrones/droneshare/blob/master/bower.json)

설치하기 위해서

```
npm install
bower install
grunt bower:install
```

### 앱을 실행

Configure your web server to the ```dist``` folder on the app and run the **build**, **prod** or **dev** tasks

```
grunt build
```

this will generate the files your web server needs to launch the app


### Tests

To run tests you need to run the test grunt task which builds the app then runs the tests


```
grunt test
```

If you are planning on debugging tests we recommend you use either the **test** or **karma** grunt tasks with the **--watch** option

```
grunt test --watch
grunt karma --watch

```

this will leave a process running watching for changes on the test files, which speeds up testing.

A pro-tip is to launch your browser at the url specified when running the tests

Here is an example excerpt output from ```grunt karma```

```
Running "karma:unit" (karma) task
INFO [karma]: Karma v0.12.16 server started at http://localhost:9876/
INFO [launcher]: Starting browser PhantomJS
INFO [PhantomJS 1.9.7 (Mac OS X)]: Connected on socket tIC2TRlp_tzgnpb0U1mB with id 25791127
```

Notice the url from Karma **http://localhost:9876/** open that on your browser so you can set debug breakpoints to help you debug your tests.


### Compiling

There are 3 ways of compiling the app depending on your needs

1. `grunt build` - will compile the app preserving individual files (when run, files will be loaded on-demand)
2. `grunt` or `grunt dev` - same as `grunt` but will watch for file changes and recompile on-the-fly
3. `grunt prod` - will compile using optimizations.  This will create one JavaScript file and one CSS file to demonstrate the power of [r.js](http://requirejs.org/docs/optimization.html), the build optimization tool for RequireJS.  And take a look at the index.html file.  Yep - it's minified too.
4. `grunt test` - will compile the app and run all unit tests


### What is Coffeescript?

Coffeescript is like javascript but with much less boilerplate code.  It compiles down to javascript (trivially).  If you've never used coffeescript,
please see this [five page user guide](http://arcturo.github.io/library/coffeescript/).  If you _still_ prefer javascript: We've got ya covered.
Simply run the following grunt task.

`grunt jslove` - will transpile all of the CoffeeScript files to JavaScript and throw out the Coffee.


### A note on tabs, spaces and line-endings

This project uses a [http://editorconfig.org/](.editorconfig) file to specify source formatting conventions.  We encourage you to install a suitable
plug-in into your text-editor of choice.

