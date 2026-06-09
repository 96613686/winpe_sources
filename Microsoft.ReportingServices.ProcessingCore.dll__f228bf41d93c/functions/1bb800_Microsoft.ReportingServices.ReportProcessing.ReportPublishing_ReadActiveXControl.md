# Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadActiveXControl

- ea: `0x1bb800`
- end: `0x1bbd70`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadActiveXControl`
- size: `1392`
- prototype: ``
- caller_count: `1`
- callee_count: `46`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1b7fe0`

## callees

- `0x198e00`
- `0x198e10`
- `0x198e20`
- `0x198e40`
- `0x198e60`
- `0x198ea0`
- `0x198ee0`
- `0x198f20`
- `0x199060`
- `0x199080`
- `0x1990a0`
- `0x1990c0`
- `0x1990e0`
- `0x199100`
- `0x199120`
- `0x199180`
- `0x199240`
- `0x199260`
- `0x199280`
- `0x199480`
- `0x19d060`
- `0x19d0a0`
- `0x19d0c0`
- `0x19d0e0`
- `0x1a74a0`
- `0x1b5180`
- `0x1b7c40`
- `0x1bb800`
- `0x1bbd70`
- `0x1c2e30`
- `0x1c2f70`
- `0x1c32a0`
- `0x1c3510`
- `0x1c37d0`
- `0x1c3f40`
- `0x1cbc90`
- `0x1cd8d0`
- `0x2643c0`
- `0x2643d0`
- `0x2643e0`
- `0x2643f0`
- `0x264820`
- `0x264830`
- `0x264880`
- `0x264b20`
- `0x264b50`

## string_xrefs

- `0x1bbad5`: `ClassID`

## pseudocode

```c

```

## disassembly

```asm
0x1bb800  ldarg.0
0x1bb801  call     instance int32 Microsoft.ReportingServices.ReportProcessing.ReportPublishing::GenerateID()
0x1bb806  ldarg.1
0x1bb807  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ActiveXControl::.ctor(int32 id, class Microsoft.ReportingServices.ReportProcessing.ReportItem parent)
0x1bb80c  stloc.0
0x1bb80d  ldloc.0
0x1bb80e  ldarg.0
0x1bb80f  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bb814  ldstr    aName_1// "Name"
0x1bb819  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x1bb81e  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Name(string value)
0x1bb823  ldarga.s 2
0x1bb825  ldloc.0
0x1bb826  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportProcessing.ReportItem::get_ObjectType()
0x1bb82b  call     instance void PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0x1bb830  ldarga.s 2
0x1bb832  ldloc.0
0x1bb833  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ReportItem::get_Name()
0x1bb838  call     instance void PublishingContextStruct::set_ObjectName(string value)
0x1bb83d  ldarg.0
0x1bb83e  ldfld    class Microsoft.ReportingServices.ReportProcessing.CLSUniqueNameValidator Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportItemNames
0x1bb843  ldarga.s 2
0x1bb845  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType PublishingContextStruct::get_ObjectType()
0x1bb84a  ldarga.s 2
0x1bb84c  call     instance string PublishingContextStruct::get_ObjectName()
0x1bb851  ldarg.0
0x1bb852  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1bb857  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.CLSUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string name, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x1bb85c  pop
0x1bb85d  ldc.i4.0
0x1bb85e  stloc.1
0x1bb85f  ldc.i4.0
0x1bb860  stloc.2
0x1bb861  ldc.i4.0
0x1bb862  stloc.3
0x1bb863  ldc.i4.0
0x1bb864  stloc.s  4
0x1bb866  ldc.i4.0
0x1bb867  stloc.s  5
0x1bb869  ldc.i4.0
0x1bb86a  stloc.s  6
0x1bb86c  ldc.i4.0
0x1bb86d  stloc.s  7
0x1bb86f  ldc.i4.0
0x1bb870  stloc.s  8
0x1bb872  ldnull
0x1bb873  stloc.s  9
0x1bb875  ldnull
0x1bb876  stloc.s  0xA
0x1bb878  ldarg.0
0x1bb879  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bb87e  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1bb883  pop
0x1bb884  ldarg.0
0x1bb885  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bb88a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1bb88f  stloc.s  0xB
0x1bb891  ldloc.s  0xB
0x1bb893  ldc.i4.1
0x1bb894  beq.s    loc_1BB8A4
0x1bb896  ldloc.s  0xB
0x1bb898  ldc.i4.s 0xF
0x1bb89a  beq      loc_1BBD07
0x1bb89f  br       loc_1BBD21
0x1bb8a4  ldarg.0
0x1bb8a5  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bb8aa  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1bb8af  stloc.s  0xD
0x1bb8b1  ldloc.s  0xD
0x1bb8b3  brfalse  loc_1BBD21
0x1bb8b8  ldloc.s  0xD
0x1bb8ba  call     instance int32 [mscorlib]System.String::get_Length()
0x1bb8bf  stloc.s  0xE
0x1bb8c1  ldloc.s  0xE
0x1bb8c3  ldc.i4.3
0x1bb8c4  sub
0x1bb8c5  switch   loc_1BBA0D, loc_1BBA23, loc_1BB90B, loc_1BB935, loc_1BB989, loc_1BB9AA, loc_1BBD21, loc_1BB95F, loc_1BBD21, loc_1BBD21, loc_1BBD21, loc_1BBD21, loc_1BBB2B, loc_1BBB15, loc_1BBB41
0x1bb906  br       loc_1BBD21
0x1bb90b  ldloc.s  0xD
0x1bb90d  ldc.i4.0
0x1bb90e  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1bb913  stloc.s  0xF
0x1bb915  ldloc.s  0xF
0x1bb917  ldc.i4.s 0x4C
0x1bb919  beq      loc_1BB9F7
0x1bb91e  ldloc.s  0xF
0x1bb920  ldc.i4.s 0x53
0x1bb922  beq      loc_1BB9CB
0x1bb927  ldloc.s  0xF
0x1bb929  ldc.i4.s 0x57
0x1bb92b  beq      loc_1BB9E1
0x1bb930  br       loc_1BBD21
0x1bb935  ldloc.s  0xD
0x1bb937  ldc.i4.0
0x1bb938  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1bb93d  stloc.s  0xF
0x1bb93f  ldloc.s  0xF
0x1bb941  ldc.i4.s 0x43
0x1bb943  beq      loc_1BBA65
0x1bb948  ldloc.s  0xF
0x1bb94a  ldc.i4.s 0x48
0x1bb94c  beq      loc_1BBA39
0x1bb951  ldloc.s  0xF
0x1bb953  ldc.i4.s 0x5A
0x1bb955  beq      loc_1BBA4F
0x1bb95a  br       loc_1BBD21
0x1bb95f  ldloc.s  0xD
0x1bb961  ldc.i4.0
0x1bb962  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1bb967  stloc.s  0xF
0x1bb969  ldloc.s  0xF
0x1bb96b  ldc.i4.s 0x50
0x1bb96d  beq      loc_1BBAA7
0x1bb972  ldloc.s  0xF
0x1bb974  ldc.i4.s 0x52
0x1bb976  beq      loc_1BBA91
0x1bb97b  ldloc.s  0xF
0x1bb97d  ldc.i4.s 0x56
0x1bb97f  beq      loc_1BBA7B
0x1bb984  br       loc_1BBD21
0x1bb989  ldloc.s  0xD
0x1bb98b  ldc.i4.0
0x1bb98c  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1bb991  stloc.s  0xF
0x1bb993  ldloc.s  0xF
0x1bb995  ldc.i4.s 0x43
0x1bb997  beq      loc_1BBAD3
0x1bb99c  ldloc.s  0xF
0x1bb99e  ldc.i4.s 0x54
0x1bb9a0  beq      loc_1BBABD
0x1bb9a5  br       loc_1BBD21
0x1bb9aa  ldloc.s  0xD
0x1bb9ac  ldc.i4.0
0x1bb9ad  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1bb9b2  stloc.s  0xF
0x1bb9b4  ldloc.s  0xF
0x1bb9b6  ldc.i4.s 0x42
0x1bb9b8  beq      loc_1BBAE9
0x1bb9bd  ldloc.s  0xF
0x1bb9bf  ldc.i4.s 0x43
0x1bb9c1  beq      loc_1BBAFF
0x1bb9c6  br       loc_1BBD21
0x1bb9cb  ldloc.s  0xD
0x1bb9cd  ldstr    aStyle_1// "Style"
0x1bb9d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bb9d7  brtrue   loc_1BBB57
0x1bb9dc  br       loc_1BBD21
0x1bb9e1  ldloc.s  0xD
0x1bb9e3  ldstr    aWidth// "Width"
0x1bb9e8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bb9ed  brtrue   loc_1BBBD0
0x1bb9f2  br       loc_1BBD21
0x1bb9f7  ldloc.s  0xD
0x1bb9f9  ldstr    aLabel// "Label"
0x1bb9fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bba03  brtrue   loc_1BBC2C
0x1bba08  br       loc_1BBD21
0x1bba0d  ldloc.s  0xD
0x1bba0f  ldstr    aTop// "Top"
0x1bba14  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bba19  brtrue   loc_1BBB9D
0x1bba1e  br       loc_1BBD21
0x1bba23  ldloc.s  0xD
0x1bba25  ldstr    aLeft// "Left"
0x1bba2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bba2f  brtrue   loc_1BBBAE
0x1bba34  br       loc_1BBD21
0x1bba39  ldloc.s  0xD
0x1bba3b  ldstr    aHeight// "Height"
0x1bba40  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bba45  brtrue   loc_1BBBBF
0x1bba4a  br       loc_1BBD21
0x1bba4f  ldloc.s  0xD
0x1bba51  ldstr    aZindex// "ZIndex"
0x1bba56  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bba5b  brtrue   loc_1BBBE1
0x1bba60  br       loc_1BBD21
0x1bba65  ldloc.s  0xD
0x1bba67  ldstr    aCustom// "Custom"
0x1bba6c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bba71  brtrue   loc_1BBC86
0x1bba76  br       loc_1BBD21
0x1bba7b  ldloc.s  0xD
0x1bba7d  ldstr    aVisibility// "Visibility"
0x1bba82  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bba87  brtrue   loc_1BBBF7
0x1bba8c  br       loc_1BBD21
0x1bba91  ldloc.s  0xD
0x1bba93  ldstr    aRepeatwith// "RepeatWith"
0x1bba98  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bba9d  brtrue   loc_1BBC69
0x1bbaa2  br       loc_1BBD21
0x1bbaa7  ldloc.s  0xD
0x1bbaa9  ldstr    aParameters// "Parameters"
0x1bbaae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbab3  brtrue   loc_1BBCD3
0x1bbab8  br       loc_1BBD21
0x1bbabd  ldloc.s  0xD
0x1bbabf  ldstr    aTooltip// "ToolTip"
0x1bbac4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbac9  brtrue   loc_1BBC0B
0x1bbace  br       loc_1BBD21
0x1bbad3  ldloc.s  0xD
0x1bbad5  ldstr    aClassid// "ClassID"
0x1bbada  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbadf  brtrue   loc_1BBCAD
0x1bbae4  br       loc_1BBD21
0x1bbae9  ldloc.s  0xD
0x1bbaeb  ldstr    aBookmark// "Bookmark"
0x1bbaf0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbaf5  brtrue   loc_1BBC51
0x1bbafa  br       loc_1BBD21
0x1bbaff  ldloc.s  0xD
0x1bbb01  ldstr    aCodebase// "CodeBase"
0x1bbb06  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbb0b  brtrue   loc_1BBCC0
0x1bbb10  br       loc_1BBD21
0x1bbb15  ldloc.s  0xD
0x1bbb17  ldstr    aCustomproperti// "CustomProperties"
0x1bbb1c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbb21  brtrue   loc_1BBC9C
0x1bbb26  br       loc_1BBD21
0x1bbb2b  ldloc.s  0xD
0x1bbb2d  ldstr    aDataelementnam// "DataElementName"
0x1bbb32  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbb37  brtrue   loc_1BBCE6
0x1bbb3c  br       loc_1BBD21
0x1bbb41  ldloc.s  0xD
0x1bbb43  ldstr    aDataelementout// "DataElementOutput"
0x1bbb48  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bbb4d  brtrue   loc_1BBCF9
0x1bbb52  br       loc_1BBD21
0x1bbb57  ldarg.0
0x1bbb58  ldarg.2
0x1bbb59  ldloca.s 1
0x1bbb5b  call     instance class StyleInformation Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadStyle(valuetype PublishingContextStruct context, [out] bool& computed)
0x1bbb60  stloc.s  0xC
0x1bbb62  ldloc.s  0xC
0x1bbb64  ldc.i4.5
0x1bbb65  ldc.i4.0
0x1bbb66  callvirt instance void StyleInformation::Filter(valuetype StyleOwnerType ownerType, bool hasNoRows)
0x1bbb6b  ldloc.0
0x1bbb6c  ldloc.s  0xC
0x1bbb6e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.StringList StyleInformation::get_Names()
0x1bbb73  ldloc.s  0xC
0x1bbb75  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfoList StyleInformation::get_Values()
0x1bbb7a  ldarga.s 2
0x1bbb7c  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType PublishingContextStruct::get_ObjectType()
0x1bbb81  ldarga.s 2
0x1bbb83  call     instance string PublishingContextStruct::get_ObjectName()
0x1bbb88  ldarg.0
0x1bbb89  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1bbb8e  call     class Microsoft.ReportingServices.ReportProcessing.Style Microsoft.ReportingServices.ReportProcessing.PublishingValidator::ValidateAndCreateStyle(class Microsoft.ReportingServices.ReportProcessing.StringList names, class Microsoft.ReportingServices.ReportProcessing.ExpressionInfoList values, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x1bbb93  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_StyleClass(class Microsoft.ReportingServices.ReportProcessing.Style value)
0x1bbb98  br       loc_1BBD21
0x1bbb9d  ldloc.0
0x1bbb9e  ldarg.0
0x1bbb9f  call     instance string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadSize()
0x1bbba4  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Top(string value)
0x1bbba9  br       loc_1BBD21
0x1bbbae  ldloc.0
0x1bbbaf  ldarg.0
0x1bbbb0  call     instance string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadSize()
0x1bbbb5  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Left(string value)
0x1bbbba  br       loc_1BBD21
0x1bbbbf  ldloc.0
0x1bbbc0  ldarg.0
0x1bbbc1  call     instance string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadSize()
0x1bbbc6  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Height(string value)
0x1bbbcb  br       loc_1BBD21
0x1bbbd0  ldloc.0
0x1bbbd1  ldarg.0
0x1bbbd2  call     instance string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadSize()
0x1bbbd7  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Width(string value)
0x1bbbdc  br       loc_1BBD21
0x1bbbe1  ldloc.0
0x1bbbe2  ldarg.0
0x1bbbe3  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bbbe8  callvirt instance int32 RmlValidatingReader::ReadInteger()
0x1bbbed  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_ZIndex(int32 value)
0x1bbbf2  br       loc_1BBD21
0x1bbbf7  ldloc.0
0x1bbbf8  ldarg.0
0x1bbbf9  ldarg.2
0x1bbbfa  ldloca.s 2
0x1bbbfc  call     instance class Microsoft.ReportingServices.ReportProcessing.Visibility Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadVisibility(valuetype PublishingContextStruct context, [out] bool& computed)
0x1bbc01  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Visibility(class Microsoft.ReportingServices.ReportProcessing.Visibility value)
0x1bbc06  br       loc_1BBD21
0x1bbc0b  ldloc.0
0x1bbc0c  ldarg.0
0x1bbc0d  ldarg.0
0x1bbc0e  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bbc13  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1bbc18  ldc.i4.0
0x1bbc19  ldc.i4.0
0x1bbc1a  ldarg.2
0x1bbc1b  ldloca.s 5
0x1bbc1d  call     instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype ConstantType constantType, valuetype PublishingContextStruct context, [out] bool& computed)
0x1bbc22  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_ToolTip(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo value)
0x1bbc27  br       loc_1BBD21
  ... truncated ...
```
