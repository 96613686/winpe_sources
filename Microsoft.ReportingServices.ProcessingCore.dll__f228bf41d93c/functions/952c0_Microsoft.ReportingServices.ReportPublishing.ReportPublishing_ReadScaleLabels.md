# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadScaleLabels

- ea: `0x952c0`
- end: `0x9564e`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadScaleLabels`
- size: `910`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x92530`
- `0x94af0`

## callees

- `0x952c0`
- `0xac750`
- `0xb0fd0`
- `0xb6840`
- `0xbcdc0`
- `0xbcde0`
- `0xbe1c0`
- `0xbe2b0`
- `0xbf370`
- `0xcfe90`
- `0xcfeb0`
- `0xcfed0`
- `0xcfef0`
- `0xcff10`
- `0xcff30`
- `0xcff40`
- `0xcff50`
- `0xcff70`
- `0xcff90`
- `0xcffb0`
- `0xcffd0`
- `0xd0990`
- `0x1177f0`
- `0x117880`

## string_xrefs

- `0x953f7`: `AllowUpsideDown`

## pseudocode

```c

```

## disassembly

```asm
0x952c0  ldarg.1
0x952c1  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanel gaugePanel)
0x952c6  stloc.0
0x952c7  ldarg.0
0x952c8  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x952cd  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x952d2  brtrue   loc_9564C
0x952d7  ldc.i4.0
0x952d8  stloc.1
0x952d9  ldarg.0
0x952da  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x952df  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x952e4  pop
0x952e5  ldarg.0
0x952e6  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x952eb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x952f0  stloc.2
0x952f1  ldloc.2
0x952f2  ldc.i4.1
0x952f3  beq.s    loc_95302
0x952f5  ldloc.2
0x952f6  ldc.i4.s 0xF
0x952f8  beq      loc_9562D
0x952fd  br       loc_95646
0x95302  ldarg.0
0x95303  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x95308  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9530d  stloc.s  4
0x9530f  ldloc.s  4
0x95311  brfalse  loc_95646
0x95316  ldloc.s  4
0x95318  call     instance int32 [mscorlib]System.String::get_Length()
0x9531d  stloc.s  5
0x9531f  ldloc.s  5
0x95321  ldc.i4.5
0x95322  sub
0x95323  switch   loc_9539D, loc_95479, loc_95646, loc_953B3, loc_9537C, loc_95646, loc_95646, loc_9544D, loc_95463, loc_95361, loc_953F5, loc_95646, loc_9540B
0x9535c  br       loc_95646
0x95361  ldloc.s  4
0x95363  ldc.i4.0
0x95364  call     instance char [mscorlib]System.String::get_Chars(int32)
0x95369  stloc.s  6
0x9536b  ldloc.s  6
0x9536d  ldc.i4.s 0x49
0x9536f  beq.s    loc_953C9
0x95371  ldloc.s  6
0x95373  ldc.i4.s 0x55
0x95375  beq.s    loc_953DF
0x95377  br       loc_95646
0x9537c  ldloc.s  4
0x9537e  ldc.i4.0
0x9537f  call     instance char [mscorlib]System.String::get_Chars(int32)
0x95384  stloc.s  6
0x95386  ldloc.s  6
0x95388  ldc.i4.s 0x46
0x9538a  beq      loc_95421
0x9538f  ldloc.s  6
0x95391  ldc.i4.s 0x50
0x95393  beq      loc_95437
0x95398  br       loc_95646
0x9539d  ldloc.s  4
0x9539f  ldstr    aStyle_1// "Style"
0x953a4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x953a9  brtrue   loc_9548F
0x953ae  br       loc_95646
0x953b3  ldloc.s  4
0x953b5  ldstr    aInterval// "Interval"
0x953ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x953bf  brtrue   loc_954CB
0x953c4  br       loc_95646
0x953c9  ldloc.s  4
0x953cb  ldstr    aIntervaloffset// "IntervalOffset"
0x953d0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x953d5  brtrue   loc_954EB
0x953da  br       loc_95646
0x953df  ldloc.s  4
0x953e1  ldstr    aUsefontpercent// "UseFontPercent"
0x953e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x953eb  brtrue   loc_95611
0x953f0  br       loc_95646
0x953f5  ldloc.s  4
0x953f7  ldstr    aAllowupsidedow// "AllowUpsideDown"
0x953fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x95401  brtrue   loc_9550B
0x95406  br       loc_95646
0x9540b  ldloc.s  4
0x9540d  ldstr    aDistancefromsc// "DistanceFromScale"
0x95412  call     bool [mscorlib]System.String::op_Equality(string, string)
0x95417  brtrue   loc_9552A
0x9541c  br       loc_95646
0x95421  ldloc.s  4
0x95423  ldstr    aFontangle// "FontAngle"
0x95428  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9542d  brtrue   loc_9554A
0x95432  br       loc_95646
0x95437  ldloc.s  4
0x95439  ldstr    aPlacement// "Placement"
0x9543e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x95443  brtrue   loc_9556A
0x95448  br       loc_95646
0x9544d  ldloc.s  4
0x9544f  ldstr    aRotatelabels// "RotateLabels"
0x95454  call     bool [mscorlib]System.String::op_Equality(string, string)
0x95459  brtrue   loc_955BD
0x9545e  br       loc_95646
0x95463  ldloc.s  4
0x95465  ldstr    aShowendlabels// "ShowEndLabels"
0x9546a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9546f  brtrue   loc_955D9
0x95474  br       loc_95646
0x95479  ldloc.s  4
0x9547b  ldstr    aHidden// "Hidden"
0x95480  call     bool [mscorlib]System.String::op_Equality(string, string)
0x95485  brtrue   loc_955F5
0x9548a  br       loc_95646
0x9548f  ldarg.0
0x95490  ldarg.2
0x95491  call     instance class Microsoft.ReportingServices.ReportPublishing.StyleInformation Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadStyle(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x95496  stloc.3
0x95497  ldloc.3
0x95498  ldc.i4.s 0xD
0x9549a  ldc.i4.0
0x9549b  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::Filter(valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType ownerType, bool hasNoRows)
0x954a0  ldloc.0
0x954a1  ldloc.3
0x954a2  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> Microsoft.ReportingServices.ReportPublishing.StyleInformation::get_Attributes()
0x954a7  ldarga.s 2
0x954a9  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0x954ae  ldarga.s 2
0x954b0  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0x954b5  ldc.i4.1
0x954b6  ldarg.0
0x954b7  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x954bc  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle(class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> attributes, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, bool isDynamicImageSubElement, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x954c1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanelStyleContainer::set_StyleClass(class Microsoft.ReportingServices.ReportIntermediateFormat.Style value)
0x954c6  br       loc_95646
0x954cb  ldloc.0
0x954cc  ldarg.0
0x954cd  ldarg.0
0x954ce  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x954d3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x954d8  ldc.i4.0
0x954d9  ldc.i4.s 0xD
0x954db  ldarg.2
0x954dc  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x954e1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_Interval(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x954e6  br       loc_95646
0x954eb  ldloc.0
0x954ec  ldarg.0
0x954ed  ldarg.0
0x954ee  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x954f3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x954f8  ldc.i4.0
0x954f9  ldc.i4.s 0xD
0x954fb  ldarg.2
0x954fc  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x95501  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_IntervalOffset(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x95506  br       loc_95646
0x9550b  ldloc.0
0x9550c  ldarg.0
0x9550d  ldarg.0
0x9550e  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x95513  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x95518  ldc.i4.0
0x95519  ldc.i4.3
0x9551a  ldarg.2
0x9551b  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x95520  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_AllowUpsideDown(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x95525  br       loc_95646
0x9552a  ldloc.0
0x9552b  ldarg.0
0x9552c  ldarg.0
0x9552d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x95532  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x95537  ldc.i4.0
0x95538  ldc.i4.s 0xD
0x9553a  ldarg.2
0x9553b  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x95540  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_DistanceFromScale(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x95545  br       loc_95646
0x9554a  ldloc.0
0x9554b  ldarg.0
0x9554c  ldarg.0
0x9554d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x95552  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x95557  ldc.i4.0
0x95558  ldc.i4.s 0xD
0x9555a  ldarg.2
0x9555b  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x95560  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_FontAngle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x95565  br       loc_95646
0x9556a  ldloc.0
0x9556b  ldarg.0
0x9556c  ldarg.0
0x9556d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x95572  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x95577  ldc.i4.0
0x95578  ldc.i4.s 0x12
0x9557a  ldarg.2
0x9557b  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x95580  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_Placement(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x95585  ldloc.0
0x95586  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::get_Placement()
0x9558b  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0x95590  brtrue   loc_95646
0x95595  ldloc.0
0x95596  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::get_Placement()
0x9559b  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0x955a0  ldarg.0
0x955a1  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x955a6  ldarg.2
0x955a7  ldarg.0
0x955a8  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x955ad  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x955b2  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateGaugeLabelPlacements(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0x955b7  pop
0x955b8  br       loc_95646
0x955bd  ldloc.0
0x955be  ldarg.0
0x955bf  ldarg.0
0x955c0  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x955c5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x955ca  ldc.i4.0
0x955cb  ldc.i4.3
0x955cc  ldarg.2
0x955cd  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x955d2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_RotateLabels(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x955d7  br.s     loc_95646
0x955d9  ldloc.0
0x955da  ldarg.0
0x955db  ldarg.0
0x955dc  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x955e1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x955e6  ldc.i4.0
0x955e7  ldc.i4.3
0x955e8  ldarg.2
0x955e9  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x955ee  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_ShowEndLabels(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x955f3  br.s     loc_95646
0x955f5  ldloc.0
0x955f6  ldarg.0
0x955f7  ldarg.0
0x955f8  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x955fd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x95602  ldc.i4.0
0x95603  ldc.i4.3
0x95604  ldarg.2
0x95605  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9560a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_Hidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9560f  br.s     loc_95646
0x95611  ldloc.0
0x95612  ldarg.0
0x95613  ldarg.0
0x95614  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x95619  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9561e  ldc.i4.0
0x9561f  ldc.i4.3
0x95620  ldarg.2
0x95621  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x95626  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ScaleLabels::set_UseFontPercent(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9562b  br.s     loc_95646
0x9562d  ldstr    aScalelabels// "ScaleLabels"
0x95632  ldarg.0
0x95633  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x95638  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9563d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x95642  brfalse.s loc_95646
0x95644  ldc.i4.1
0x95645  stloc.1
0x95646  ldloc.1
0x95647  brfalse  loc_952D9
0x9564c  ldloc.0
0x9564d  ret
```
