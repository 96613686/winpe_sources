# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartTitle

- ea: `0xa1840`
- end: `0xa1d04`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartTitle`
- size: `1220`
- prototype: ``
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xa0630`
- `0xa2180`

## callees

- `0x9f8c0`
- `0xa1840`
- `0xa4020`
- `0xac750`
- `0xb0fd0`
- `0xb8ca0`
- `0xb8d90`
- `0xb9ac0`
- `0xbcdc0`
- `0xbcde0`
- `0xbce20`
- `0xbe1c0`
- `0xbe2b0`
- `0xbf370`
- `0xc17c0`
- `0xf8090`
- `0xf8330`
- `0xf8370`
- `0xf8380`
- `0xf8390`
- `0xf83a0`
- `0xf83c0`
- `0xf83d0`
- `0xf83e0`
- `0xf8400`
- `0xf8420`
- `0xf8440`
- `0xf8460`
- `0xf8470`
- `0xf8480`
- `0xf84a0`
- `0x1079e0`
- `0x1177f0`
- `0x117880`
- `0x124ca0`

## string_xrefs

- `0xa1a50`: `DockOutsideChartArea`

## pseudocode

```c

```

## disassembly

```asm
0xa1840  ldarg.3
0xa1841  brtrue.s loc_A187C
0xa1843  ldarg.2
0xa1844  ldarg.0
0xa1845  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa184a  ldstr    aName_1// "Name"
0xa184f  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa1854  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::set_TitleName(string value)
0xa1859  ldarg.s  5
0xa185b  ldc.i4.0
0xa185c  ldstr    aCharttitle// "ChartTitle"
0xa1861  ldc.i4.s 0x10
0xa1863  ldarg.1
0xa1864  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0xa1869  ldarg.2
0xa186a  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::get_TitleName()
0xa186f  ldarga.s 4
0xa1871  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa1876  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.DynamicImageOrCustomUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyNameValue, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa187b  pop
0xa187c  ldarg.0
0xa187d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1882  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa1887  brtrue   loc_A1D03
0xa188c  ldc.i4.0
0xa188d  stloc.0
0xa188e  ldarg.0
0xa188f  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1894  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa1899  pop
0xa189a  ldarg.0
0xa189b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa18a0  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa18a5  stloc.1
0xa18a6  ldloc.1
0xa18a7  ldc.i4.1
0xa18a8  beq.s    loc_A18B7
0xa18aa  ldloc.1
0xa18ab  ldc.i4.s 0xF
0xa18ad  beq      loc_A1CC6
0xa18b2  br       loc_A1CFD
0xa18b7  ldarg.0
0xa18b8  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa18bd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa18c2  stloc.s  4
0xa18c4  ldloc.s  4
0xa18c6  brfalse  loc_A1CFD
0xa18cb  ldloc.s  4
0xa18cd  call     instance int32 [mscorlib]System.String::get_Length()
0xa18d2  stloc.s  5
0xa18d4  ldloc.s  5
0xa18d6  ldc.i4.5
0xa18d7  sub
0xa18d8  switch   loc_A19E0, loc_A1A0C, loc_A1914, loc_A19F6, loc_A1CFD, loc_A197D, loc_A1CFD, loc_A1CFD, loc_A1CFD, loc_A1CFD, loc_A193B
0xa1909  ldloc.s  5
0xa190b  ldc.i4.s 0x14
0xa190d  beq.s    loc_A195C
0xa190f  br       loc_A1CFD
0xa1914  ldloc.s  4
0xa1916  ldc.i4.0
0xa1917  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa191c  stloc.s  6
0xa191e  ldloc.s  6
0xa1920  ldc.i4.s 0x43
0xa1922  beq.s    loc_A199E
0xa1924  ldloc.s  6
0xa1926  ldc.i4.s 0x44
0xa1928  beq      loc_A19B4
0xa192d  ldloc.s  6
0xa192f  ldc.i4.s 0x54
0xa1931  beq      loc_A19CA
0xa1936  br       loc_A1CFD
0xa193b  ldloc.s  4
0xa193d  ldc.i4.0
0xa193e  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa1943  stloc.s  6
0xa1945  ldloc.s  6
0xa1947  ldc.i4.s 0x44
0xa1949  beq      loc_A1A22
0xa194e  ldloc.s  6
0xa1950  ldc.i4.s 0x54
0xa1952  beq      loc_A1A38
0xa1957  br       loc_A1CFD
0xa195c  ldloc.s  4
0xa195e  ldc.i4.0
0xa195f  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa1964  stloc.s  6
0xa1966  ldloc.s  6
0xa1968  ldc.i4.s 0x43
0xa196a  beq      loc_A1A64
0xa196f  ldloc.s  6
0xa1971  ldc.i4.s 0x44
0xa1973  beq      loc_A1A4E
0xa1978  br       loc_A1CFD
0xa197d  ldloc.s  4
0xa197f  ldc.i4.0
0xa1980  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa1985  stloc.s  6
0xa1987  ldloc.s  6
0xa1989  ldc.i4.s 0x41
0xa198b  beq      loc_A1A90
0xa1990  ldloc.s  6
0xa1992  ldc.i4.s 0x44
0xa1994  beq      loc_A1A7A
0xa1999  br       loc_A1CFD
0xa199e  ldloc.s  4
0xa19a0  ldstr    aCaption// "Caption"
0xa19a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa19aa  brtrue   loc_A1AA6
0xa19af  br       loc_A1CFD
0xa19b4  ldloc.s  4
0xa19b6  ldstr    aDocking// "Docking"
0xa19bb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa19c0  brtrue   loc_A1B7B
0xa19c5  br       loc_A1CFD
0xa19ca  ldloc.s  4
0xa19cc  ldstr    aTooltip// "ToolTip"
0xa19d1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa19d6  brtrue   loc_A1C28
0xa19db  br       loc_A1CFD
0xa19e0  ldloc.s  4
0xa19e2  ldstr    aStyle_1// "Style"
0xa19e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa19ec  brtrue   loc_A1AC7
0xa19f1  br       loc_A1CFD
0xa19f6  ldloc.s  4
0xa19f8  ldstr    aPosition// "Position"
0xa19fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1a02  brtrue   loc_A1B05
0xa1a07  br       loc_A1CFD
0xa1a0c  ldloc.s  4
0xa1a0e  ldstr    aHidden// "Hidden"
0xa1a13  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1a18  brtrue   loc_A1B5B
0xa1a1d  br       loc_A1CFD
0xa1a22  ldloc.s  4
0xa1a24  ldstr    aDocktochartare// "DockToChartArea"
0xa1a29  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1a2e  brtrue   loc_A1BD1
0xa1a33  br       loc_A1CFD
0xa1a38  ldloc.s  4
0xa1a3a  ldstr    aTextorientatio// "TextOrientation"
0xa1a3f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1a44  brtrue   loc_A1C60
0xa1a49  br       loc_A1CFD
0xa1a4e  ldloc.s  4
0xa1a50  ldstr    aDockoutsidecha// "DockOutsideChartArea"
0xa1a55  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1a5a  brtrue   loc_A1BE7
0xa1a5f  br       loc_A1CFD
0xa1a64  ldloc.s  4
0xa1a66  ldstr    aChartelementpo// "ChartElementPosition"
0xa1a6b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1a70  brtrue   loc_A1CB0
0xa1a75  br       loc_A1CFD
0xa1a7a  ldloc.s  4
0xa1a7c  ldstr    aDockoffset// "DockOffset"
0xa1a81  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1a86  brtrue   loc_A1C07
0xa1a8b  br       loc_A1CFD
0xa1a90  ldloc.s  4
0xa1a92  ldstr    aActioninfo// "ActionInfo"
0xa1a97  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa1a9c  brtrue   loc_A1C49
0xa1aa1  br       loc_A1CFD
0xa1aa6  ldarg.2
0xa1aa7  ldarg.0
0xa1aa8  ldarg.0
0xa1aa9  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1aae  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1ab3  ldc.i4.0
0xa1ab4  ldc.i4.s 0x12
0xa1ab6  ldarg.s  4
0xa1ab8  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa1abd  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitleBase::set_Caption(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa1ac2  br       loc_A1CFD
0xa1ac7  ldarg.0
0xa1ac8  ldarg.s  4
0xa1aca  call     instance class Microsoft.ReportingServices.ReportPublishing.StyleInformation Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadStyle(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa1acf  stloc.2
0xa1ad0  ldloc.2
0xa1ad1  ldc.i4.s 0xB
0xa1ad3  ldc.i4.0
0xa1ad4  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::Filter(valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType ownerType, bool hasNoRows)
0xa1ad9  ldarg.2
0xa1ada  ldloc.2
0xa1adb  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> Microsoft.ReportingServices.ReportPublishing.StyleInformation::get_Attributes()
0xa1ae0  ldarga.s 4
0xa1ae2  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa1ae7  ldarga.s 4
0xa1ae9  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xa1aee  ldc.i4.1
0xa1aef  ldarga.s 4
0xa1af1  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa1af6  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle(class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> attributes, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, bool isDynamicImageSubElement, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa1afb  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartStyleContainer::set_StyleClass(class Microsoft.ReportingServices.ReportIntermediateFormat.Style value)
0xa1b00  br       loc_A1CFD
0xa1b05  ldarg.2
0xa1b06  ldarg.0
0xa1b07  ldarg.0
0xa1b08  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1b0d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1b12  ldc.i4.0
0xa1b13  ldc.i4.s 0x12
0xa1b15  ldarg.s  4
0xa1b17  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa1b1c  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::set_Position(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa1b21  ldarg.2
0xa1b22  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::get_Position()
0xa1b27  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa1b2c  brtrue   loc_A1CFD
0xa1b31  ldarg.2
0xa1b32  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::get_Position()
0xa1b37  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0xa1b3c  ldarga.s 4
0xa1b3e  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa1b43  ldarg.s  4
0xa1b45  ldarg.0
0xa1b46  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1b4b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1b50  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartTitlePositions(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xa1b55  pop
0xa1b56  br       loc_A1CFD
0xa1b5b  ldarg.2
0xa1b5c  ldarg.0
0xa1b5d  ldarg.0
0xa1b5e  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1b63  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1b68  ldc.i4.0
0xa1b69  ldc.i4.3
0xa1b6a  ldarg.s  4
0xa1b6c  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa1b71  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::set_Hidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa1b76  br       loc_A1CFD
0xa1b7b  ldarg.2
0xa1b7c  ldarg.0
0xa1b7d  ldarg.0
0xa1b7e  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1b83  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1b88  ldc.i4.0
0xa1b89  ldc.i4.s 0x12
0xa1b8b  ldarg.s  4
0xa1b8d  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa1b92  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::set_Docking(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa1b97  ldarg.2
0xa1b98  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::get_Docking()
0xa1b9d  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa1ba2  brtrue   loc_A1CFD
0xa1ba7  ldarg.2
0xa1ba8  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::get_Docking()
0xa1bad  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0xa1bb2  ldarga.s 4
0xa1bb4  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa1bb9  ldarg.s  4
0xa1bbb  ldarg.0
0xa1bbc  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1bc1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1bc6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartTitleDockings(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xa1bcb  pop
0xa1bcc  br       loc_A1CFD
0xa1bd1  ldarg.2
0xa1bd2  ldarg.0
0xa1bd3  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1bd8  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xa1bdd  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::set_DockToChartArea(string value)
0xa1be2  br       loc_A1CFD
0xa1be7  ldarg.2
0xa1be8  ldarg.0
0xa1be9  ldarg.0
0xa1bea  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1bef  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1bf4  ldc.i4.0
0xa1bf5  ldc.i4.3
0xa1bf6  ldarg.s  4
0xa1bf8  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa1bfd  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::set_DockOutsideChartArea(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa1c02  br       loc_A1CFD
0xa1c07  ldarg.2
0xa1c08  ldarg.0
0xa1c09  ldarg.0
0xa1c0a  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1c0f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1c14  ldc.i4.0
0xa1c15  ldc.i4.s 9
0xa1c17  ldarg.s  4
0xa1c19  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa1c1e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::set_DockOffset(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa1c23  br       loc_A1CFD
0xa1c28  ldarg.2
0xa1c29  ldarg.0
0xa1c2a  ldarg.0
0xa1c2b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa1c30  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1c35  ldc.i4.0
0xa1c36  ldc.i4.s 0x12
0xa1c38  ldarg.s  4
0xa1c3a  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa1c3f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartTitle::set_ToolTip(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa1c44  br       loc_A1CFD
0xa1c49  ldarg.2
  ... truncated ...
```
