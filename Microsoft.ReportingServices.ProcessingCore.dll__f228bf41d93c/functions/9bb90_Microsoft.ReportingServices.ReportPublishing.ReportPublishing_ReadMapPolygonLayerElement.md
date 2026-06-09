# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPolygonLayerElement

- ea: `0x9bb90`
- end: `0x9bc53`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPolygonLayerElement`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x9bae0`

## callees

- `0x99ff0`
- `0x9a580`
- `0x9aa00`
- `0x9b300`
- `0x9b540`
- `0x9bb90`
- `0x9c230`
- `0xe3000`
- `0xe3020`
- `0xe3030`
- `0xe3040`
- `0xe3060`
- `0xe3080`

## string_xrefs

- `0x9bb9d`: `MapPolygonTemplate`
- `0x9bbb7`: `MapMarkerTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x9bb90  ldarg.0
0x9bb91  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9bb96  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9bb9b  stloc.1
0x9bb9c  ldloc.1
0x9bb9d  ldstr    aMappolygontemp// "MapPolygonTemplate"
0x9bba2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bba7  brtrue.s loc_9BBDF
0x9bba9  ldloc.1
0x9bbaa  ldstr    aMappolygonrule// "MapPolygonRules"
0x9bbaf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bbb4  brtrue.s loc_9BBEF
0x9bbb6  ldloc.1
0x9bbb7  ldstr    aMapmarkertempl// "MapMarkerTemplate"
0x9bbbc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bbc1  brtrue.s loc_9BBFF
0x9bbc3  ldloc.1
0x9bbc4  ldstr    aMapcenterpoint// "MapCenterPointRules"
0x9bbc9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bbce  brtrue.s loc_9BC24
0x9bbd0  ldloc.1
0x9bbd1  ldstr    aMappolygons// "MapPolygons"
0x9bbd6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9bbdb  brtrue.s loc_9BC39
0x9bbdd  br.s     loc_9BC49
0x9bbdf  ldarg.2
0x9bbe0  ldarg.0
0x9bbe1  ldarg.2
0x9bbe2  ldarg.1
0x9bbe3  ldarg.3
0x9bbe4  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonTemplate Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPolygonTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer mapPolygonLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9bbe9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer::set_MapPolygonTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonTemplate value)
0x9bbee  ret
0x9bbef  ldarg.2
0x9bbf0  ldarg.0
0x9bbf1  ldarg.2
0x9bbf2  ldarg.1
0x9bbf3  ldarg.3
0x9bbf4  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonRules Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPolygonRules(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer mapPolygonLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9bbf9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer::set_MapPolygonRules(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonRules value)
0x9bbfe  ret
0x9bbff  ldarg.2
0x9bc00  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer::get_MapCenterPointTemplate()
0x9bc05  stloc.0
0x9bc06  ldarg.0
0x9bc07  ldarg.2
0x9bc08  ldarg.1
0x9bc09  ldarg.3
0x9bc0a  ldloca.s 0
0x9bc0c  ldarg.0
0x9bc0d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9bc12  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9bc17  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapVectorLayer mapVectorLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate& symbolTemplate, string propertyName)
0x9bc1c  ldarg.2
0x9bc1d  ldloc.0
0x9bc1e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer::set_MapCenterPointTemplate(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointTemplate value)
0x9bc23  ret
0x9bc24  ldarg.2
0x9bc25  ldarg.0
0x9bc26  ldarg.2
0x9bc27  ldarg.1
0x9bc28  ldarg.3
0x9bc29  ldstr    aMapcenterpoint// "MapCenterPointRules"
0x9bc2e  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointRules Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPointRules(class Microsoft.ReportingServices.ReportIntermediateFormat.MapVectorLayer mapVectorLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string tagName)
0x9bc33  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer::set_MapCenterPointRules(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPointRules value)
0x9bc38  ret
0x9bc39  ldarg.2
0x9bc3a  ldarg.0
0x9bc3b  ldarg.2
0x9bc3c  ldarg.1
0x9bc3d  ldarg.3
0x9bc3e  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapPolygons(class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer mapPolygonLayer, class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9bc43  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygonLayer::set_MapPolygons(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapPolygon> value)
0x9bc48  ret
0x9bc49  ldarg.0
0x9bc4a  ldarg.1
0x9bc4b  ldarg.2
0x9bc4c  ldarg.3
0x9bc4d  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapVectorLayerElement(class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, class Microsoft.ReportingServices.ReportIntermediateFormat.MapVectorLayer mapVectorLayer, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9bc52  ret
```
