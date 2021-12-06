
### 配列の関数
ひとまず、私が使ったことのある関数を調べてみました。

戻り値が空欄なら、戻り値が無い関数です。
副作用が空欄なら、配列自体に変化が無い関数です。

どの関数も `arr` の初期値は `['りんご', 'バナナ']` になっています。

|関数|概要|試したコード|戻り値|副作用（配列の状態）|
|:---|:---|:---|:---|:---|
|push|末尾に要素を追加して<br>要素数を返す|arr.push( 'みかん' );|3|[ 'りんご', 'バナナ', 'みかん' ]|
unshift|先頭に要素を追加して<br>要素数を返す|arr.unshift( 'みかん' );|3|[ 'みかん', 'りんご', 'バナナ' ]
shift|先頭の要素を取り出す|arr.shift( );|'りんご'|[ 'バナナ' ]
pop|末尾の要素を取り出す|arr.pop( );|'バナナ'|[ 'りんご' ]
splice|◯番めから△個分を置換<br>（追加や削除もできるよ）|①arr.splice( 0, 1, 'いちご' ); <br>②arr.splice( 0, 1 );|① [ 'りんご' ]<br>② [ 'りんご' ]|① [ 'いちご', 'バナナ' ]<br>② [ 'バナナ' ]
slice|◯番めから△番めの手前まで取得<br>単純な配列のコピーに便利|arr.slice( 0, 1 );|[ 'りんご' ]|
indexOf|要素の添字を取得|arr.indexOf( 'バナナ' );|1||
toString|配列を文字列に変換|arr.toString( );|'りんご,バナナ'|
join|文字列に変換する<br>区切り文字を指定可|arr.join(' / ');|'りんご / バナナ'|
concat|配列をつなぐ|const array1 = ['a', 'b', 'c'];<br>const array2 =  ['d', 'e', 'f'];<br>array1.concat( array2 );|<br><br>[ 'a', 'b', 'c', 'd', 'e', 'f' ]|
reduce|配列の内容を１つにまとめる<br>数学の Σ とか Π みたいな|const num = [ 1, 2, 3, 4 ];<br>num.reduce( ( p, c ) => p + c )|<br>10|
reverse|要素を反転する|const count = ['one', 'two', 'three'];<br>count.reverse( );|<br>[ 'three', 'two', 'one' ]|<br>[ 'three', 'two', 'one' ]
sort|配列のソート|const month = ['Jan', 'March', 'Dec'];<br>month.sort( );|<br>[ 'Dec', 'Jan', 'March' ]|<br>[ 'Dec', 'Jan', 'March' ]

戻り値が配列になったり、ならなかったり、
slice と splice で、引数の書き方に微妙な違いがあったり...ややこしいですね。

---

###  おまけ: 連想配列の関数
連想配列だとどうかな？と思って調べてみました。

`myMap` の初期値は `Map { 'foo' => 'bar' }` です。

|関数|概要|試したコード|戻り値|副作用（Mapの状態）|
|:---|:---|:---|:---|:---|
set|追加|myMap.set( 'hoge', 'fuga' );|Map { 'foo' => 'bar', 'hoge' => 'fuga' }|Map { 'foo' => 'bar', 'hoge' => 'fuga' }
get(key)|参照|myMap.get('foo');|'bar'|
delete(key)|要素の削除|myMap.delete('foo');|true|Map { }
clear|全部削除|myMap.clear( );||Map { }
has(key)|あるかどうか|myMap.has('foo');|true|

こっちは割と素直な印象でしたが、いかがでしょう？
