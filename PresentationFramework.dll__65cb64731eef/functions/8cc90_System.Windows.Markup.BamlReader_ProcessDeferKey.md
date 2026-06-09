# System.Windows.Markup.BamlReader::ProcessDeferKey

- ea: `0x8cc90`
- end: `0x8cf73`
- name: `System.Windows.Markup.BamlReader::ProcessDeferKey`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x8cc50`

## callees

- `0x8a810`
- `0x8aa60`
- `0x8cc90`
- `0x8cf80`
- `0x8d020`
- `0x8d7b0`
- `0x8e810`
- `0x8e9f0`
- `0x96340`
- `0x963c0`
- `0x969a0`
- `0x969b0`
- `0x969f0`
- `0x96fa0`
- `0x985d0`
- `0x99580`
- `0xb4030`
- `0x263d80`
- `0x263da0`
- `0x263dc0`
- `0x263de0`
- `0x263e00`
- `0x263e10`
- `0x263e20`
- `0x263e40`
- `0x263ea0`
- `0x263ee0`
- `0x263f00`
- `0x263f10`

## string_xrefs

- `0x8cd29`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x8cd39`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x8cd9e`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x8ce89`: `http://schemas.microsoft.com/winfx/2006/xaml`

## pseudocode

```c

```

## disassembly

```asm
0x8cc90  ldarg.0
0x8cc91  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8cc96  callvirt instance valuetype System.Windows.Markup.BamlRecordType System.Windows.Markup.BamlRecord::get_RecordType()
0x8cc9b  stloc.2
0x8cc9c  ldloc.2
0x8cc9d  ldc.i4.s 0x26
0x8cc9f  sub
0x8cca0  switch   loc_8CCC6, loc_8CD86, loc_8CEDD
0x8ccb1  ldloc.2
0x8ccb2  ldc.i4.s 0x30
0x8ccb4  beq      loc_8CF0C
0x8ccb9  ldloc.2
0x8ccba  ldc.i4.s 0x37
0x8ccbc  beq      loc_8CF0C
0x8ccc1  br       loc_8CF6B
0x8ccc6  ldarg.0
0x8ccc7  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8cccc  isinst   System.Windows.Markup.BamlDefAttributeKeyStringRecord
0x8ccd1  stloc.0
0x8ccd2  ldloc.0
0x8ccd3  brfalse  loc_8CF72
0x8ccd8  ldarg.0
0x8ccd9  call     instance class BamlKeyInfo System.Windows.Markup.BamlReader::CheckForSharedness()
0x8ccde  stloc.3
0x8ccdf  ldloc.3
0x8cce0  brfalse.s loc_8CCEE
0x8cce2  ldarg.0
0x8cce3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8cce8  ldloc.3
0x8cce9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::Add(var<u1>)
0x8ccee  ldloc.0
0x8ccef  ldarg.0
0x8ccf0  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8ccf5  ldloc.0
0x8ccf6  callvirt instance int16 System.Windows.Markup.BamlDefAttributeKeyStringRecord::get_ValueId()
0x8ccfb  callvirt instance string System.Windows.Markup.BamlMapTable::GetStringFromStringId(int32 id)
0x8cd00  callvirt instance void System.Windows.Markup.BamlStringValueRecord::set_Value(string value)
0x8cd05  newobj   instance void BamlKeyInfo::.ctor()
0x8cd0a  stloc.3
0x8cd0b  ldloc.3
0x8cd0c  ldloc.0
0x8cd0d  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x8cd12  callvirt instance void BamlPropertyInfo::set_Value(string value)
0x8cd17  ldloc.3
0x8cd18  ldsfld   string [mscorlib]System.String::Empty
0x8cd1d  callvirt instance void BamlNodeInfo::set_AssemblyName(string value)
0x8cd22  ldloc.3
0x8cd23  ldarg.0
0x8cd24  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8cd29  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8cd2e  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8cd33  callvirt instance void BamlNodeInfo::set_Prefix(string value)
0x8cd38  ldloc.3
0x8cd39  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8cd3e  callvirt instance void BamlNodeInfo::set_XmlNamespace(string value)
0x8cd43  ldloc.3
0x8cd44  ldsfld   string [mscorlib]System.String::Empty
0x8cd49  callvirt instance void BamlNodeInfo::set_ClrNamespace(string value)
0x8cd4e  ldloc.3
0x8cd4f  ldstr    aKey// "Key"
0x8cd54  callvirt instance void BamlNodeInfo::set_Name(string value)
0x8cd59  ldloc.3
0x8cd5a  ldloc.3
0x8cd5b  callvirt instance string BamlNodeInfo::get_Name()
0x8cd60  callvirt instance void BamlNodeInfo::set_LocalName(string value)
0x8cd65  ldloc.3
0x8cd66  ldc.i4.s 0x19
0x8cd68  callvirt instance void BamlNodeInfo::set_RecordType(valuetype System.Windows.Markup.BamlRecordType value)
0x8cd6d  ldloc.3
0x8cd6e  ldloc.0
0x8cd6f  callvirt instance int32 System.Windows.Markup.IBamlDictionaryKey::get_ValuePosition()
0x8cd74  callvirt instance void BamlKeyInfo::set_Offset(int32 value)
0x8cd79  ldarg.0
0x8cd7a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8cd7f  ldloc.3
0x8cd80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::Add(var<u1>)
0x8cd85  ret
0x8cd86  ldarg.0
0x8cd87  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8cd8c  isinst   System.Windows.Markup.BamlDefAttributeKeyTypeRecord
0x8cd91  stloc.1
0x8cd92  ldloc.1
0x8cd93  brfalse  loc_8CF72
0x8cd98  ldarg.0
0x8cd99  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8cd9e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8cda3  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8cda8  stloc.s  4
0x8cdaa  ldloc.s  4
0x8cdac  ldsfld   string [mscorlib]System.String::Empty
0x8cdb1  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8cdb6  brfalse.s loc_8CDCD
0x8cdb8  ldstr    asc_29CBA0// "{"
0x8cdbd  ldloc.s  4
0x8cdbf  ldstr    aType_1// ":Type "
0x8cdc4  call     string [mscorlib]System.String::Concat(string, string, string)
0x8cdc9  stloc.s  5
0x8cdcb  br.s     loc_8CDD4
0x8cdcd  ldstr    aType_2// "{Type "
0x8cdd2  stloc.s  5
0x8cdd4  ldarg.0
0x8cdd5  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8cdda  ldloc.1
0x8cddb  callvirt instance int16 System.Windows.Markup.BamlElementStartRecord::get_TypeId()
0x8cde0  callvirt instance class System.Windows.Markup.BamlTypeInfoRecord System.Windows.Markup.BamlMapTable::GetTypeInfoFromId(int16 id)
0x8cde5  stloc.s  6
0x8cde7  ldloc.s  6
0x8cde9  callvirt instance string System.Windows.Markup.BamlTypeInfoRecord::get_TypeFullName()
0x8cdee  stloc.s  7
0x8cdf0  ldloc.s  7
0x8cdf2  ldloc.s  7
0x8cdf4  ldstr    asc_28A756// "."
0x8cdf9  ldc.i4.4
0x8cdfa  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x8cdff  ldc.i4.1
0x8ce00  add
0x8ce01  callvirt instance string [mscorlib]System.String::Substring(int32)
0x8ce06  stloc.s  7
0x8ce08  ldarg.0
0x8ce09  ldloc.s  6
0x8ce0b  ldloca.s 8
0x8ce0d  ldloca.s 9
0x8ce0f  ldloca.s 0xA
0x8ce11  call     instance void System.Windows.Markup.BamlReader::GetAssemblyAndPrefixAndXmlns(class System.Windows.Markup.BamlTypeInfoRecord typeInfo, [out] string& assemblyFullName, [out] string& prefix, [out] string& xmlns)
0x8ce16  ldloc.s  9
0x8ce18  ldsfld   string [mscorlib]System.String::Empty
0x8ce1d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8ce22  brfalse.s loc_8CE52
0x8ce24  ldc.i4.5
0x8ce25  newarr   [mscorlib]System.String
0x8ce2a  dup
0x8ce2b  ldc.i4.0
0x8ce2c  ldloc.s  5
0x8ce2e  stelem.ref
0x8ce2f  dup
0x8ce30  ldc.i4.1
0x8ce31  ldloc.s  9
0x8ce33  stelem.ref
0x8ce34  dup
0x8ce35  ldc.i4.2
0x8ce36  ldstr    asc_291A4E// ":"
0x8ce3b  stelem.ref
0x8ce3c  dup
0x8ce3d  ldc.i4.3
0x8ce3e  ldloc.s  7
0x8ce40  stelem.ref
0x8ce41  dup
0x8ce42  ldc.i4.4
0x8ce43  ldstr    asc_29CBC0// "}"
0x8ce48  stelem.ref
0x8ce49  call     string [mscorlib]System.String::Concat(string[])
0x8ce4e  stloc.s  7
0x8ce50  br.s     loc_8CE62
0x8ce52  ldloc.s  5
0x8ce54  ldloc.s  7
0x8ce56  ldstr    asc_29CBC0// "}"
0x8ce5b  call     string [mscorlib]System.String::Concat(string, string, string)
0x8ce60  stloc.s  7
0x8ce62  newobj   instance void BamlKeyInfo::.ctor()
0x8ce67  stloc.s  0xB
0x8ce69  ldloc.s  0xB
0x8ce6b  ldloc.s  7
0x8ce6d  callvirt instance void BamlPropertyInfo::set_Value(string value)
0x8ce72  ldloc.s  0xB
0x8ce74  ldsfld   string [mscorlib]System.String::Empty
0x8ce79  callvirt instance void BamlNodeInfo::set_AssemblyName(string value)
0x8ce7e  ldloc.s  0xB
0x8ce80  ldloc.s  4
0x8ce82  callvirt instance void BamlNodeInfo::set_Prefix(string value)
0x8ce87  ldloc.s  0xB
0x8ce89  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8ce8e  callvirt instance void BamlNodeInfo::set_XmlNamespace(string value)
0x8ce93  ldloc.s  0xB
0x8ce95  ldsfld   string [mscorlib]System.String::Empty
0x8ce9a  callvirt instance void BamlNodeInfo::set_ClrNamespace(string value)
0x8ce9f  ldloc.s  0xB
0x8cea1  ldstr    aKey// "Key"
0x8cea6  callvirt instance void BamlNodeInfo::set_Name(string value)
0x8ceab  ldloc.s  0xB
0x8cead  ldloc.s  0xB
0x8ceaf  callvirt instance string BamlNodeInfo::get_Name()
0x8ceb4  callvirt instance void BamlNodeInfo::set_LocalName(string value)
0x8ceb9  ldloc.s  0xB
0x8cebb  ldc.i4.s 0x19
0x8cebd  callvirt instance void BamlNodeInfo::set_RecordType(valuetype System.Windows.Markup.BamlRecordType value)
0x8cec2  ldloc.s  0xB
0x8cec4  ldloc.1
0x8cec5  callvirt instance int32 System.Windows.Markup.IBamlDictionaryKey::get_ValuePosition()
0x8ceca  callvirt instance void BamlKeyInfo::set_Offset(int32 value)
0x8cecf  ldarg.0
0x8ced0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8ced5  ldloc.s  0xB
0x8ced7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::Add(var<u1>)
0x8cedc  ret
0x8cedd  ldarg.0
0x8cede  call     instance class BamlKeyInfo System.Windows.Markup.BamlReader::CheckForSharedness()
0x8cee3  stloc.s  0xC
0x8cee5  ldloc.s  0xC
0x8cee7  brfalse.s loc_8CEF6
0x8cee9  ldarg.0
0x8ceea  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8ceef  ldloc.s  0xC
0x8cef1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::Add(var<u1>)
0x8cef6  ldarg.0
0x8cef7  call     instance class BamlKeyInfo System.Windows.Markup.BamlReader::ProcessKeyTree()
0x8cefc  stloc.s  0xC
0x8cefe  ldarg.0
0x8ceff  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8cf04  ldloc.s  0xC
0x8cf06  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::Add(var<u1>)
0x8cf0b  ret
0x8cf0c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Markup.BamlRecord>::.ctor()
0x8cf11  stloc.s  0xD
0x8cf13  ldarg.0
0x8cf14  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8cf19  callvirt instance void System.Windows.Markup.BamlRecord::Pin()
0x8cf1e  ldloc.s  0xD
0x8cf20  ldarg.0
0x8cf21  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8cf26  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Markup.BamlRecord>::Add(var<u1>)
0x8cf2b  ldarg.0
0x8cf2c  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8cf31  callvirt instance valuetype System.Windows.Markup.BamlRecordType System.Windows.Markup.BamlRecord::get_RecordType()
0x8cf36  ldc.i4.s 0x30
0x8cf38  bne.un.s loc_8CF42
0x8cf3a  ldarg.0
0x8cf3b  ldloc.s  0xD
0x8cf3d  call     instance void System.Windows.Markup.BamlReader::ProcessStaticResourceTree(class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Markup.BamlRecord> srRecords)
0x8cf42  ldarg.0
0x8cf43  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8cf48  ldarg.0
0x8cf49  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8cf4e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::get_Count()
0x8cf53  ldc.i4.1
0x8cf54  sub
0x8cf55  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::get_Item(!!T0)
0x8cf5a  stloc.s  0xE
0x8cf5c  ldloc.s  0xE
0x8cf5e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Markup.BamlRecord>> BamlKeyInfo::get_StaticResources()
0x8cf63  ldloc.s  0xD
0x8cf65  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Markup.BamlRecord>>::Add(var<u1>)
0x8cf6a  ret
0x8cf6b  ldarg.0
0x8cf6c  ldc.i4.1
0x8cf6d  stfld    bool System.Windows.Markup.BamlReader::_haveUnprocessedRecord
0x8cf72  ret
```
