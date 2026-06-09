# System.Xml.XsdValidatingReader::ReadContentAsLong

- ea: `0x42cb0`
- end: `0x42d47`
- name: `System.Xml.XsdValidatingReader::ReadContentAsLong`
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
- `0x42cb0`
- `0x43f60`
- `0x43f70`
- `0x44730`
- `0xd6c00`
- `0xdb2b0`

## string_xrefs

- `0x42d09`: `Xml_ReadContentAsFormatException`
- `0x42d1d`: `Xml_ReadContentAsFormatException`
- `0x42d32`: `Xml_ReadContentAsFormatException`
- `0x42cbe`: `ReadContentAsLong`

## pseudocode

```c

```

## disassembly

```asm
0x42cb0  ldarg.0
0x42cb1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42cb6  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x42cbb  brtrue.s loc_42CC9
0x42cbd  ldarg.0
0x42cbe  ldstr    aReadcontentasl// "ReadContentAsLong"
0x42cc3  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x42cc8  throw
0x42cc9  ldarg.0
0x42cca  call     instance object System.Xml.XsdValidatingReader::InternalReadContentAsObject()
0x42ccf  stloc.0
0x42cd0  ldarg.0
0x42cd1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42cd6  ldc.i4.2
0x42cd7  beq.s    loc_42CE1
0x42cd9  ldarg.0
0x42cda  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x42cdf  br.s     loc_42CE7
0x42ce1  ldarg.0
0x42ce2  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x42ce7  stloc.1
0x42ce8  ldloc.1
0x42ce9  brfalse.s loc_42CFA
0x42ceb  ldloc.1
0x42cec  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42cf1  ldloc.0
0x42cf2  callvirt instance int64 System.Xml.Schema.XmlValueConverter::ToInt64(object value)
0x42cf7  stloc.2
0x42cf8  leave.s  loc_42D45
0x42cfa  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x42cff  ldloc.0
0x42d00  callvirt instance int64 System.Xml.Schema.XmlValueConverter::ToInt64(object value)
0x42d05  stloc.2
0x42d06  leave.s  loc_42D45
0x42d08  stloc.3
0x42d09  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42d0e  ldstr    aLong// "Long"
0x42d13  ldloc.3
0x42d14  ldarg.0
0x42d15  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42d1a  throw
0x42d1b  stloc.s  4
0x42d1d  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42d22  ldstr    aLong// "Long"
0x42d27  ldloc.s  4
0x42d29  ldarg.0
0x42d2a  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42d2f  throw
0x42d30  stloc.s  5
0x42d32  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42d37  ldstr    aLong// "Long"
0x42d3c  ldloc.s  5
0x42d3e  ldarg.0
0x42d3f  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42d44  throw
0x42d45  ldloc.2
0x42d46  ret
```
