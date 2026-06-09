# System.Windows.Markup.BamlReader::ProcessKeyTree

- ea: `0x8d020`
- end: `0x8d7a3`
- name: `System.Windows.Markup.BamlReader::ProcessKeyTree`
- size: `1923`
- prototype: ``
- caller_count: `2`
- callee_count: `44`
- tags: `broker_com_uri`

## callers

- `0x8c340`
- `0x8cc90`

## callees

- `0x38c70`
- `0x8a810`
- `0x8aa60`
- `0x8ab50`
- `0x8b280`
- `0x8b6c0`
- `0x8b6f0`
- `0x8c050`
- `0x8c780`
- `0x8c7d0`
- `0x8d020`
- `0x8d830`
- `0x8d990`
- `0x8de10`
- `0x8e6c0`
- `0x8e760`
- `0x8e810`
- `0x8e9f0`
- `0x96340`
- `0x969a0`
- `0x969b0`
- `0x969f0`
- `0x972f0`
- `0x97400`
- `0x974d0`
- `0x977d0`
- `0x98210`
- `0x985d0`
- `0x98ed0`
- `0x99580`
- `0xb4030`
- `0x263d80`
- `0x263da0`
- `0x263dc0`
- `0x263de0`
- `0x263e00`
- `0x263e10`
- `0x263e20`
- `0x263e30`
- `0x263e40`
- `0x263e90`
- `0x263ea0`
- `0x263ee0`
- `0x263f00`

## string_xrefs

- `0x8d749`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x8d75a`: `http://schemas.microsoft.com/winfx/2006/xaml`

## pseudocode

```c

```

## disassembly

```asm
0x8d020  ldarg.0
0x8d021  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8d026  isinst   System.Windows.Markup.BamlKeyElementStartRecord
0x8d02b  stloc.0
0x8d02c  ldarg.0
0x8d02d  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8d032  ldloc.0
0x8d033  callvirt instance int16 System.Windows.Markup.BamlElementStartRecord::get_TypeId()
0x8d038  callvirt instance class System.Windows.Markup.BamlTypeInfoRecord System.Windows.Markup.BamlMapTable::GetTypeInfoFromId(int16 id)
0x8d03d  stloc.1
0x8d03e  ldloc.1
0x8d03f  callvirt instance string System.Windows.Markup.BamlTypeInfoRecord::get_TypeFullName()
0x8d044  stloc.2
0x8d045  ldloc.2
0x8d046  ldloc.2
0x8d047  ldstr    asc_28A756// "."
0x8d04c  ldc.i4.4
0x8d04d  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x8d052  ldc.i4.1
0x8d053  add
0x8d054  callvirt instance string [mscorlib]System.String::Substring(int32)
0x8d059  stloc.2
0x8d05a  ldarg.0
0x8d05b  ldloc.1
0x8d05c  ldloca.s 3
0x8d05e  ldloca.s 4
0x8d060  ldloca.s 5
0x8d062  call     instance void System.Windows.Markup.BamlReader::GetAssemblyAndPrefixAndXmlns(class System.Windows.Markup.BamlTypeInfoRecord typeInfo, [out] string& assemblyFullName, [out] string& prefix, [out] string& xmlns)
0x8d067  ldloc.s  4
0x8d069  ldsfld   string [mscorlib]System.String::Empty
0x8d06e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8d073  brfalse.s loc_8D0A4
0x8d075  ldc.i4.5
0x8d076  newarr   [mscorlib]System.String
0x8d07b  dup
0x8d07c  ldc.i4.0
0x8d07d  ldstr    asc_29CBA0// "{"
0x8d082  stelem.ref
0x8d083  dup
0x8d084  ldc.i4.1
0x8d085  ldloc.s  4
0x8d087  stelem.ref
0x8d088  dup
0x8d089  ldc.i4.2
0x8d08a  ldstr    asc_291A4E// ":"
0x8d08f  stelem.ref
0x8d090  dup
0x8d091  ldc.i4.3
0x8d092  ldloc.2
0x8d093  stelem.ref
0x8d094  dup
0x8d095  ldc.i4.4
0x8d096  ldstr    asc_28CAA8// " "
0x8d09b  stelem.ref
0x8d09c  call     string [mscorlib]System.String::Concat(string[])
0x8d0a1  stloc.2
0x8d0a2  br.s     loc_8D0B5
0x8d0a4  ldstr    asc_29CBA0// "{"
0x8d0a9  ldloc.2
0x8d0aa  ldstr    asc_28CAA8// " "
0x8d0af  call     string [mscorlib]System.String::Concat(string, string, string)
0x8d0b4  stloc.2
0x8d0b5  ldc.i4.1
0x8d0b6  stloc.s  6
0x8d0b8  newobj   instance void [mscorlib]System.Collections.Stack::.ctor()
0x8d0bd  stloc.s  8
0x8d0bf  newobj   instance void [mscorlib]System.Collections.Stack::.ctor()
0x8d0c4  stloc.s  9
0x8d0c6  newobj   instance void [mscorlib]System.Collections.Stack::.ctor()
0x8d0cb  stloc.s  0xA
0x8d0cd  ldloc.s  8
0x8d0cf  ldc.i4.0
0x8d0d0  box      [mscorlib]System.Boolean
0x8d0d5  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x8d0da  ldloc.s  9
0x8d0dc  ldc.i4.0
0x8d0dd  box      [mscorlib]System.Boolean
0x8d0e2  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x8d0e7  ldloc.s  0xA
0x8d0e9  ldc.i4.0
0x8d0ea  box      [mscorlib]System.Boolean
0x8d0ef  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x8d0f4  br       loc_8D71F
0x8d0f9  ldarg.0
0x8d0fa  ldfld    bool System.Windows.Markup.BamlReader::_haveUnprocessedRecord
0x8d0ff  brtrue.s loc_8D109
0x8d101  ldarg.0
0x8d102  call     instance void System.Windows.Markup.BamlReader::GetNextRecord()
0x8d107  br.s     loc_8D110
0x8d109  ldarg.0
0x8d10a  ldc.i4.0
0x8d10b  stfld    bool System.Windows.Markup.BamlReader::_haveUnprocessedRecord
0x8d110  ldarg.0
0x8d111  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8d116  callvirt instance valuetype System.Windows.Markup.BamlRecordType System.Windows.Markup.BamlRecord::get_RecordType()
0x8d11b  stloc.s  0x12
0x8d11d  ldloc.s  0x12
0x8d11f  ldc.i4.3
0x8d120  sub
0x8d121  switch   loc_8D2F9, loc_8D409, loc_8D4DE, loc_8D540, loc_8D212, loc_8D71F
0x8d13e  ldloc.s  0x12
0x8d140  ldc.i4.s 0x10
0x8d142  beq      loc_8D269
0x8d147  ldloc.s  0x12
0x8d149  ldc.i4.s 0x1C
0x8d14b  sub
0x8d14c  switch   loc_8D1B6, loc_8D1C1, loc_8D1C1, loc_8D1DC, loc_8D1F7, loc_8D58E, loc_8D5FB, loc_8D66C, loc_8D4DE, loc_8D6ED, loc_8D6ED, loc_8D6ED, loc_8D6ED, loc_8D6D5, loc_8D432, loc_8D44C, loc_8D47B, loc_8D6ED, loc_8D6ED, loc_8D6ED, loc_8D6ED, loc_8D6ED, loc_8D6ED, loc_8D269
0x8d1b1  br       loc_8D6ED
0x8d1b6  ldarg.0
0x8d1b7  call     instance void System.Windows.Markup.BamlReader::ReadAssemblyInfoRecord()
0x8d1bc  br       loc_8D71F
0x8d1c1  ldarg.0
0x8d1c2  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8d1c7  ldarg.0
0x8d1c8  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8d1cd  castclass System.Windows.Markup.BamlTypeInfoRecord
0x8d1d2  callvirt instance void System.Windows.Markup.BamlMapTable::LoadTypeInfoRecord(class System.Windows.Markup.BamlTypeInfoRecord record)
0x8d1d7  br       loc_8D71F
0x8d1dc  ldarg.0
0x8d1dd  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8d1e2  ldarg.0
0x8d1e3  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8d1e8  castclass System.Windows.Markup.BamlAttributeInfoRecord
0x8d1ed  callvirt instance void System.Windows.Markup.BamlMapTable::LoadAttributeInfoRecord(class System.Windows.Markup.BamlAttributeInfoRecord record)
0x8d1f2  br       loc_8D71F
0x8d1f7  ldarg.0
0x8d1f8  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8d1fd  ldarg.0
0x8d1fe  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8d203  castclass System.Windows.Markup.BamlStringInfoRecord
0x8d208  callvirt instance void System.Windows.Markup.BamlMapTable::LoadStringInfoRecord(class System.Windows.Markup.BamlStringInfoRecord record)
0x8d20d  br       loc_8D71F
0x8d212  ldarg.0
0x8d213  call     instance void System.Windows.Markup.BamlReader::ReadPropertyComplexStartRecord()
0x8d218  ldarg.0
0x8d219  ldfld    class [mscorlib]System.Collections.Stack System.Windows.Markup.BamlReader::_nodeStack
0x8d21e  callvirt instance object [mscorlib]System.Collections.Stack::Pop()
0x8d223  castclass BamlNodeInfo
0x8d228  stloc.s  7
0x8d22a  ldloc.s  8
0x8d22c  callvirt instance object [mscorlib]System.Collections.Stack::Pop()
0x8d231  unbox.any [mscorlib]System.Boolean
0x8d236  brfalse.s loc_8D244
0x8d238  ldloc.2
0x8d239  ldstr    asc_29CBD2// ", "
0x8d23e  call     string [mscorlib]System.String::Concat(string, string)
0x8d243  stloc.2
0x8d244  ldloc.2
0x8d245  ldloc.s  7
0x8d247  callvirt instance string BamlNodeInfo::get_LocalName()
0x8d24c  ldstr    asc_291ACA// "="
0x8d251  call     string [mscorlib]System.String::Concat(string, string, string)
0x8d256  stloc.2
0x8d257  ldloc.s  8
0x8d259  ldc.i4.1
0x8d25a  box      [mscorlib]System.Boolean
0x8d25f  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x8d264  br       loc_8D71F
0x8d269  ldarg.0
0x8d26a  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8d26f  isinst   System.Windows.Markup.BamlTextWithIdRecord
0x8d274  stloc.s  0xC
0x8d276  ldloc.s  0xC
0x8d278  brfalse.s loc_8D293
0x8d27a  ldloc.s  0xC
0x8d27c  ldarg.0
0x8d27d  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8d282  ldloc.s  0xC
0x8d284  callvirt instance int16 System.Windows.Markup.BamlTextWithIdRecord::get_ValueId()
0x8d289  callvirt instance string System.Windows.Markup.BamlMapTable::GetStringFromStringId(int32 id)
0x8d28e  callvirt instance void System.Windows.Markup.BamlStringValueRecord::set_Value(string value)
0x8d293  ldarg.0
0x8d294  ldarg.0
0x8d295  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8d29a  castclass System.Windows.Markup.BamlTextRecord
0x8d29f  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x8d2a4  call     instance string System.Windows.Markup.BamlReader::EscapeString(string value)
0x8d2a9  stloc.s  0xD
0x8d2ab  ldloc.s  0xA
0x8d2ad  callvirt instance object [mscorlib]System.Collections.Stack::Peek()
0x8d2b2  unbox.any [mscorlib]System.Boolean
0x8d2b7  brfalse.s loc_8D2C5
0x8d2b9  ldloc.2
0x8d2ba  ldstr    asc_29CBD2// ", "
0x8d2bf  call     string [mscorlib]System.String::Concat(string, string)
0x8d2c4  stloc.2
0x8d2c5  ldloc.2
0x8d2c6  ldloc.s  0xD
0x8d2c8  call     string [mscorlib]System.String::Concat(string, string)
0x8d2cd  stloc.2
0x8d2ce  ldloc.s  9
0x8d2d0  callvirt instance object [mscorlib]System.Collections.Stack::Peek()
0x8d2d5  unbox.any [mscorlib]System.Boolean
0x8d2da  brfalse  loc_8D71F
0x8d2df  ldloc.s  0xA
0x8d2e1  callvirt instance object [mscorlib]System.Collections.Stack::Pop()
0x8d2e6  pop
0x8d2e7  ldloc.s  0xA
0x8d2e9  ldc.i4.1
0x8d2ea  box      [mscorlib]System.Boolean
0x8d2ef  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x8d2f4  br       loc_8D71F
0x8d2f9  ldloc.s  0xA
0x8d2fb  callvirt instance object [mscorlib]System.Collections.Stack::Peek()
0x8d300  unbox.any [mscorlib]System.Boolean
0x8d305  brfalse.s loc_8D313
0x8d307  ldloc.2
0x8d308  ldstr    asc_29CBD2// ", "
0x8d30d  call     string [mscorlib]System.String::Concat(string, string)
0x8d312  stloc.2
0x8d313  ldloc.s  9
0x8d315  callvirt instance object [mscorlib]System.Collections.Stack::Peek()
0x8d31a  unbox.any [mscorlib]System.Boolean
0x8d31f  brfalse.s loc_8D336
0x8d321  ldloc.s  0xA
0x8d323  callvirt instance object [mscorlib]System.Collections.Stack::Pop()
0x8d328  pop
0x8d329  ldloc.s  0xA
0x8d32b  ldc.i4.1
0x8d32c  box      [mscorlib]System.Boolean
0x8d331  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x8d336  ldloc.s  8
0x8d338  ldc.i4.0
0x8d339  box      [mscorlib]System.Boolean
0x8d33e  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x8d343  ldloc.s  9
0x8d345  ldc.i4.0
0x8d346  box      [mscorlib]System.Boolean
0x8d34b  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x8d350  ldloc.s  0xA
0x8d352  ldc.i4.0
0x8d353  box      [mscorlib]System.Boolean
0x8d358  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x8d35d  ldarg.0
0x8d35e  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8d363  isinst   System.Windows.Markup.BamlElementStartRecord
0x8d368  stloc.s  0xE
0x8d36a  ldarg.0
0x8d36b  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8d370  ldloc.s  0xE
0x8d372  callvirt instance int16 System.Windows.Markup.BamlElementStartRecord::get_TypeId()
0x8d377  callvirt instance class System.Windows.Markup.BamlTypeInfoRecord System.Windows.Markup.BamlMapTable::GetTypeInfoFromId(int16 id)
0x8d37c  stloc.s  0xF
0x8d37e  ldloc.s  0xF
0x8d380  callvirt instance string System.Windows.Markup.BamlTypeInfoRecord::get_TypeFullName()
0x8d385  stloc.s  0x10
0x8d387  ldloc.s  0x10
0x8d389  ldloc.s  0x10
0x8d38b  ldstr    asc_28A756// "."
0x8d390  ldc.i4.4
0x8d391  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x8d396  ldc.i4.1
0x8d397  add
0x8d398  callvirt instance string [mscorlib]System.String::Substring(int32)
0x8d39d  stloc.s  0x10
0x8d39f  ldarg.0
0x8d3a0  ldloc.s  0xF
0x8d3a2  ldloca.s 3
0x8d3a4  ldloca.s 4
0x8d3a6  ldloca.s 5
0x8d3a8  call     instance void System.Windows.Markup.BamlReader::GetAssemblyAndPrefixAndXmlns(class System.Windows.Markup.BamlTypeInfoRecord typeInfo, [out] string& assemblyFullName, [out] string& prefix, [out] string& xmlns)
0x8d3ad  ldloc.s  4
0x8d3af  ldsfld   string [mscorlib]System.String::Empty
0x8d3b4  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8d3b9  brfalse.s loc_8D3F2
0x8d3bb  ldc.i4.6
0x8d3bc  newarr   [mscorlib]System.String
0x8d3c1  dup
0x8d3c2  ldc.i4.0
0x8d3c3  ldloc.2
0x8d3c4  stelem.ref
0x8d3c5  dup
0x8d3c6  ldc.i4.1
0x8d3c7  ldstr    asc_29CBA0// "{"
0x8d3cc  stelem.ref
0x8d3cd  dup
0x8d3ce  ldc.i4.2
0x8d3cf  ldloc.s  4
0x8d3d1  stelem.ref
0x8d3d2  dup
0x8d3d3  ldc.i4.3
0x8d3d4  ldstr    asc_291A4E// ":"
0x8d3d9  stelem.ref
0x8d3da  dup
0x8d3db  ldc.i4.4
0x8d3dc  ldloc.s  0x10
0x8d3de  stelem.ref
0x8d3df  dup
0x8d3e0  ldc.i4.5
0x8d3e1  ldstr    asc_28CAA8// " "
0x8d3e6  stelem.ref
0x8d3e7  call     string [mscorlib]System.String::Concat(string[])
0x8d3ec  stloc.2
0x8d3ed  br       loc_8D71F
0x8d3f2  ldstr    asc_29CBA0// "{"
0x8d3f7  ldloc.s  0x10
0x8d3f9  ldstr    asc_28CAA8// " "
0x8d3fe  call     string [mscorlib]System.String::Concat(string, string, string)
0x8d403  stloc.2
0x8d404  br       loc_8D71F
  ... truncated ...
```
