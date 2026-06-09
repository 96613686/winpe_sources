# System.Windows.Markup.KnownTypes::GetKnownPropertyAttributeId

- ea: `0xa05f0`
- end: `0xa21e7`
- name: `System.Windows.Markup.KnownTypes::GetKnownPropertyAttributeId`
- size: `7159`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8af70`
- `0x8b2e0`

## callees

- `0xa05f0`

## string_xrefs

- `0xa1183`: `Template`
- `0xa1004`: `ContentTemplate`
- `0xa106a`: `ContentTemplate`
- `0xa1014`: `ContentTemplateSelector`
- `0xa107a`: `ContentTemplateSelector`
- `0xa0ed3`: `Command`
- `0xa0ee2`: `CommandParameter`
- `0xa0ef1`: `CommandTarget`
- `0xa108a`: `RecognizesAccessKey`
- `0xa15a1`: `HeaderTemplate`
- `0xa15e4`: `HeaderTemplate`
- `0xa15b1`: `HeaderTemplateSelector`
- `0xa15f4`: `HeaderTemplateSelector`
- `0xa1643`: `NavigateUri`
- `0xa1749`: `ItemTemplate`
- `0xa1759`: `ItemTemplateSelector`
- `0xa1a57`: `IsOpen`
- `0xa1b21`: `IsReadOnly`
- `0xa1e71`: `IsReadOnly`
- `0xa21d3`: `XmlSerializer`

## pseudocode

```c

```

## disassembly

```asm
0xa05f0  ldarg.0
0xa05f1  ldc.i4   0x15A
0xa05f6  bgt      loc_A095E
0xa05fb  ldarg.0
0xa05fc  ldc.i4   0x85
0xa0601  bgt      loc_A075B
0xa0606  ldarg.0
0xa0607  ldc.i4.s 0x3C
0xa0609  bgt      loc_A06AC
0xa060e  ldarg.0
0xa060f  ldc.i4.s 0x1C
0xa0611  bgt.s    loc_A0658
0xa0613  ldarg.0
0xa0614  ldc.i4.8
0xa0615  bgt.s    loc_A063B
0xa0617  ldarg.0
0xa0618  ldc.i4.1
0xa0619  sub
0xa061a  switch   loc_A0D93, loc_A0DA5, loc_A21E5, loc_A0DBB
0xa062f  ldarg.0
0xa0630  ldc.i4.8
0xa0631  beq      loc_A0DD1
0xa0636  br       loc_A21E5
0xa063b  ldarg.0
0xa063c  ldc.i4.s 0xE
0xa063e  beq      loc_A0DE7
0xa0643  ldarg.0
0xa0644  ldc.i4.s 0x11
0xa0646  beq      loc_A0DFD
0xa064b  ldarg.0
0xa064c  ldc.i4.s 0x1C
0xa064e  beq      loc_A0E0F
0xa0653  br       loc_A21E5
0xa0658  ldarg.0
0xa0659  ldc.i4.s 0x29
0xa065b  bgt.s    loc_A0672
0xa065d  ldarg.0
0xa065e  ldc.i4.s 0x25
0xa0660  beq      loc_A0E21
0xa0665  ldarg.0
0xa0666  ldc.i4.s 0x29
0xa0668  beq      loc_A0E37
0xa066d  br       loc_A21E5
0xa0672  ldarg.0
0xa0673  ldc.i4.s 0x2D
0xa0675  beq      loc_A0E4D
0xa067a  ldarg.0
0xa067b  ldc.i4.s 0x32
0xa067d  sub
0xa067e  switch   loc_A0E63, loc_A21E5, loc_A21E5, loc_A21E5, loc_A0EA6, loc_A0EBC, loc_A0ED2
0xa069f  ldarg.0
0xa06a0  ldc.i4.s 0x3C
0xa06a2  beq      loc_A0F26
0xa06a7  br       loc_A21E5
0xa06ac  ldarg.0
0xa06ad  ldc.i4.s 0x5D
0xa06af  bgt.s    loc_A06F9
0xa06b1  ldarg.0
0xa06b2  ldc.i4.s 0x45
0xa06b4  bgt.s    loc_A06CB
0xa06b6  ldarg.0
0xa06b7  ldc.i4.s 0x42
0xa06b9  beq      loc_A0F3C
0xa06be  ldarg.0
0xa06bf  ldc.i4.s 0x45
0xa06c1  beq      loc_A0F52
0xa06c6  br       loc_A21E5
0xa06cb  ldarg.0
0xa06cc  ldc.i4.s 0x4A
0xa06ce  beq      loc_A0F68
0xa06d3  ldarg.0
0xa06d4  ldc.i4.s 0x54
0xa06d6  beq      loc_A0F7E
0xa06db  ldarg.0
0xa06dc  ldc.i4.s 0x5A
0xa06de  sub
0xa06df  switch   loc_A0F94, loc_A21E5, loc_A0FC7, loc_A0FDD
0xa06f4  br       loc_A21E5
0xa06f9  ldarg.0
0xa06fa  ldc.i4.s 0x78
0xa06fc  bgt.s    loc_A0738
0xa06fe  ldarg.0
0xa06ff  ldc.i4.s 0x64
0xa0701  sub
0xa0702  switch   loc_A0FF3, loc_A1036, loc_A1049, loc_A21E5, loc_A21E5, loc_A109C, loc_A21E5, loc_A10B2, loc_A11A5
0xa072b  ldarg.0
0xa072c  ldc.i4.s 0x78
0xa072e  beq      loc_A11BB
0xa0733  br       loc_A21E5
0xa0738  ldarg.0
0xa0739  ldc.i4.s 0x7A
0xa073b  beq      loc_A11D1
0xa0740  ldarg.0
0xa0741  ldc.i4   0x81
0xa0746  beq      loc_A11E7
0xa074b  ldarg.0
0xa074c  ldc.i4   0x85
0xa0751  beq      loc_A11FD
0xa0756  br       loc_A21E5
0xa075b  ldarg.0
0xa075c  ldc.i4   0xFB
0xa0761  bgt      loc_A0855
0xa0766  ldarg.0
0xa0767  ldc.i4   0xE1
0xa076c  bgt      loc_A080C
0xa0771  ldarg.0
0xa0772  ldc.i4   0xAB
0xa0777  bgt.s    loc_A07A9
0xa0779  ldarg.0
0xa077a  ldc.i4   0xA3
0xa077f  sub
0xa0780  switch   loc_A1213, loc_A21E5, loc_A21E5, loc_A1249, loc_A125F
0xa0799  ldarg.0
0xa079a  ldc.i4   0xAB
0xa079f  beq      loc_A1272
0xa07a4  br       loc_A21E5
0xa07a9  ldarg.0
0xa07aa  ldc.i4   0xB7
0xa07af  beq      loc_A1288
0xa07b4  ldarg.0
0xa07b5  ldc.i4   0xC6
0xa07ba  sub
0xa07bb  switch   loc_A129B, loc_A12B1, loc_A21E5, loc_A21E5, loc_A12C7, loc_A21E5, loc_A21E5, loc_A12DD, loc_A12F3, loc_A1309, loc_A131F, loc_A1335, loc_A134B, loc_A1361, loc_A1374
0xa07fc  ldarg.0
0xa07fd  ldc.i4   0xE1
0xa0802  beq      loc_A1387
0xa0807  br       loc_A21E5
0xa080c  ldarg.0
0xa080d  ldc.i4   0xE7
0xa0812  bgt.s    loc_A082F
0xa0814  ldarg.0
0xa0815  ldc.i4   0xE2
0xa081a  beq      loc_A139A
0xa081f  ldarg.0
0xa0820  ldc.i4   0xE7
0xa0825  beq      loc_A145D
0xa082a  br       loc_A21E5
0xa082f  ldarg.0
0xa0830  ldc.i4   0xEC
0xa0835  beq      loc_A1473
0xa083a  ldarg.0
0xa083b  ldc.i4   0xF2
0xa0840  beq      loc_A1486
0xa0845  ldarg.0
0xa0846  ldc.i4   0xFB
0xa084b  beq      loc_A1499
0xa0850  br       loc_A21E5
0xa0855  ldarg.0
0xa0856  ldc.i4   0x12C
0xa085b  bgt      loc_A0904
0xa0860  ldarg.0
0xa0861  ldc.i4   0x111
0xa0866  bgt.s    loc_A08C9
0xa0868  ldarg.0
0xa0869  ldc.i4   0xFE
0xa086e  sub
0xa086f  switch   loc_A14AC, loc_A21E5, loc_A21E5, loc_A21E5, loc_A1502, loc_A1518, loc_A152B
0xa0890  ldarg.0
0xa0891  ldc.i4   0x108
0xa0896  sub
0xa0897  switch   loc_A1541, loc_A1557, loc_A21E5, loc_A21E5, loc_A21E5, loc_A156D, loc_A15C3, loc_A1619, loc_A21E5, loc_A162F
0xa08c4  br       loc_A21E5
0xa08c9  ldarg.0
0xa08ca  ldc.i4   0x119
0xa08cf  beq      loc_A1655
0xa08d4  ldarg.0
0xa08d5  ldc.i4   0x120
0xa08da  sub
0xa08db  switch   loc_A1678, loc_A168E, loc_A21E5, loc_A21E5, loc_A16A4
0xa08f4  ldarg.0
0xa08f5  ldc.i4   0x12C
0xa08fa  beq      loc_A16BA
0xa08ff  br       loc_A21E5
0xa0904  ldarg.0
0xa0905  ldc.i4   0x138
0xa090a  bgt.s    loc_A0927
0xa090c  ldarg.0
0xa090d  ldc.i4   0x131
0xa0912  beq      loc_A16D0
0xa0917  ldarg.0
0xa0918  ldc.i4   0x138
0xa091d  beq      loc_A16E6
0xa0922  br       loc_A21E5
0xa0927  ldarg.0
0xa0928  ldc.i4   0x143
0xa092d  beq      loc_A16FC
0xa0932  ldarg.0
0xa0933  ldc.i4   0x147
0xa0938  sub
0xa0939  switch   loc_A1712, loc_A21E5, loc_A1728, loc_A179E
0xa094e  ldarg.0
0xa094f  ldc.i4   0x15A
0xa0954  beq      loc_A17B4
0xa0959  br       loc_A21E5
0xa095e  ldarg.0
0xa095f  ldc.i4   0x229
0xa0964  bgt      loc_A0B74
0xa0969  ldarg.0
0xa096a  ldc.i4   0x1E7
0xa096f  bgt      loc_A0AC9
0xa0974  ldarg.0
0xa0975  ldc.i4   0x1A3
0xa097a  bgt      loc_A0A33
0xa097f  ldarg.0
0xa0980  ldc.i4   0x180
0xa0985  bgt.s    loc_A09D7
0xa0987  ldarg.0
0xa0988  ldc.i4   0x166
0xa098d  beq      loc_A17CA
0xa0992  ldarg.0
0xa0993  ldc.i4   0x174
0xa0998  sub
0xa0999  switch   loc_A17E0, loc_A17F6, loc_A180C, loc_A21E5, loc_A1822, loc_A1838, loc_A184E, loc_A21E5, loc_A21E5, loc_A21E5, loc_A21E5, loc_A21E5, loc_A1864
0xa09d2  br       loc_A21E5
0xa09d7  ldarg.0
0xa09d8  ldc.i4   0x185
0xa09dd  beq      loc_A1877
0xa09e2  ldarg.0
0xa09e3  ldc.i4   0x191
0xa09e8  sub
0xa09e9  switch   loc_A188D, loc_A18A3, loc_A18B9, loc_A21E5, loc_A21E5, loc_A21E5, loc_A21E5, loc_A18CF, loc_A18E2
0xa0a12  ldarg.0
0xa0a13  ldc.i4   0x1A0
0xa0a18  sub
0xa0a19  switch   loc_A18F8, loc_A21E5, loc_A190E, loc_A1924
0xa0a2e  br       loc_A21E5
0xa0a33  ldarg.0
0xa0a34  ldc.i4   0x1CC
0xa0a39  bgt.s    loc_A0AA3
0xa0a3b  ldarg.0
0xa0a3c  ldc.i4   0x1AC
0xa0a41  sub
0xa0a42  switch   loc_A193A, loc_A21E5, loc_A21E5, loc_A21E5, loc_A21E5, loc_A21E5, loc_A1950, loc_A1963, loc_A1979, loc_A198F, loc_A19B5, loc_A19CB, loc_A21E5, loc_A21E5, loc_A19E1, loc_A19F4, loc_A21E5, loc_A21E5, loc_A1A07
0xa0a93  ldarg.0
0xa0a94  ldc.i4   0x1CC
0xa0a99  beq      loc_A1A1A
0xa0a9e  br       loc_A21E5
0xa0aa3  ldarg.0
0xa0aa4  ldc.i4   0x1D6
0xa0aa9  beq      loc_A1A30
0xa0aae  ldarg.0
0xa0aaf  ldc.i4   0x1E5
0xa0ab4  beq      loc_A1A46
0xa0ab9  ldarg.0
0xa0aba  ldc.i4   0x1E7
0xa0abf  beq      loc_A1A89
0xa0ac4  br       loc_A21E5
0xa0ac9  ldarg.0
0xa0aca  ldc.i4   0x20A
0xa0acf  bgt.s    loc_A0B1A
0xa0ad1  ldarg.0
0xa0ad2  ldc.i4   0x1F6
0xa0ad7  bgt.s    loc_A0AF4
0xa0ad9  ldarg.0
0xa0ada  ldc.i4   0x1F1
0xa0adf  beq      loc_A1A9F
0xa0ae4  ldarg.0
0xa0ae5  ldc.i4   0x1F6
0xa0aea  beq      loc_A1AB5
0xa0aef  br       loc_A21E5
0xa0af4  ldarg.0
0xa0af5  ldc.i4   0x1F7
0xa0afa  beq      loc_A1ACB
0xa0aff  ldarg.0
0xa0b00  ldc.i4   0x1FE
0xa0b05  beq      loc_A1AE1
0xa0b0a  ldarg.0
0xa0b0b  ldc.i4   0x20A
0xa0b10  beq      loc_A1AF7
0xa0b15  br       loc_A21E5
0xa0b1a  ldarg.0
0xa0b1b  ldc.i4   0x215
0xa0b20  bgt.s    loc_A0B3D
0xa0b22  ldarg.0
0xa0b23  ldc.i4   0x20F
0xa0b28  beq      loc_A1B0D
0xa0b2d  ldarg.0
0xa0b2e  ldc.i4   0x215
0xa0b33  beq      loc_A1B36
0xa0b38  br       loc_A21E5
0xa0b3d  ldarg.0
0xa0b3e  ldc.i4   0x21D
0xa0b43  beq      loc_A1B4C
0xa0b48  ldarg.0
0xa0b49  ldc.i4   0x21E
0xa0b4e  beq      loc_A1B7F
0xa0b53  ldarg.0
0xa0b54  ldc.i4   0x226
0xa0b59  sub
0xa0b5a  switch   loc_A1B95, loc_A1BDB, loc_A21E5, loc_A1BF1
0xa0b6f  br       loc_A21E5
0xa0b74  ldarg.0
0xa0b75  ldc.i4   0x288
0xa0b7a  bgt      loc_A0C73
0xa0b7f  ldarg.0
0xa0b80  ldc.i4   0x25D
0xa0b85  bgt.s    loc_A0BE5
0xa0b87  ldarg.0
0xa0b88  ldc.i4   0x232
0xa0b8d  bgt.s    loc_A0BAA
  ... truncated ...
```
