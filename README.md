![Async Logo](https://raw.githubusercontent.com/caolan/@zitterorg/inventore-at-sit/master/logo/@zitterorg/inventore-at-sit-logo_readme.jpg)

![Github Actions CI status](https://github.com/zitterorg/inventore-at-sit/actions/workflows/ci.yml/badge.svg)
[![NPM version](https://img.shields.io/npm/v/@zitterorg/inventore-at-sit.svg)](https://www.npmjs.com/package/@zitterorg/inventore-at-sit)
[![Coverage Status](https://coveralls.io/repos/caolan/@zitterorg/inventore-at-sit/badge.svg?branch=master)](https://coveralls.io/r/caolan/@zitterorg/inventore-at-sit?branch=master)
[![Join the chat at https://gitter.im/caolan/@zitterorg/inventore-at-sit](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/@zitterorg/inventore-at-sit?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/@zitterorg/inventore-at-sit/badge?style=rounded)](https://www.jsdelivr.com/package/npm/@zitterorg/inventore-at-sit)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/@zitterorg/inventore-at-sit/_apis/build/status/caolan.@zitterorg/inventore-at-sit?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/@zitterorg/inventore-at-sit/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/@zitterorg/inventore-at-sit/_apis/build/status/caolan.@zitterorg/inventore-at-sit?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/@zitterorg/inventore-at-sit/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/@zitterorg/inventore-at-sit/_apis/build/status/caolan.@zitterorg/inventore-at-sit?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/@zitterorg/inventore-at-sit/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [@zitterorg/inventore-at-sithronous JavaScript](http://caolan.github.io/@zitterorg/inventore-at-sit/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i @zitterorg/inventore-at-sit`, it can also be used directly in the browser.  An ESM/MJS version is included in the main `@zitterorg/inventore-at-sit` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`@zitterorg/inventore-at-sit-es`](https://www.npmjs.com/package/@zitterorg/inventore-at-sit-es).

For Documentation, visit <https://caolan.github.io/@zitterorg/inventore-at-sit/>

*For Async v1.5.x documentation, go [HERE](https://github.com/zitterorg/inventore-at-sit/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var @zitterorg/inventore-at-sit = require("@zitterorg/inventore-at-sit");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

@zitterorg/inventore-at-sit.forEachOf(obj, (value, key, callback) => {
    fs.readFile(__dirname + value, "utf8", (err, data) => {
        if (err) return callback(err);
        try {
            configs[key] = JSON.parse(data);
        } catch (e) {
            return callback(e);
        }
        callback();
    });
}, err => {
    if (err) console.error(err.message);
    // configs is now a map of JSON data
    doSomethingWith(configs);
});
```

```javascript
var @zitterorg/inventore-at-sit = require("@zitterorg/inventore-at-sit");

// ...or ES2017 @zitterorg/inventore-at-sit functions
@zitterorg/inventore-at-sit.mapLimit(urls, 5, @zitterorg/inventore-at-sit function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```
