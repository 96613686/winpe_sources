# System.Xml.XsdValidatingReader::ReadElementContentAsDouble

- ea: `0x42fe0`
- end: `0x4305d`
- name: `System.Xml.XsdValidatingReader::ReadElementContentAsDouble`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x42fe0`
- `0x44850`
- `0xd6c00`
- `0xdb3f0`

## string_xrefs

- `0x4301f`: `Xml_ReadContentAsFormatException`
- `0x43033`: `Xml_ReadContentAsFormatException`
- `0x43048`: `Xml_ReadContentAsFormatException`
- `0x42fea`: `ReadElementContentAsDouble`

## pseudocode

```c

```

## disassembly

```asm
0x42fe0  ldarg.0
0x42fe1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42fe6  ldc.i4.1
0x42fe7  beq.s    loc_42FF5
0x42fe9  ldarg.0
0x42fea  ldstr    aReadelementcon_4// "ReadElementContentAsDouble"
0x42fef  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x42ff4  throw
0x42ff5  ldarg.0
0x42ff6  ldloca.s 0
0x42ff8  call     instance object System.Xml.XsdValidatingReader::InternalReadElementContentAsObject([out] class System.Xml.Schema.XmlSchemaType& xmlType)
0x42ffd  stloc.1
0x42ffe  ldloc.0
0x42fff  brfalse.s loc_43010
0x43001  ldloc.0
0x43002  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x43007  ldloc.1
0x43008  callvirt instance float64 System.Xml.Schema.XmlValueConverter::ToDouble(object value)
0x4300d  stloc.2
0x4300e  leave.s  loc_4305B
0x43010  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x43015  ldloc.1
0x43016  callvirt instance float64 System.Xml.Schema.XmlValueConverter::ToDouble(object value)
0x4301b  stloc.2
0x4301c  leave.s  loc_4305B
0x4301e  stloc.3
0x4301f  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x43024  ldstr    aDouble// "Double"
0x43029  ldloc.3
0x4302a  ldarg.0
0x4302b  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x43030  throw
0x43031  stloc.s  4
0x43033  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x43038  ldstr    aDouble// "Double"
0x4303d  ldloc.s  4
0x4303f  ldarg.0
0x43040  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x43045  throw
0x43046  stloc.s  5
0x43048  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x4304d  ldstr    aDouble// "Double"
0x43052  ldloc.s  5
0x43054  ldarg.0
0x43055  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x4305a  throw
0x4305b  ldloc.2
0x4305c  ret
```
