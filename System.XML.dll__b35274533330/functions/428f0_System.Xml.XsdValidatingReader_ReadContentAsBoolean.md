# System.Xml.XsdValidatingReader::ReadContentAsBoolean

- ea: `0x428f0`
- end: `0x42987`
- name: `System.Xml.XsdValidatingReader::ReadContentAsBoolean`
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
- `0x428f0`
- `0x43f60`
- `0x43f70`
- `0x44730`
- `0xd6c00`
- `0xdb170`

## string_xrefs

- `0x428fe`: `ReadContentAsBoolean`
- `0x42949`: `Xml_ReadContentAsFormatException`
- `0x4295d`: `Xml_ReadContentAsFormatException`
- `0x42972`: `Xml_ReadContentAsFormatException`

## pseudocode

```c

```

## disassembly

```asm
0x428f0  ldarg.0
0x428f1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x428f6  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x428fb  brtrue.s loc_42909
0x428fd  ldarg.0
0x428fe  ldstr    aReadcontentasb_1// "ReadContentAsBoolean"
0x42903  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x42908  throw
0x42909  ldarg.0
0x4290a  call     instance object System.Xml.XsdValidatingReader::InternalReadContentAsObject()
0x4290f  stloc.0
0x42910  ldarg.0
0x42911  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42916  ldc.i4.2
0x42917  beq.s    loc_42921
0x42919  ldarg.0
0x4291a  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x4291f  br.s     loc_42927
0x42921  ldarg.0
0x42922  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x42927  stloc.1
0x42928  ldloc.1
0x42929  brfalse.s loc_4293A
0x4292b  ldloc.1
0x4292c  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42931  ldloc.0
0x42932  callvirt instance bool System.Xml.Schema.XmlValueConverter::ToBoolean(object value)
0x42937  stloc.2
0x42938  leave.s  loc_42985
0x4293a  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x4293f  ldloc.0
0x42940  callvirt instance bool System.Xml.Schema.XmlValueConverter::ToBoolean(object value)
0x42945  stloc.2
0x42946  leave.s  loc_42985
0x42948  stloc.3
0x42949  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x4294e  ldstr    aBoolean_0// "Boolean"
0x42953  ldloc.3
0x42954  ldarg.0
0x42955  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x4295a  throw
0x4295b  stloc.s  4
0x4295d  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42962  ldstr    aBoolean_0// "Boolean"
0x42967  ldloc.s  4
0x42969  ldarg.0
0x4296a  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x4296f  throw
0x42970  stloc.s  5
0x42972  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42977  ldstr    aBoolean_0// "Boolean"
0x4297c  ldloc.s  5
0x4297e  ldarg.0
0x4297f  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42984  throw
0x42985  ldloc.2
0x42986  ret
```
