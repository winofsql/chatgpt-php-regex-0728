# chatgpt-php-regex-0728

```php
<?php
// URLからテキストを取得する関数
function getWebPageText($url) {
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, $url);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
    $result = curl_exec($ch);
    curl_close($ch);
    return $result;
}

// 正規表現パターン
$pattern = '/\s+/';

// テキストを取得するURL
$url = 'ここにURLを指定してください'; // 実際のURLに置き換えてください

// URLからテキストを取得
$pageText = getWebPageText($url);

// 正規表現によるマッチング
preg_match_all($pattern, $pageText, $matches);

// マッチした文字列の一覧を表示
if (isset($matches[0])) {
    foreach ($matches[0] as $match) {
        echo $match . PHP_EOL;
    }
} else {
    echo "マッチする文字列はありませんでした。";
}
?>

```
