# System.Xml.XsdValidatingReader::ReadContentAsString

- ea: `0x42d50`
- end: `0x42de2`
- name: `System.Xml.XsdValidatingReader::ReadContentAsString`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22910`
- `0x22a30`
- `0x42d50`
- `0x43f60`
- `0x43f70`
- `0x44730`
- `0xd6c00`
- `0xdb680`

## string_xrefs

- `0x42da4`: `Xml_ReadContentAsFormatException`
- `0x42db8`: `Xml_ReadContentAsFormatException`
- `0x42dcd`: `Xml_ReadContentAsFormatException`
- `0x42d5e`: `ReadContentAsString`

## pseudocode

```c

```

## disassembly

```asm
0x42d50  ldarg.0
0x42d51  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42d56  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x42d5b  brtrue.s loc_42D69
0x42d5d  ldarg.0
0x42d5e  ldstr    aReadcontentass// "ReadContentAsString"
0x42d63  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x42d68  throw
0x42d69  ldarg.0
0x42d6a  call     instance object System.Xml.XsdValidatingReader::InternalReadContentAsObject()
0x42d6f  stloc.0
0x42d70  ldarg.0
0x42d71  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42d76  ldc.i4.2
0x42d77  beq.s    loc_42D81
0x42d79  ldarg.0
0x42d7a  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x42d7f  br.s     loc_42D87
0x42d81  ldarg.0
0x42d82  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x42d87  stloc.1
0x42d88  ldloc.1
0x42d89  brfalse.s loc_42D9A
0x42d8b  ldloc.1
0x42d8c  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42d91  ldloc.0
0x42d92  callvirt instance string System.Xml.Schema.XmlValueConverter::ToString(object value)
0x42d97  stloc.2
0x42d98  leave.s  loc_42DE0
0x42d9a  ldloc.0
0x42d9b  isinst   [mscorlib]System.String
0x42da0  stloc.2
0x42da1  leave.s  loc_42DE0
0x42da3  stloc.3
0x42da4  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42da9  ldstr    aString_0// "String"
0x42dae  ldloc.3
0x42daf  ldarg.0
0x42db0  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42db5  throw
0x42db6  stloc.s  4
0x42db8  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42dbd  ldstr    aString_0// "String"
0x42dc2  ldloc.s  4
0x42dc4  ldarg.0
0x42dc5  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42dca  throw
0x42dcb  stloc.s  5
0x42dcd  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42dd2  ldstr    aString_0// "String"
0x42dd7  ldloc.s  5
0x42dd9  ldarg.0
0x42dda  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42ddf  throw
0x42de0  ldloc.2
0x42de1  ret
```
