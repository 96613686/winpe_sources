# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadPinLabel

- ea: `0x93920`
- end: `0x93be8`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadPinLabel`
- size: `712`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x95650`

## callees

- `0x93920`
- `0xac750`
- `0xb0fd0`
- `0xb6840`
- `0xbcdc0`
- `0xbcde0`
- `0xbe1c0`
- `0xbe2b0`
- `0xbf370`
- `0xc8370`
- `0xc8390`
- `0xc83b0`
- `0xc83d0`
- `0xc83f0`
- `0xc8400`
- `0xc8410`
- `0xc8430`
- `0xc8450`
- `0xd0990`
- `0x1177f0`
- `0x117880`

## string_xrefs

- `0x93a05`: `AllowUpsideDown`

## pseudocode

```c

```

## disassembly

```asm
0x93920  ldarg.1
0x93921  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanel gaugePanel)
0x93926  stloc.0
0x93927  ldarg.0
0x93928  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9392d  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x93932  brtrue   loc_93BE6
0x93937  ldc.i4.0
0x93938  stloc.1
0x93939  ldarg.0
0x9393a  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9393f  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x93944  pop
0x93945  ldarg.0
0x93946  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9394b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x93950  stloc.2
0x93951  ldloc.2
0x93952  ldc.i4.1
0x93953  beq.s    loc_93962
0x93955  ldloc.2
0x93956  ldc.i4.s 0xF
0x93958  beq      loc_93BC7
0x9395d  br       loc_93BE0
0x93962  ldarg.0
0x93963  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93968  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9396d  stloc.s  4
0x9396f  ldloc.s  4
0x93971  brfalse  loc_93BE0
0x93976  ldloc.s  4
0x93978  call     instance int32 [mscorlib]System.String::get_Length()
0x9397d  stloc.s  5
0x9397f  ldloc.s  5
0x93981  ldc.i4.4
0x93982  beq.s    loc_939ED
0x93984  ldloc.s  5
0x93986  ldc.i4.5
0x93987  beq.s    loc_939D7
0x93989  ldloc.s  5
0x9398b  ldc.i4.s 9
0x9398d  sub
0x9398e  switch   loc_939BC, loc_93BE0, loc_93A5B, loc_93BE0, loc_93BE0, loc_93A71, loc_93A03, loc_93BE0, loc_93A19
0x939b7  br       loc_93BE0
0x939bc  ldloc.s  4
0x939be  ldc.i4.0
0x939bf  call     instance char [mscorlib]System.String::get_Chars(int32)
0x939c4  stloc.s  6
0x939c6  ldloc.s  6
0x939c8  ldc.i4.s 0x46
0x939ca  beq.s    loc_93A2F
0x939cc  ldloc.s  6
0x939ce  ldc.i4.s 0x50
0x939d0  beq.s    loc_93A45
0x939d2  br       loc_93BE0
0x939d7  ldloc.s  4
0x939d9  ldstr    aStyle_1// "Style"
0x939de  call     bool [mscorlib]System.String::op_Equality(string, string)
0x939e3  brtrue   loc_93A87
0x939e8  br       loc_93BE0
0x939ed  ldloc.s  4
0x939ef  ldstr    aText// "Text"
0x939f4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x939f9  brtrue   loc_93AC3
0x939fe  br       loc_93BE0
0x93a03  ldloc.s  4
0x93a05  ldstr    aAllowupsidedow// "AllowUpsideDown"
0x93a0a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93a0f  brtrue   loc_93AE3
0x93a14  br       loc_93BE0
0x93a19  ldloc.s  4
0x93a1b  ldstr    aDistancefromsc// "DistanceFromScale"
0x93a20  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93a25  brtrue   loc_93B02
0x93a2a  br       loc_93BE0
0x93a2f  ldloc.s  4
0x93a31  ldstr    aFontangle// "FontAngle"
0x93a36  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93a3b  brtrue   loc_93B22
0x93a40  br       loc_93BE0
0x93a45  ldloc.s  4
0x93a47  ldstr    aPlacement// "Placement"
0x93a4c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93a51  brtrue   loc_93B42
0x93a56  br       loc_93BE0
0x93a5b  ldloc.s  4
0x93a5d  ldstr    aRotatelabel// "RotateLabel"
0x93a62  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93a67  brtrue   loc_93B8F
0x93a6c  br       loc_93BE0
0x93a71  ldloc.s  4
0x93a73  ldstr    aUsefontpercent// "UseFontPercent"
0x93a78  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93a7d  brtrue   loc_93BAB
0x93a82  br       loc_93BE0
0x93a87  ldarg.0
0x93a88  ldarg.2
0x93a89  call     instance class Microsoft.ReportingServices.ReportPublishing.StyleInformation Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadStyle(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x93a8e  stloc.3
0x93a8f  ldloc.3
0x93a90  ldc.i4.s 0xD
0x93a92  ldc.i4.0
0x93a93  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::Filter(valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType ownerType, bool hasNoRows)
0x93a98  ldloc.0
0x93a99  ldloc.3
0x93a9a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> Microsoft.ReportingServices.ReportPublishing.StyleInformation::get_Attributes()
0x93a9f  ldarga.s 2
0x93aa1  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0x93aa6  ldarga.s 2
0x93aa8  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0x93aad  ldc.i4.1
0x93aae  ldarg.0
0x93aaf  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x93ab4  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle(class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> attributes, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, bool isDynamicImageSubElement, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x93ab9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.GaugePanelStyleContainer::set_StyleClass(class Microsoft.ReportingServices.ReportIntermediateFormat.Style value)
0x93abe  br       loc_93BE0
0x93ac3  ldloc.0
0x93ac4  ldarg.0
0x93ac5  ldarg.0
0x93ac6  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93acb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x93ad0  ldc.i4.0
0x93ad1  ldc.i4.s 0x12
0x93ad3  ldarg.2
0x93ad4  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x93ad9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::set_Text(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x93ade  br       loc_93BE0
0x93ae3  ldloc.0
0x93ae4  ldarg.0
0x93ae5  ldarg.0
0x93ae6  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93aeb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x93af0  ldc.i4.0
0x93af1  ldc.i4.3
0x93af2  ldarg.2
0x93af3  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x93af8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::set_AllowUpsideDown(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x93afd  br       loc_93BE0
0x93b02  ldloc.0
0x93b03  ldarg.0
0x93b04  ldarg.0
0x93b05  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93b0a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x93b0f  ldc.i4.0
0x93b10  ldc.i4.s 0xD
0x93b12  ldarg.2
0x93b13  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x93b18  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::set_DistanceFromScale(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x93b1d  br       loc_93BE0
0x93b22  ldloc.0
0x93b23  ldarg.0
0x93b24  ldarg.0
0x93b25  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93b2a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x93b2f  ldc.i4.0
0x93b30  ldc.i4.s 0xD
0x93b32  ldarg.2
0x93b33  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x93b38  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::set_FontAngle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x93b3d  br       loc_93BE0
0x93b42  ldloc.0
0x93b43  ldarg.0
0x93b44  ldarg.0
0x93b45  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93b4a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x93b4f  ldc.i4.0
0x93b50  ldc.i4.s 0x12
0x93b52  ldarg.2
0x93b53  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x93b58  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::set_Placement(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x93b5d  ldloc.0
0x93b5e  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::get_Placement()
0x93b63  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0x93b68  brtrue.s loc_93BE0
0x93b6a  ldloc.0
0x93b6b  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::get_Placement()
0x93b70  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0x93b75  ldarg.0
0x93b76  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x93b7b  ldarg.2
0x93b7c  ldarg.0
0x93b7d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93b82  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x93b87  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateGaugeLabelPlacements(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0x93b8c  pop
0x93b8d  br.s     loc_93BE0
0x93b8f  ldloc.0
0x93b90  ldarg.0
0x93b91  ldarg.0
0x93b92  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93b97  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x93b9c  ldc.i4.0
0x93b9d  ldc.i4.3
0x93b9e  ldarg.2
0x93b9f  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x93ba4  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::set_RotateLabel(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x93ba9  br.s     loc_93BE0
0x93bab  ldloc.0
0x93bac  ldarg.0
0x93bad  ldarg.0
0x93bae  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93bb3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x93bb8  ldc.i4.0
0x93bb9  ldc.i4.3
0x93bba  ldarg.2
0x93bbb  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x93bc0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.PinLabel::set_UseFontPercent(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x93bc5  br.s     loc_93BE0
0x93bc7  ldstr    aPinlabel// "PinLabel"
0x93bcc  ldarg.0
0x93bcd  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x93bd2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x93bd7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x93bdc  brfalse.s loc_93BE0
0x93bde  ldc.i4.1
0x93bdf  stloc.1
0x93be0  ldloc.1
0x93be1  brfalse  loc_93939
0x93be6  ldloc.0
0x93be7  ret
```
