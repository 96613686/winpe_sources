# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadCustomLabel

- ea: `0x90070`
- end: `0x90427`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadCustomLabel`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x90430`

## callees

- `0x90070`
- `0x904c0`
- `0xac750`
- `0xb0fd0`
- `0xb6840`
- `0xbcdc0`
- `0xbcde0`
- `0xbe1c0`
- `0xbe2b0`
- `0xbf370`
- `0xc17c0`
- `0xc6480`
- `0xc6490`
- `0xc64a0`
- `0xc64c0`
- `0xc64e0`
- `0xc6500`
- `0xc6520`
- `0xc6530`
- `0xc6540`
- `0xc6560`
- `0xc6580`
- `0xc65a0`
- `0xc65c0`
- `0xc65e0`
- `0xd0990`
- `0x1177f0`
- `0x117880`
- `0x124ca0`

## string_xrefs

- `0x901c9`: `AllowUpsideDown`

## pseudocode

```c

```

## disassembly

```asm
0x90070  ldarg.1
0x90071  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanel gaugePanel)
0x90076  stloc.0
0x90077  ldloc.0
0x90078  ldarg.0
0x90079  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9007e  ldstr    aName_1// "Name"
0x90083  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x90088  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_Name(string value)
0x9008d  ldarg.3
0x9008e  ldc.i4.0
0x9008f  ldstr    aCustomlabel// "CustomLabel"
0x90094  ldc.i4.s 0xE
0x90096  ldarg.1
0x90097  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0x9009c  ldloc.0
0x9009d  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::get_Name()
0x900a2  ldarg.0
0x900a3  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x900a8  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.DynamicImageOrCustomUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyNameValue, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x900ad  pop
0x900ae  ldarg.0
0x900af  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x900b4  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x900b9  brtrue   loc_90425
0x900be  ldc.i4.0
0x900bf  stloc.1
0x900c0  ldarg.0
0x900c1  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x900c6  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x900cb  pop
0x900cc  ldarg.0
0x900cd  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x900d2  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x900d7  stloc.2
0x900d8  ldloc.2
0x900d9  ldc.i4.1
0x900da  beq.s    loc_900E9
0x900dc  ldloc.2
0x900dd  ldc.i4.s 0xF
0x900df  beq      loc_90406
0x900e4  br       loc_9041F
0x900e9  ldarg.0
0x900ea  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x900ef  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x900f4  stloc.s  4
0x900f6  ldloc.s  4
0x900f8  brfalse  loc_9041F
0x900fd  ldloc.s  4
0x900ff  call     instance int32 [mscorlib]System.String::get_Length()
0x90104  stloc.s  5
0x90106  ldloc.s  5
0x90108  ldc.i4.4
0x90109  sub
0x9010a  switch   loc_901B1, loc_9014C, loc_9024B, loc_9041F, loc_9041F, loc_90167, loc_9041F, loc_9021F, loc_9041F, loc_90235, loc_90261, loc_901C7, loc_9041F, loc_901DD
0x90147  br       loc_9041F
0x9014c  ldloc.s  4
0x9014e  ldc.i4.0
0x9014f  call     instance char [mscorlib]System.String::get_Chars(int32)
0x90154  stloc.s  6
0x90156  ldloc.s  6
0x90158  ldc.i4.s 0x53
0x9015a  beq.s    loc_90185
0x9015c  ldloc.s  6
0x9015e  ldc.i4.s 0x56
0x90160  beq.s    loc_9019B
0x90162  br       loc_9041F
0x90167  ldloc.s  4
0x90169  ldc.i4.0
0x9016a  call     instance char [mscorlib]System.String::get_Chars(int32)
0x9016f  stloc.s  6
0x90171  ldloc.s  6
0x90173  ldc.i4.s 0x46
0x90175  beq.s    loc_901F3
0x90177  ldloc.s  6
0x90179  ldc.i4.s 0x50
0x9017b  beq      loc_90209
0x90180  br       loc_9041F
0x90185  ldloc.s  4
0x90187  ldstr    aStyle_1// "Style"
0x9018c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x90191  brtrue   loc_90277
0x90196  br       loc_9041F
0x9019b  ldloc.s  4
0x9019d  ldstr    aValue// "Value"
0x901a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x901a7  brtrue   loc_903B1
0x901ac  br       loc_9041F
0x901b1  ldloc.s  4
0x901b3  ldstr    aText// "Text"
0x901b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x901bd  brtrue   loc_902B3
0x901c2  br       loc_9041F
0x901c7  ldloc.s  4
0x901c9  ldstr    aAllowupsidedow// "AllowUpsideDown"
0x901ce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x901d3  brtrue   loc_902D3
0x901d8  br       loc_9041F
0x901dd  ldloc.s  4
0x901df  ldstr    aDistancefromsc// "DistanceFromScale"
0x901e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x901e9  brtrue   loc_902F2
0x901ee  br       loc_9041F
0x901f3  ldloc.s  4
0x901f5  ldstr    aFontangle// "FontAngle"
0x901fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x901ff  brtrue   loc_90312
0x90204  br       loc_9041F
0x90209  ldloc.s  4
0x9020b  ldstr    aPlacement// "Placement"
0x90210  call     bool [mscorlib]System.String::op_Equality(string, string)
0x90215  brtrue   loc_90332
0x9021a  br       loc_9041F
0x9021f  ldloc.s  4
0x90221  ldstr    aRotatelabel// "RotateLabel"
0x90226  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9022b  brtrue   loc_90385
0x90230  br       loc_9041F
0x90235  ldloc.s  4
0x90237  ldstr    aTickmarkstyle// "TickMarkStyle"
0x9023c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x90241  brtrue   loc_903A1
0x90246  br       loc_9041F
0x9024b  ldloc.s  4
0x9024d  ldstr    aHidden// "Hidden"
0x90252  call     bool [mscorlib]System.String::op_Equality(string, string)
0x90257  brtrue   loc_903CE
0x9025c  br       loc_9041F
0x90261  ldloc.s  4
0x90263  ldstr    aUsefontpercent// "UseFontPercent"
0x90268  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9026d  brtrue   loc_903EA
0x90272  br       loc_9041F
0x90277  ldarg.0
0x90278  ldarg.2
0x90279  call     instance class Microsoft.ReportingServices.ReportPublishing.StyleInformation Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadStyle(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9027e  stloc.3
0x9027f  ldloc.3
0x90280  ldc.i4.s 0xD
0x90282  ldc.i4.0
0x90283  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::Filter(valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType ownerType, bool hasNoRows)
0x90288  ldloc.0
0x90289  ldloc.3
0x9028a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> Microsoft.ReportingServices.ReportPublishing.StyleInformation::get_Attributes()
0x9028f  ldarga.s 2
0x90291  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0x90296  ldarga.s 2
0x90298  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0x9029d  ldc.i4.1
0x9029e  ldarg.0
0x9029f  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x902a4  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle(class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> attributes, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, bool isDynamicImageSubElement, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x902a9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanelStyleContainer::set_StyleClass(class Microsoft.ReportingServices.ReportIntermediateFormat.Style value)
0x902ae  br       loc_9041F
0x902b3  ldloc.0
0x902b4  ldarg.0
0x902b5  ldarg.0
0x902b6  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x902bb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x902c0  ldc.i4.0
0x902c1  ldc.i4.s 0x12
0x902c3  ldarg.2
0x902c4  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x902c9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_Text(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x902ce  br       loc_9041F
0x902d3  ldloc.0
0x902d4  ldarg.0
0x902d5  ldarg.0
0x902d6  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x902db  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x902e0  ldc.i4.0
0x902e1  ldc.i4.3
0x902e2  ldarg.2
0x902e3  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x902e8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_AllowUpsideDown(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x902ed  br       loc_9041F
0x902f2  ldloc.0
0x902f3  ldarg.0
0x902f4  ldarg.0
0x902f5  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x902fa  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x902ff  ldc.i4.0
0x90300  ldc.i4.s 0xD
0x90302  ldarg.2
0x90303  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x90308  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_DistanceFromScale(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9030d  br       loc_9041F
0x90312  ldloc.0
0x90313  ldarg.0
0x90314  ldarg.0
0x90315  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9031a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9031f  ldc.i4.0
0x90320  ldc.i4.s 0xD
0x90322  ldarg.2
0x90323  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x90328  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_FontAngle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9032d  br       loc_9041F
0x90332  ldloc.0
0x90333  ldarg.0
0x90334  ldarg.0
0x90335  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9033a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9033f  ldc.i4.0
0x90340  ldc.i4.s 0x12
0x90342  ldarg.2
0x90343  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x90348  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_Placement(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9034d  ldloc.0
0x9034e  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::get_Placement()
0x90353  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0x90358  brtrue   loc_9041F
0x9035d  ldloc.0
0x9035e  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::get_Placement()
0x90363  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0x90368  ldarg.0
0x90369  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x9036e  ldarg.2
0x9036f  ldarg.0
0x90370  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x90375  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9037a  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateGaugeLabelPlacements(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0x9037f  pop
0x90380  br       loc_9041F
0x90385  ldloc.0
0x90386  ldarg.0
0x90387  ldarg.0
0x90388  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9038d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x90392  ldc.i4.0
0x90393  ldc.i4.3
0x90394  ldarg.2
0x90395  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9039a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_RotateLabel(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9039f  br.s     loc_9041F
0x903a1  ldloc.0
0x903a2  ldarg.0
0x903a3  ldarg.1
0x903a4  ldarg.2
0x903a5  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.TickMarkStyle Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadTickMarkStyle(class Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanel gaugePanel, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x903aa  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_TickMarkStyle(class Microsoft.ReportingServices.ReportIntermediateFormat.TickMarkStyle value)
0x903af  br.s     loc_9041F
0x903b1  ldloc.0
0x903b2  ldarg.0
0x903b3  ldarg.0
0x903b4  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x903b9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x903be  ldc.i4.0
0x903bf  ldc.i4.s 0xD
0x903c1  ldarg.2
0x903c2  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x903c7  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_Value(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x903cc  br.s     loc_9041F
0x903ce  ldloc.0
0x903cf  ldarg.0
0x903d0  ldarg.0
0x903d1  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x903d6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x903db  ldc.i4.0
0x903dc  ldc.i4.3
0x903dd  ldarg.2
0x903de  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x903e3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_Hidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x903e8  br.s     loc_9041F
0x903ea  ldloc.0
0x903eb  ldarg.0
0x903ec  ldarg.0
0x903ed  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x903f2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x903f7  ldc.i4.0
0x903f8  ldc.i4.3
0x903f9  ldarg.2
0x903fa  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x903ff  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::set_UseFontPercent(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x90404  br.s     loc_9041F
0x90406  ldstr    aCustomlabel// "CustomLabel"
0x9040b  ldarg.0
0x9040c  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x90411  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x90416  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9041b  brfalse.s loc_9041F
0x9041d  ldc.i4.1
0x9041e  stloc.1
0x9041f  ldloc.1
0x90420  brfalse  loc_900C0
0x90425  ldloc.0
0x90426  ret
```
