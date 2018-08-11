<?php
$upperCase = "";
if (isset($_GET['text'])) {
    $text = $_GET['text'];
    preg_match_all('/\w+/', $text, $words);
    $words = $words[0];


    $upperCase = array_filter($words, function($word) {
        return strtoupper($word) == $word;
    });

    $upperCase = implode(", ", $upperCase);
}
?>
<form>
    <textarea rows="10" name="text"><?= $upperCase ?></textarea> <br>
    <input type="submit" value="Extract">
</form>
