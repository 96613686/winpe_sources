# System.Windows.Markup.BamlReader::ReadPresentationOptionsAttributeRecord

- ea: `0x8cb00`
- end: `0x8cb94`
- name: `System.Windows.Markup.BamlReader::ReadPresentationOptionsAttributeRecord`
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
- `0x97200`
- `0x97220`
- `0x97230`
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

- `0x8cb47`: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`
- `0x8cb57`: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`

## pseudocode

```c

```

## disassembly

```asm
0x8cb00  ldarg.0
0x8cb01  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8cb06  castclass System.Windows.Markup.BamlPresentationOptionsAttributeRecord
0x8cb0b  stloc.0
0x8cb0c  ldloc.0
0x8cb0d  ldarg.0
0x8cb0e  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8cb13  ldloc.0
0x8cb14  callvirt instance int16 System.Windows.Markup.BamlPresentationOptionsAttributeRecord::get_NameId()
0x8cb19  callvirt instance string System.Windows.Markup.BamlMapTable::GetStringFromStringId(int32 id)
0x8cb1e  callvirt instance void System.Windows.Markup.BamlPresentationOptionsAttributeRecord::set_Name(string value)
0x8cb23  newobj   instance void BamlPropertyInfo::.ctor()
0x8cb28  stloc.1
0x8cb29  ldloc.1
0x8cb2a  ldloc.0
0x8cb2b  callvirt instance string System.Windows.Markup.BamlStringValueRecord::get_Value()
0x8cb30  callvirt instance void BamlPropertyInfo::set_Value(string value)
0x8cb35  ldloc.1
0x8cb36  ldsfld   string [mscorlib]System.String::Empty
0x8cb3b  callvirt instance void BamlNodeInfo::set_AssemblyName(string value)
0x8cb40  ldloc.1
0x8cb41  ldarg.0
0x8cb42  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8cb47  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/winfx/2006"...
0x8cb4c  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8cb51  callvirt instance void BamlNodeInfo::set_Prefix(string value)
0x8cb56  ldloc.1
0x8cb57  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/winfx/2006"...
0x8cb5c  callvirt instance void BamlNodeInfo::set_XmlNamespace(string value)
0x8cb61  ldloc.1
0x8cb62  ldsfld   string [mscorlib]System.String::Empty
0x8cb67  callvirt instance void BamlNodeInfo::set_ClrNamespace(string value)
0x8cb6c  ldloc.1
0x8cb6d  ldloc.0
0x8cb6e  callvirt instance string System.Windows.Markup.BamlPresentationOptionsAttributeRecord::get_Name()
0x8cb73  callvirt instance void BamlNodeInfo::set_Name(string value)
0x8cb78  ldloc.1
0x8cb79  ldloc.1
0x8cb7a  callvirt instance string BamlNodeInfo::get_Name()
0x8cb7f  callvirt instance void BamlNodeInfo::set_LocalName(string value)
0x8cb84  ldloc.1
0x8cb85  ldc.i4.s 0x34
0x8cb87  callvirt instance void BamlNodeInfo::set_RecordType(valuetype System.Windows.Markup.BamlRecordType value)
0x8cb8c  ldarg.0
0x8cb8d  ldloc.1
0x8cb8e  call     instance void System.Windows.Markup.BamlReader::AddToPropertyInfoCollection(object info)
0x8cb93  ret
```
