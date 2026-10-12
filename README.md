# zmk-keyboard-uollp
## 概要
このリポジトリは自作キーボード [skubmdi/uollp](https://github.com/skubmdi/uollp) のZMK Shield定義です。  
ビルドやキーマップのカスタマイズを行う場合は、リポジトリ [zmk-config-uollp](https://github.com/skubmdi/zmk-config-uollp) をフォークして使用してください。

## 使用方法
### 1. ZMKモジュールとして追加
```yaml
# west.yml
manifest:
  remotes:
    - name: skubmdi
      url-base: https://github.com/skubmdi
  projects:
    - name: zmk-keyboard-uollp
      remote: skubmdi
      revision: v0.2
      import: west.yml
  self:
    path: config
```

### 2. keymapファイルで任意のレイアウトを設定
 - `&layout4x5x1`: 4行5列20キー
 - `&layout4x6x1`: 4行6列24キー
 - `&layout5x6x1`: 5行6列30キー
 - `&layout4x5x2`: 4行5列左右40キー
 - `&layout4x6x2`: 4行6列左右48キー
 - `&layout5x6x2`: 5行6列左右60キー
```dts
/ {
	chosen {

		zmk,physical-layout = &layout4x5x2;
	};
};
```
