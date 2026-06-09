# KnownTypes::GetKnownProperty

- ea: `0x25c0b0`
- end: `0x25d805`
- name: `KnownTypes::GetKnownProperty`
- size: `5973`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3f9f0`
- `0x25d830`

## callees

- `0x25c0b0`

## string_xrefs

- `0x25c735`: `Template`
- `0x25c5d5`: `ContentTemplate`
- `0x25c635`: `ContentTemplate`
- `0x25c5e5`: `ContentTemplateSelector`
- `0x25c645`: `ContentTemplateSelector`
- `0x25c555`: `Command`
- `0x25c565`: `CommandParameter`
- `0x25c575`: `CommandTarget`
- `0x25c655`: `RecognizesAccessKey`
- `0x25c97f`: `HeaderTemplate`
- `0x25c9cb`: `HeaderTemplate`
- `0x25c992`: `HeaderTemplateSelector`
- `0x25c9de`: `HeaderTemplateSelector`
- `0x25c9f1`: `NavigateUri`
- `0x25ca50`: `ItemTemplate`
- `0x25ca63`: `ItemTemplateSelector`
- `0x25cb34`: `IsOpen`
- `0x25d7ed`: `XmlSerializer`

## pseudocode

```c

```

## disassembly

```asm
0x25c0b0  ldarg.0
0x25c0b1  ldc.i4   0xFFFFFEF4
0x25c0b6  sub
0x25c0b7  switch   loc_25D7E5, loc_25D7D5, loc_25D7C5, loc_25D7B5, loc_25D7A5, loc_25D795, loc_25D785, loc_25D775, loc_25D762, loc_25D74F, loc_25D73C, loc_25D729, loc_25D716, loc_25D703, loc_25D6F0, loc_25D6DD, loc_25D6CA, loc_25D6B7, loc_25D6A4, loc_25D691, loc_25D67E, loc_25D66B, loc_25D658, loc_25D645, loc_25D632, loc_25D61F, loc_25D60C, loc_25D5F9, loc_25D5E6, loc_25D5D3, loc_25D5C0, loc_25D5AD, loc_25D59A, loc_25D587, loc_25D574, loc_25D561, loc_25D54E, loc_25D53B, loc_25D528, loc_25D515, loc_25D502, loc_25D4EF, loc_25D4DC, loc_25D4C9, loc_25D4B6, loc_25D4A3, loc_25D490, loc_25D47D, loc_25D46A, loc_25D457, loc_25D444, loc_25D431, loc_25D41E \
0x25c4ec  br       loc_25D7F5
0x25c4f1  ldarg.1
0x25c4f2  ldc.i4.m1
0x25c4f3  stind.i2
0x25c4f4  ldarg.2
0x25c4f5  ldstr    aText// "Text"
0x25c4fa  stind.ref
0x25c4fb  br       loc_25D7FF
0x25c500  ldarg.1
0x25c501  ldc.i4.s 0xEF
0x25c503  stind.i2
0x25c504  ldarg.2
0x25c505  ldstr    aStoryboard_0// "Storyboard"
0x25c50a  stind.ref
0x25c50b  br       loc_25D7FF
0x25c510  ldarg.1
0x25c511  ldc.i4.s 0xE4
0x25c513  stind.i2
0x25c514  ldarg.2
0x25c515  ldstr    aChildren// "Children"
0x25c51a  stind.ref
0x25c51b  br       loc_25D7FF
0x25c520  ldarg.1
0x25c521  ldc.i4.s 0xCE
0x25c523  stind.i2
0x25c524  ldarg.2
0x25c525  ldstr    aBackground// "Background"
0x25c52a  stind.ref
0x25c52b  br       loc_25D7FF
0x25c530  ldarg.1
0x25c531  ldc.i4.s 0xCE
0x25c533  stind.i2
0x25c534  ldarg.2
0x25c535  ldstr    aBorderbrush// "BorderBrush"
0x25c53a  stind.ref
0x25c53b  br       loc_25D7FF
0x25c540  ldarg.1
0x25c541  ldc.i4.s 0xCE
0x25c543  stind.i2
0x25c544  ldarg.2
0x25c545  ldstr    aBorderthicknes// "BorderThickness"
0x25c54a  stind.ref
0x25c54b  br       loc_25D7FF
0x25c550  ldarg.1
0x25c551  ldc.i4.s 0xC8
0x25c553  stind.i2
0x25c554  ldarg.2
0x25c555  ldstr    aCommand// "Command"
0x25c55a  stind.ref
0x25c55b  br       loc_25D7FF
0x25c560  ldarg.1
0x25c561  ldc.i4.s 0xC8
0x25c563  stind.i2
0x25c564  ldarg.2
0x25c565  ldstr    aCommandparamet// "CommandParameter"
0x25c56a  stind.ref
0x25c56b  br       loc_25D7FF
0x25c570  ldarg.1
0x25c571  ldc.i4.s 0xC8
0x25c573  stind.i2
0x25c574  ldarg.2
0x25c575  ldstr    aCommandtarget// "CommandTarget"
0x25c57a  stind.ref
0x25c57b  br       loc_25D7FF
0x25c580  ldarg.1
0x25c581  ldc.i4.s 0xC8
0x25c583  stind.i2
0x25c584  ldarg.2
0x25c585  ldstr    aIspressed// "IsPressed"
0x25c58a  stind.ref
0x25c58b  br       loc_25D7FF
0x25c590  ldarg.1
0x25c591  ldc.i4.s 0xA6
0x25c593  stind.i2
0x25c594  ldarg.2
0x25c595  ldstr    aMaxwidth// "MaxWidth"
0x25c59a  stind.ref
0x25c59b  br       loc_25D7FF
0x25c5a0  ldarg.1
0x25c5a1  ldc.i4.s 0xA6
0x25c5a3  stind.i2
0x25c5a4  ldarg.2
0x25c5a5  ldstr    aMinwidth// "MinWidth"
0x25c5aa  stind.ref
0x25c5ab  br       loc_25D7FF
0x25c5b0  ldarg.1
0x25c5b1  ldc.i4.s 0xA6
0x25c5b3  stind.i2
0x25c5b4  ldarg.2
0x25c5b5  ldstr    aWidth// "Width"
0x25c5ba  stind.ref
0x25c5bb  br       loc_25D7FF
0x25c5c0  ldarg.1
0x25c5c1  ldc.i4.s 0x9C
0x25c5c3  stind.i2
0x25c5c4  ldarg.2
0x25c5c5  ldstr    aContent// "Content"
0x25c5ca  stind.ref
0x25c5cb  br       loc_25D7FF
0x25c5d0  ldarg.1
0x25c5d1  ldc.i4.s 0x9C
0x25c5d3  stind.i2
0x25c5d4  ldarg.2
0x25c5d5  ldstr    aContenttemplat// "ContentTemplate"
0x25c5da  stind.ref
0x25c5db  br       loc_25D7FF
0x25c5e0  ldarg.1
0x25c5e1  ldc.i4.s 0x9C
0x25c5e3  stind.i2
0x25c5e4  ldarg.2
0x25c5e5  ldstr    aContenttemplat_0// "ContentTemplateSelector"
0x25c5ea  stind.ref
0x25c5eb  br       loc_25D7FF
0x25c5f0  ldarg.1
0x25c5f1  ldc.i4.s 0x9C
0x25c5f3  stind.i2
0x25c5f4  ldarg.2
0x25c5f5  ldstr    aHascontent// "HasContent"
0x25c5fa  stind.ref
0x25c5fb  br       loc_25D7FF
0x25c600  ldarg.1
0x25c601  ldc.i4.s 0x9B
0x25c603  stind.i2
0x25c604  ldarg.2
0x25c605  ldstr    aFocusable// "Focusable"
0x25c60a  stind.ref
0x25c60b  br       loc_25D7FF
0x25c610  ldarg.1
0x25c611  ldc.i4.s 0x9A
0x25c613  stind.i2
0x25c614  ldarg.2
0x25c615  ldstr    aContent// "Content"
0x25c61a  stind.ref
0x25c61b  br       loc_25D7FF
0x25c620  ldarg.1
0x25c621  ldc.i4.s 0x9A
0x25c623  stind.i2
0x25c624  ldarg.2
0x25c625  ldstr    aContentsource// "ContentSource"
0x25c62a  stind.ref
0x25c62b  br       loc_25D7FF
0x25c630  ldarg.1
0x25c631  ldc.i4.s 0x9A
0x25c633  stind.i2
0x25c634  ldarg.2
0x25c635  ldstr    aContenttemplat// "ContentTemplate"
0x25c63a  stind.ref
0x25c63b  br       loc_25D7FF
0x25c640  ldarg.1
0x25c641  ldc.i4.s 0x9A
0x25c643  stind.i2
0x25c644  ldarg.2
0x25c645  ldstr    aContenttemplat_0// "ContentTemplateSelector"
0x25c64a  stind.ref
0x25c64b  br       loc_25D7FF
0x25c650  ldarg.1
0x25c651  ldc.i4.s 0x9A
0x25c653  stind.i2
0x25c654  ldarg.2
0x25c655  ldstr    aRecognizesacce// "RecognizesAccessKey"
0x25c65a  stind.ref
0x25c65b  br       loc_25D7FF
0x25c660  ldarg.1
0x25c661  ldc.i4.s 0x95
0x25c663  stind.i2
0x25c664  ldarg.2
0x25c665  ldstr    aBackground// "Background"
0x25c66a  stind.ref
0x25c66b  br       loc_25D7FF
0x25c670  ldarg.1
0x25c671  ldc.i4.s 0x95
0x25c673  stind.i2
0x25c674  ldarg.2
0x25c675  ldstr    aBorderbrush// "BorderBrush"
0x25c67a  stind.ref
0x25c67b  br       loc_25D7FF
0x25c680  ldarg.1
0x25c681  ldc.i4.s 0x95
0x25c683  stind.i2
0x25c684  ldarg.2
0x25c685  ldstr    aBorderthicknes// "BorderThickness"
0x25c68a  stind.ref
0x25c68b  br       loc_25D7FF
0x25c690  ldarg.1
0x25c691  ldc.i4.s 0x95
0x25c693  stind.i2
0x25c694  ldarg.2
0x25c695  ldstr    aFontfamily// "FontFamily"
0x25c69a  stind.ref
0x25c69b  br       loc_25D7FF
0x25c6a0  ldarg.1
0x25c6a1  ldc.i4.s 0x95
0x25c6a3  stind.i2
0x25c6a4  ldarg.2
0x25c6a5  ldstr    aFontsize// "FontSize"
0x25c6aa  stind.ref
0x25c6ab  br       loc_25D7FF
0x25c6b0  ldarg.1
0x25c6b1  ldc.i4.s 0x95
0x25c6b3  stind.i2
0x25c6b4  ldarg.2
0x25c6b5  ldstr    aFontstretch// "FontStretch"
0x25c6ba  stind.ref
0x25c6bb  br       loc_25D7FF
0x25c6c0  ldarg.1
0x25c6c1  ldc.i4.s 0x95
0x25c6c3  stind.i2
0x25c6c4  ldarg.2
0x25c6c5  ldstr    aFontstyle// "FontStyle"
0x25c6ca  stind.ref
0x25c6cb  br       loc_25D7FF
0x25c6d0  ldarg.1
0x25c6d1  ldc.i4.s 0x95
0x25c6d3  stind.i2
0x25c6d4  ldarg.2
0x25c6d5  ldstr    aFontweight// "FontWeight"
0x25c6da  stind.ref
0x25c6db  br       loc_25D7FF
0x25c6e0  ldarg.1
0x25c6e1  ldc.i4.s 0x95
0x25c6e3  stind.i2
0x25c6e4  ldarg.2
0x25c6e5  ldstr    aForeground// "Foreground"
0x25c6ea  stind.ref
0x25c6eb  br       loc_25D7FF
0x25c6f0  ldarg.1
0x25c6f1  ldc.i4.s 0x95
0x25c6f3  stind.i2
0x25c6f4  ldarg.2
0x25c6f5  ldstr    aHorizontalcont// "HorizontalContentAlignment"
0x25c6fa  stind.ref
0x25c6fb  br       loc_25D7FF
0x25c700  ldarg.1
0x25c701  ldc.i4.s 0x95
0x25c703  stind.i2
0x25c704  ldarg.2
0x25c705  ldstr    aIstabstop// "IsTabStop"
0x25c70a  stind.ref
0x25c70b  br       loc_25D7FF
0x25c710  ldarg.1
0x25c711  ldc.i4.s 0x95
0x25c713  stind.i2
0x25c714  ldarg.2
0x25c715  ldstr    aPadding// "Padding"
0x25c71a  stind.ref
0x25c71b  br       loc_25D7FF
0x25c720  ldarg.1
0x25c721  ldc.i4.s 0x95
0x25c723  stind.i2
0x25c724  ldarg.2
0x25c725  ldstr    aTabindex// "TabIndex"
0x25c72a  stind.ref
0x25c72b  br       loc_25D7FF
0x25c730  ldarg.1
0x25c731  ldc.i4.s 0x95
0x25c733  stind.i2
0x25c734  ldarg.2
0x25c735  ldstr    aTemplate// "Template"
0x25c73a  stind.ref
0x25c73b  br       loc_25D7FF
0x25c740  ldarg.1
0x25c741  ldc.i4.s 0x95
0x25c743  stind.i2
0x25c744  ldarg.2
0x25c745  ldstr    aVerticalconten// "VerticalContentAlignment"
0x25c74a  stind.ref
0x25c74b  br       loc_25D7FF
0x25c750  ldarg.1
0x25c751  ldc.i4   0xFFFFFF5D
0x25c756  stind.i2
0x25c757  ldarg.2
0x25c758  ldstr    aDock// "Dock"
0x25c75d  stind.ref
0x25c75e  br       loc_25D7FF
0x25c763  ldarg.1
0x25c764  ldc.i4   0xFFFFFF5D
0x25c769  stind.i2
0x25c76a  ldarg.2
0x25c76b  ldstr    aLastchildfill// "LastChildFill"
0x25c770  stind.ref
0x25c771  br       loc_25D7FF
0x25c776  ldarg.1
0x25c777  ldc.i4   0xFFFFFF59
0x25c77c  stind.i2
0x25c77d  ldarg.2
0x25c77e  ldstr    aDocument// "Document"
0x25c783  stind.ref
0x25c784  br       loc_25D7FF
0x25c789  ldarg.1
0x25c78a  ldc.i4   0xFFFFFF49
0x25c78f  stind.i2
0x25c790  ldarg.2
0x25c791  ldstr    aChildren// "Children"
0x25c796  stind.ref
0x25c797  br       loc_25D7FF
0x25c79c  ldarg.1
  ... truncated ...
```
