# System.Xml.XsdValidatingReader::ReadContentAsInt

- ea: `0x42c10`
- end: `0x42ca7`
- name: `System.Xml.XsdValidatingReader::ReadContentAsInt`
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
- `0x42c10`
- `0x43f60`
- `0x43f70`
- `0x44730`
- `0xd6c00`
- `0xdb210`

## string_xrefs

- `0x42c69`: `Xml_ReadContentAsFormatException`
- `0x42c7d`: `Xml_ReadContentAsFormatException`
- `0x42c92`: `Xml_ReadContentAsFormatException`
- `0x42c1e`: `ReadContentAsInt`

## pseudocode

```c

```

## disassembly

```asm
0x42c10  ldarg.0
0x42c11  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42c16  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x42c1b  brtrue.s loc_42C29
0x42c1d  ldarg.0
0x42c1e  ldstr    aReadcontentasi// "ReadContentAsInt"
0x42c23  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x42c28  throw
0x42c29  ldarg.0
0x42c2a  call     instance object System.Xml.XsdValidatingReader::InternalReadContentAsObject()
0x42c2f  stloc.0
0x42c30  ldarg.0
0x42c31  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42c36  ldc.i4.2
0x42c37  beq.s    loc_42C41
0x42c39  ldarg.0
0x42c3a  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x42c3f  br.s     loc_42C47
0x42c41  ldarg.0
0x42c42  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x42c47  stloc.1
0x42c48  ldloc.1
0x42c49  brfalse.s loc_42C5A
0x42c4b  ldloc.1
0x42c4c  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42c51  ldloc.0
0x42c52  callvirt instance int32 System.Xml.Schema.XmlValueConverter::ToInt32(object value)
0x42c57  stloc.2
0x42c58  leave.s  loc_42CA5
0x42c5a  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x42c5f  ldloc.0
0x42c60  callvirt instance int32 System.Xml.Schema.XmlValueConverter::ToInt32(object value)
0x42c65  stloc.2
0x42c66  leave.s  loc_42CA5
0x42c68  stloc.3
0x42c69  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42c6e  ldstr    aInt// "Int"
0x42c73  ldloc.3
0x42c74  ldarg.0
0x42c75  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42c7a  throw
0x42c7b  stloc.s  4
0x42c7d  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42c82  ldstr    aInt// "Int"
0x42c87  ldloc.s  4
0x42c89  ldarg.0
0x42c8a  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42c8f  throw
0x42c90  stloc.s  5
0x42c92  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42c97  ldstr    aInt// "Int"
0x42c9c  ldloc.s  5
0x42c9e  ldarg.0
0x42c9f  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42ca4  throw
0x42ca5  ldloc.2
0x42ca6  ret
```
