# System.Xml.XsdValidatingReader::ReadElementContentAsLong

- ea: `0x431e0`
- end: `0x4325d`
- name: `System.Xml.XsdValidatingReader::ReadElementContentAsLong`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x431e0`
- `0x44850`
- `0xd6c00`
- `0xdb2b0`

## string_xrefs

- `0x4321f`: `Xml_ReadContentAsFormatException`
- `0x43233`: `Xml_ReadContentAsFormatException`
- `0x43248`: `Xml_ReadContentAsFormatException`
- `0x431ea`: `ReadElementContentAsLong`

## pseudocode

```c

```

## disassembly

```asm
0x431e0  ldarg.0
0x431e1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x431e6  ldc.i4.1
0x431e7  beq.s    loc_431F5
0x431e9  ldarg.0
0x431ea  ldstr    aReadelementcon_8// "ReadElementContentAsLong"
0x431ef  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x431f4  throw
0x431f5  ldarg.0
0x431f6  ldloca.s 0
0x431f8  call     instance object System.Xml.XsdValidatingReader::InternalReadElementContentAsObject([out] class System.Xml.Schema.XmlSchemaType& xmlType)
0x431fd  stloc.1
0x431fe  ldloc.0
0x431ff  brfalse.s loc_43210
0x43201  ldloc.0
0x43202  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x43207  ldloc.1
0x43208  callvirt instance int64 System.Xml.Schema.XmlValueConverter::ToInt64(object value)
0x4320d  stloc.2
0x4320e  leave.s  loc_4325B
0x43210  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x43215  ldloc.1
0x43216  callvirt instance int64 System.Xml.Schema.XmlValueConverter::ToInt64(object value)
0x4321b  stloc.2
0x4321c  leave.s  loc_4325B
0x4321e  stloc.3
0x4321f  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x43224  ldstr    aLong// "Long"
0x43229  ldloc.3
0x4322a  ldarg.0
0x4322b  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x43230  throw
0x43231  stloc.s  4
0x43233  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x43238  ldstr    aLong// "Long"
0x4323d  ldloc.s  4
0x4323f  ldarg.0
0x43240  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x43245  throw
0x43246  stloc.s  5
0x43248  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x4324d  ldstr    aLong// "Long"
0x43252  ldloc.s  5
0x43254  ldarg.0
0x43255  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x4325a  throw
0x4325b  ldloc.2
0x4325c  ret
```
