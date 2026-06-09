# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapTileLayerElement

- ea: `0x9c140`
- end: `0x9c224`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapTileLayerElement`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x9c0a0`

## callees

- `0x9b700`
- `0x9c020`
- `0x9c140`
- `0xac750`
- `0xb7740`
- `0xe4be0`
- `0xe4bf0`
- `0xe4c00`
- `0xe4c20`
- `0xe4c40`
- `0x1177f0`
- `0x117880`

## string_xrefs

- `0x9c14d`: `ServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0x9c140  ldarg.0
0x9c141  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9c146  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9c14b  stloc.0
0x9c14c  ldloc.0
0x9c14d  ldstr    aServiceurl// "ServiceUrl"
0x9c152  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9c157  brtrue.s loc_9C188
0x9c159  ldloc.0
0x9c15a  ldstr    aTilestyle// "TileStyle"
0x9c15f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9c164  brtrue.s loc_9C1A4
0x9c166  ldloc.0
0x9c167  ldstr    aUsesecureconne// "UseSecureConnection"
0x9c16c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9c171  brtrue.s loc_9C1F0
0x9c173  ldloc.0
0x9c174  ldstr    aMaptiles// "MapTiles"
0x9c179  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9c17e  brtrue   loc_9C20B
0x9c183  br       loc_9C21A
0x9c188  ldarg.2
0x9c189  ldarg.0
0x9c18a  ldarg.0
0x9c18b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9c190  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9c195  ldc.i4.0
0x9c196  ldc.i4.s 0x12
0x9c198  ldarg.3
0x9c199  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9c19e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::set_ServiceUrl(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9c1a3  ret
0x9c1a4  ldarg.2
0x9c1a5  ldarg.0
0x9c1a6  ldarg.0
0x9c1a7  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9c1ac  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9c1b1  ldc.i4.0
0x9c1b2  ldc.i4.s 0x12
0x9c1b4  ldarg.3
0x9c1b5  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9c1ba  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::set_TileStyle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9c1bf  ldarg.2
0x9c1c0  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::get_TileStyle()
0x9c1c5  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0x9c1ca  brtrue.s loc_9C223
0x9c1cc  ldarg.2
0x9c1cd  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::get_TileStyle()
0x9c1d2  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0x9c1d7  ldarg.0
0x9c1d8  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x9c1dd  ldarg.3
0x9c1de  ldarg.0
0x9c1df  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9c1e4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9c1e9  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateMapTileStyle(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0x9c1ee  pop
0x9c1ef  ret
0x9c1f0  ldarg.2
0x9c1f1  ldarg.0
0x9c1f2  ldarg.0
0x9c1f3  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9c1f8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9c1fd  ldc.i4.0
0x9c1fe  ldc.i4.3
0x9c1ff  ldarg.3
0x9c200  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9c205  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::set_UseSecureConnection(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9c20a  ret
0x9c20b  ldarg.2
0x9c20c  ldarg.0
0x9c20d  ldarg.1
0x9c20e  ldarg.3
0x9c20f  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapTile> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapTiles(class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9c214  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapTileLayer::set_MapTiles(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.MapTile> value)
0x9c219  ret
0x9c21a  ldarg.0
0x9c21b  ldarg.1
0x9c21c  ldarg.2
0x9c21d  ldarg.3
0x9c21e  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapLayerElement(class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, class Microsoft.ReportingServices.ReportIntermediateFormat.MapLayer mapLayer, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9c223  ret
```
