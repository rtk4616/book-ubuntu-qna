---
layout: page
title: 手動安裝全字庫字型(CNS11643)
description: >
  Ubuntu環境，手動安裝全字庫字型(CNS11643)
date: 2016-09-02 13:21:30 +0800
parent:
  title: 字型的安裝與設定
  url: /read/case/font
---

## 操作環境

* Xubuntu 16.04 64位元

## 操作步驟

### 建立工作資料夾

執行

``` sh
$ mkdir ~/tmp -p
$ cd tmp
```

### 下載

執行

``` sh
$ wget -c http://www.cns11643.gov.tw/AIDB/Open_Data.zip
```

### 刪除資料夾「Open_Data」和「cns11643」 (若有的話)

``` sh
$ rm ./Open_Data -rf
$ rm ./CNS11643 -rf
```

### 解壓縮

執行

``` sh
$ unzip -O big5 Open_Data.zip
```

注意: 解開壓縮檔，產生亂碼，可以延伸閱讀「[這篇](/book-ubuntu-qna/read/case/file-archiving-and-compression/zip/unzip-big5.html)」

### 更名Fonts資料夾

執行

``` sh
$ mv Open_Data/Fonts ./CNS11643
```

### 移到系統資料夾

執行

``` sh
$ sudo mv CNS11643 /usr/local/share/fonts/
```

### 更改「Owner」和「Group」

執行

``` sh
$ sudo chown root:staff /usr/local/share/fonts/CNS11643 -R
```

### 更改檔案權限

``` sh
$ sudo chmod 644 /usr/local/share/fonts/CNS11643/*
```


## 更改資料夾權限

``` sh
$ sudo chmod 755 /usr/local/share/fonts/CNS11643
```

### 更新字型暫存資料 (安裝字型)

``` sh
$ sudo fc-cache -fv
```

### 檢驗

執行

``` sh
$ fc-list | grep CNS11643
```

顯示

```
/usr/local/share/fonts/CNS11643/TW-Kai-98_1.ttf: TW\-Kai,全字庫正楷體:style=Regular
/usr/local/share/fonts/CNS11643/TW-Sung-Plus-98_1.ttf: TW\-Sung\-Plus,全字庫正宋體 Plus:style=Regular
/usr/local/share/fonts/CNS11643/TW-Sung-Ext-B-98_1.ttf: TW\-Sung\-Ext\-B,全字庫正宋體 Ext\-B:style=Regular
/usr/local/share/fonts/CNS11643/TW-Sung-98_1.ttf: TW\-Sung,全字庫正宋體:style=Regular
/usr/local/share/fonts/CNS11643/TW-Kai-Plus-98_1.ttf: TW\-Kai\-Plus,全字庫正楷體 Plus:style=Regular
/usr/local/share/fonts/CNS11643/TW-Kai-Ext-B-98_1.ttf: TW\-Kai\-Ext\-B,全字庫正楷體 Ext\-B:style=Regular
```

執行

``` sh
$ fc-match -a | grep TW
```

顯示

```
TW-Kai-98_1.ttf: "TW-Kai" "Regular"
TW-Sung-98_1.ttf: "TW-Sung" "Regular"
TW-Kai-Plus-98_1.ttf: "TW-Kai-Plus" "Regular"
TW-Sung-Ext-B-98_1.ttf: "TW-Sung-Ext-B" "Regular"
TW-Sung-Plus-98_1.ttf: "TW-Sung-Plus" "Regular"
TW-Kai-Ext-B-98_1.ttf: "TW-Kai-Ext-B" "Regular"
```

## 相關網址

* [http://data.gov.tw/node/5961](http://data.gov.tw/node/5961)
* [http://data.gov.tw/node/gov/resource/27234](http://data.gov.tw/node/gov/resource/27234)
* [http://www.cns11643.gov.tw/](http://www.cns11643.gov.tw/)

## 關鍵字查詢

* [全字庫](https://www.google.com.tw/#q=%E5%85%A8%E5%AD%97%E5%BA%AB)