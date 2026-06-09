# System.Windows.Markup.BamlReader::ReadDefAttributeKeyTypeRecord

- ea: `0x8cba0`
- end: `0x8cc22`
- name: `System.Windows.Markup.BamlReader::ReadDefAttributeKeyTypeRecord`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x8c340`

## callees

- `0x8bd70`
- `0x8e760`
- `0x985d0`
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

- `0x8cbd6`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x8cbe6`: `http://schemas.microsoft.com/winfx/2006/xaml`

## pseudocode

```c

```

## disassembly

```asm
0x8cba0  ldarg.0
0x8cba1  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8cba6  castclass System.Windows.Markup.BamlDefAttributeKeyTypeRecord
0x8cbab  stloc.0
0x8cbac  newobj   instance void BamlPropertyInfo::.ctor()
0x8cbb1  stloc.1
0x8cbb2  ldloc.1
0x8cbb3  ldarg.0
0x8cbb4  ldloc.0
0x8cbb5  callvirt instance int16 System.Windows.Markup.BamlElementStartRecord::get_TypeId()
0x8cbba  call     instance string System.Windows.Markup.BamlReader::GetTypeValueString(int16 typeId)
0x8cbbf  callvirt instance void BamlPropertyInfo::set_Value(string value)
0x8cbc4  ldloc.1
0x8cbc5  ldsfld   string [mscorlib]System.String::Empty
0x8cbca  callvirt instance void BamlNodeInfo::set_AssemblyName(string value)
0x8cbcf  ldloc.1
0x8cbd0  ldarg.0
0x8cbd1  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8cbd6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8cbdb  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8cbe0  callvirt instance void BamlNodeInfo::set_Prefix(string value)
0x8cbe5  ldloc.1
0x8cbe6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8cbeb  callvirt instance void BamlNodeInfo::set_XmlNamespace(string value)
0x8cbf0  ldloc.1
0x8cbf1  ldsfld   string [mscorlib]System.String::Empty
0x8cbf6  callvirt instance void BamlNodeInfo::set_ClrNamespace(string value)
0x8cbfb  ldloc.1
0x8cbfc  ldstr    aKey// "Key"
0x8cc01  callvirt instance void BamlNodeInfo::set_Name(string value)
0x8cc06  ldloc.1
0x8cc07  ldloc.1
0x8cc08  callvirt instance string BamlNodeInfo::get_Name()
0x8cc0d  callvirt instance void BamlNodeInfo::set_LocalName(string value)
0x8cc12  ldloc.1
0x8cc13  ldc.i4.s 0x19
0x8cc15  callvirt instance void BamlNodeInfo::set_RecordType(valuetype System.Windows.Markup.BamlRecordType value)
0x8cc1a  ldarg.0
0x8cc1b  ldloc.1
0x8cc1c  call     instance void System.Windows.Markup.BamlReader::AddToPropertyInfoCollection(object info)
0x8cc21  ret
```
