# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointElement

- ea: `0x9b440`
- end: `0x9b4b5`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointElement`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b3d0`

## callees

- `0x9b380`
- `0x9b440`
- `0x9b540`
- `0xac750`
- `0xec290`
- `0xec2a0`
- `0xec2b0`

## string_xrefs

- `0x9b45a`: `MapMarkerTemplate`
- `0x9b44d`: `UseCustomPointTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x9b440  ldarg.0
0x9b441  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9b446  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9b44b  stloc.1
0x9b44c  ldloc.1
0x9b44d  ldstr    aUsecustompoint// "UseCustomPointTemplate"
0x9b452  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9b457  brtrue.s loc_9B468
0x9b459  ldloc.1
0x9b45a  ldstr    aMapmarkertempl// "MapMarkerTemplate"
0x9b45f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9b464  brtrue.s loc_9B484
0x9b466  br.s     loc_9B4AA
0x9b468  ldarg.3
0x9b469  ldarg.0
0x9b46a  ldarg.0
0x9b46b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9b470  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9b475  ldc.i4.0
0x9b476  ldc.i4.3
0x9b477  ldarg.s  4
0x9b479  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9b47e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPoint::set_UseCustomPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9b483  ret
0x9b484  ldarg.3
0x9b485  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate Microsoft.ReportingServices.ReportIntermediateFormat.MapPoint::get_MapPointTemplate()
0x9b48a  stloc.0
0x9b48b  ldarg.0
0x9b48c  ldarg.1
0x9b48d  ldarg.2
0x9b48e  ldarg.s  4
0x9b490  ldloca.s 0
0x9b492  ldarg.0
0x9b493  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9b498  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9b49d  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapVectorLayer mapVectorLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate& symbolTemplate, string propertyName)
0x9b4a2  ldarg.3
0x9b4a3  ldloc.0
0x9b4a4  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPoint::set_MapPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate value)
0x9b4a9  ret
0x9b4aa  ldarg.0
0x9b4ab  ldarg.2
0x9b4ac  ldarg.3
0x9b4ad  ldarg.s  4
0x9b4af  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapSpatialElementElement(class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, class Microsoft.ReportingServices.ReportIntermediateFormat.MapSpatialElement mapSpatialElement, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9b4b4  ret
```
