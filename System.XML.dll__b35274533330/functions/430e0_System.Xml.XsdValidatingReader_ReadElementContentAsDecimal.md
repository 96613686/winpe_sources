# System.Xml.XsdValidatingReader::ReadElementContentAsDecimal

- ea: `0x430e0`
- end: `0x4315d`
- name: `System.Xml.XsdValidatingReader::ReadElementContentAsDecimal`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x430e0`
- `0x44850`
- `0xd6c00`
- `0xdb350`

## string_xrefs

- `0x4311f`: `Xml_ReadContentAsFormatException`
- `0x43133`: `Xml_ReadContentAsFormatException`
- `0x43148`: `Xml_ReadContentAsFormatException`
- `0x430ea`: `ReadElementContentAsDecimal`

## pseudocode

```c

```

## disassembly

```asm
0x430e0  ldarg.0
0x430e1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x430e6  ldc.i4.1
0x430e7  beq.s    loc_430F5
0x430e9  ldarg.0
0x430ea  ldstr    aReadelementcon_6// "ReadElementContentAsDecimal"
0x430ef  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x430f4  throw
0x430f5  ldarg.0
0x430f6  ldloca.s 0
0x430f8  call     instance object System.Xml.XsdValidatingReader::InternalReadElementContentAsObject([out] class System.Xml.Schema.XmlSchemaType& xmlType)
0x430fd  stloc.1
0x430fe  ldloc.0
0x430ff  brfalse.s loc_43110
0x43101  ldloc.0
0x43102  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x43107  ldloc.1
0x43108  callvirt instance valuetype [mscorlib]System.Decimal System.Xml.Schema.XmlValueConverter::ToDecimal(object value)
0x4310d  stloc.2
0x4310e  leave.s  loc_4315B
0x43110  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x43115  ldloc.1
0x43116  callvirt instance valuetype [mscorlib]System.Decimal System.Xml.Schema.XmlValueConverter::ToDecimal(object value)
0x4311b  stloc.2
0x4311c  leave.s  loc_4315B
0x4311e  stloc.3
0x4311f  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x43124  ldstr    aDecimal// "Decimal"
0x43129  ldloc.3
0x4312a  ldarg.0
0x4312b  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x43130  throw
0x43131  stloc.s  4
0x43133  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x43138  ldstr    aDecimal// "Decimal"
0x4313d  ldloc.s  4
0x4313f  ldarg.0
0x43140  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x43145  throw
0x43146  stloc.s  5
0x43148  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x4314d  ldstr    aDecimal// "Decimal"
0x43152  ldloc.s  5
0x43154  ldarg.0
0x43155  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x4315a  throw
0x4315b  ldloc.2
0x4315c  ret
```
