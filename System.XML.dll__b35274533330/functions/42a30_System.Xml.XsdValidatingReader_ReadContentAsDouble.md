# System.Xml.XsdValidatingReader::ReadContentAsDouble

- ea: `0x42a30`
- end: `0x42ac7`
- name: `System.Xml.XsdValidatingReader::ReadContentAsDouble`
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
- `0x42a30`
- `0x43f60`
- `0x43f70`
- `0x44730`
- `0xd6c00`
- `0xdb3f0`

## string_xrefs

- `0x42a89`: `Xml_ReadContentAsFormatException`
- `0x42a9d`: `Xml_ReadContentAsFormatException`
- `0x42ab2`: `Xml_ReadContentAsFormatException`
- `0x42a3e`: `ReadContentAsDouble`

## pseudocode

```c

```

## disassembly

```asm
0x42a30  ldarg.0
0x42a31  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42a36  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x42a3b  brtrue.s loc_42A49
0x42a3d  ldarg.0
0x42a3e  ldstr    aReadcontentasd_1// "ReadContentAsDouble"
0x42a43  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x42a48  throw
0x42a49  ldarg.0
0x42a4a  call     instance object System.Xml.XsdValidatingReader::InternalReadContentAsObject()
0x42a4f  stloc.0
0x42a50  ldarg.0
0x42a51  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42a56  ldc.i4.2
0x42a57  beq.s    loc_42A61
0x42a59  ldarg.0
0x42a5a  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x42a5f  br.s     loc_42A67
0x42a61  ldarg.0
0x42a62  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x42a67  stloc.1
0x42a68  ldloc.1
0x42a69  brfalse.s loc_42A7A
0x42a6b  ldloc.1
0x42a6c  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42a71  ldloc.0
0x42a72  callvirt instance float64 System.Xml.Schema.XmlValueConverter::ToDouble(object value)
0x42a77  stloc.2
0x42a78  leave.s  loc_42AC5
0x42a7a  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x42a7f  ldloc.0
0x42a80  callvirt instance float64 System.Xml.Schema.XmlValueConverter::ToDouble(object value)
0x42a85  stloc.2
0x42a86  leave.s  loc_42AC5
0x42a88  stloc.3
0x42a89  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42a8e  ldstr    aDouble// "Double"
0x42a93  ldloc.3
0x42a94  ldarg.0
0x42a95  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42a9a  throw
0x42a9b  stloc.s  4
0x42a9d  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42aa2  ldstr    aDouble// "Double"
0x42aa7  ldloc.s  4
0x42aa9  ldarg.0
0x42aaa  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42aaf  throw
0x42ab0  stloc.s  5
0x42ab2  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42ab7  ldstr    aDouble// "Double"
0x42abc  ldloc.s  5
0x42abe  ldarg.0
0x42abf  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42ac4  throw
0x42ac5  ldloc.2
0x42ac6  ret
```
