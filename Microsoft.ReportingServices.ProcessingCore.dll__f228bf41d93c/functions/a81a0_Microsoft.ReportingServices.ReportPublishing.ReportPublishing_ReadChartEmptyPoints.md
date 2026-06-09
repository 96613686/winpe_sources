# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartEmptyPoints

- ea: `0xa81a0`
- end: `0xa83be`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartEmptyPoints`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0xa6830`

## callees

- `0x9f6f0`
- `0x9f8c0`
- `0xa7170`
- `0xa7320`
- `0xa81a0`
- `0xac750`
- `0xb0fd0`
- `0xbcdc0`
- `0xbcde0`
- `0xbce20`
- `0xbe1c0`
- `0xbe2b0`
- `0xbf370`
- `0x1025b0`
- `0x1025e0`
- `0x102630`
- `0x102650`
- `0x102670`
- `0x102690`
- `0x1026b0`
- `0x1079e0`

## string_xrefs

- `0xa839d`: `ChartEmptyPoints`

## pseudocode

```c

```

## disassembly

```asm
0xa81a0  ldarg.1
0xa81a1  ldarg.2
0xa81a2  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartEmptyPoints::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart, class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries chartSeries)
0xa81a7  stloc.0
0xa81a8  ldarg.0
0xa81a9  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa81ae  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa81b3  brtrue   loc_A83BC
0xa81b8  ldc.i4.0
0xa81b9  stloc.1
0xa81ba  ldc.i4.0
0xa81bb  stloc.2
0xa81bc  ldarg.0
0xa81bd  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa81c2  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa81c7  pop
0xa81c8  ldarg.0
0xa81c9  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa81ce  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa81d3  stloc.3
0xa81d4  ldloc.3
0xa81d5  ldc.i4.1
0xa81d6  beq.s    loc_A81E5
0xa81d8  ldloc.3
0xa81d9  ldc.i4.s 0xF
0xa81db  beq      loc_A839D
0xa81e0  br       loc_A83B6
0xa81e5  ldarg.0
0xa81e6  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa81eb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa81f0  stloc.s  5
0xa81f2  ldloc.s  5
0xa81f4  brfalse  loc_A83B6
0xa81f9  ldloc.s  5
0xa81fb  call     instance int32 [mscorlib]System.String::get_Length()
0xa8200  stloc.s  6
0xa8202  ldloc.s  6
0xa8204  ldc.i4.5
0xa8205  sub
0xa8206  switch   loc_A8240, loc_A83B6, loc_A82C4, loc_A83B6, loc_A8298, loc_A8256, loc_A826C, loc_A83B6, loc_A83B6, loc_A8282, loc_A83B6, loc_A82AE
0xa823b  br       loc_A83B6
0xa8240  ldloc.s  5
0xa8242  ldstr    aStyle_1// "Style"
0xa8247  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa824c  brtrue   loc_A82DA
0xa8251  br       loc_A83B6
0xa8256  ldloc.s  5
0xa8258  ldstr    aActioninfo// "ActionInfo"
0xa825d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa8262  brtrue   loc_A831A
0xa8267  br       loc_A83B6
0xa826c  ldloc.s  5
0xa826e  ldstr    aChartmarker// "ChartMarker"
0xa8273  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa8278  brtrue   loc_A8330
0xa827d  br       loc_A83B6
0xa8282  ldloc.s  5
0xa8284  ldstr    aChartdatalabel// "ChartDataLabel"
0xa8289  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa828e  brtrue   loc_A8342
0xa8293  br       loc_A83B6
0xa8298  ldloc.s  5
0xa829a  ldstr    aAxislabel// "AxisLabel"
0xa829f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa82a4  brtrue   loc_A8354
0xa82a9  br       loc_A83B6
0xa82ae  ldloc.s  5
0xa82b0  ldstr    aCustomproperti// "CustomProperties"
0xa82b5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa82ba  brtrue   loc_A8371
0xa82bf  br       loc_A83B6
0xa82c4  ldloc.s  5
0xa82c6  ldstr    aTooltip// "ToolTip"
0xa82cb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa82d0  brtrue   loc_A8380
0xa82d5  br       loc_A83B6
0xa82da  ldarg.0
0xa82db  ldarg.3
0xa82dc  call     instance class Microsoft.ReportingServices.ReportPublishing.StyleInformation Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadStyle(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa82e1  stloc.s  4
0xa82e3  ldloc.s  4
0xa82e5  ldc.i4.s 0xB
0xa82e7  ldc.i4.0
0xa82e8  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::Filter(valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType ownerType, bool hasNoRows)
0xa82ed  ldloc.0
0xa82ee  ldloc.s  4
0xa82f0  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> Microsoft.ReportingServices.ReportPublishing.StyleInformation::get_Attributes()
0xa82f5  ldarga.s 3
0xa82f7  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa82fc  ldarga.s 3
0xa82fe  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xa8303  ldc.i4.1
0xa8304  ldarga.s 3
0xa8306  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa830b  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle(class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> attributes, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, bool isDynamicImageSubElement, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa8310  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartStyleContainer::set_StyleClass(class Microsoft.ReportingServices.ReportIntermediateFormat.Style value)
0xa8315  br       loc_A83B6
0xa831a  ldloc.0
0xa831b  ldarg.0
0xa831c  ldarg.3
0xa831d  ldc.i4.s 0xB
0xa831f  ldloca.s 2
0xa8321  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Action Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadActionInfo(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType styleOwnerType, [out] bool& computed)
0xa8326  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartEmptyPoints::set_Action(class Microsoft.ReportingServices.ReportIntermediateFormat.Action value)
0xa832b  br       loc_A83B6
0xa8330  ldloc.0
0xa8331  ldarg.0
0xa8332  ldarg.1
0xa8333  ldarg.2
0xa8334  ldnull
0xa8335  ldarg.3
0xa8336  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ChartMarker Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartMarker(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart, class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries series, class Microsoft.ReportingServices.ReportIntermediateFormat.ChartDataPoint dataPoint, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa833b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartEmptyPoints::set_Marker(class Microsoft.ReportingServices.ReportIntermediateFormat.ChartMarker value)
0xa8340  br.s     loc_A83B6
0xa8342  ldloc.0
0xa8343  ldarg.0
0xa8344  ldarg.1
0xa8345  ldarg.2
0xa8346  ldnull
0xa8347  ldarg.3
0xa8348  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ChartDataLabel Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartDataLabel(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart, class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries series, class Microsoft.ReportingServices.ReportIntermediateFormat.ChartDataPoint dataPoint, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa834d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartEmptyPoints::set_DataLabel(class Microsoft.ReportingServices.ReportIntermediateFormat.ChartDataLabel value)
0xa8352  br.s     loc_A83B6
0xa8354  ldloc.0
0xa8355  ldarg.0
0xa8356  ldarg.0
0xa8357  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa835c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa8361  ldc.i4.0
0xa8362  ldc.i4.s 0x12
0xa8364  ldarg.3
0xa8365  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa836a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartEmptyPoints::set_AxisLabel(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa836f  br.s     loc_A83B6
0xa8371  ldloc.0
0xa8372  ldarg.0
0xa8373  ldarg.3
0xa8374  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataValueList Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadCustomProperties(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa8379  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartEmptyPoints::set_CustomProperties(class Microsoft.ReportingServices.ReportIntermediateFormat.DataValueList value)
0xa837e  br.s     loc_A83B6
0xa8380  ldloc.0
0xa8381  ldarg.0
0xa8382  ldarg.0
0xa8383  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa8388  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa838d  ldc.i4.0
0xa838e  ldc.i4.s 0x12
0xa8390  ldarg.3
0xa8391  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa8396  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartEmptyPoints::set_ToolTip(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa839b  br.s     loc_A83B6
0xa839d  ldstr    aChartemptypoin// "ChartEmptyPoints"
0xa83a2  ldarg.0
0xa83a3  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa83a8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa83ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa83b2  brfalse.s loc_A83B6
0xa83b4  ldc.i4.1
0xa83b5  stloc.1
0xa83b6  ldloc.1
0xa83b7  brfalse  loc_A81BC
0xa83bc  ldloc.0
0xa83bd  ret
```
