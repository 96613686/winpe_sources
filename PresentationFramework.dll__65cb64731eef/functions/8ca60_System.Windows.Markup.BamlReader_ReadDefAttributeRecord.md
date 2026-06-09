# System.Windows.Markup.BamlReader::ReadDefAttributeRecord

- ea: `0x8ca60`
- end: `0x8caf4`
- name: `System.Windows.Markup.BamlReader::ReadDefAttributeRecord`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x8c340`

## callees

- `0x8aa60`
- `0x8bd70`
- `0x8e9f0`
- `0x969a0`
- `0x970b0`
- `0x970d0`
- `0x970e0`
- `0xb4030`
- `0x263d80`
- `0x263da0`
- `0x263dc0`
- `0x263de0`
- `0x263e00`
- `0x263e10`
- `0x263e20`
- `0x263e40`
- `0x263e80`
- `0x263ea0`

## string_xrefs

- `0x8caa7`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x8cab7`: `http://schemas.microsoft.com/winfx/2006/xaml`

## pseudocode

```c

```

## disassembly

```asm
0x8ca60  ldarg.0
0x8ca61  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8ca66  castclass System.Windows.Markup.BamlDefAttributeRecord
0x8ca6b  stloc.0
0x8ca6c  ldloc.0
0x8ca6d  ldarg.0
0x8ca6e  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8ca73  ldloc.0
0x8ca74  callvirt instance int16 System.Windows.Markup.BamlDefAttributeRecord::get_NameId()
0x8ca79  callvirt instance string System.Windows.Markup.BamlMapTable::GetStringFromStringId(int32 id)
0x8ca7e  callvirt instance void System.Windows.Markup.BamlDefAttributeRecord::set_Name(string value)
0x8ca83  newobj   instance void BamlPropertyInfo::.ctor()
0x8ca88  stloc.1
0x8ca89  ldloc.1
0x8ca8a  ldloc.0
0x8ca8b  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x8ca90  callvirt instance void BamlPropertyInfo::set_Value(string value)
0x8ca95  ldloc.1
0x8ca96  ldsfld   string [mscorlib]System.String::Empty
0x8ca9b  callvirt instance void BamlNodeInfo::set_AssemblyName(string value)
0x8caa0  ldloc.1
0x8caa1  ldarg.0
0x8caa2  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8caa7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8caac  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8cab1  callvirt instance void BamlNodeInfo::set_Prefix(string value)
0x8cab6  ldloc.1
0x8cab7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8cabc  callvirt instance void BamlNodeInfo::set_XmlNamespace(string value)
0x8cac1  ldloc.1
0x8cac2  ldsfld   string [mscorlib]System.String::Empty
0x8cac7  callvirt instance void BamlNodeInfo::set_ClrNamespace(string value)
0x8cacc  ldloc.1
0x8cacd  ldloc.0
0x8cace  callvirt instance string System.Windows.Markup.BamlDefAttributeRecord::get_Name()
0x8cad3  callvirt instance void BamlNodeInfo::set_Name(string value)
0x8cad8  ldloc.1
0x8cad9  ldloc.1
0x8cada  callvirt instance string BamlNodeInfo::get_Name()
0x8cadf  callvirt instance void BamlNodeInfo::set_LocalName(string value)
0x8cae4  ldloc.1
0x8cae5  ldc.i4.s 0x19
0x8cae7  callvirt instance void BamlNodeInfo::set_RecordType(valuetype System.Windows.Markup.BamlRecordType value)
0x8caec  ldarg.0
0x8caed  ldloc.1
0x8caee  call     instance void System.Windows.Markup.BamlReader::AddToPropertyInfoCollection(object info)
0x8caf3  ret
```
