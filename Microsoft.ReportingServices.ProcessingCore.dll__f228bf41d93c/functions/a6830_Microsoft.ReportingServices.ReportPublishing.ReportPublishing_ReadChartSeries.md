# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartSeries

- ea: `0xa6830`
- end: `0xa6d3c`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartSeries`
- size: `1292`
- prototype: ``
- caller_count: `2`
- callee_count: `45`
- tags: `service_task, broker_com_uri`

## callers

- `0xa5a30`
- `0xa6330`

## callees

- `0x9d040`
- `0x9f6f0`
- `0xa4140`
- `0xa6830`
- `0xa6d40`
- `0xa7170`
- `0xa7320`
- `0xa8070`
- `0xa81a0`
- `0xac750`
- `0xb0fd0`
- `0xb8750`
- `0xb87d0`
- `0xbcdc0`
- `0xbcde0`
- `0xbce20`
- `0xbd050`
- `0xbd070`
- `0xbe1c0`
- `0xbe2b0`
- `0xbe3d0`
- `0xbf370`
- `0xc17c0`
- `0x100da0`
- `0x100dd0`
- `0x100e30`
- `0x100e90`
- `0x100ea0`
- `0x100ec0`
- `0x100ee0`
- `0x100f00`
- `0x100f40`
- `0x100f60`
- `0x100f80`
- `0x100fa0`
- `0x100fc0`
- `0x100fe0`
- `0x100ff0`
- `0x101000`
- `0x101070`
- `0x101150`
- `0x101170`
- `0x1177f0`
- `0x117880`
- `0x124ca0`

## string_xrefs

- `0xa69b8`: `ChartEmptyPoints`

## pseudocode

```c

```

## disassembly

```asm
0xa6830  ldarg.1
0xa6831  ldarg.2
0xa6832  ldarg.0
0xa6833  call     instance int32 Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GenerateID()
0xa6838  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart, class Microsoft.ReportingServices.ReportIntermediateFormat.ChartDerivedSeries parentDerivedSeries, int32 id)
0xa683d  stloc.0
0xa683e  ldloc.0
0xa683f  ldarg.0
0xa6840  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa6845  ldstr    aName_1// "Name"
0xa684a  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa684f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::set_Name(string value)
0xa6854  ldloc.0
0xa6855  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::get_Name()
0xa685a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa685f  brtrue.s loc_A6884
0xa6861  ldarg.s  5
0xa6863  ldc.i4.0
0xa6864  ldstr    aChartseries// "ChartSeries"
0xa6869  ldc.i4.s 0x10
0xa686b  ldarg.1
0xa686c  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0xa6871  ldloc.0
0xa6872  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::get_Name()
0xa6877  ldarga.s 3
0xa6879  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa687e  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.DynamicImageOrCustomUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyNameValue, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa6883  pop
0xa6884  ldarg.0
0xa6885  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa688a  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa688f  brtrue   loc_A6D3A
0xa6894  ldnull
0xa6895  stloc.1
0xa6896  ldc.i4.0
0xa6897  stloc.2
0xa6898  ldarg.0
0xa6899  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa689e  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa68a3  pop
0xa68a4  ldarg.0
0xa68a5  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa68aa  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa68af  stloc.3
0xa68b0  ldloc.3
0xa68b1  ldc.i4.1
0xa68b2  beq.s    loc_A68C1
0xa68b4  ldloc.3
0xa68b5  ldc.i4.s 0xF
0xa68b7  beq      loc_A6D1B
0xa68bc  br       loc_A6D34
0xa68c1  ldarg.0
0xa68c2  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa68c7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa68cc  stloc.s  6
0xa68ce  ldloc.s  6
0xa68d0  brfalse  loc_A6D34
0xa68d5  ldloc.s  6
0xa68d7  call     instance int32 [mscorlib]System.String::get_Length()
0xa68dc  stloc.s  7
0xa68de  ldloc.s  7
0xa68e0  ldc.i4.4
0xa68e1  sub
0xa68e2  switch   loc_A6A0E, loc_A698A, loc_A6A7C, loc_A6A24, loc_A6D34, loc_A6D34, loc_A6A3A, loc_A6AA8, loc_A6D34, loc_A6969, loc_A6A92, loc_A6948, loc_A6924, loc_A6ABE
0xa691f  br       loc_A6D34
0xa6924  ldloc.s  6
0xa6926  ldc.i4.1
0xa6927  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa692c  stloc.s  8
0xa692e  ldloc.s  8
0xa6930  ldc.i4.s 0x61
0xa6932  beq      loc_A69CC
0xa6937  ldloc.s  8
0xa6939  ldc.i4.s 0x68
0xa693b  beq.s    loc_A69B6
0xa693d  ldloc.s  8
0xa693f  ldc.i4.s 0x75
0xa6941  beq.s    loc_A69A0
0xa6943  br       loc_A6D34
0xa6948  ldloc.s  6
0xa694a  ldc.i4.5
0xa694b  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa6950  stloc.s  8
0xa6952  ldloc.s  8
0xa6954  ldc.i4.s 0x44
0xa6956  beq      loc_A69E2
0xa695b  ldloc.s  8
0xa695d  ldc.i4.s 0x53
0xa695f  beq      loc_A69F8
0xa6964  br       loc_A6D34
0xa6969  ldloc.s  6
0xa696b  ldc.i4.0
0xa696c  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa6971  stloc.s  8
0xa6973  ldloc.s  8
0xa6975  ldc.i4.s 0x43
0xa6977  beq      loc_A6A50
0xa697c  ldloc.s  8
0xa697e  ldc.i4.s 0x56
0xa6980  beq      loc_A6A66
0xa6985  br       loc_A6D34
0xa698a  ldloc.s  6
0xa698c  ldstr    aStyle_1// "Style"
0xa6991  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6996  brtrue   loc_A6AD4
0xa699b  br       loc_A6D34
0xa69a0  ldloc.s  6
0xa69a2  ldstr    aCustomproperti// "CustomProperties"
0xa69a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa69ac  brtrue   loc_A6B20
0xa69b1  br       loc_A6D34
0xa69b6  ldloc.s  6
0xa69b8  ldstr    aChartemptypoin// "ChartEmptyPoints"
0xa69bd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa69c2  brtrue   loc_A6C1E
0xa69c7  br       loc_A6D34
0xa69cc  ldloc.s  6
0xa69ce  ldstr    aCategoryaxisna// "CategoryAxisName"
0xa69d3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa69d8  brtrue   loc_A6C92
0xa69dd  br       loc_A6D34
0xa69e2  ldloc.s  6
0xa69e4  ldstr    aChartdatapoint// "ChartDataPoints"
0xa69e9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa69ee  brtrue   loc_A6B32
0xa69f3  br       loc_A6D34
0xa69f8  ldloc.s  6
0xa69fa  ldstr    aChartsmartlabe// "ChartSmartLabel"
0xa69ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6a04  brtrue   loc_A6CCE
0xa6a09  br       loc_A6D34
0xa6a0e  ldloc.s  6
0xa6a10  ldstr    aType_0// "Type"
0xa6a15  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6a1a  brtrue   loc_A6B47
0xa6a1f  br       loc_A6D34
0xa6a24  ldloc.s  6
0xa6a26  ldstr    aSubtype// "Subtype"
0xa6a2b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6a30  brtrue   loc_A6B9B
0xa6a35  br       loc_A6D34
0xa6a3a  ldloc.s  6
0xa6a3c  ldstr    aLegendname// "LegendName"
0xa6a41  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6a46  brtrue   loc_A6C32
0xa6a4b  br       loc_A6D34
0xa6a50  ldloc.s  6
0xa6a52  ldstr    aChartareaname// "ChartAreaName"
0xa6a57  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6a5c  brtrue   loc_A6C52
0xa6a61  br       loc_A6D34
0xa6a66  ldloc.s  6
0xa6a68  ldstr    aValueaxisname// "ValueAxisName"
0xa6a6d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6a72  brtrue   loc_A6C72
0xa6a77  br       loc_A6D34
0xa6a7c  ldloc.s  6
0xa6a7e  ldstr    aHidden// "Hidden"
0xa6a83  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6a88  brtrue   loc_A6CB2
0xa6a8d  br       loc_A6D34
0xa6a92  ldloc.s  6
0xa6a94  ldstr    aChartdatalabel// "ChartDataLabel"
0xa6a99  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6a9e  brtrue   loc_A6CDF
0xa6aa3  br       loc_A6D34
0xa6aa8  ldloc.s  6
0xa6aaa  ldstr    aChartmarker// "ChartMarker"
0xa6aaf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6ab4  brtrue   loc_A6CF4
0xa6ab9  br       loc_A6D34
0xa6abe  ldloc.s  6
0xa6ac0  ldstr    aChartiteminleg// "ChartItemInLegend"
0xa6ac5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6aca  brtrue   loc_A6D09
0xa6acf  br       loc_A6D34
0xa6ad4  ldarg.0
0xa6ad5  ldarg.3
0xa6ad6  call     instance class Microsoft.ReportingServices.ReportPublishing.StyleInformation Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadStyle(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa6adb  stloc.s  4
0xa6add  ldarg.2
0xa6ade  brfalse.s loc_A6AEC
0xa6ae0  ldloc.s  4
0xa6ae2  ldc.i4.s 0xB
0xa6ae4  ldc.i4.0
0xa6ae5  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::Filter(valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType ownerType, bool hasNoRows)
0xa6aea  br.s     loc_A6AF3
0xa6aec  ldloc.s  4
0xa6aee  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::FilterChartSeriesStyle()
0xa6af3  ldloc.0
0xa6af4  ldloc.s  4
0xa6af6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> Microsoft.ReportingServices.ReportPublishing.StyleInformation::get_Attributes()
0xa6afb  ldarga.s 3
0xa6afd  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa6b02  ldarga.s 3
0xa6b04  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xa6b09  ldc.i4.1
0xa6b0a  ldarga.s 3
0xa6b0c  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa6b11  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle(class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> attributes, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, bool isDynamicImageSubElement, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa6b16  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::set_StyleClass(class Microsoft.ReportingServices.ReportIntermediateFormat.Style value)
0xa6b1b  br       loc_A6D34
0xa6b20  ldloc.0
0xa6b21  ldarg.0
0xa6b22  ldarg.3
0xa6b23  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.DataValueList Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadCustomProperties(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa6b28  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::set_CustomProperties(class Microsoft.ReportingServices.ReportIntermediateFormat.DataValueList value)
0xa6b2d  br       loc_A6D34
0xa6b32  ldloc.0
0xa6b33  ldarg.0
0xa6b34  ldarg.1
0xa6b35  ldarg.3
0xa6b36  ldarg.s  4
0xa6b38  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ChartDataPointList Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartDataPoints(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, bool& hasAggregates)
0xa6b3d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::set_DataPoints(class Microsoft.ReportingServices.ReportIntermediateFormat.ChartDataPointList value)
0xa6b42  br       loc_A6D34
0xa6b47  ldloc.0
0xa6b48  ldarg.0
0xa6b49  ldarg.0
0xa6b4a  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa6b4f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa6b54  ldc.i4.0
0xa6b55  ldc.i4.s 0x12
0xa6b57  ldarg.3
0xa6b58  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa6b5d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::set_Type(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa6b62  ldloc.0
0xa6b63  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::get_Type()
0xa6b68  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa6b6d  brtrue   loc_A6D34
0xa6b72  ldloc.0
0xa6b73  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::get_Type()
0xa6b78  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0xa6b7d  ldarga.s 3
0xa6b7f  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa6b84  ldarg.3
0xa6b85  ldarg.0
0xa6b86  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa6b8b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa6b90  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartSeriesType(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xa6b95  pop
0xa6b96  br       loc_A6D34
0xa6b9b  ldarg.0
0xa6b9c  ldarg.0
0xa6b9d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa6ba2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa6ba7  ldc.i4.0
0xa6ba8  ldc.i4.s 0x12
0xa6baa  ldarg.3
0xa6bab  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa6bb0  stloc.s  5
0xa6bb2  ldloc.s  5
0xa6bb4  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa6bb9  brtrue.s loc_A6BE6
0xa6bbb  ldloc.s  5
0xa6bbd  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0xa6bc2  ldarga.s 3
0xa6bc4  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa6bc9  ldarg.3
0xa6bca  ldarg.0
0xa6bcb  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa6bd0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa6bd5  ldarg.0
0xa6bd6  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa6bdb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa6be0  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartSeriesSubtype(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName, string elementNamespace)
0xa6be5  pop
0xa6be6  ldloc.1
0xa6be7  brfalse.s loc_A6C05
0xa6be9  call     class Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::get_Instance()
0xa6bee  ldarg.0
0xa6bef  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa6bf4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa6bf9  ldloc.1
0xa6bfa  callvirt instance int32 Microsoft.ReportingServices.ReportPublishing.RdlNamespaceComparer::Compare(string x, string y)
0xa6bff  ldc.i4.0
0xa6c00  ble      loc_A6D34
0xa6c05  ldloc.0
0xa6c06  ldloc.s  5
0xa6c08  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::set_Subtype(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa6c0d  ldarg.0
0xa6c0e  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa6c13  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa6c18  stloc.1
0xa6c19  br       loc_A6D34
0xa6c1e  ldloc.0
0xa6c1f  ldarg.0
0xa6c20  ldarg.1
0xa6c21  ldloc.0
0xa6c22  ldarg.3
0xa6c23  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ChartEmptyPoints Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartEmptyPoints(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart, class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries series, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa6c28  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries::set_EmptyPoints(class Microsoft.ReportingServices.ReportIntermediateFormat.ChartEmptyPoints value)
0xa6c2d  br       loc_A6D34
0xa6c32  ldloc.0
0xa6c33  ldarg.0
0xa6c34  ldarg.0
0xa6c35  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa6c3a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa6c3f  ldc.i4.0
0xa6c40  ldc.i4.s 0x12
  ... truncated ...
```
