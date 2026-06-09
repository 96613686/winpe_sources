# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextHelpActions

- ea: `0x6280`
- end: `0x66ea`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::ReadNextHelpActions`
- size: `1130`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `broker_com_uri`

## callers

- `0x58d0`

## callees

- `0x3f60`
- `0x3f80`
- `0x3fa0`
- `0x3fc0`
- `0x3fe0`
- `0x4000`
- `0x4020`
- `0x4040`
- `0x4060`
- `0x4080`
- `0x40a0`
- `0x40c0`
- `0x6280`
- `0x7f00`
- `0x7f20`
- `0x7f40`
- `0x7f60`
- `0x7f80`
- `0x7fa0`
- `0x7fc0`
- `0x7fe0`
- `0x8000`
- `0x8020`
- `0x8040`
- `0x8060`
- `0x8080`
- `0x80a0`
- `0x80c0`
- `0x80e0`
- `0x8100`
- `0x8120`
- `0x8140`
- `0x8160`

## pseudocode

```c

```

## disassembly

```asm
0x6280  ldloca.s 0
0x6282  initobj  Microsoft.ManagementConsole.Internal.ActionsPaneRootData
0x6288  ldarg.0
0x6289  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x628e  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_Id_Count()
0x6293  ldarg.0
0x6294  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x6299  ldelem.i4
0x629a  stloc.1
0x629b  ldnull
0x629c  stloc.2
0x629d  ldloc.1
0x629e  ldc.i4.0
0x629f  blt.s    loc_62CF
0x62a1  ldloc.1
0x62a2  newarr   [mscorlib]System.Int32
0x62a7  stloc.2
0x62a8  ldarg.0
0x62a9  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x62ae  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_Id()
0x62b3  ldarg.0
0x62b4  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_Id_Offset
0x62b9  ldloc.2
0x62ba  ldc.i4.0
0x62bb  ldloc.1
0x62bc  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x62c1  ldarg.0
0x62c2  ldarg.0
0x62c3  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_Id_Offset
0x62c8  ldloc.1
0x62c9  add
0x62ca  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_Id_Offset
0x62cf  ldloca.s 0
0x62d1  ldloc.2
0x62d2  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetId(int32[] value)
0x62d7  ldarg.0
0x62d8  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x62dd  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_ItemType_Count()
0x62e2  ldarg.0
0x62e3  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x62e8  ldelem.i4
0x62e9  stloc.3
0x62ea  ldnull
0x62eb  stloc.s  4
0x62ed  ldloc.3
0x62ee  ldc.i4.0
0x62ef  blt.s    loc_62F9
0x62f1  ldloc.3
0x62f2  newarr   Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType
0x62f7  stloc.s  4
0x62f9  ldc.i4.0
0x62fa  stloc.s  5
0x62fc  ldc.i4.0
0x62fd  stloc.s  5
0x62ff  br.s     loc_632C
0x6301  ldloc.s  4
0x6303  ldloc.s  5
0x6305  ldarg.0
0x6306  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x630b  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_ItemType()
0x6310  ldarg.0
0x6311  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_ItemType_Offset
0x6316  ldelem.i4
0x6317  stelem.i4
0x6318  ldarg.0
0x6319  ldarg.0
0x631a  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_ItemType_Offset
0x631f  ldc.i4.1
0x6320  add
0x6321  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_ItemType_Offset
0x6326  ldloc.s  5
0x6328  ldc.i4.1
0x6329  add
0x632a  stloc.s  5
0x632c  ldloc.s  5
0x632e  ldloc.3
0x632f  blt.s    loc_6301
0x6331  ldloca.s 0
0x6333  ldloc.s  4
0x6335  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetItemType(valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType[] value)
0x633a  ldarg.0
0x633b  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x6340  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_InsertionLocation_Count()
0x6345  ldarg.0
0x6346  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x634b  ldelem.i4
0x634c  stloc.s  6
0x634e  ldnull
0x634f  stloc.s  7
0x6351  ldloc.s  6
0x6353  ldc.i4.0
0x6354  blt.s    loc_635F
0x6356  ldloc.s  6
0x6358  newarr   Microsoft.ManagementConsole.Internal.ActionsInsertionLocation
0x635d  stloc.s  7
0x635f  ldc.i4.0
0x6360  stloc.s  8
0x6362  ldc.i4.0
0x6363  stloc.s  8
0x6365  br.s     loc_6392
0x6367  ldloc.s  7
0x6369  ldloc.s  8
0x636b  ldarg.0
0x636c  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x6371  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_InsertionLocation()
0x6376  ldarg.0
0x6377  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_InsertionLocation_Offset
0x637c  ldelem.i4
0x637d  stelem.i4
0x637e  ldarg.0
0x637f  ldarg.0
0x6380  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_InsertionLocation_Offset
0x6385  ldc.i4.1
0x6386  add
0x6387  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_InsertionLocation_Offset
0x638c  ldloc.s  8
0x638e  ldc.i4.1
0x638f  add
0x6390  stloc.s  8
0x6392  ldloc.s  8
0x6394  ldloc.s  6
0x6396  blt.s    loc_6367
0x6398  ldloca.s 0
0x639a  ldloc.s  7
0x639c  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetInsertionLocation(valuetype Microsoft.ManagementConsole.Internal.ActionsInsertionLocation[] value)
0x63a1  ldarg.0
0x63a2  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x63a7  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_DisplayName_Count()
0x63ac  ldarg.0
0x63ad  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x63b2  ldelem.i4
0x63b3  stloc.s  9
0x63b5  ldnull
0x63b6  stloc.s  0xA
0x63b8  ldloc.s  9
0x63ba  ldc.i4.0
0x63bb  blt.s    loc_63C6
0x63bd  ldloc.s  9
0x63bf  newarr   [mscorlib]System.String
0x63c4  stloc.s  0xA
0x63c6  ldc.i4.0
0x63c7  stloc.s  0xB
0x63c9  ldc.i4.0
0x63ca  stloc.s  0xB
0x63cc  br.s     loc_63F2
0x63ce  ldloc.s  0xA
0x63d0  ldloc.s  0xB
0x63d2  ldarg.0
0x63d3  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x63d8  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x63dd  stelem.ref
0x63de  ldarg.0
0x63df  ldarg.0
0x63e0  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_DisplayName_Offset
0x63e5  ldc.i4.1
0x63e6  add
0x63e7  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_DisplayName_Offset
0x63ec  ldloc.s  0xB
0x63ee  ldc.i4.1
0x63ef  add
0x63f0  stloc.s  0xB
0x63f2  ldloc.s  0xB
0x63f4  ldloc.s  9
0x63f6  blt.s    loc_63CE
0x63f8  ldloca.s 0
0x63fa  ldloc.s  0xA
0x63fc  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetDisplayName(string[] value)
0x6401  ldarg.0
0x6402  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x6407  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_MnemonicDisplayName_Count()
0x640c  ldarg.0
0x640d  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x6412  ldelem.i4
0x6413  stloc.s  0xC
0x6415  ldnull
0x6416  stloc.s  0xD
0x6418  ldloc.s  0xC
0x641a  ldc.i4.0
0x641b  blt.s    loc_6426
0x641d  ldloc.s  0xC
0x641f  newarr   [mscorlib]System.String
0x6424  stloc.s  0xD
0x6426  ldc.i4.0
0x6427  stloc.s  0xE
0x6429  ldc.i4.0
0x642a  stloc.s  0xE
0x642c  br.s     loc_6452
0x642e  ldloc.s  0xD
0x6430  ldloc.s  0xE
0x6432  ldarg.0
0x6433  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x6438  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x643d  stelem.ref
0x643e  ldarg.0
0x643f  ldarg.0
0x6440  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_MnemonicDisplayName_Offset
0x6445  ldc.i4.1
0x6446  add
0x6447  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_MnemonicDisplayName_Offset
0x644c  ldloc.s  0xE
0x644e  ldc.i4.1
0x644f  add
0x6450  stloc.s  0xE
0x6452  ldloc.s  0xE
0x6454  ldloc.s  0xC
0x6456  blt.s    loc_642E
0x6458  ldloca.s 0
0x645a  ldloc.s  0xD
0x645c  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetMnemonicDisplayName(string[] value)
0x6461  ldarg.0
0x6462  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x6467  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_Description_Count()
0x646c  ldarg.0
0x646d  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x6472  ldelem.i4
0x6473  stloc.s  0xF
0x6475  ldnull
0x6476  stloc.s  0x10
0x6478  ldloc.s  0xF
0x647a  ldc.i4.0
0x647b  blt.s    loc_6486
0x647d  ldloc.s  0xF
0x647f  newarr   [mscorlib]System.String
0x6484  stloc.s  0x10
0x6486  ldc.i4.0
0x6487  stloc.s  0x11
0x6489  ldc.i4.0
0x648a  stloc.s  0x11
0x648c  br.s     loc_64B2
0x648e  ldloc.s  0x10
0x6490  ldloc.s  0x11
0x6492  ldarg.0
0x6493  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x6498  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x649d  stelem.ref
0x649e  ldarg.0
0x649f  ldarg.0
0x64a0  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_Description_Offset
0x64a5  ldc.i4.1
0x64a6  add
0x64a7  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_Description_Offset
0x64ac  ldloc.s  0x11
0x64ae  ldc.i4.1
0x64af  add
0x64b0  stloc.s  0x11
0x64b2  ldloc.s  0x11
0x64b4  ldloc.s  0xF
0x64b6  blt.s    loc_648E
0x64b8  ldloca.s 0
0x64ba  ldloc.s  0x10
0x64bc  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetDescription(string[] value)
0x64c1  ldarg.0
0x64c2  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x64c7  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_LanguageIndependentName_Count()
0x64cc  ldarg.0
0x64cd  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x64d2  ldelem.i4
0x64d3  stloc.s  0x12
0x64d5  ldnull
0x64d6  stloc.s  0x13
0x64d8  ldloc.s  0x12
0x64da  ldc.i4.0
0x64db  blt.s    loc_64E6
0x64dd  ldloc.s  0x12
0x64df  newarr   [mscorlib]System.String
0x64e4  stloc.s  0x13
0x64e6  ldc.i4.0
0x64e7  stloc.s  0x14
0x64e9  ldc.i4.0
0x64ea  stloc.s  0x14
0x64ec  br.s     loc_6512
0x64ee  ldloc.s  0x13
0x64f0  ldloc.s  0x14
0x64f2  ldarg.0
0x64f3  ldfld    class [mscorlib]System.IO.BinaryReader Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_strings
0x64f8  callvirt instance string [mscorlib]System.IO.BinaryReader::ReadString()
0x64fd  stelem.ref
0x64fe  ldarg.0
0x64ff  ldarg.0
0x6500  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_LanguageIndependentName_Offset
0x6505  ldc.i4.1
0x6506  add
0x6507  stfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_HelpActions_LanguageIndependentName_Offset
0x650c  ldloc.s  0x14
0x650e  ldc.i4.1
0x650f  add
0x6510  stloc.s  0x14
0x6512  ldloc.s  0x14
0x6514  ldloc.s  0x12
0x6516  blt.s    loc_64EE
0x6518  ldloca.s 0
0x651a  ldloc.s  0x13
0x651c  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::SetLanguageIndependentName(string[] value)
0x6521  ldarg.0
0x6522  ldfld    class Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_source
0x6527  callvirt instance int32[] Microsoft.ManagementConsole.Internal.InsertScopeNodesCommand::Get_HelpActions_ImageIndex_Count()
0x652c  ldarg.0
0x652d  ldfld    int32 Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandReader::_currentIndex
0x6532  ldelem.i4
0x6533  stloc.s  0x15
  ... truncated ...
```
