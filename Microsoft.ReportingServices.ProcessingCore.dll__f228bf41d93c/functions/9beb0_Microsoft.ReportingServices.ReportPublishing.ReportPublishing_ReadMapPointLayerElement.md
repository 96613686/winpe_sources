# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointLayerElement

- ea: `0x9beb0`
- end: `0x9bf39`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointLayerElement`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x9be00`

## callees

- `0x9a580`
- `0x9b4c0`
- `0x9b540`
- `0x9beb0`
- `0x9c230`
- `0xe41e0`
- `0xe41f0`
- `0xe4210`
- `0xe4230`

## string_xrefs

- `0x9bebd`: `MapMarkerTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x9beb0  ldarg.0
0x9beb1  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9beb6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9bebb  stloc.1
0x9bebc  ldloc.1
0x9bebd  ldstr    aMapmarkertempl// "MapMarkerTemplate"
0x9bec2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bec7  brtrue.s loc_9BEE5
0x9bec9  ldloc.1
0x9beca  ldstr    aMappointrules// "MapPointRules"
0x9becf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bed4  brtrue.s loc_9BF0A
0x9bed6  ldloc.1
0x9bed7  ldstr    aMappoints// "MapPoints"
0x9bedc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bee1  brtrue.s loc_9BF1F
0x9bee3  br.s     loc_9BF2F
0x9bee5  ldarg.2
0x9bee6  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate Microsoft.ReportingServices.ReportIntermediateFormat.MapPointLayer::get_MapPointTemplate()
0x9beeb  stloc.0
0x9beec  ldarg.0
0x9beed  ldarg.2
0x9beee  ldarg.1
0x9beef  ldarg.3
0x9bef0  ldloca.s 0
0x9bef2  ldarg.0
0x9bef3  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9bef8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9befd  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapVectorLayer mapVectorLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate& symbolTemplate, string propertyName)
0x9bf02  ldarg.2
0x9bf03  ldloc.0
0x9bf04  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPointLayer::set_MapPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate value)
0x9bf09  ret
0x9bf0a  ldarg.2
0x9bf0b  ldarg.0
0x9bf0c  ldarg.2
0x9bf0d  ldarg.1
0x9bf0e  ldarg.3
0x9bf0f  ldstr    aMappointrules// "MapPointRules"
0x9bf14  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointRules Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointRules(class Microsoft.ReportingServices.ReportIntermediateFormat.MapVectorLayer mapVectorLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string tagName)
0x9bf19  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPointLayer::set_MapPointRules(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointRules value)
0x9bf1e  ret
0x9bf1f  ldarg.2
0x9bf20  ldarg.0
0x9bf21  ldarg.2
0x9bf22  ldarg.1
0x9bf23  ldarg.3
0x9bf24  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapPoint> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPoints(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointLayer mapPointLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9bf29  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPointLayer::set_MapPoints(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapPoint> value)
0x9bf2e  ret
0x9bf2f  ldarg.0
0x9bf30  ldarg.1
0x9bf31  ldarg.2
0x9bf32  ldarg.3
0x9bf33  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapVectorLayerElement(class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, class Microsoft.ReportingServices.ReportIntermediateFormat.MapVectorLayer mapVectorLayer, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9bf38  ret
```
