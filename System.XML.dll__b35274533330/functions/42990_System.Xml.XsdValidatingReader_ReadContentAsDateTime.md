# System.Xml.XsdValidatingReader::ReadContentAsDateTime

- ea: `0x42990`
- end: `0x42a27`
- name: `System.Xml.XsdValidatingReader::ReadContentAsDateTime`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22910`
- `0x22a30`
- `0x42990`
- `0x43f60`
- `0x43f70`
- `0x44730`
- `0xd6c00`
- `0xdb530`

## string_xrefs

- `0x429e9`: `Xml_ReadContentAsFormatException`
- `0x429fd`: `Xml_ReadContentAsFormatException`
- `0x42a12`: `Xml_ReadContentAsFormatException`
- `0x4299e`: `ReadContentAsDateTime`

## pseudocode

```c

```

## disassembly

```asm
0x42990  ldarg.0
0x42991  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42996  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x4299b  brtrue.s loc_429A9
0x4299d  ldarg.0
0x4299e  ldstr    aReadcontentasd// "ReadContentAsDateTime"
0x429a3  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x429a8  throw
0x429a9  ldarg.0
0x429aa  call     instance object System.Xml.XsdValidatingReader::InternalReadContentAsObject()
0x429af  stloc.0
0x429b0  ldarg.0
0x429b1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x429b6  ldc.i4.2
0x429b7  beq.s    loc_429C1
0x429b9  ldarg.0
0x429ba  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x429bf  br.s     loc_429C7
0x429c1  ldarg.0
0x429c2  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x429c7  stloc.1
0x429c8  ldloc.1
0x429c9  brfalse.s loc_429DA
0x429cb  ldloc.1
0x429cc  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x429d1  ldloc.0
0x429d2  callvirt instance valuetype [mscorlib]System.DateTime System.Xml.Schema.XmlValueConverter::ToDateTime(object value)
0x429d7  stloc.2
0x429d8  leave.s  loc_42A25
0x429da  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x429df  ldloc.0
0x429e0  callvirt instance valuetype [mscorlib]System.DateTime System.Xml.Schema.XmlValueConverter::ToDateTime(object value)
0x429e5  stloc.2
0x429e6  leave.s  loc_42A25
0x429e8  stloc.3
0x429e9  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x429ee  ldstr    aDatetime// "DateTime"
0x429f3  ldloc.3
0x429f4  ldarg.0
0x429f5  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x429fa  throw
0x429fb  stloc.s  4
0x429fd  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42a02  ldstr    aDatetime// "DateTime"
0x42a07  ldloc.s  4
0x42a09  ldarg.0
0x42a0a  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42a0f  throw
0x42a10  stloc.s  5
0x42a12  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42a17  ldstr    aDatetime// "DateTime"
0x42a1c  ldloc.s  5
0x42a1e  ldarg.0
0x42a1f  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42a24  throw
0x42a25  ldloc.2
0x42a26  ret
```
