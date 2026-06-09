# System.Xml.XsdValidatingReader::ReadContentAs

- ea: `0x42df0`
- end: `0x42eb3`
- name: `System.Xml.XsdValidatingReader::ReadContentAs`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22910`
- `0x22a30`
- `0x42df0`
- `0x43f60`
- `0x43f70`
- `0x44750`
- `0xd6bb0`
- `0xd6c00`
- `0xdb740`
- `0xdb750`

## string_xrefs

- `0x42e71`: `Xml_ReadContentAsFormatException`
- `0x42e87`: `Xml_ReadContentAsFormatException`
- `0x42e9d`: `Xml_ReadContentAsFormatException`
- `0x42dfe`: `ReadContentAs`

## pseudocode

```c

```

## disassembly

```asm
0x42df0  ldarg.0
0x42df1  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42df6  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x42dfb  brtrue.s loc_42E09
0x42dfd  ldarg.0
0x42dfe  ldstr    aReadcontentas// "ReadContentAs"
0x42e03  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x42e08  throw
0x42e09  ldarg.0
0x42e0a  ldc.i4.0
0x42e0b  ldloca.s 0
0x42e0d  call     instance object System.Xml.XsdValidatingReader::InternalReadContentAsObject(bool unwrapTypedValue, [out] string& originalStringValue)
0x42e12  stloc.1
0x42e13  ldarg.0
0x42e14  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x42e19  ldc.i4.2
0x42e1a  beq.s    loc_42E24
0x42e1c  ldarg.0
0x42e1d  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x42e22  br.s     loc_42E2A
0x42e24  ldarg.0
0x42e25  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x42e2a  stloc.2
0x42e2b  ldloc.2
0x42e2c  brfalse.s loc_42E5F
0x42e2e  ldarg.1
0x42e2f  ldtoken  [mscorlib]System.DateTimeOffset
0x42e34  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x42e39  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x42e3e  brfalse.s loc_42E4F
0x42e40  ldloc.2
0x42e41  callvirt instance class System.Xml.Schema.XmlSchemaDatatype System.Xml.Schema.XmlSchemaType::get_Datatype()
0x42e46  isinst   System.Xml.Schema.Datatype_dateTimeBase
0x42e4b  brfalse.s loc_42E4F
0x42e4d  ldloc.0
0x42e4e  stloc.1
0x42e4f  ldloc.2
0x42e50  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x42e55  ldloc.1
0x42e56  ldarg.1
0x42e57  callvirt instance object System.Xml.Schema.XmlValueConverter::ChangeType(object value, class [mscorlib]System.Type destinationType)
0x42e5c  stloc.3
0x42e5d  leave.s  loc_42EB1
0x42e5f  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x42e64  ldloc.1
0x42e65  ldarg.1
0x42e66  ldarg.2
0x42e67  callvirt instance object System.Xml.Schema.XmlValueConverter::ChangeType(object value, class [mscorlib]System.Type destinationType, class System.Xml.IXmlNamespaceResolver nsResolver)
0x42e6c  stloc.3
0x42e6d  leave.s  loc_42EB1
0x42e6f  stloc.s  4
0x42e71  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42e76  ldarg.1
0x42e77  callvirt instance string [mscorlib]System.Object::ToString()
0x42e7c  ldloc.s  4
0x42e7e  ldarg.0
0x42e7f  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42e84  throw
0x42e85  stloc.s  5
0x42e87  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42e8c  ldarg.1
0x42e8d  callvirt instance string [mscorlib]System.Object::ToString()
0x42e92  ldloc.s  5
0x42e94  ldarg.0
0x42e95  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42e9a  throw
0x42e9b  stloc.s  6
0x42e9d  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x42ea2  ldarg.1
0x42ea3  callvirt instance string [mscorlib]System.Object::ToString()
0x42ea8  ldloc.s  6
0x42eaa  ldarg.0
0x42eab  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x42eb0  throw
0x42eb1  ldloc.3
0x42eb2  ret
```
