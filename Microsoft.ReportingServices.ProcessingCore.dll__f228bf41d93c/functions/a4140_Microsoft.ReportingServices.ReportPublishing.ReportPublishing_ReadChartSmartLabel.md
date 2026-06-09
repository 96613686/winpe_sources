# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartSmartLabel

- ea: `0xa4140`
- end: `0xa470c`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadChartSmartLabel`
- size: `1484`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xa6830`

## callees

- `0xa3990`
- `0xa4140`
- `0xac750`
- `0xb84a0`
- `0xb84e0`
- `0xb8530`
- `0xb85a0`
- `0xbcdc0`
- `0xbcde0`
- `0xbce20`
- `0xbe860`
- `0xbe9a0`
- `0xff1f0`
- `0xff220`
- `0xff230`
- `0xff240`
- `0xff250`
- `0xff260`
- `0xff270`
- `0xff280`
- `0xff290`
- `0xff2a0`
- `0xff2b0`
- `0xff2c0`
- `0xff2d0`
- `0xff2e0`
- `0xff2f0`
- `0xff310`
- `0xff330`
- `0xff340`
- `0xff350`
- `0xff360`
- `0xff370`
- `0xff390`
- `0xff3b0`
- `0x1177f0`
- `0x117880`

## string_xrefs

- `0xa4338`: `ChartNoMoveDirections`
- `0xa4241`: `AllowOutSidePlotArea`

## pseudocode

```c

```

## disassembly

```asm
0xa4140  ldarg.1
0xa4141  ldarg.2
0xa4142  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.Chart chart, class Microsoft.ReportingServices.ReportIntermediateFormat.ChartSeries chartSeries)
0xa4147  stloc.0
0xa4148  ldarg.0
0xa4149  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa414e  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa4153  brtrue   loc_A470A
0xa4158  ldc.i4.0
0xa4159  stloc.1
0xa415a  ldarg.0
0xa415b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4160  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xa4165  pop
0xa4166  ldarg.0
0xa4167  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa416c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa4171  stloc.2
0xa4172  ldloc.2
0xa4173  ldc.i4.1
0xa4174  beq.s    loc_A4183
0xa4176  ldloc.2
0xa4177  ldc.i4.s 0xF
0xa4179  beq      loc_A46EB
0xa417e  br       loc_A4704
0xa4183  ldarg.0
0xa4184  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4189  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa418e  stloc.3
0xa418f  ldloc.3
0xa4190  brfalse  loc_A4704
0xa4195  ldloc.3
0xa4196  call     instance int32 [mscorlib]System.String::get_Length()
0xa419b  stloc.s  4
0xa419d  ldloc.s  4
0xa419f  ldc.i4.8
0xa41a0  beq      loc_A4322
0xa41a5  ldloc.s  4
0xa41a7  ldc.i4.s 0xC
0xa41a9  sub
0xa41aa  switch   loc_A42F8, loc_A4704, loc_A430D, loc_A4704, loc_A41DC, loc_A4203, loc_A4704, loc_A4704, loc_A4240, loc_A4337
0xa41d7  br       loc_A4704
0xa41dc  ldloc.3
0xa41dd  ldc.i4.s 0xB
0xa41df  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa41e4  stloc.s  5
0xa41e6  ldloc.s  5
0xa41e8  ldc.i4.s 0x43
0xa41ea  beq.s    loc_A4255
0xa41ec  ldloc.s  5
0xa41ee  ldc.i4.s 0x53
0xa41f0  beq      loc_A427A
0xa41f5  ldloc.s  5
0xa41f7  ldc.i4.s 0x57
0xa41f9  beq      loc_A428F
0xa41fe  br       loc_A4704
0xa4203  ldloc.3
0xa4204  ldc.i4.2
0xa4205  call     instance char [mscorlib]System.String::get_Chars(int32)
0xa420a  stloc.s  5
0xa420c  ldloc.s  5
0xa420e  ldc.i4.s 0x6E
0xa4210  bgt.un.s loc_A4229
0xa4212  ldloc.s  5
0xa4214  ldc.i4.s 0x6C
0xa4216  beq      loc_A42A4
0xa421b  ldloc.s  5
0xa421d  ldc.i4.s 0x6E
0xa421f  beq      loc_A42E3
0xa4224  br       loc_A4704
0xa4229  ldloc.s  5
0xa422b  ldc.i4.s 0x72
0xa422d  beq      loc_A42B9
0xa4232  ldloc.s  5
0xa4234  ldc.i4.s 0x78
0xa4236  beq      loc_A42CE
0xa423b  br       loc_A4704
0xa4240  ldloc.3
0xa4241  ldstr    aAllowoutsidepl// "AllowOutSidePlotArea"
0xa4246  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa424b  brtrue   loc_A434C
0xa4250  br       loc_A4704
0xa4255  ldloc.3
0xa4256  ldstr    aCalloutbackcol// "CalloutBackColor"
0xa425b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4260  brtrue   loc_A43A0
0xa4265  ldloc.3
0xa4266  ldstr    aCalloutlinecol// "CalloutLineColor"
0xa426b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4270  brtrue   loc_A4450
0xa4275  br       loc_A4704
0xa427a  ldloc.3
0xa427b  ldstr    aCalloutlinesty// "CalloutLineStyle"
0xa4280  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4285  brtrue   loc_A44AC
0xa428a  br       loc_A4704
0xa428f  ldloc.3
0xa4290  ldstr    aCalloutlinewid// "CalloutLineWidth"
0xa4295  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa429a  brtrue   loc_A4500
0xa429f  br       loc_A4704
0xa42a4  ldloc.3
0xa42a5  ldstr    aCalloutlineanc// "CalloutLineAnchor"
0xa42aa  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa42af  brtrue   loc_A43FC
0xa42b4  br       loc_A4704
0xa42b9  ldloc.3
0xa42ba  ldstr    aMarkeroverlapp// "MarkerOverlapping"
0xa42bf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa42c4  brtrue   loc_A45D9
0xa42c9  br       loc_A4704
0xa42ce  ldloc.3
0xa42cf  ldstr    aMaxmovingdista// "MaxMovingDistance"
0xa42d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa42d9  brtrue   loc_A45F8
0xa42de  br       loc_A4704
0xa42e3  ldloc.3
0xa42e4  ldstr    aMinmovingdista// "MinMovingDistance"
0xa42e9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa42ee  brtrue   loc_A465E
0xa42f3  br       loc_A4704
0xa42f8  ldloc.3
0xa42f9  ldstr    aCalloutstyle// "CalloutStyle"
0xa42fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4303  brtrue   loc_A4566
0xa4308  br       loc_A4704
0xa430d  ldloc.3
0xa430e  ldstr    aShowoverlapped// "ShowOverlapped"
0xa4313  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4318  brtrue   loc_A45BA
0xa431d  br       loc_A4704
0xa4322  ldloc.3
0xa4323  ldstr    aDisabled// "Disabled"
0xa4328  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa432d  brtrue   loc_A46BE
0xa4332  br       loc_A4704
0xa4337  ldloc.3
0xa4338  ldstr    aChartnomovedir// "ChartNoMoveDirections"
0xa433d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa4342  brtrue   loc_A46DA
0xa4347  br       loc_A4704
0xa434c  ldloc.0
0xa434d  ldarg.0
0xa434e  ldarg.0
0xa434f  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4354  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa4359  ldc.i4.0
0xa435a  ldc.i4.s 0x12
0xa435c  ldarg.3
0xa435d  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa4362  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::set_AllowOutSidePlotArea(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa4367  ldloc.0
0xa4368  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_AllowOutSidePlotArea()
0xa436d  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa4372  brtrue   loc_A4704
0xa4377  ldloc.0
0xa4378  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_AllowOutSidePlotArea()
0xa437d  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0xa4382  ldarga.s 3
0xa4384  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa4389  ldarg.3
0xa438a  ldarg.0
0xa438b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4390  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa4395  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartAllowOutsideChartArea(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xa439a  pop
0xa439b  br       loc_A4704
0xa43a0  ldloc.0
0xa43a1  ldarg.0
0xa43a2  ldarg.0
0xa43a3  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa43a8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa43ad  ldc.i4.0
0xa43ae  ldc.i4.s 0x12
0xa43b0  ldarg.3
0xa43b1  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa43b6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::set_CalloutBackColor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa43bb  ldloc.0
0xa43bc  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutBackColor()
0xa43c1  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa43c6  brtrue   loc_A4704
0xa43cb  ldloc.0
0xa43cc  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutBackColor()
0xa43d1  ldarga.s 3
0xa43d3  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa43d8  ldarga.s 3
0xa43da  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xa43df  ldarg.0
0xa43e0  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa43e5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa43ea  ldarga.s 3
0xa43ec  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa43f1  call     bool Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateColor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo color, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa43f6  pop
0xa43f7  br       loc_A4704
0xa43fc  ldloc.0
0xa43fd  ldarg.0
0xa43fe  ldarg.0
0xa43ff  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4404  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa4409  ldc.i4.0
0xa440a  ldc.i4.s 0x12
0xa440c  ldarg.3
0xa440d  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa4412  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::set_CalloutLineAnchor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa4417  ldloc.0
0xa4418  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutLineAnchor()
0xa441d  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa4422  brtrue   loc_A4704
0xa4427  ldloc.0
0xa4428  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutLineAnchor()
0xa442d  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0xa4432  ldarga.s 3
0xa4434  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa4439  ldarg.3
0xa443a  ldarg.0
0xa443b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4440  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa4445  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartCalloutLineAnchor(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xa444a  pop
0xa444b  br       loc_A4704
0xa4450  ldloc.0
0xa4451  ldarg.0
0xa4452  ldarg.0
0xa4453  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4458  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa445d  ldc.i4.0
0xa445e  ldc.i4.s 0x12
0xa4460  ldarg.3
0xa4461  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa4466  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::set_CalloutLineColor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa446b  ldloc.0
0xa446c  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutLineColor()
0xa4471  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa4476  brtrue   loc_A4704
0xa447b  ldloc.0
0xa447c  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutLineColor()
0xa4481  ldarga.s 3
0xa4483  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa4488  ldarga.s 3
0xa448a  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xa448f  ldarg.0
0xa4490  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4495  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa449a  ldarga.s 3
0xa449c  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa44a1  call     bool Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateColor(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo color, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xa44a6  pop
0xa44a7  br       loc_A4704
0xa44ac  ldloc.0
0xa44ad  ldarg.0
0xa44ae  ldarg.0
0xa44af  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa44b4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa44b9  ldc.i4.0
0xa44ba  ldc.i4.s 0x12
0xa44bc  ldarg.3
0xa44bd  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa44c2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::set_CalloutLineStyle(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa44c7  ldloc.0
0xa44c8  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutLineStyle()
0xa44cd  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa44d2  brtrue   loc_A4704
0xa44d7  ldloc.0
0xa44d8  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutLineStyle()
0xa44dd  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0xa44e2  ldarga.s 3
0xa44e4  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xa44e9  ldarg.3
0xa44ea  ldarg.0
0xa44eb  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa44f0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa44f5  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartCalloutLineStyle(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xa44fa  pop
0xa44fb  br       loc_A4704
0xa4500  ldloc.0
0xa4501  ldarg.0
0xa4502  ldarg.0
0xa4503  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa4508  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa450d  ldc.i4.0
0xa450e  ldc.i4.s 0x12
0xa4510  ldarg.3
0xa4511  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0xa4516  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::set_CalloutLineWidth(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0xa451b  ldloc.0
0xa451c  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutLineWidth()
0xa4521  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0xa4526  brtrue   loc_A4704
0xa452b  ldloc.0
0xa452c  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ChartSmartLabel::get_CalloutLineWidth()
0xa4531  ldsfld   float64 Microsoft.ReportingServices.ReportPublishing.Validator::NormalMin
0xa4536  ldsfld   float64 Microsoft.ReportingServices.ReportPublishing.Validator::NormalMax
0xa453b  ldarga.s 3
0xa453d  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xa4542  ldarga.s 3
0xa4544  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xa4549  ldarg.0
0xa454a  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xa454f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
  ... truncated ...
```
