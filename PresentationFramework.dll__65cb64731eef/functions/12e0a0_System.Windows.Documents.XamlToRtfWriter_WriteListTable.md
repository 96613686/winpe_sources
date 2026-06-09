# System.Windows.Documents.XamlToRtfWriter::WriteListTable

- ea: `0x12e0a0`
- end: `0x12e53f`
- name: `System.Windows.Documents.XamlToRtfWriter::WriteListTable`
- size: `1183`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x12de80`

## callees

- `0xf28b0`
- `0xf28d0`
- `0xf2920`
- `0xf29c0`
- `0xf2a00`
- `0xf2a30`
- `0xf2ae0`
- `0xf2b00`
- `0xf2b40`
- `0xf2b80`
- `0xf5d90`
- `0xf5da0`
- `0x12e0a0`

## string_xrefs

- `0x12e0f2`: `\listtemplateid`
- `0x12e248`: `\leveltemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x12e0a0  ldarg.0
0x12e0a1  ldfld    class System.Windows.Documents.ConverterState System.Windows.Documents.XamlToRtfWriter::_converterState
0x12e0a6  callvirt instance class System.Windows.Documents.ListTable System.Windows.Documents.ConverterState::get_ListTable()
0x12e0ab  stloc.0
0x12e0ac  ldloc.0
0x12e0ad  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x12e0b2  ldc.i4.0
0x12e0b3  ble      loc_12E40B
0x12e0b8  ldarg.0
0x12e0b9  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e0be  ldstr    aListtable_0// "\r\n{\\*\\listtable"
0x12e0c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e0c8  pop
0x12e0c9  ldc.i4.5
0x12e0ca  stloc.2
0x12e0cb  ldc.i4.0
0x12e0cc  stloc.3
0x12e0cd  br       loc_12E3EE
0x12e0d2  ldloc.0
0x12e0d3  ldloc.3
0x12e0d4  callvirt instance class System.Windows.Documents.ListTableEntry System.Windows.Documents.ListTable::EntryAt(int32 index)
0x12e0d9  stloc.s  4
0x12e0db  ldarg.0
0x12e0dc  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e0e1  ldstr    aList_1// "\r\n{\\list"
0x12e0e6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e0eb  pop
0x12e0ec  ldarg.0
0x12e0ed  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e0f2  ldstr    aListtemplateid_0// "\\listtemplateid"
0x12e0f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e0fc  pop
0x12e0fd  ldarg.0
0x12e0fe  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e103  ldloc.s  4
0x12e105  callvirt instance int64 System.Windows.Documents.ListTableEntry::get_ID()
0x12e10a  stloc.s  6
0x12e10c  ldloca.s 6
0x12e10e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e113  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x12e118  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e11d  pop
0x12e11e  ldarg.0
0x12e11f  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e124  ldstr    aListhybrid_0// "\\listhybrid"
0x12e129  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e12e  pop
0x12e12f  ldloc.s  4
0x12e131  callvirt instance class System.Windows.Documents.ListLevelTable System.Windows.Documents.ListTableEntry::get_Levels()
0x12e136  stloc.s  5
0x12e138  ldc.i4.0
0x12e139  stloc.s  7
0x12e13b  br       loc_12E388
0x12e140  ldloc.s  5
0x12e142  ldloc.s  7
0x12e144  callvirt instance class System.Windows.Documents.ListLevel System.Windows.Documents.ListLevelTable::EntryAt(int32 index)
0x12e149  stloc.s  8
0x12e14b  ldloc.s  8
0x12e14d  callvirt instance valuetype System.Windows.Documents.MarkerStyle System.Windows.Documents.ListLevel::get_Marker()
0x12e152  conv.i8
0x12e153  stloc.s  9
0x12e155  ldarg.0
0x12e156  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e15b  ldstr    aListlevel_0// "\r\n{\\listlevel"
0x12e160  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e165  pop
0x12e166  ldarg.0
0x12e167  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e16c  ldstr    aLevelnfc_0// "\\levelnfc"
0x12e171  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e176  pop
0x12e177  ldarg.0
0x12e178  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e17d  ldloca.s 9
0x12e17f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e184  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x12e189  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e18e  pop
0x12e18f  ldarg.0
0x12e190  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e195  ldstr    aLevelnfcn_0// "\\levelnfcn"
0x12e19a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e19f  pop
0x12e1a0  ldarg.0
0x12e1a1  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e1a6  ldloca.s 9
0x12e1a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e1ad  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x12e1b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e1b7  pop
0x12e1b8  ldarg.0
0x12e1b9  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e1be  ldstr    aLeveljc0// "\\leveljc0"
0x12e1c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e1c8  pop
0x12e1c9  ldarg.0
0x12e1ca  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e1cf  ldstr    aLeveljcn0// "\\leveljcn0"
0x12e1d4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e1d9  pop
0x12e1da  ldarg.0
0x12e1db  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e1e0  ldstr    aLevelfollow0// "\\levelfollow0"
0x12e1e5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e1ea  pop
0x12e1eb  ldarg.0
0x12e1ec  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e1f1  ldstr    aLevelstartat_0// "\\levelstartat"
0x12e1f6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e1fb  pop
0x12e1fc  ldarg.0
0x12e1fd  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e202  ldloc.s  8
0x12e204  callvirt instance int64 System.Windows.Documents.ListLevel::get_StartIndex()
0x12e209  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int64)
0x12e20e  pop
0x12e20f  ldarg.0
0x12e210  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e215  ldstr    aLevelspace0// "\\levelspace0"
0x12e21a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e21f  pop
0x12e220  ldarg.0
0x12e221  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e226  ldstr    aLevelindent0// "\\levelindent0"
0x12e22b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e230  pop
0x12e231  ldarg.0
0x12e232  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e237  ldstr    aLeveltext_0// "{\\leveltext"
0x12e23c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e241  pop
0x12e242  ldarg.0
0x12e243  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e248  ldstr    aLeveltemplatei_0// "\\leveltemplateid"
0x12e24d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e252  pop
0x12e253  ldarg.0
0x12e254  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e259  ldloca.s 2
0x12e25b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e260  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x12e265  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e26a  pop
0x12e26b  ldloc.2
0x12e26c  ldc.i4.1
0x12e26d  add
0x12e26e  stloc.2
0x12e26f  ldloc.s  8
0x12e271  callvirt instance valuetype System.Windows.Documents.MarkerStyle System.Windows.Documents.ListLevel::get_Marker()
0x12e276  ldc.i4.s 0x17
0x12e278  bne.un.s loc_12E29E
0x12e27a  ldarg.0
0x12e27b  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e280  ldstr    a01B7// "\\'01\\'b7}"
0x12e285  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e28a  pop
0x12e28b  ldarg.0
0x12e28c  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e291  ldstr    aLevelnumbers_0// "{\\levelnumbers;}"
0x12e296  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e29b  pop
0x12e29c  br.s     loc_12E2E9
0x12e29e  ldarg.0
0x12e29f  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e2a4  ldstr    a020// "\\'02\\'0"
0x12e2a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e2ae  pop
0x12e2af  ldarg.0
0x12e2b0  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e2b5  ldloca.s 7
0x12e2b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e2bc  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x12e2c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e2c6  pop
0x12e2c7  ldarg.0
0x12e2c8  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e2cd  ldstr    asc_2B38B2// ".;}"
0x12e2d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e2d7  pop
0x12e2d8  ldarg.0
0x12e2d9  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e2de  ldstr    aLevelnumbers01// "{\\levelnumbers\\'01;}"
0x12e2e3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e2e8  pop
0x12e2e9  ldarg.0
0x12e2ea  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e2ef  ldstr    aFi360// "\\fi-360"
0x12e2f4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e2f9  pop
0x12e2fa  ldarg.0
0x12e2fb  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e300  ldstr    aLi_0// "\\li"
0x12e305  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e30a  pop
0x12e30b  ldloc.s  7
0x12e30d  ldc.i4.1
0x12e30e  add
0x12e30f  ldc.i4   0x2D0
0x12e314  mul
0x12e315  stloc.s  0xB
0x12e317  ldloca.s 0xB
0x12e319  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e31e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x12e323  stloc.s  0xA
0x12e325  ldarg.0
0x12e326  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e32b  ldloc.s  0xA
0x12e32d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e332  pop
0x12e333  ldarg.0
0x12e334  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e339  ldstr    aLin_0// "\\lin"
0x12e33e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e343  pop
0x12e344  ldarg.0
0x12e345  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e34a  ldloc.s  0xA
0x12e34c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e351  pop
0x12e352  ldarg.0
0x12e353  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e358  ldstr    aJclisttabTx// "\\jclisttab\\tx"
0x12e35d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e362  pop
0x12e363  ldarg.0
0x12e364  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e369  ldloc.s  0xA
0x12e36b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e370  pop
0x12e371  ldarg.0
0x12e372  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e377  ldstr    asc_29CBC0// "}"
0x12e37c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e381  pop
0x12e382  ldloc.s  7
0x12e384  ldc.i4.1
0x12e385  add
0x12e386  stloc.s  7
0x12e388  ldloc.s  7
0x12e38a  ldloc.s  5
0x12e38c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x12e391  blt      loc_12E140
0x12e396  ldarg.0
0x12e397  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e39c  ldstr    aListname_0// "\r\n{\\listname ;}"
0x12e3a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e3a6  pop
0x12e3a7  ldarg.0
0x12e3a8  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e3ad  ldstr    aListid_0// "\\listid"
0x12e3b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e3b7  pop
0x12e3b8  ldarg.0
0x12e3b9  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e3be  ldloc.s  4
0x12e3c0  callvirt instance int64 System.Windows.Documents.ListTableEntry::get_ID()
0x12e3c5  stloc.s  6
0x12e3c7  ldloca.s 6
0x12e3c9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e3ce  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x12e3d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e3d8  pop
0x12e3d9  ldarg.0
0x12e3da  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e3df  ldstr    asc_29CBC0// "}"
0x12e3e4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e3e9  pop
0x12e3ea  ldloc.3
0x12e3eb  ldc.i4.1
0x12e3ec  add
0x12e3ed  stloc.3
0x12e3ee  ldloc.3
0x12e3ef  ldloc.0
0x12e3f0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x12e3f5  blt      loc_12E0D2
0x12e3fa  ldarg.0
0x12e3fb  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e400  ldstr    asc_2B3952// "}\r\n"
0x12e405  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e40a  pop
0x12e40b  ldarg.0
0x12e40c  ldfld    class System.Windows.Documents.ConverterState System.Windows.Documents.XamlToRtfWriter::_converterState
0x12e411  callvirt instance class System.Windows.Documents.ListOverrideTable System.Windows.Documents.ConverterState::get_ListOverrideTable()
0x12e416  stloc.1
0x12e417  ldloc.1
0x12e418  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x12e41d  ldc.i4.0
0x12e41e  ble      loc_12E53E
0x12e423  ldarg.0
0x12e424  ldfld    class [mscorlib]System.Text.StringBuilder System.Windows.Documents.XamlToRtfWriter::_rtfBuilder
0x12e429  ldstr    aListoverrideta_0// "{\\*\\listoverridetable"
0x12e42e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12e433  pop
0x12e434  ldc.i4.0
0x12e435  stloc.s  0xC
0x12e437  br       loc_12E520
0x12e43c  ldloc.1
0x12e43d  ldloc.s  0xC
0x12e43f  callvirt instance class System.Windows.Documents.ListOverride System.Windows.Documents.ListOverrideTable::EntryAt(int32 index)
0x12e444  stloc.s  0xD
  ... truncated ...
```
