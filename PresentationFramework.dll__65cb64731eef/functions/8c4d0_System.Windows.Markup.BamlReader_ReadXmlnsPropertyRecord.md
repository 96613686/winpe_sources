# System.Windows.Markup.BamlReader::ReadXmlnsPropertyRecord

- ea: `0x8c4d0`
- end: `0x8c5af`
- name: `System.Windows.Markup.BamlReader::ReadXmlnsPropertyRecord`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x8c340`

## callees

- `0x8bd70`
- `0x8c4d0`
- `0x96730`
- `0x96750`
- `0xad120`
- `0xb4040`
- `0x263d80`
- `0x263da0`
- `0x263dc0`
- `0x263de0`
- `0x263e00`
- `0x263e20`
- `0x263e40`
- `0x263e80`
- `0x263ea0`

## string_xrefs

- `0x8c543`: `xmlns`
- `0x8c595`: `xmlns`
- `0x8c583`: `xmlns:`

## pseudocode

```c

```

## disassembly

```asm
0x8c4d0  ldarg.0
0x8c4d1  ldfld    class System.Windows.Markup.BamlRecord System.Windows.Markup.BamlReader::_currentBamlRecord
0x8c4d6  castclass System.Windows.Markup.BamlXmlnsPropertyRecord
0x8c4db  stloc.0
0x8c4dc  ldarg.0
0x8c4dd  ldfld    class System.Windows.Markup.ParserContext System.Windows.Markup.BamlReader::_parserContext
0x8c4e2  callvirt instance class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.ParserContext::get_XmlnsDictionary()
0x8c4e7  ldloc.0
0x8c4e8  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_Prefix()
0x8c4ed  ldloc.0
0x8c4ee  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_XmlNamespace()
0x8c4f3  callvirt instance void System.Windows.Markup.XmlnsDictionary::set_Item(string prefix, string value)
0x8c4f8  ldarg.0
0x8c4f9  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8c4fe  ldloc.0
0x8c4ff  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_XmlNamespace()
0x8c504  ldloc.0
0x8c505  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_Prefix()
0x8c50a  callvirt instance void System.Windows.Markup.XmlnsDictionary::set_Item(string prefix, string value)
0x8c50f  newobj   instance void BamlPropertyInfo::.ctor()
0x8c514  stloc.1
0x8c515  ldloc.1
0x8c516  ldloc.0
0x8c517  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_XmlNamespace()
0x8c51c  callvirt instance void BamlPropertyInfo::set_Value(string value)
0x8c521  ldloc.1
0x8c522  ldsfld   string [mscorlib]System.String::Empty
0x8c527  callvirt instance void BamlNodeInfo::set_XmlNamespace(string value)
0x8c52c  ldloc.1
0x8c52d  ldsfld   string [mscorlib]System.String::Empty
0x8c532  callvirt instance void BamlNodeInfo::set_ClrNamespace(string value)
0x8c537  ldloc.1
0x8c538  ldsfld   string [mscorlib]System.String::Empty
0x8c53d  callvirt instance void BamlNodeInfo::set_AssemblyName(string value)
0x8c542  ldloc.1
0x8c543  ldstr    aXmlns// "xmlns"
0x8c548  callvirt instance void BamlNodeInfo::set_Prefix(string value)
0x8c54d  ldloc.1
0x8c54e  ldloc.0
0x8c54f  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_Prefix()
0x8c554  brfalse.s loc_8C55E
0x8c556  ldloc.0
0x8c557  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_Prefix()
0x8c55c  br.s     loc_8C563
0x8c55e  ldsfld   string [mscorlib]System.String::Empty
0x8c563  callvirt instance void BamlNodeInfo::set_LocalName(string value)
0x8c568  ldloc.1
0x8c569  ldloc.0
0x8c56a  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_Prefix()
0x8c56f  brfalse.s loc_8C595
0x8c571  ldloc.0
0x8c572  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_Prefix()
0x8c577  ldsfld   string [mscorlib]System.String::Empty
0x8c57c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8c581  brtrue.s loc_8C595
0x8c583  ldstr    aXmlns_0// "xmlns:"
0x8c588  ldloc.0
0x8c589  callvirt instance string System.Windows.Markup.BamlXmlnsPropertyRecord::get_Prefix()
0x8c58e  call     string [mscorlib]System.String::Concat(string, string)
0x8c593  br.s     loc_8C59A
0x8c595  ldstr    aXmlns// "xmlns"
0x8c59a  callvirt instance void BamlNodeInfo::set_Name(string value)
0x8c59f  ldloc.1
0x8c5a0  ldc.i4.s 0x14
0x8c5a2  callvirt instance void BamlNodeInfo::set_RecordType(valuetype System.Windows.Markup.BamlRecordType value)
0x8c5a7  ldarg.0
0x8c5a8  ldloc.1
0x8c5a9  call     instance void System.Windows.Markup.BamlReader::AddToPropertyInfoCollection(object info)
0x8c5ae  ret
```
