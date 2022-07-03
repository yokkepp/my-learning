# `styled-components`とは
css in javascriptの一つであり、componentごとにstyleを設定することができるため、Reactとの相性が非常に良さそう。
記述方法に癖があると思うので、覚えなければならない。

## 使用方法
1. Reactのプロジェクトを作成する
```
$ create react-app project_name
```

2. ディレクトリを移動する
```
$ cd project_name
```

3. styled-componentsのインストール
```
$ npm install styled-components
```
※今はデフォルトになっているため不要になったようですが、--saveオプション（パッケージのインストール時、package.json の dependencies に追加してくれる機能。）が記載されている記事も多かった。

4. プロジェクトへのインポート
```
import styled from 'styled-components'
```

## 記述例
### 基本形
```js
/* styled.jsx */
import styled from 'styled-components';

// 名前 = styled.要素名
const Title = styled.h1`
    color: red;
    text-decoration: underline;
`
```

```js
/* App.jsx */
import Title from './components/styled.jsx';

export const App = () => {
    return (
      <Title>カウントするサンプルアプリです</Title>
    );
};
```
### 引数の受け渡し
```js

export const Header = () => {
    return (
        <Title color={"red"}>これはタイトルです</Title>
    )
}

const Title = styled.h1`
    color: ${ props => props.color || "gray"};
    text-decoration: underline;
`

```
