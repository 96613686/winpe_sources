# System.Xml.XsdValidatingReader::ReadElementContentAsFloat

- ea: `0x43060`
- end: `0x430dd`
- name: `System.Xml.XsdValidatingReader::ReadElementContentAsFloat`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x43060`
- `0x44850`
- `0xd6c00`
- `0xdb490`

## string_xrefs

- `0x4309f`: `Xml_ReadContentAsFormatException`
- `0x430b3`: `Xml_ReadContentAsFormatException`
- `0x430c8`: `Xml_ReadContentAsFormatException`
- `0x4306a`: `ReadElementContentAsFloat`

## pseudocode

```c

```

## disassembly

```asm
0x43060  ldarg.0
0x43061  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x43066  ldc.i4.1
0x43067  beq.s    loc_43075
0x43069  ldarg.0
0x4306a  ldstr    aReadelementcon_5// "ReadElementContentAsFloat"
0x4306f  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x43074  throw
0x43075  ldarg.0
0x43076  ldloca.s 0
0x43078  call     instance object System.Xml.XsdValidatingReader::InternalReadElementContentAsObject([out] class System.Xml.Schema.XmlSchemaType& xmlType)
0x4307d  stloc.1
0x4307e  ldloc.0
0x4307f  brfalse.s loc_43090
0x43081  ldloc.0
0x43082  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x43087  ldloc.1
0x43088  callvirt instance float32 System.Xml.Schema.XmlValueConverter::ToSingle(object value)
0x4308d  stloc.2
0x4308e  leave.s  loc_430DB
0x43090  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x43095  ldloc.1
0x43096  callvirt instance float32 System.Xml.Schema.XmlValueConverter::ToSingle(object value)
0x4309b  stloc.2
0x4309c  leave.s  loc_430DB
0x4309e  stloc.3
0x4309f  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x430a4  ldstr    aFloat// "Float"
0x430a9  ldloc.3
0x430aa  ldarg.0
0x430ab  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x430b0  throw
0x430b1  stloc.s  4
0x430b3  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x430b8  ldstr    aFloat// "Float"
0x430bd  ldloc.s  4
0x430bf  ldarg.0
0x430c0  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x430c5  throw
0x430c6  stloc.s  5
0x430c8  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x430cd  ldstr    aFloat// "Float"
0x430d2  ldloc.s  5
0x430d4  ldarg.0
0x430d5  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x430da  throw
0x430db  ldloc.2
0x430dc  ret
```
