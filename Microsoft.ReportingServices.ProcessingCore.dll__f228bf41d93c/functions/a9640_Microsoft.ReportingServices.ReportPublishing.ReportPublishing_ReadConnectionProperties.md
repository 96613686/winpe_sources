# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadConnectionProperties

- ea: `0xa9640`
- end: `0xa9776`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadConnectionProperties`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0xaab40`

## callees

- `0xa9640`
- `0xac9b0`
- `0xadae0`
- `0xbb940`
- `0xbcdc0`
- `0xbcde0`
- `0x113250`
- `0x113260`
- `0x113270`
- `0x113290`
- `0x1132b0`
- `0x1177f0`
- `0x1179c0`
- `0x170830`

## string_xrefs

- `0xa9692`: `IntegratedSecurity`

## pseudocode

```c

```

## disassembly

```asm
0xa9640  ldc.i4.0
0xa9641  stloc.0
0xa9642  ldarg.0
0xa9643  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9648  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa964d  pop
0xa964e  ldarg.0
0xa964f  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9654  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa9659  stloc.1
0xa965a  ldloc.1
0xa965b  ldc.i4.1
0xa965c  beq.s    loc_A966B
0xa965e  ldloc.1
0xa965f  ldc.i4.s 0xF
0xa9661  beq      loc_A9756
0xa9666  br       loc_A976F
0xa966b  ldarg.0
0xa966c  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9671  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa9676  stloc.2
0xa9677  ldloc.2
0xa9678  ldstr    aDataprovider// "DataProvider"
0xa967d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa9682  brtrue.s loc_A96B3
0xa9684  ldloc.2
0xa9685  ldstr    aConnectstring// "ConnectString"
0xa968a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa968f  brtrue.s loc_A96C9
0xa9691  ldloc.2
0xa9692  ldstr    aIntegratedsecu// "IntegratedSecurity"
0xa9697  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa969c  brtrue.s loc_A9717
0xa969e  ldloc.2
0xa969f  ldstr    aPrompt// "Prompt"
0xa96a4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa96a9  brtrue   loc_A9743
0xa96ae  br       loc_A976F
0xa96b3  ldarg.1
0xa96b4  ldarg.0
0xa96b5  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa96ba  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xa96bf  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::set_Type(string value)
0xa96c4  br       loc_A976F
0xa96c9  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xa96ce  ldc.i4.s 0x13
0xa96d0  ldarga.s 2
0xa96d2  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa96d7  ceq
0xa96d9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0xa96de  ldarg.1
0xa96df  ldarg.0
0xa96e0  ldarg.2
0xa96e1  ldc.i4.s 0x12
0xa96e3  ldarg.3
0xa96e4  ldarg.s  4
0xa96e6  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadQueryOrParameterExpression(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, valuetype Microsoft.ReportingServices.ReportProcessing.DataType dataType, bool& isComplex, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> parametersInQuery)
0xa96eb  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::set_ConnectStringExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa96f0  ldarg.1
0xa96f1  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_ConnectStringExpression()
0xa96f6  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa96fb  brtrue.s loc_A976F
0xa96fd  ldarg.1
0xa96fe  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::get_ConnectStringExpression()
0xa9703  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_OriginalText()
0xa9708  call     bool Microsoft.ReportingServices.DataExtensions.DataSourceInfo::HasUseridReference(string connectionString)
0xa970d  brfalse.s loc_A976F
0xa970f  ldarg.0
0xa9710  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::SetConnectionStringUserProfileDependency()
0xa9715  br.s     loc_A976F
0xa9717  ldarg.1
0xa9718  ldarg.0
0xa9719  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa971e  ldarga.s 2
0xa9720  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa9725  ldarga.s 2
0xa9727  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xa972c  ldarg.0
0xa972d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9732  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa9737  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::ReadBoolean(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName)
0xa973c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::set_IntegratedSecurity(bool value)
0xa9741  br.s     loc_A976F
0xa9743  ldarg.1
0xa9744  ldarg.0
0xa9745  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa974a  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xa974f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.DataSource::set_Prompt(string value)
0xa9754  br.s     loc_A976F
0xa9756  ldstr    aConnectionprop// "ConnectionProperties"
0xa975b  ldarg.0
0xa975c  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa9761  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa9766  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa976b  brfalse.s loc_A976F
0xa976d  ldc.i4.1
0xa976e  stloc.0
0xa976f  ldloc.0
0xa9770  brfalse  loc_A9642
0xa9775  ret
```
