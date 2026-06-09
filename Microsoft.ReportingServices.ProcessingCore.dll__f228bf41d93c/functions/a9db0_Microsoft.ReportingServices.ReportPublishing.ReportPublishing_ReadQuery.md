# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadQuery

- ea: `0xa9db0`
- end: `0xa9f1b`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadQuery`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0xa9880`

## callees

- `0xa9db0`
- `0xa9f20`
- `0xa9f50`
- `0xadae0`
- `0xbb9a0`
- `0xbcdc0`
- `0xbcdd0`
- `0xbcde0`
- `0x116480`
- `0x1164a0`
- `0x1164c0`
- `0x1164e0`
- `0x116500`
- `0x116520`
- `0x116830`

## string_xrefs

- `0xa9dfb`: `CommandType`
- `0xa9e08`: `CommandText`
- `0xa9e15`: `PreviewCommandText`

## pseudocode

```c

```

## disassembly

```asm
0xa9db0  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::.ctor()
0xa9db5  stloc.0
0xa9db6  ldc.i4.0
0xa9db7  stloc.1
0xa9db8  ldarg.0
0xa9db9  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9dbe  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa9dc3  pop
0xa9dc4  ldarg.0
0xa9dc5  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9dca  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa9dcf  stloc.2
0xa9dd0  ldloc.2
0xa9dd1  ldc.i4.1
0xa9dd2  beq.s    loc_A9DE1
0xa9dd4  ldloc.2
0xa9dd5  ldc.i4.s 0xF
0xa9dd7  beq      loc_A9EFA
0xa9ddc  br       loc_A9F13
0xa9de1  ldarg.0
0xa9de2  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9de7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa9dec  stloc.3
0xa9ded  ldloc.3
0xa9dee  ldstr    aDatasourcename// "DataSourceName"
0xa9df3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9df8  brtrue.s loc_A9E49
0xa9dfa  ldloc.3
0xa9dfb  ldstr    aCommandtype// "CommandType"
0xa9e00  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9e05  brtrue.s loc_A9E5F
0xa9e07  ldloc.3
0xa9e08  ldstr    aCommandtext// "CommandText"
0xa9e0d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9e12  brtrue.s loc_A9E70
0xa9e14  ldloc.3
0xa9e15  ldstr    aPreviewcommand// "PreviewCommandText"
0xa9e1a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9e1f  brtrue   loc_A9EAA
0xa9e24  ldloc.3
0xa9e25  ldstr    aQueryparameter// "QueryParameters"
0xa9e2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9e2f  brtrue   loc_A9EBD
0xa9e34  ldloc.3
0xa9e35  ldstr    aTimeout// "Timeout"
0xa9e3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9e3f  brtrue   loc_A9ECE
0xa9e44  br       loc_A9F13
0xa9e49  ldloc.0
0xa9e4a  ldarg.0
0xa9e4b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9e50  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xa9e55  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_DataSourceName(string value)
0xa9e5a  br       loc_A9F13
0xa9e5f  ldloc.0
0xa9e60  ldarg.0
0xa9e61  call     instance valuetype [System.Data]System.Data.CommandType Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadCommandType()
0xa9e66  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0xa9e6b  br       loc_A9F13
0xa9e70  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xa9e75  ldc.i4.s 0x14
0xa9e77  ldarga.s 1
0xa9e79  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa9e7e  ceq
0xa9e80  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0xa9e85  ldarga.s 1
0xa9e87  ldc.i4.s 0x16
0xa9e89  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0xa9e8e  ldloc.0
0xa9e8f  ldarg.0
0xa9e90  ldarg.1
0xa9e91  ldc.i4.s 0x12
0xa9e93  ldarg.2
0xa9e94  ldarg.3
0xa9e95  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadQueryOrParameterExpression(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, valuetype Microsoft.ReportingServices.ReportProcessing.DataType dataType, bool& isComplex, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> parametersInQuery)
0xa9e9a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_CommandText(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa9e9f  ldarga.s 1
0xa9ea1  ldc.i4.s 0x14
0xa9ea3  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0xa9ea8  br.s     loc_A9F13
0xa9eaa  ldloc.0
0xa9eab  ldarg.0
0xa9eac  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9eb1  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xa9eb6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_PreviewCommandText(string value)
0xa9ebb  br.s     loc_A9F13
0xa9ebd  ldloc.0
0xa9ebe  ldarg.0
0xa9ebf  ldarg.1
0xa9ec0  ldarg.2
0xa9ec1  ldarg.3
0xa9ec2  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadQueryParameters(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, bool& hasComplexParams, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> parametersInQuery)
0xa9ec7  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_Parameters(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> value)
0xa9ecc  br.s     loc_A9F13
0xa9ece  ldloc.0
0xa9ecf  ldarg.0
0xa9ed0  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9ed5  ldarga.s 1
0xa9ed7  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa9edc  ldarga.s 1
0xa9ede  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xa9ee3  ldarg.0
0xa9ee4  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9ee9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa9eee  callvirt instance int32 Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::ReadInteger(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName)
0xa9ef3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportQuery::set_TimeOut(int32 value)
0xa9ef8  br.s     loc_A9F13
0xa9efa  ldstr    aQuery// "Query"
0xa9eff  ldarg.0
0xa9f00  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9f05  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa9f0a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9f0f  brfalse.s loc_A9F13
0xa9f11  ldc.i4.1
0xa9f12  stloc.1
0xa9f13  ldloc.1
0xa9f14  brfalse  loc_A9DB8
0xa9f19  ldloc.0
0xa9f1a  ret
```
