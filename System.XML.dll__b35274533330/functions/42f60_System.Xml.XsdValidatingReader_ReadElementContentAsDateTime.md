# System.Xml.XsdValidatingReader::ReadElementContentAsDateTime

- ea: `0x42f60`
- end: `0x42fdd`
- name: `System.Xml.XsdValidatingReader::ReadElementContentAsDateTime`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x42f60`
- `0x44850`
- `0xd6c00`
- `0xdb530`

## string_xrefs

- `0x42f9f`: `Xml_ReadContentAsFormatException`
- `0x42fb3`: `Xml_ReadContentAsFormatException`
- `0x42fc8`: `Xml_ReadContentAsFormatException`
- `0x42f6a`: `ReadElementContentAsDateTime`

## pseudocode

```c

```

## disassembly

```asm
0x42f60  ldarg.0
0x42f61  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42f66  ldc.i4.1
0x42f67  beq.s    loc_42F75
0x42f69  ldarg.0
0x42f6a  ldstr    aReadelementcon_3// "ReadElementContentAsDateTime"
0x42f6f  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x42f74  throw
0x42f75  ldarg.0
0x42f76  ldloca.s 0
0x42f78  call     instance object System.Xml.XsdValidatingReader::InternalReadElementContentAsObject([out] class System.Xml.Schema.XmlSchemaType& xmlType)
0x42f7d  stloc.1
0x42f7e  ldloc.0
0x42f7f  brfalse.s loc_42F90
0x42f81  ldloc.0
0x42f82  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42f87  ldloc.1
0x42f88  callvirt instance valuetype [mscorlib]System.DateTime System.Xml.Schema.XmlValueConverter::ToDateTime(object value)
0x42f8d  stloc.2
0x42f8e  leave.s  loc_42FDB
0x42f90  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x42f95  ldloc.1
0x42f96  callvirt instance valuetype [mscorlib]System.DateTime System.Xml.Schema.XmlValueConverter::ToDateTime(object value)
0x42f9b  stloc.2
0x42f9c  leave.s  loc_42FDB
0x42f9e  stloc.3
0x42f9f  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42fa4  ldstr    aDatetime// "DateTime"
0x42fa9  ldloc.3
0x42faa  ldarg.0
0x42fab  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42fb0  throw
0x42fb1  stloc.s  4
0x42fb3  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42fb8  ldstr    aDatetime// "DateTime"
0x42fbd  ldloc.s  4
0x42fbf  ldarg.0
0x42fc0  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42fc5  throw
0x42fc6  stloc.s  5
0x42fc8  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42fcd  ldstr    aDatetime// "DateTime"
0x42fd2  ldloc.s  5
0x42fd4  ldarg.0
0x42fd5  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42fda  throw
0x42fdb  ldloc.2
0x42fdc  ret
```
