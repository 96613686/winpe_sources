# System.Windows.Media.KnownColors::ColorStringToKnownColor

- ea: `0x9d240`
- end: `0x9e187`
- name: `System.Windows.Media.KnownColors::ColorStringToKnownColor`
- size: `3911`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x93c70`
- `0x9d110`
- `0x10c030`

## callees

- `0x9d240`

## string_xrefs

- `0x9d7aa`: `MAGENTA`
- `0x9ddd1`: `DARKMAGENTA`

## pseudocode

```c

```

## disassembly

```asm
0x9d240  ldarg.0
0x9d241  brfalse  loc_9E185
0x9d246  ldarg.0
0x9d247  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9d24c  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x9d251  stloc.0
0x9d252  ldloc.0
0x9d253  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9d258  stloc.s  0xC
0x9d25a  ldloc.s  0xC
0x9d25c  ldc.i4.3
0x9d25d  sub
0x9d25e  switch   loc_9D2B0, loc_9D2D9, loc_9D43A, loc_9D58F, loc_9D6E6, loc_9D801, loc_9D912, loc_9DBB8, loc_9DD78, loc_9DEC9, loc_9DF8B, loc_9E062, loc_9E113, loc_9E14C, loc_9E15F, loc_9E185, loc_9E185, loc_9E172
0x9d2ab  br       loc_9E185
0x9d2b0  ldloc.0
0x9d2b1  ldstr    aRed// "RED"
0x9d2b6  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d2bb  brfalse.s loc_9D2C3
0x9d2bd  ldc.i4   0xFFFF0000
0x9d2c2  ret
0x9d2c3  ldloc.0
0x9d2c4  ldstr    aTan// "TAN"
0x9d2c9  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d2ce  brfalse  loc_9E185
0x9d2d3  ldc.i4   0xFFD2B48C
0x9d2d8  ret
0x9d2d9  ldloc.0
0x9d2da  ldc.i4.0
0x9d2db  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x9d2e0  stloc.s  0xA
0x9d2e2  ldloc.s  0xA
0x9d2e4  ldc.i4.s 0x41
0x9d2e6  sub
0x9d2e7  switch   loc_9D33B, loc_9D351, loc_9D367, loc_9E185, loc_9E185, loc_9E185, loc_9D37D
0x9d308  ldloc.s  0xA
0x9d30a  ldc.i4.s 0x4C
0x9d30c  sub
0x9d30d  switch   loc_9D3A6, loc_9E185, loc_9D3BC, loc_9E185, loc_9D3D2, loc_9E185, loc_9E185, loc_9D40E, loc_9D424
0x9d336  br       loc_9E185
0x9d33b  ldloc.0
0x9d33c  ldstr    aAqua// "AQUA"
0x9d341  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d346  brfalse  loc_9E185
0x9d34b  ldc.i4   0xFF00FFFF
0x9d350  ret
0x9d351  ldloc.0
0x9d352  ldstr    aBlue// "BLUE"
0x9d357  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d35c  brfalse  loc_9E185
0x9d361  ldc.i4   0xFF0000FF
0x9d366  ret
0x9d367  ldloc.0
0x9d368  ldstr    aCyan// "CYAN"
0x9d36d  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d372  brfalse  loc_9E185
0x9d377  ldc.i4   0xFF00FFFF
0x9d37c  ret
0x9d37d  ldloc.0
0x9d37e  ldstr    aGold// "GOLD"
0x9d383  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d388  brfalse.s loc_9D390
0x9d38a  ldc.i4   0xFFFFD700
0x9d38f  ret
0x9d390  ldloc.0
0x9d391  ldstr    aGray// "GRAY"
0x9d396  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d39b  brfalse  loc_9E185
0x9d3a0  ldc.i4   0xFF808080
0x9d3a5  ret
0x9d3a6  ldloc.0
0x9d3a7  ldstr    aLime// "LIME"
0x9d3ac  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d3b1  brfalse  loc_9E185
0x9d3b6  ldc.i4   0xFF00FF00
0x9d3bb  ret
0x9d3bc  ldloc.0
0x9d3bd  ldstr    aNavy// "NAVY"
0x9d3c2  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d3c7  brfalse  loc_9E185
0x9d3cc  ldc.i4   0xFF000080
0x9d3d1  ret
0x9d3d2  ldloc.0
0x9d3d3  ldstr    aPeru// "PERU"
0x9d3d8  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d3dd  brfalse.s loc_9D3E5
0x9d3df  ldc.i4   0xFFCD853F
0x9d3e4  ret
0x9d3e5  ldloc.0
0x9d3e6  ldstr    aPink// "PINK"
0x9d3eb  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d3f0  brfalse.s loc_9D3F8
0x9d3f2  ldc.i4   0xFFFFC0CB
0x9d3f7  ret
0x9d3f8  ldloc.0
0x9d3f9  ldstr    aPlum// "PLUM"
0x9d3fe  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d403  brfalse  loc_9E185
0x9d408  ldc.i4   0xFFDDA0DD
0x9d40d  ret
0x9d40e  ldloc.0
0x9d40f  ldstr    aSnow// "SNOW"
0x9d414  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d419  brfalse  loc_9E185
0x9d41e  ldc.i4   0xFFFFFAFA
0x9d423  ret
0x9d424  ldloc.0
0x9d425  ldstr    aTeal// "TEAL"
0x9d42a  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d42f  brfalse  loc_9E185
0x9d434  ldc.i4   0xFF008080
0x9d439  ret
0x9d43a  ldloc.0
0x9d43b  ldc.i4.0
0x9d43c  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x9d441  stloc.s  9
0x9d443  ldloc.s  9
0x9d445  ldc.i4.s 0x41
0x9d447  sub
0x9d448  switch   loc_9D497, loc_9D4AD, loc_9D4E9, loc_9E185, loc_9E185, loc_9E185, loc_9D4FF, loc_9E185, loc_9D515, loc_9E185, loc_9D528, loc_9D53E, loc_9E185, loc_9E185, loc_9D554
0x9d489  ldloc.s  9
0x9d48b  ldc.i4.s 0x57
0x9d48d  beq      loc_9D56A
0x9d492  br       loc_9E185
0x9d497  ldloc.0
0x9d498  ldstr    aAzure// "AZURE"
0x9d49d  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d4a2  brfalse  loc_9E185
0x9d4a7  ldc.i4   0xFFF0FFFF
0x9d4ac  ret
0x9d4ad  ldloc.0
0x9d4ae  ldstr    aBeige// "BEIGE"
0x9d4b3  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d4b8  brfalse.s loc_9D4C0
0x9d4ba  ldc.i4   0xFFF5F5DC
0x9d4bf  ret
0x9d4c0  ldloc.0
0x9d4c1  ldstr    aBlack_0// "BLACK"
0x9d4c6  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d4cb  brfalse.s loc_9D4D3
0x9d4cd  ldc.i4   0xFF000000
0x9d4d2  ret
0x9d4d3  ldloc.0
0x9d4d4  ldstr    aBrown// "BROWN"
0x9d4d9  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d4de  brfalse  loc_9E185
0x9d4e3  ldc.i4   0xFFA52A2A
0x9d4e8  ret
0x9d4e9  ldloc.0
0x9d4ea  ldstr    aCoral// "CORAL"
0x9d4ef  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d4f4  brfalse  loc_9E185
0x9d4f9  ldc.i4   0xFFFF7F50
0x9d4fe  ret
0x9d4ff  ldloc.0
0x9d500  ldstr    aGreen// "GREEN"
0x9d505  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d50a  brfalse  loc_9E185
0x9d50f  ldc.i4   0xFF008000
0x9d514  ret
0x9d515  ldloc.0
0x9d516  ldstr    aIvory// "IVORY"
0x9d51b  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d520  brfalse  loc_9E185
0x9d525  ldc.i4.s 0xF0
0x9d527  ret
0x9d528  ldloc.0
0x9d529  ldstr    aKhaki// "KHAKI"
0x9d52e  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d533  brfalse  loc_9E185
0x9d538  ldc.i4   0xFFF0E68C
0x9d53d  ret
0x9d53e  ldloc.0
0x9d53f  ldstr    aLinen// "LINEN"
0x9d544  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d549  brfalse  loc_9E185
0x9d54e  ldc.i4   0xFFFAF0E6
0x9d553  ret
0x9d554  ldloc.0
0x9d555  ldstr    aOlive// "OLIVE"
0x9d55a  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d55f  brfalse  loc_9E185
0x9d564  ldc.i4   0xFF808000
0x9d569  ret
0x9d56a  ldloc.0
0x9d56b  ldstr    aWheat// "WHEAT"
0x9d570  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d575  brfalse.s loc_9D57D
0x9d577  ldc.i4   0xFFF5DEB3
0x9d57c  ret
0x9d57d  ldloc.0
0x9d57e  ldstr    aWhite// "WHITE"
0x9d583  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d588  brfalse  loc_9E185
0x9d58d  ldc.i4.m1
0x9d58e  ret
0x9d58f  ldloc.0
0x9d590  ldc.i4.0
0x9d591  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x9d596  stloc.s  8
0x9d598  ldloc.s  8
0x9d59a  ldc.i4.s 0x42
0x9d59c  beq.s    loc_9D5E7
0x9d59e  ldloc.s  8
0x9d5a0  ldc.i4.s 0x49
0x9d5a2  beq.s    loc_9D5FD
0x9d5a4  ldloc.s  8
0x9d5a6  ldc.i4.s 0x4D
0x9d5a8  sub
0x9d5a9  switch   loc_9D613, loc_9E185, loc_9D629, loc_9D652, loc_9E185, loc_9E185, loc_9D668, loc_9D6A4, loc_9E185, loc_9D6BA, loc_9E185, loc_9E185, loc_9D6D0
0x9d5e2  br       loc_9E185
0x9d5e7  ldloc.0
0x9d5e8  ldstr    aBisque// "BISQUE"
0x9d5ed  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d5f2  brfalse  loc_9E185
0x9d5f7  ldc.i4   0xFFFFE4C4
0x9d5fc  ret
0x9d5fd  ldloc.0
0x9d5fe  ldstr    aIndigo// "INDIGO"
0x9d603  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d608  brfalse  loc_9E185
0x9d60d  ldc.i4   0xFF4B0082
0x9d612  ret
0x9d613  ldloc.0
0x9d614  ldstr    aMaroon// "MAROON"
0x9d619  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d61e  brfalse  loc_9E185
0x9d623  ldc.i4   0xFF800000
0x9d628  ret
0x9d629  ldloc.0
0x9d62a  ldstr    aOrange// "ORANGE"
0x9d62f  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d634  brfalse.s loc_9D63C
0x9d636  ldc.i4   0xFFFFA500
0x9d63b  ret
0x9d63c  ldloc.0
0x9d63d  ldstr    aOrchid// "ORCHID"
0x9d642  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d647  brfalse  loc_9E185
0x9d64c  ldc.i4   0xFFDA70D6
0x9d651  ret
0x9d652  ldloc.0
0x9d653  ldstr    aPurple// "PURPLE"
0x9d658  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d65d  brfalse  loc_9E185
0x9d662  ldc.i4   0xFF800080
0x9d667  ret
0x9d668  ldloc.0
0x9d669  ldstr    aSalmon// "SALMON"
0x9d66e  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d673  brfalse.s loc_9D67B
0x9d675  ldc.i4   0xFFFA8072
0x9d67a  ret
0x9d67b  ldloc.0
0x9d67c  ldstr    aSienna// "SIENNA"
0x9d681  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d686  brfalse.s loc_9D68E
0x9d688  ldc.i4   0xFFA0522D
0x9d68d  ret
0x9d68e  ldloc.0
0x9d68f  ldstr    aSilver// "SILVER"
0x9d694  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d699  brfalse  loc_9E185
0x9d69e  ldc.i4   0xFFC0C0C0
0x9d6a3  ret
0x9d6a4  ldloc.0
0x9d6a5  ldstr    aTomato// "TOMATO"
0x9d6aa  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d6af  brfalse  loc_9E185
0x9d6b4  ldc.i4   0xFFFF6347
0x9d6b9  ret
0x9d6ba  ldloc.0
0x9d6bb  ldstr    aViolet// "VIOLET"
0x9d6c0  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d6c5  brfalse  loc_9E185
0x9d6ca  ldc.i4   0xFFEE82EE
0x9d6cf  ret
0x9d6d0  ldloc.0
0x9d6d1  ldstr    aYellow// "YELLOW"
0x9d6d6  callvirt instance bool [mscorlib]System.String::Equals(string)
0x9d6db  brfalse  loc_9E185
0x9d6e0  ldc.i4   0xFFFFFF00
0x9d6e5  ret
0x9d6e6  ldloc.0
0x9d6e7  ldc.i4.0
0x9d6e8  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x9d6ed  stloc.3
0x9d6ee  ldloc.3
0x9d6ef  ldc.i4.s 0x4D
0x9d6f1  bgt.un.s loc_9D721
0x9d6f3  ldloc.3
0x9d6f4  ldc.i4.s 0x43
0x9d6f6  sub
0x9d6f7  switch   loc_9D73E, loc_9D754, loc_9E185, loc_9D77D, loc_9E185, loc_9D793
0x9d714  ldloc.3
0x9d715  ldc.i4.s 0x4D
0x9d717  beq      loc_9D7A9
0x9d71c  br       loc_9E185
0x9d721  ldloc.3
0x9d722  ldc.i4.s 0x4F
0x9d724  beq      loc_9D7BF
  ... truncated ...
```
