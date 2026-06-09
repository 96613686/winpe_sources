# System.Windows.Markup.BamlReader::InsertDeferedKey

- ea: `0x8e1a0`
- end: `0x8e269`
- name: `System.Windows.Markup.BamlReader::InsertDeferedKey`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x8db80`

## callees

- `0x8bd70`
- `0x8e1a0`
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
- `0x263e90`
- `0x263ea0`
- `0x263ef0`

## string_xrefs

- `0x8e1e6`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x8e1f6`: `http://schemas.microsoft.com/winfx/2006/xaml`

## pseudocode

```c

```

## disassembly

```asm
0x8e1a0  ldarg.0
0x8e1a1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8e1a6  brtrue.s loc_8E1A9
0x8e1a8  ret
0x8e1a9  ldarg.0
0x8e1aa  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8e1af  ldc.i4.0
0x8e1b0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::get_Item(!!T0)
0x8e1b5  stloc.0
0x8e1b6  br       loc_8E25C
0x8e1bb  ldarg.0
0x8e1bc  ldloc.0
0x8e1bd  stfld    class BamlKeyInfo System.Windows.Markup.BamlReader::_currentKeyInfo
0x8e1c2  newobj   instance void BamlPropertyInfo::.ctor()
0x8e1c7  stloc.1
0x8e1c8  ldloc.1
0x8e1c9  ldloc.0
0x8e1ca  callvirt instance string BamlPropertyInfo::get_Value()
0x8e1cf  callvirt instance void BamlPropertyInfo::set_Value(string value)
0x8e1d4  ldloc.1
0x8e1d5  ldsfld   string [mscorlib]System.String::Empty
0x8e1da  callvirt instance void BamlNodeInfo::set_AssemblyName(string value)
0x8e1df  ldloc.1
0x8e1e0  ldarg.0
0x8e1e1  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8e1e6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8e1eb  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8e1f0  callvirt instance void BamlNodeInfo::set_Prefix(string value)
0x8e1f5  ldloc.1
0x8e1f6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8e1fb  callvirt instance void BamlNodeInfo::set_XmlNamespace(string value)
0x8e200  ldloc.1
0x8e201  ldsfld   string [mscorlib]System.String::Empty
0x8e206  callvirt instance void BamlNodeInfo::set_ClrNamespace(string value)
0x8e20b  ldloc.1
0x8e20c  ldloc.0
0x8e20d  callvirt instance string BamlNodeInfo::get_Name()
0x8e212  callvirt instance void BamlNodeInfo::set_Name(string value)
0x8e217  ldloc.1
0x8e218  ldloc.1
0x8e219  callvirt instance string BamlNodeInfo::get_Name()
0x8e21e  callvirt instance void BamlNodeInfo::set_LocalName(string value)
0x8e223  ldloc.1
0x8e224  ldc.i4.s 0x19
0x8e226  callvirt instance void BamlNodeInfo::set_RecordType(valuetype System.Windows.Markup.BamlRecordType value)
0x8e22b  ldarg.0
0x8e22c  ldloc.1
0x8e22d  call     instance void System.Windows.Markup.BamlReader::AddToPropertyInfoCollection(object info)
0x8e232  ldarg.0
0x8e233  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8e238  ldc.i4.0
0x8e239  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::RemoveAt(int32)
0x8e23e  ldarg.0
0x8e23f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8e244  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::get_Count()
0x8e249  ldc.i4.0
0x8e24a  ble.s    loc_8E25B
0x8e24c  ldarg.0
0x8e24d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo> System.Windows.Markup.BamlReader::_deferKeys
0x8e252  ldc.i4.0
0x8e253  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class BamlKeyInfo>::get_Item(!!T0)
0x8e258  stloc.0
0x8e259  br.s     loc_8E25C
0x8e25b  ret
0x8e25c  ldloc.0
0x8e25d  callvirt instance int32 BamlKeyInfo::get_Offset()
0x8e262  ldarg.1
0x8e263  beq      loc_8E1BB
0x8e268  ret
```
