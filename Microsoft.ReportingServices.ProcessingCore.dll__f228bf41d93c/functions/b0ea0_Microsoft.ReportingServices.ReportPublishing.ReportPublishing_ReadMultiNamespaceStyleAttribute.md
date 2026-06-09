# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMultiNamespaceStyleAttribute

- ea: `0xb0ea0`
- end: `0xb0fcd`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMultiNamespaceStyleAttribute`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0xad360`
- `0xb07f0`

## callees

- `0xac760`
- `0xb0ea0`
- `0xb9e20`
- `0xba260`
- `0xbcdc0`
- `0xbcde0`
- `0xbce20`
- `0xbd050`
- `0xbd070`
- `0xbe1e0`
- `0xbe230`
- `0x117880`
- `0x117890`
- `0x1767c0`

## string_xrefs

- `0xb0ee0`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/reportdefinition`
- `0xb0ef7`: `http://schemas.microsoft.com/sqlserver/reporting/2013/01/reportdefinition`

## pseudocode

```c

```

## disassembly

```asm
0xb0ea0  ldarg.s  6
0xb0ea2  ldc.i4.0
0xb0ea3  stind.i1
0xb0ea4  ldarg.0
0xb0ea5  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb0eaa  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb0eaf  stloc.0
0xb0eb0  ldarg.s  5
0xb0eb2  ldind.ref
0xb0eb3  brfalse.s loc_B0ED3
0xb0eb5  call     class Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::get_Instance()
0xb0eba  ldarg.0
0xb0ebb  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb0ec0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb0ec5  ldarg.s  5
0xb0ec7  ldind.ref
0xb0ec8  callvirt instance int32 Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::Compare(string x, string y)
0xb0ecd  ldc.i4.0
0xb0ece  ble      loc_B0FCB
0xb0ed3  ldc.i4.0
0xb0ed4  stloc.1
0xb0ed5  ldarg.0
0xb0ed6  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb0edb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb0ee0  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/sqlserver/"...
0xb0ee5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb0eea  brtrue.s loc_B0F03
0xb0eec  ldarg.0
0xb0eed  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb0ef2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb0ef7  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/sqlserver/"...
0xb0efc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb0f01  brfalse.s loc_B0F7B
0xb0f03  ldarg.0
0xb0f04  ldfld    class Microsoft.ReportingServices.ReportPublishing.PublishingContextBase Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_publishingContext
0xb0f09  callvirt instance class Microsoft.ReportingServices.ReportPublishing.PublishingVersioning Microsoft.ReportingServices.ReportPublishing.PublishingContextBase::get_PublishingVersioning()
0xb0f0e  ldarg.3
0xb0f0f  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.PublishingVersioning::IsRdlFeatureRestricted(valuetype Microsoft.ReportingServices.ReportPublishing.RdlFeatures feature)
0xb0f14  brfalse.s loc_B0F3D
0xb0f16  ldarga.s 2
0xb0f18  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb0f1d  ldc.i4   0x205
0xb0f22  ldc.i4.0
0xb0f23  ldarga.s 2
0xb0f25  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb0f2a  ldarga.s 2
0xb0f2c  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb0f31  ldloc.0
0xb0f32  call     T0x2B000001
0xb0f37  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb0f3c  pop
0xb0f3d  ldarg.s  4
0xb0f3f  brfalse.s loc_B0F7B
0xb0f41  ldarg.0
0xb0f42  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb0f47  ldstr    aValuetype// "ValueType"
0xb0f4c  ldarg.0
0xb0f4d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb0f52  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb0f57  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string, string)
0xb0f5c  stloc.3
0xb0f5d  ldloc.3
0xb0f5e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb0f63  brtrue.s loc_B0F7B
0xb0f65  ldtoken  Microsoft.ReportingServices.ReportIntermediateFormat.ValueType
0xb0f6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb0f6f  ldloc.3
0xb0f70  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0xb0f75  unbox.any Microsoft.ReportingServices.ReportIntermediateFormat.ValueType
0xb0f7a  stloc.1
0xb0f7b  ldarg.s  5
0xb0f7d  ldind.ref
0xb0f7e  brfalse.s loc_B0F87
0xb0f80  ldarg.1
0xb0f81  ldloc.0
0xb0f82  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::RemoveAttribute(string name)
0xb0f87  ldarg.s  5
0xb0f89  ldarg.0
0xb0f8a  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb0f8f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb0f94  stind.ref
0xb0f95  ldarg.0
0xb0f96  ldloc.0
0xb0f97  ldc.i4.0
0xb0f98  ldc.i4.s 0x12
0xb0f9a  ldarg.2
0xb0f9b  ldarg.s  6
0xb0f9d  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, [out] bool& computed)
0xb0fa2  stloc.2
0xb0fa3  ldarg.3
0xb0fa4  ldc.i4.s 0x1C
0xb0fa6  bne.un.s loc_B0FC0
0xb0fa8  ldloc.2
0xb0fa9  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0xb0fae  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb0fb3  brfalse.s loc_B0FC0
0xb0fb5  ldloc.2
0xb0fb6  ldstr    aArial// "Arial"
0xb0fbb  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::set_StringValue(string value)
0xb0fc0  ldarg.1
0xb0fc1  ldloc.0
0xb0fc2  ldloc.2
0xb0fc3  ldloc.1
0xb0fc4  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.ValueType valueType)
0xb0fc9  ldc.i4.1
0xb0fca  ret
0xb0fcb  ldc.i4.0
0xb0fcc  ret
```
