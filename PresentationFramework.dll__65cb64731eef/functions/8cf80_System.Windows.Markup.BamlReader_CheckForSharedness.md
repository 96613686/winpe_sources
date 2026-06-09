# System.Windows.Markup.BamlReader::CheckForSharedness

- ea: `0x8cf80`
- end: `0x8d014`
- name: `System.Windows.Markup.BamlReader::CheckForSharedness`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x8cc90`

## callees

- `0x8cf80`
- `0x969f0`
- `0x96a50`
- `0x96a70`
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

## string_xrefs

- `0x8cfc2`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x8cfd2`: `http://schemas.microsoft.com/winfx/2006/xaml`

## pseudocode

```c

```

## disassembly

```asm
0x8cf80  ldarg.0
0x8cf81  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8cf86  castclass System.Windows.Markup.IBamlDictionaryKey
0x8cf8b  stloc.0
0x8cf8c  ldloc.0
0x8cf8d  callvirt instance bool System.Windows.Markup.IBamlDictionaryKey::get_SharedSet()
0x8cf92  brtrue.s loc_8CF96
0x8cf94  ldnull
0x8cf95  ret
0x8cf96  newobj   instance void BamlKeyInfo::.ctor()
0x8cf9b  stloc.1
0x8cf9c  ldloc.1
0x8cf9d  ldloc.0
0x8cf9e  callvirt instance bool System.Windows.Markup.IBamlDictionaryKey::get_Shared()
0x8cfa3  stloc.2
0x8cfa4  ldloca.s 2
0x8cfa6  call     instance string [mscorlib]System.Boolean::ToString()
0x8cfab  callvirt instance void BamlPropertyInfo::set_Value(string value)
0x8cfb0  ldloc.1
0x8cfb1  ldsfld   string [mscorlib]System.String::Empty
0x8cfb6  callvirt instance void BamlNodeInfo::set_AssemblyName(string value)
0x8cfbb  ldloc.1
0x8cfbc  ldarg.0
0x8cfbd  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8cfc2  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8cfc7  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8cfcc  callvirt instance void BamlNodeInfo::set_Prefix(string value)
0x8cfd1  ldloc.1
0x8cfd2  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8cfd7  callvirt instance void BamlNodeInfo::set_XmlNamespace(string value)
0x8cfdc  ldloc.1
0x8cfdd  ldsfld   string [mscorlib]System.String::Empty
0x8cfe2  callvirt instance void BamlNodeInfo::set_ClrNamespace(string value)
0x8cfe7  ldloc.1
0x8cfe8  ldstr    aShared// "Shared"
0x8cfed  callvirt instance void BamlNodeInfo::set_Name(string value)
0x8cff2  ldloc.1
0x8cff3  ldloc.1
0x8cff4  callvirt instance string BamlNodeInfo::get_Name()
0x8cff9  callvirt instance void BamlNodeInfo::set_LocalName(string value)
0x8cffe  ldloc.1
0x8cfff  ldc.i4.s 0x19
0x8d001  callvirt instance void BamlNodeInfo::set_RecordType(valuetype System.Windows.Markup.BamlRecordType value)
0x8d006  ldloc.1
0x8d007  ldloc.0
0x8d008  callvirt instance int32 System.Windows.Markup.IBamlDictionaryKey::get_ValuePosition()
0x8d00d  callvirt instance void BamlKeyInfo::set_Offset(int32 value)
0x8d012  ldloc.1
0x8d013  ret
```
