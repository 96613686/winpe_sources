# System.Xml.XsdValidatingReader::ReadElementContentAs

- ea: `0x432e0`
- end: `0x4338a`
- name: `System.Xml.XsdValidatingReader::ReadElementContentAs`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x432e0`
- `0x44870`
- `0xd6bb0`
- `0xd6c00`
- `0xdb750`

## string_xrefs

- `0x43348`: `Xml_ReadContentAsFormatException`
- `0x4335e`: `Xml_ReadContentAsFormatException`
- `0x43374`: `Xml_ReadContentAsFormatException`
- `0x432ea`: `ReadElementContentAs`

## pseudocode

```c

```

## disassembly

```asm
0x432e0  ldarg.0
0x432e1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x432e6  ldc.i4.1
0x432e7  beq.s    loc_432F5
0x432e9  ldarg.0
0x432ea  ldstr    aReadelementcon_10// "ReadElementContentAs"
0x432ef  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x432f4  throw
0x432f5  ldarg.0
0x432f6  ldloca.s 0
0x432f8  ldc.i4.0
0x432f9  ldloca.s 1
0x432fb  call     instance object System.Xml.XsdValidatingReader::InternalReadElementContentAsObject([out] class System.Xml.Schema.XmlSchemaType& xmlType, bool unwrapTypedValue, [out] string& originalString)
0x43300  stloc.2
0x43301  ldloc.0
0x43302  brfalse.s loc_43336
0x43304  ldarg.1
0x43305  ldtoken  [mscorlib]System.DateTimeOffset
0x4330a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4330f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x43314  brfalse.s loc_43325
0x43316  ldloc.0
0x43317  callvirt instance class System.Xml.Schema.XmlSchemaDatatype System.Xml.Schema.XmlSchemaType::get_Datatype()
0x4331c  isinst   System.Xml.Schema.Datatype_dateTimeBase
0x43321  brfalse.s loc_43325
0x43323  ldloc.1
0x43324  stloc.2
0x43325  ldloc.0
0x43326  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x4332b  ldloc.2
0x4332c  ldarg.1
0x4332d  ldarg.2
0x4332e  callvirt instance object System.Xml.Schema.XmlValueConverter::ChangeType(object value, class [mscorlib]System.Type destinationType, class System.Xml.IXmlNamespaceResolver nsResolver)
0x43333  stloc.3
0x43334  leave.s  loc_43388
0x43336  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x4333b  ldloc.2
0x4333c  ldarg.1
0x4333d  ldarg.2
0x4333e  callvirt instance object System.Xml.Schema.XmlValueConverter::ChangeType(object value, class [mscorlib]System.Type destinationType, class System.Xml.IXmlNamespaceResolver nsResolver)
0x43343  stloc.3
0x43344  leave.s  loc_43388
0x43346  stloc.s  4
0x43348  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x4334d  ldarg.1
0x4334e  callvirt instance string [mscorlib]System.Object::ToString()
0x43353  ldloc.s  4
0x43355  ldarg.0
0x43356  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x4335b  throw
0x4335c  stloc.s  5
0x4335e  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x43363  ldarg.1
0x43364  callvirt instance string [mscorlib]System.Object::ToString()
0x43369  ldloc.s  5
0x4336b  ldarg.0
0x4336c  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x43371  throw
0x43372  stloc.s  6
0x43374  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x43379  ldarg.1
0x4337a  callvirt instance string [mscorlib]System.Object::ToString()
0x4337f  ldloc.s  6
0x43381  ldarg.0
0x43382  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x43387  throw
0x43388  ldloc.3
0x43389  ret
```
