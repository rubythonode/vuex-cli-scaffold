# vuex-cli-scaffold

Generating module entities for your store is repeating and verbose. This packages lets you create multiple entities at once including state, mutations, actions getters, the module and even root store. You can also create nested entities.

## Setup

### Install

```bash
$ npm install vuex-cli-scaffold --save-dev
```

### Script

Inside your `package.json`, add this to `scripts`:

```
"vuex-cli-scaffold": "NODE_PATH=. node ./node_modules/vuex-cli-scaffold/src/index.js"
```

## Commands

### Modules directory

By default, this package assumes that you'll have your modules stored at `src/store/modules` and the store itself at `src/store/index.js`. To change the modules directory, simply append `modules=path` where `path` starts from your applications root directory.

### Create entity

To create an entity, simply type this into the console.

```bash
$ npm run vuex-cli-scaffold product
```

This will create all necessary module files at `src/store/modules` including the state, mutations, actions, getters and the module.

### Create multiple entities

To create an entity, type this into the console.

```bash
$ npm run vuex-cli-scaffold product shop basket
```

### Nested entity

You can even create nested entities.

```bash
$ npm run vuex-cli-scaffold shop shop/products shop/products/product
```

**Important**: When you creating nested entities you have to manually set the modules value in the parent modules. In our case, you would need to set the modules for all entities.

### Initialize store

If you start from zero you can create a store next to other entities.

```bash
$ npm run vuex-cli-scaffold shop shop/products shop/products/product -new
```

All root entities will be added to the store. In our case the only root entity is `shop`.