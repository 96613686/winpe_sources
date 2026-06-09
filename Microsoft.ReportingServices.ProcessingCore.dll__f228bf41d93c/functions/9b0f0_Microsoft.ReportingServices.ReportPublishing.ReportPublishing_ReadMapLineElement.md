# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapLineElement

- ea: `0x9b0f0`
- end: `0x9b150`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapLineElement`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b080`

## callees

- `0x9a8f0`
- `0x9b0f0`
- `0x9b380`
- `0xac750`
- `0xeb600`
- `0xeb620`

## string_xrefs

- `0x9b10a`: `MapLineTemplate`
- `0x9b0fd`: `UseCustomLineTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x9b0f0  ldarg.0
0x9b0f1  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9b0f6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9b0fb  stloc.0
0x9b0fc  ldloc.0
0x9b0fd  ldstr    aUsecustomlinet// "UseCustomLineTemplate"
0x9b102  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9b107  brtrue.s loc_9B118
0x9b109  ldloc.0
0x9b10a  ldstr    aMaplinetemplat// "MapLineTemplate"
0x9b10f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9b114  brtrue.s loc_9B134
0x9b116  br.s     loc_9B145
0x9b118  ldarg.3
0x9b119  ldarg.0
0x9b11a  ldarg.0
0x9b11b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9b120  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9b125  ldc.i4.0
0x9b126  ldc.i4.3
0x9b127  ldarg.s  4
0x9b129  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9b12e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapLine::set_UseCustomLineTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9b133  ret
0x9b134  ldarg.3
0x9b135  ldarg.0
0x9b136  ldarg.1
0x9b137  ldarg.2
0x9b138  ldarg.s  4
0x9b13a  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapLineTemplate Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapLineTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapLineLayer mapLineLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9b13f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapLine::set_MapLineTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapLineTemplate value)
0x9b144  ret
0x9b145  ldarg.0
0x9b146  ldarg.2
0x9b147  ldarg.3
0x9b148  ldarg.s  4
0x9b14a  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapSpatialElementElement(class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, class Microsoft.ReportingServices.ReportIntermediateFormat.MapSpatialElement mapSpatialElement, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9b14f  ret
```
