# System.Xml.XsdValidatingReader::ReadElementContentAsString

- ea: `0x43260`
- end: `0x432d8`
- name: `System.Xml.XsdValidatingReader::ReadElementContentAsString`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x43260`
- `0x44850`
- `0xd6c00`
- `0xdb680`

## string_xrefs

- `0x4329a`: `Xml_ReadContentAsFormatException`
- `0x432ae`: `Xml_ReadContentAsFormatException`
- `0x432c3`: `Xml_ReadContentAsFormatException`
- `0x4326a`: `ReadElementContentAsString`

## pseudocode

```c

```

## disassembly

```asm
0x43260  ldarg.0
0x43261  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x43266  ldc.i4.1
0x43267  beq.s    loc_43275
0x43269  ldarg.0
0x4326a  ldstr    aReadelementcon_9// "ReadElementContentAsString"
0x4326f  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x43274  throw
0x43275  ldarg.0
0x43276  ldloca.s 0
0x43278  call     instance object System.Xml.XsdValidatingReader::InternalReadElementContentAsObject([out] class System.Xml.Schema.XmlSchemaType& xmlType)
0x4327d  stloc.1
0x4327e  ldloc.0
0x4327f  brfalse.s loc_43290
0x43281  ldloc.0
0x43282  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x43287  ldloc.1
0x43288  callvirt instance string System.Xml.Schema.XmlValueConverter::ToString(object value)
0x4328d  stloc.2
0x4328e  leave.s  loc_432D6
0x43290  ldloc.1
0x43291  isinst   [mscorlib]System.String
0x43296  stloc.2
0x43297  leave.s  loc_432D6
0x43299  stloc.3
0x4329a  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x4329f  ldstr    aString_0// "String"
0x432a4  ldloc.3
0x432a5  ldarg.0
0x432a6  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x432ab  throw
0x432ac  stloc.s  4
0x432ae  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x432b3  ldstr    aString_0// "String"
0x432b8  ldloc.s  4
0x432ba  ldarg.0
0x432bb  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x432c0  throw
0x432c1  stloc.s  5
0x432c3  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x432c8  ldstr    aString_0// "String"
0x432cd  ldloc.s  5
0x432cf  ldarg.0
0x432d0  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x432d5  throw
0x432d6  ldloc.2
0x432d7  ret
```
