# basic webpack setup

1. run npm init --y
2. run npm install webpack webpack-cli --save-dev to install webpack to the node_modules directory of your project
3. add a .gitignore file and include node_modules
4. create src and add index.js and index.html
5. create a dist folder
6. create webpack.config.js file
7. run npm install --save-dev html-webpack-plugin.
8. copy the following into webpack.config.js file
   
const path = require('path');
const htmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist'),
  },
   plugins: [
     new HtmlWebpackPlugin({
       template: './src/index.html',
       filename: 'index.html',
       inject: 'body'
};

8. in package.json add "build": "webpack --watch"
9. now type npm run build (should create index.html and main.js in dist folder)
10. run npm install --save-dev style-loader css-loader
11. add the following to webpack.config.js file for css 
module: {
    rules: [
      {
        test: /\.css$/i,
        use: ['style-loader', 'css-loader'],
      },
    ],
  },
12. create a styles.css file
13. add some styling e.g. color: red;
14. in index.js add import './styles.css'; (should all work)
15. add the following to webpack.config.js for images
 {
    test: /\.(png|svg|jpg|jpeg|gif)$/i,
    type: 'asset/resource',
  },
16. add to webpack.config.js devtool: 'inline-source-map',
17. make sure to quit the build and re run for the source map to work
18. npm install --save-dev eslint prettier eslint-config-prettier
19. npm init @eslint/config
20. copy into settings.json
{
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "eslint.validate": ["javascript"]
}
21. in .estlintrc.json add "extends": ["airbnb-base", "prettier"],
(18. run npm install eslint --save-dev
21. run ./node_modules/.bin/eslint --init
22. type the following in command palette --> Preferences: Open Workspace Settings (JSON).
23. copy into settings.json
{
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "eslint.validate": ["javascript"]
}
24. copy the following into eslintrc.json
"rules" : {
    "no-console": "off",
    "quotes": [
        "error",
        "double"
    ]
} )
