# System.Xml.XsdValidatingReader::ReadElementContentAsBoolean

- ea: `0x42ee0`
- end: `0x42f5d`
- name: `System.Xml.XsdValidatingReader::ReadElementContentAsBoolean`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x42ee0`
- `0x44850`
- `0xd6c00`
- `0xdb170`

## string_xrefs

- `0x42f1f`: `Xml_ReadContentAsFormatException`
- `0x42f33`: `Xml_ReadContentAsFormatException`
- `0x42f48`: `Xml_ReadContentAsFormatException`
- `0x42eea`: `ReadElementContentAsBoolean`

## pseudocode

```c

```

## disassembly

```asm
0x42ee0  ldarg.0
0x42ee1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42ee6  ldc.i4.1
0x42ee7  beq.s    loc_42EF5
0x42ee9  ldarg.0
0x42eea  ldstr    aReadelementcon_2// "ReadElementContentAsBoolean"
0x42eef  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x42ef4  throw
0x42ef5  ldarg.0
0x42ef6  ldloca.s 0
0x42ef8  call     instance object System.Xml.XsdValidatingReader::InternalReadElementContentAsObject([out] class System.Xml.Schema.XmlSchemaType& xmlType)
0x42efd  stloc.1
0x42efe  ldloc.0
0x42eff  brfalse.s loc_42F10
0x42f01  ldloc.0
0x42f02  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42f07  ldloc.1
0x42f08  callvirt instance bool System.Xml.Schema.XmlValueConverter::ToBoolean(object value)
0x42f0d  stloc.2
0x42f0e  leave.s  loc_42F5B
0x42f10  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x42f15  ldloc.1
0x42f16  callvirt instance bool System.Xml.Schema.XmlValueConverter::ToBoolean(object value)
0x42f1b  stloc.2
0x42f1c  leave.s  loc_42F5B
0x42f1e  stloc.3
0x42f1f  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42f24  ldstr    aBoolean_0// "Boolean"
0x42f29  ldloc.3
0x42f2a  ldarg.0
0x42f2b  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42f30  throw
0x42f31  stloc.s  4
0x42f33  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42f38  ldstr    aBoolean_0// "Boolean"
0x42f3d  ldloc.s  4
0x42f3f  ldarg.0
0x42f40  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42f45  throw
0x42f46  stloc.s  5
0x42f48  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42f4d  ldstr    aBoolean_0// "Boolean"
0x42f52  ldloc.s  5
0x42f54  ldarg.0
0x42f55  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42f5a  throw
0x42f5b  ldloc.2
0x42f5c  ret
```
