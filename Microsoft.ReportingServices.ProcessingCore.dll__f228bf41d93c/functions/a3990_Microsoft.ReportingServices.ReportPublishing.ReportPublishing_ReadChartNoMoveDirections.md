# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartNoMoveDirections

- ea: `0xa3990`
- end: `0xa3bea`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartNoMoveDirections`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0xa4140`

## callees

- `0xa3990`
- `0xac750`
- `0xfe190`
- `0xfe1d0`
- `0xfe1f0`
- `0xfe210`
- `0xfe230`
- `0xfe250`
- `0xfe270`
- `0xfe290`
- `0xfe2b0`

## string_xrefs

- `0xa3bc9`: `ChartNoMoveDirections`

## pseudocode

```c

```

## disassembly

```asm
0xa3990  ldarg.1
0xa3991  ldarg.2
0xa3992  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart, class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries chartSeries)
0xa3997  stloc.0
0xa3998  ldarg.0
0xa3999  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa399e  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa39a3  brtrue   loc_A3BE8
0xa39a8  ldc.i4.0
0xa39a9  stloc.1
0xa39aa  ldarg.0
0xa39ab  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa39b0  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa39b5  pop
0xa39b6  ldarg.0
0xa39b7  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa39bc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa39c1  stloc.2
0xa39c2  ldloc.2
0xa39c3  ldc.i4.1
0xa39c4  beq.s    loc_A39D3
0xa39c6  ldloc.2
0xa39c7  ldc.i4.s 0xF
0xa39c9  beq      loc_A3BC9
0xa39ce  br       loc_A3BE2
0xa39d3  ldarg.0
0xa39d4  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa39d9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa39de  stloc.3
0xa39df  ldloc.3
0xa39e0  brfalse  loc_A3BE2
0xa39e5  ldloc.3
0xa39e6  call     instance int32 [mscorlib]System.String::get_Length()
0xa39eb  stloc.s  4
0xa39ed  ldloc.s  4
0xa39ef  ldc.i4.2
0xa39f0  sub
0xa39f1  switch   loc_A3A35, loc_A3BE2, loc_A3A1B, loc_A3A74, loc_A3A89, loc_A3A9E, loc_A3AB3, loc_A3AC8
0xa3a16  br       loc_A3BE2
0xa3a1b  ldloc.3
0xa3a1c  ldc.i4.0
0xa3a1d  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa3a22  stloc.s  5
0xa3a24  ldloc.s  5
0xa3a26  ldc.i4.s 0x44
0xa3a28  beq.s    loc_A3A4A
0xa3a2a  ldloc.s  5
0xa3a2c  ldc.i4.s 0x4C
0xa3a2e  beq.s    loc_A3A5F
0xa3a30  br       loc_A3BE2
0xa3a35  ldloc.3
0xa3a36  ldstr    aUp// "Up"
0xa3a3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3a40  brtrue   loc_A3ADD
0xa3a45  br       loc_A3BE2
0xa3a4a  ldloc.3
0xa3a4b  ldstr    aDown// "Down"
0xa3a50  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3a55  brtrue   loc_A3AFC
0xa3a5a  br       loc_A3BE2
0xa3a5f  ldloc.3
0xa3a60  ldstr    aLeft// "Left"
0xa3a65  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3a6a  brtrue   loc_A3B1B
0xa3a6f  br       loc_A3BE2
0xa3a74  ldloc.3
0xa3a75  ldstr    aRight// "Right"
0xa3a7a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3a7f  brtrue   loc_A3B3A
0xa3a84  br       loc_A3BE2
0xa3a89  ldloc.3
0xa3a8a  ldstr    aUpleft// "UpLeft"
0xa3a8f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3a94  brtrue   loc_A3B59
0xa3a99  br       loc_A3BE2
0xa3a9e  ldloc.3
0xa3a9f  ldstr    aUpright// "UpRight"
0xa3aa4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3aa9  brtrue   loc_A3B75
0xa3aae  br       loc_A3BE2
0xa3ab3  ldloc.3
0xa3ab4  ldstr    aDownleft// "DownLeft"
0xa3ab9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3abe  brtrue   loc_A3B91
0xa3ac3  br       loc_A3BE2
0xa3ac8  ldloc.3
0xa3ac9  ldstr    aDownright// "DownRight"
0xa3ace  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3ad3  brtrue   loc_A3BAD
0xa3ad8  br       loc_A3BE2
0xa3add  ldloc.0
0xa3ade  ldarg.0
0xa3adf  ldarg.0
0xa3ae0  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa3ae5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa3aea  ldc.i4.0
0xa3aeb  ldc.i4.3
0xa3aec  ldarg.3
0xa3aed  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa3af2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::set_Up(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa3af7  br       loc_A3BE2
0xa3afc  ldloc.0
0xa3afd  ldarg.0
0xa3afe  ldarg.0
0xa3aff  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa3b04  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa3b09  ldc.i4.0
0xa3b0a  ldc.i4.3
0xa3b0b  ldarg.3
0xa3b0c  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa3b11  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::set_Down(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa3b16  br       loc_A3BE2
0xa3b1b  ldloc.0
0xa3b1c  ldarg.0
0xa3b1d  ldarg.0
0xa3b1e  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa3b23  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa3b28  ldc.i4.0
0xa3b29  ldc.i4.3
0xa3b2a  ldarg.3
0xa3b2b  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa3b30  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::set_Left(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa3b35  br       loc_A3BE2
0xa3b3a  ldloc.0
0xa3b3b  ldarg.0
0xa3b3c  ldarg.0
0xa3b3d  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa3b42  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa3b47  ldc.i4.0
0xa3b48  ldc.i4.3
0xa3b49  ldarg.3
0xa3b4a  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa3b4f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::set_Right(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa3b54  br       loc_A3BE2
0xa3b59  ldloc.0
0xa3b5a  ldarg.0
0xa3b5b  ldarg.0
0xa3b5c  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa3b61  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa3b66  ldc.i4.0
0xa3b67  ldc.i4.3
0xa3b68  ldarg.3
0xa3b69  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa3b6e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::set_UpLeft(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa3b73  br.s     loc_A3BE2
0xa3b75  ldloc.0
0xa3b76  ldarg.0
0xa3b77  ldarg.0
0xa3b78  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa3b7d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa3b82  ldc.i4.0
0xa3b83  ldc.i4.3
0xa3b84  ldarg.3
0xa3b85  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa3b8a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::set_UpRight(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa3b8f  br.s     loc_A3BE2
0xa3b91  ldloc.0
0xa3b92  ldarg.0
0xa3b93  ldarg.0
0xa3b94  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa3b99  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa3b9e  ldc.i4.0
0xa3b9f  ldc.i4.3
0xa3ba0  ldarg.3
0xa3ba1  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa3ba6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::set_DownLeft(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa3bab  br.s     loc_A3BE2
0xa3bad  ldloc.0
0xa3bae  ldarg.0
0xa3baf  ldarg.0
0xa3bb0  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa3bb5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa3bba  ldc.i4.0
0xa3bbb  ldc.i4.3
0xa3bbc  ldarg.3
0xa3bbd  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa3bc2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartNoMoveDirections::set_DownRight(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa3bc7  br.s     loc_A3BE2
0xa3bc9  ldstr    aChartnomovedir// "ChartNoMoveDirections"
0xa3bce  ldarg.0
0xa3bcf  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa3bd4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa3bd9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa3bde  brfalse.s loc_A3BE2
0xa3be0  ldc.i4.1
0xa3be1  stloc.1
0xa3be2  ldloc.1
0xa3be3  brfalse  loc_A39AA
0xa3be8  ldloc.0
0xa3be9  ret
```
