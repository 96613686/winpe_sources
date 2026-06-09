# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartLegend

- ea: `0xa4fa0`
- end: `0xa57fb`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartLegend`
- size: `2139`
- prototype: ``
- caller_count: `1`
- callee_count: `54`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xa2220`

## callees

- `0xa1ec0`
- `0xa4020`
- `0xa4fa0`
- `0xa5800`
- `0xa5890`
- `0xac750`
- `0xb0fd0`
- `0xb85e0`
- `0xb8e80`
- `0xbcdc0`
- `0xbcde0`
- `0xbce20`
- `0xbe1c0`
- `0xbe2b0`
- `0xbe860`
- `0xbe9a0`
- `0xbf370`
- `0xc17c0`
- `0xfca70`
- `0xfca80`
- `0xfca90`
- `0xfcab0`
- `0xfcad0`
- `0xfcaf0`
- `0xfcb10`
- `0xfcb30`
- `0xfcb50`
- `0xfcb70`
- `0xfcb80`
- `0xfcb90`
- `0xfcba0`
- `0xfcbb0`
- `0xfcbc0`
- `0xfcbd0`
- `0xfcbe0`
- `0xfcbf0`
- `0xfcc00`
- `0xfcc10`
- `0xfcc30`
- `0xfcc50`
- `0xfcc60`
- `0xfcc70`
- `0xfcc90`
- `0xfcca0`
- `0xfccb0`
- `0xfccd0`
- `0xfccf0`
- `0xfcd10`
- `0xfcd30`
- `0xfcd50`

## string_xrefs

- `0xa524c`: `DockOutsideChartArea`

## pseudocode

```c

```

## disassembly

```asm
0xa4fa0  ldarg.1
0xa4fa1  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart)
0xa4fa6  stloc.0
0xa4fa7  ldloc.0
0xa4fa8  ldarg.0
0xa4fa9  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4fae  ldstr    aName_1// "Name"
0xa4fb3  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xa4fb8  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::set_LegendName(string value)
0xa4fbd  ldarg.3
0xa4fbe  ldc.i4.0
0xa4fbf  ldstr    aChartlegend// "ChartLegend"
0xa4fc4  ldc.i4.s 0x10
0xa4fc6  ldarg.1
0xa4fc7  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0xa4fcc  ldloc.0
0xa4fcd  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::get_LegendName()
0xa4fd2  ldarga.s 2
0xa4fd4  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa4fd9  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.DynamicImageOrCustomUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string propertyName, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyNameValue, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa4fde  pop
0xa4fdf  ldarg.0
0xa4fe0  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4fe5  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa4fea  brtrue   loc_A57F9
0xa4fef  ldc.i4.0
0xa4ff0  stloc.1
0xa4ff1  ldarg.0
0xa4ff2  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4ff7  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa4ffc  pop
0xa4ffd  ldarg.0
0xa4ffe  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa5003  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa5008  stloc.2
0xa5009  ldloc.2
0xa500a  ldc.i4.1
0xa500b  beq.s    loc_A501A
0xa500d  ldloc.2
0xa500e  ldc.i4.s 0xF
0xa5010  beq      loc_A57DA
0xa5015  br       loc_A57F3
0xa501a  ldarg.0
0xa501b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa5020  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa5025  stloc.s  4
0xa5027  ldloc.s  4
0xa5029  brfalse  loc_A57F3
0xa502e  ldloc.s  4
0xa5030  call     instance int32 [mscorlib]System.String::get_Length()
0xa5035  stloc.s  5
0xa5037  ldloc.s  5
0xa5039  ldc.i4.5
0xa503a  sub
0xa503b  switch   loc_A51C6, loc_A508D, loc_A57F3, loc_A50AE, loc_A57F3, loc_A57F3, loc_A5158, loc_A57F3, loc_A5310, loc_A5326, loc_A50CF, loc_A52A2, loc_A5368, loc_A5179, loc_A5137, loc_A50F9, loc_A57F3, loc_A537E
0xa5088  br       loc_A57F3
0xa508d  ldloc.s  4
0xa508f  ldc.i4.0
0xa5090  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa5095  stloc.s  6
0xa5097  ldloc.s  6
0xa5099  ldc.i4.s 0x48
0xa509b  beq      loc_A519A
0xa50a0  ldloc.s  6
0xa50a2  ldc.i4.s 0x4C
0xa50a4  beq      loc_A51B0
0xa50a9  br       loc_A57F3
0xa50ae  ldloc.s  4
0xa50b0  ldc.i4.0
0xa50b1  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa50b6  stloc.s  6
0xa50b8  ldloc.s  6
0xa50ba  ldc.i4.s 0x50
0xa50bc  beq      loc_A51DC
0xa50c1  ldloc.s  6
0xa50c3  ldc.i4.s 0x52
0xa50c5  beq      loc_A51F2
0xa50ca  br       loc_A57F3
0xa50cf  ldloc.s  4
0xa50d1  ldc.i4.0
0xa50d2  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa50d7  stloc.s  6
0xa50d9  ldloc.s  6
0xa50db  ldc.i4.s 0x43
0xa50dd  beq      loc_A5234
0xa50e2  ldloc.s  6
0xa50e4  ldc.i4.s 0x44
0xa50e6  beq      loc_A5208
0xa50eb  ldloc.s  6
0xa50ed  ldc.i4.s 0x48
0xa50ef  beq      loc_A521E
0xa50f4  br       loc_A57F3
0xa50f9  ldloc.s  4
0xa50fb  ldc.i4.3
0xa50fc  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa5101  stloc.s  6
0xa5103  ldloc.s  6
0xa5105  ldc.i4.s 0x6B
0xa5107  bgt.un.s loc_A5120
0xa5109  ldloc.s  6
0xa510b  ldc.i4.s 0x64
0xa510d  beq      loc_A5260
0xa5112  ldloc.s  6
0xa5114  ldc.i4.s 0x6B
0xa5116  beq      loc_A524A
0xa511b  br       loc_A57F3
0xa5120  ldloc.s  6
0xa5122  ldc.i4.s 0x72
0xa5124  beq      loc_A528C
0xa5129  ldloc.s  6
0xa512b  ldc.i4.s 0x75
0xa512d  beq      loc_A5276
0xa5132  br       loc_A57F3
0xa5137  ldloc.s  4
0xa5139  ldc.i4.0
0xa513a  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa513f  stloc.s  6
0xa5141  ldloc.s  6
0xa5143  ldc.i4.s 0x41
0xa5145  beq      loc_A52B8
0xa514a  ldloc.s  6
0xa514c  ldc.i4.s 0x49
0xa514e  beq      loc_A52CE
0xa5153  br       loc_A57F3
0xa5158  ldloc.s  4
0xa515a  ldc.i4.1
0xa515b  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa5160  stloc.s  6
0xa5162  ldloc.s  6
0xa5164  ldc.i4.s 0x61
0xa5166  beq      loc_A52FA
0xa516b  ldloc.s  6
0xa516d  ldc.i4.s 0x69
0xa516f  beq      loc_A52E4
0xa5174  br       loc_A57F3
0xa5179  ldloc.s  4
0xa517b  ldc.i4.0
0xa517c  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa5181  stloc.s  6
0xa5183  ldloc.s  6
0xa5185  ldc.i4.s 0x43
0xa5187  beq      loc_A5352
0xa518c  ldloc.s  6
0xa518e  ldc.i4.s 0x45
0xa5190  beq      loc_A533C
0xa5195  br       loc_A57F3
0xa519a  ldloc.s  4
0xa519c  ldstr    aHidden// "Hidden"
0xa51a1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa51a6  brtrue   loc_A5394
0xa51ab  br       loc_A57F3
0xa51b0  ldloc.s  4
0xa51b2  ldstr    aLayout// "Layout"
0xa51b7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa51bc  brtrue   loc_A5410
0xa51c1  br       loc_A57F3
0xa51c6  ldloc.s  4
0xa51c8  ldstr    aStyle_1// "Style"
0xa51cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa51d2  brtrue   loc_A53B3
0xa51d7  br       loc_A57F3
0xa51dc  ldloc.s  4
0xa51de  ldstr    aPosition// "Position"
0xa51e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa51e8  brtrue   loc_A53F0
0xa51ed  br       loc_A57F3
0xa51f2  ldloc.s  4
0xa51f4  ldstr    aReversed// "Reversed"
0xa51f9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa51fe  brtrue   loc_A5717
0xa5203  br       loc_A57F3
0xa5208  ldloc.s  4
0xa520a  ldstr    aDocktochartare// "DockToChartArea"
0xa520f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5214  brtrue   loc_A5430
0xa5219  br       loc_A57F3
0xa521e  ldloc.s  4
0xa5220  ldstr    aHeaderseparato// "HeaderSeparator"
0xa5225  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa522a  brtrue   loc_A54FD
0xa522f  br       loc_A57F3
0xa5234  ldloc.s  4
0xa5236  ldstr    aColumnseparato// "ColumnSeparator"
0xa523b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5240  brtrue   loc_A55AD
0xa5245  br       loc_A57F3
0xa524a  ldloc.s  4
0xa524c  ldstr    aDockoutsidecha// "DockOutsideChartArea"
0xa5251  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5256  brtrue   loc_A5446
0xa525b  br       loc_A57F3
0xa5260  ldloc.s  4
0xa5262  ldstr    aHeaderseparato_0// "HeaderSeparatorColor"
0xa5267  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa526c  brtrue   loc_A5551
0xa5271  br       loc_A57F3
0xa5276  ldloc.s  4
0xa5278  ldstr    aColumnseparato_0// "ColumnSeparatorColor"
0xa527d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5282  brtrue   loc_A5601
0xa5287  br       loc_A57F3
0xa528c  ldloc.s  4
0xa528e  ldstr    aChartelementpo// "ChartElementPosition"
0xa5293  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5298  brtrue   loc_A57C5
0xa529d  br       loc_A57F3
0xa52a2  ldloc.s  4
0xa52a4  ldstr    aChartlegendtit// "ChartLegendTitle"
0xa52a9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa52ae  brtrue   loc_A5465
0xa52b3  br       loc_A57F3
0xa52b8  ldloc.s  4
0xa52ba  ldstr    aAutofittextdis// "AutoFitTextDisabled"
0xa52bf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa52c4  brtrue   loc_A5478
0xa52c9  br       loc_A57F3
0xa52ce  ldloc.s  4
0xa52d0  ldstr    aInterlacedrows_0// "InterlacedRowsColor"
0xa52d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa52da  brtrue   loc_A569C
0xa52df  br       loc_A57F3
0xa52e4  ldloc.s  4
0xa52e6  ldstr    aMinfontsize// "MinFontSize"
0xa52eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa52f0  brtrue   loc_A5497
0xa52f5  br       loc_A57F3
0xa52fa  ldloc.s  4
0xa52fc  ldstr    aMaxautosize// "MaxAutoSize"
0xa5301  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5306  brtrue   loc_A576B
0xa530b  br       loc_A57F3
0xa5310  ldloc.s  4
0xa5312  ldstr    aColumnspacing// "ColumnSpacing"
0xa5317  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa531c  brtrue   loc_A565D
0xa5321  br       loc_A57F3
0xa5326  ldloc.s  4
0xa5328  ldstr    aInterlacedrows// "InterlacedRows"
0xa532d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5332  brtrue   loc_A567D
0xa5337  br       loc_A57F3
0xa533c  ldloc.s  4
0xa533e  ldstr    aEquallyspacedi// "EquallySpacedItems"
0xa5343  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5348  brtrue   loc_A56F8
0xa534d  br       loc_A57F3
0xa5352  ldloc.s  4
0xa5354  ldstr    aChartlegendcol_0// "ChartLegendColumns"
0xa5359  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa535e  brtrue   loc_A57A5
0xa5363  br       loc_A57F3
0xa5368  ldloc.s  4
0xa536a  ldstr    aTextwrapthresh// "TextWrapThreshold"
0xa536f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa5374  brtrue   loc_A5788
0xa5379  br       loc_A57F3
0xa537e  ldloc.s  4
0xa5380  ldstr    aChartlegendcus_2// "ChartLegendCustomItems"
0xa5385  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa538a  brtrue   loc_A57B5
0xa538f  br       loc_A57F3
0xa5394  ldloc.0
0xa5395  ldarg.0
0xa5396  ldarg.0
0xa5397  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa539c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa53a1  ldc.i4.0
0xa53a2  ldc.i4.3
0xa53a3  ldarg.2
0xa53a4  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa53a9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartLegend::set_Hidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa53ae  br       loc_A57F3
0xa53b3  ldarg.0
0xa53b4  ldarg.2
0xa53b5  call     instance class Microsoft.ReportingServices.ReportPublishing.StyleInformation Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadStyle(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa53ba  stloc.3
0xa53bb  ldloc.3
0xa53bc  ldc.i4.s 0xB
0xa53be  ldc.i4.0
0xa53bf  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::Filter(valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType ownerType, bool hasNoRows)
0xa53c4  ldloc.0
0xa53c5  ldloc.3
0xa53c6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> Microsoft.ReportingServices.ReportPublishing.StyleInformation::get_Attributes()
0xa53cb  ldarga.s 2
0xa53cd  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa53d2  ldarga.s 2
0xa53d4  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xa53d9  ldc.i4.1
0xa53da  ldarga.s 2
0xa53dc  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa53e1  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle(class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> attributes, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, bool isDynamicImageSubElement, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa53e6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartStyleContainer::set_StyleClass(class Microsoft.ReportingServices.ReportIntermediateFormat.Style value)
0xa53eb  br       loc_A57F3
0xa53f0  ldloc.0
0xa53f1  ldarg.0
0xa53f2  ldarg.0
0xa53f3  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa53f8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa53fd  ldc.i4.0
0xa53fe  ldc.i4.s 0x12
  ... truncated ...
```
