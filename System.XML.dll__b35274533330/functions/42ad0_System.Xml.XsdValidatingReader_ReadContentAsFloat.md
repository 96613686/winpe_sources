# System.Xml.XsdValidatingReader::ReadContentAsFloat

- ea: `0x42ad0`
- end: `0x42b67`
- name: `System.Xml.XsdValidatingReader::ReadContentAsFloat`
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
- `0x42ad0`
- `0x43f60`
- `0x43f70`
- `0x44730`
- `0xd6c00`
- `0xdb490`

## string_xrefs

- `0x42b29`: `Xml_ReadContentAsFormatException`
- `0x42b3d`: `Xml_ReadContentAsFormatException`
- `0x42b52`: `Xml_ReadContentAsFormatException`
- `0x42ade`: `ReadContentAsFloat`

## pseudocode

```c

```

## disassembly

```asm
0x42ad0  ldarg.0
0x42ad1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42ad6  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x42adb  brtrue.s loc_42AE9
0x42add  ldarg.0
0x42ade  ldstr    aReadcontentasf// "ReadContentAsFloat"
0x42ae3  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x42ae8  throw
0x42ae9  ldarg.0
0x42aea  call     instance object System.Xml.XsdValidatingReader::InternalReadContentAsObject()
0x42aef  stloc.0
0x42af0  ldarg.0
0x42af1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42af6  ldc.i4.2
0x42af7  beq.s    loc_42B01
0x42af9  ldarg.0
0x42afa  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x42aff  br.s     loc_42B07
0x42b01  ldarg.0
0x42b02  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x42b07  stloc.1
0x42b08  ldloc.1
0x42b09  brfalse.s loc_42B1A
0x42b0b  ldloc.1
0x42b0c  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42b11  ldloc.0
0x42b12  callvirt instance float32 System.Xml.Schema.XmlValueConverter::ToSingle(object value)
0x42b17  stloc.2
0x42b18  leave.s  loc_42B65
0x42b1a  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x42b1f  ldloc.0
0x42b20  callvirt instance float32 System.Xml.Schema.XmlValueConverter::ToSingle(object value)
0x42b25  stloc.2
0x42b26  leave.s  loc_42B65
0x42b28  stloc.3
0x42b29  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42b2e  ldstr    aFloat// "Float"
0x42b33  ldloc.3
0x42b34  ldarg.0
0x42b35  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42b3a  throw
0x42b3b  stloc.s  4
0x42b3d  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42b42  ldstr    aFloat// "Float"
0x42b47  ldloc.s  4
0x42b49  ldarg.0
0x42b4a  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42b4f  throw
0x42b50  stloc.s  5
0x42b52  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42b57  ldstr    aFloat// "Float"
0x42b5c  ldloc.s  5
0x42b5e  ldarg.0
0x42b5f  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42b64  throw
0x42b65  ldloc.2
0x42b66  ret
```
