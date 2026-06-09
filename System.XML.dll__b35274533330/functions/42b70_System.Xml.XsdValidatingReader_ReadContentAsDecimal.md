# System.Xml.XsdValidatingReader::ReadContentAsDecimal

- ea: `0x42b70`
- end: `0x42c07`
- name: `System.Xml.XsdValidatingReader::ReadContentAsDecimal`
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
- `0x42b70`
- `0x43f60`
- `0x43f70`
- `0x44730`
- `0xd6c00`
- `0xdb350`

## string_xrefs

- `0x42bc9`: `Xml_ReadContentAsFormatException`
- `0x42bdd`: `Xml_ReadContentAsFormatException`
- `0x42bf2`: `Xml_ReadContentAsFormatException`
- `0x42b7e`: `ReadContentAsDecimal`

## pseudocode

```c

```

## disassembly

```asm
0x42b70  ldarg.0
0x42b71  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42b76  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x42b7b  brtrue.s loc_42B89
0x42b7d  ldarg.0
0x42b7e  ldstr    aReadcontentasd_2// "ReadContentAsDecimal"
0x42b83  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x42b88  throw
0x42b89  ldarg.0
0x42b8a  call     instance object System.Xml.XsdValidatingReader::InternalReadContentAsObject()
0x42b8f  stloc.0
0x42b90  ldarg.0
0x42b91  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42b96  ldc.i4.2
0x42b97  beq.s    loc_42BA1
0x42b99  ldarg.0
0x42b9a  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x42b9f  br.s     loc_42BA7
0x42ba1  ldarg.0
0x42ba2  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x42ba7  stloc.1
0x42ba8  ldloc.1
0x42ba9  brfalse.s loc_42BBA
0x42bab  ldloc.1
0x42bac  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42bb1  ldloc.0
0x42bb2  callvirt instance valuetype [mscorlib]System.Decimal System.Xml.Schema.XmlValueConverter::ToDecimal(object value)
0x42bb7  stloc.2
0x42bb8  leave.s  loc_42C05
0x42bba  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x42bbf  ldloc.0
0x42bc0  callvirt instance valuetype [mscorlib]System.Decimal System.Xml.Schema.XmlValueConverter::ToDecimal(object value)
0x42bc5  stloc.2
0x42bc6  leave.s  loc_42C05
0x42bc8  stloc.3
0x42bc9  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42bce  ldstr    aDecimal// "Decimal"
0x42bd3  ldloc.3
0x42bd4  ldarg.0
0x42bd5  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42bda  throw
0x42bdb  stloc.s  4
0x42bdd  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42be2  ldstr    aDecimal// "Decimal"
0x42be7  ldloc.s  4
0x42be9  ldarg.0
0x42bea  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42bef  throw
0x42bf0  stloc.s  5
0x42bf2  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42bf7  ldstr    aDecimal// "Decimal"
0x42bfc  ldloc.s  5
0x42bfe  ldarg.0
0x42bff  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42c04  throw
0x42c05  ldloc.2
0x42c06  ret
```
