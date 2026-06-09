# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPolygonElement

- ea: `0x9b240`
- end: `0x9b2fc`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPolygonElement`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b1d0`

## callees

- `0x9aa00`
- `0x9b240`
- `0x9b380`
- `0x9b540`
- `0xac750`
- `0xeb930`
- `0xeb950`
- `0xeb970`
- `0xeb980`
- `0xeb990`

## string_xrefs

- `0x9b25a`: `MapPolygonTemplate`
- `0x9b274`: `MapMarkerTemplate`
- `0x9b24d`: `UseCustomPolygonTemplate`
- `0x9b267`: `UseCustomCenterPointTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x9b240  ldarg.0
0x9b241  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9b246  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9b24b  stloc.1
0x9b24c  ldloc.1
0x9b24d  ldstr    aUsecustompolyg// "UseCustomPolygonTemplate"
0x9b252  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9b257  brtrue.s loc_9B282
0x9b259  ldloc.1
0x9b25a  ldstr    aMappolygontemp// "MapPolygonTemplate"
0x9b25f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9b264  brtrue.s loc_9B29E
0x9b266  ldloc.1
0x9b267  ldstr    aUsecustomcente// "UseCustomCenterPointTemplate"
0x9b26c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9b271  brtrue.s loc_9B2AF
0x9b273  ldloc.1
0x9b274  ldstr    aMapmarkertempl// "MapMarkerTemplate"
0x9b279  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9b27e  brtrue.s loc_9B2CB
0x9b280  br.s     loc_9B2F1
0x9b282  ldarg.3
0x9b283  ldarg.0
0x9b284  ldarg.0
0x9b285  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9b28a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9b28f  ldc.i4.0
0x9b290  ldc.i4.3
0x9b291  ldarg.s  4
0x9b293  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9b298  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::set_UseCustomPolygonTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9b29d  ret
0x9b29e  ldarg.3
0x9b29f  ldarg.0
0x9b2a0  ldarg.1
0x9b2a1  ldarg.2
0x9b2a2  ldarg.s  4
0x9b2a4  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonTemplate Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPolygonTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer mapPolygonLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9b2a9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::set_MapPolygonTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonTemplate value)
0x9b2ae  ret
0x9b2af  ldarg.3
0x9b2b0  ldarg.0
0x9b2b1  ldarg.0
0x9b2b2  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9b2b7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9b2bc  ldc.i4.0
0x9b2bd  ldc.i4.3
0x9b2be  ldarg.s  4
0x9b2c0  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9b2c5  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::set_UseCustomCenterPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9b2ca  ret
0x9b2cb  ldarg.3
0x9b2cc  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::get_MapCenterPointTemplate()
0x9b2d1  stloc.0
0x9b2d2  ldarg.0
0x9b2d3  ldarg.1
0x9b2d4  ldarg.2
0x9b2d5  ldarg.s  4
0x9b2d7  ldloca.s 0
0x9b2d9  ldarg.0
0x9b2da  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9b2df  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9b2e4  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapVectorLayer mapVectorLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate& symbolTemplate, string propertyName)
0x9b2e9  ldarg.3
0x9b2ea  ldloc.0
0x9b2eb  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon::set_MapCenterPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate value)
0x9b2f0  ret
0x9b2f1  ldarg.0
0x9b2f2  ldarg.2
0x9b2f3  ldarg.3
0x9b2f4  ldarg.s  4
0x9b2f6  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapSpatialElementElement(class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, class Microsoft.ReportingServices.ReportIntermediateFormat.MapSpatialElement mapSpatialElement, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9b2fb  ret
```
