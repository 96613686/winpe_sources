# Microsoft.ReportingServices.OnDemandReportRendering.Style::ConstructStyleDefinition

- ea: `0x84470`
- end: `0x85322`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.Style::ConstructStyleDefinition`
- size: `3762`
- prototype: ``
- caller_count: `1`
- callee_count: `115`
- tags: `service_task, broker_com_uri`

## callers

- `0x77920`

## callees

- `0x71eb0`
- `0x777f0`
- `0x778a0`
- `0x77eb0`
- `0x78a10`
- `0x7fc70`
- `0x7fc90`
- `0x7fcb0`
- `0x7fcd0`
- `0x7fcf0`
- `0x7fd10`
- `0x7fd30`
- `0x7fd50`
- `0x7fd70`
- `0x7fd90`
- `0x7fdb0`
- `0x7fdd0`
- `0x7fdf0`
- `0x7fe10`
- `0x7fe30`
- `0x7fe50`
- `0x7fe70`
- `0x7fe90`
- `0x7feb0`
- `0x7fed0`
- `0x7fef0`
- `0x7ff10`
- `0x7ff30`
- `0x7ff50`
- `0x7ff70`
- `0x7ff90`
- `0x7ffb0`
- `0x7ffd0`
- `0x7fff0`
- `0x804d0`
- `0x80580`
- `0x80630`
- `0x80700`
- `0x807b0`
- `0x80880`
- `0x80930`
- `0x80a00`
- `0x80ad0`
- `0x80ba0`
- `0x80c70`
- `0x80d40`
- `0x80df0`
- `0x80ec0`
- `0x80f90`
- `0x81040`

## pseudocode

```c

```

## disassembly

```asm
0x84470  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x84475  ldarg.0
0x84476  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportElement Microsoft.ReportingServices.OnDemandReportRendering.Style::get_ReportElement()
0x8447b  ldnull
0x8447c  cgt.un
0x8447e  ldstr    aReportelementN// "(ReportElement != null)"
0x84483  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x84488  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x8448d  ldarg.0
0x8448e  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportElement Microsoft.ReportingServices.OnDemandReportRendering.Style::get_ReportElement()
0x84493  isinst   Microsoft.ReportingServices.OnDemandReportRendering.ReportItem
0x84498  ldnull
0x84499  cgt.un
0x8449b  ldstr    aReportelementI// "(ReportElement is ReportItem)"
0x844a0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x844a5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x844aa  ldarg.0
0x844ab  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportElement Microsoft.ReportingServices.OnDemandReportRendering.Style::get_ReportElement()
0x844b0  callvirt instance valuetype CriGenerationPhases Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_CriGenerationPhase()
0x844b5  ldc.i4.1
0x844b6  ceq
0x844b8  ldstr    aReportelementC// "(ReportElement.CriGenerationPhase == Re"...
0x844bd  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x844c2  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x844c7  ldarg.0
0x844c8  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportElement Microsoft.ReportingServices.OnDemandReportRendering.Style::get_ReportElement()
0x844cd  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ReportItemDef()
0x844d2  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_StyleClass()
0x844d7  ldnull
0x844d8  ceq
0x844da  ldstr    aReportelementR// "(ReportElement.ReportItemDef.StyleClass"...
0x844df  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x844e4  ldarg.0
0x844e5  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportElement Microsoft.ReportingServices.OnDemandReportRendering.Style::get_ReportElement()
0x844ea  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ReportItemDef()
0x844ef  ldc.i4.0
0x844f0  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::.ctor(valuetype Microsoft.ReportingServices.ReportIntermediateFormat.ConstructionPhase phase)
0x844f5  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_StyleClass(class Microsoft.ReportingServices.ReportIntermediateFormat.Style value)
0x844fa  ldarg.0
0x844fb  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportElement Microsoft.ReportingServices.OnDemandReportRendering.Style::get_ReportElement()
0x84500  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ReportItemDef()
0x84505  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_StyleClass()
0x8450a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::InitializeForCRIGeneratedReportItem()
0x8450f  ldarg.0
0x84510  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.Border Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_Border()
0x84515  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.Border::ConstructBorderDefinition()
0x8451a  ldarg.0
0x8451b  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.Border Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_TopBorder()
0x84520  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.Border::ConstructBorderDefinition()
0x84525  ldarg.0
0x84526  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.Border Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_BottomBorder()
0x8452b  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.Border::ConstructBorderDefinition()
0x84530  ldarg.0
0x84531  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.Border Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_LeftBorder()
0x84536  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.Border::ConstructBorderDefinition()
0x8453b  ldarg.0
0x8453c  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.Border Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_RightBorder()
0x84541  callvirt instance void Microsoft.ReportingServices.OnDemandReportRendering.Border::ConstructBorderDefinition()
0x84546  ldarg.0
0x84547  call     instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportElement Microsoft.ReportingServices.OnDemandReportRendering.Style::get_ReportElement()
0x8454c  castclass Microsoft.ReportingServices.OnDemandReportRendering.ReportItem
0x84551  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x84556  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.StyleInstance Microsoft.ReportingServices.OnDemandReportRendering.ReportElementInstance::get_Style()
0x8455b  stloc.0
0x8455c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x84561  ldarg.0
0x84562  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportColorProperty Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_BackgroundColor()
0x84567  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x8456c  ldc.i4.0
0x8456d  ceq
0x8456f  ldstr    aThisBackground// "(!this.BackgroundColor.IsExpression)"
0x84574  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x84579  ldloc.0
0x8457a  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.StyleInstance::get_IsBackgroundColorAssigned()
0x8457f  brfalse.s loc_845B8
0x84581  ldloc.0
0x84582  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportColor Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_BackgroundColor()
0x84587  brtrue.s loc_8458C
0x84589  ldnull
0x8458a  br.s     loc_84597
0x8458c  ldloc.0
0x8458d  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportColor Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_BackgroundColor()
0x84592  callvirt instance string [mscorlib]System.Object::ToString()
0x84597  stloc.1
0x84598  ldarg.0
0x84599  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x8459e  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x845a3  ldarg.0
0x845a4  ldc.i4.s 0xF
0x845a6  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x845ab  ldloc.1
0x845ac  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateConstExpression(string value)
0x845b1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x845b6  br.s     loc_845D5
0x845b8  ldarg.0
0x845b9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x845be  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x845c3  ldarg.0
0x845c4  ldc.i4.s 0xF
0x845c6  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x845cb  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateEmptyExpression()
0x845d0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x845d5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x845da  ldarg.0
0x845db  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportColorProperty Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_BackgroundGradientEndColor()
0x845e0  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x845e5  ldc.i4.0
0x845e6  ceq
0x845e8  ldstr    aThisBackground_0// "(!this.BackgroundGradientEndColor.IsExp"...
0x845ed  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x845f2  ldloc.0
0x845f3  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.StyleInstance::get_IsBackgroundGradientEndColorAssigned()
0x845f8  brfalse.s loc_84631
0x845fa  ldloc.0
0x845fb  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportColor Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_BackgroundGradientEndColor()
0x84600  brtrue.s loc_84605
0x84602  ldnull
0x84603  br.s     loc_84610
0x84605  ldloc.0
0x84606  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportColor Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_BackgroundGradientEndColor()
0x8460b  callvirt instance string [mscorlib]System.Object::ToString()
0x84610  stloc.2
0x84611  ldarg.0
0x84612  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x84617  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x8461c  ldarg.0
0x8461d  ldc.i4.s 0x26
0x8461f  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x84624  ldloc.2
0x84625  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateConstExpression(string value)
0x8462a  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x8462f  br.s     loc_8464E
0x84631  ldarg.0
0x84632  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x84637  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x8463c  ldarg.0
0x8463d  ldc.i4.s 0x26
0x8463f  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x84644  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateEmptyExpression()
0x84649  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x8464e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x84653  ldarg.0
0x84654  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportColorProperty Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_Color()
0x84659  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x8465e  ldc.i4.0
0x8465f  ceq
0x84661  ldstr    aThisColorIsexp// "(!this.Color.IsExpression)"
0x84666  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8466b  ldloc.0
0x8466c  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.StyleInstance::get_IsColorAssigned()
0x84671  brfalse.s loc_846AA
0x84673  ldloc.0
0x84674  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportColor Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_Color()
0x84679  brtrue.s loc_8467E
0x8467b  ldnull
0x8467c  br.s     loc_84689
0x8467e  ldloc.0
0x8467f  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportColor Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_Color()
0x84684  callvirt instance string [mscorlib]System.Object::ToString()
0x84689  stloc.3
0x8468a  ldarg.0
0x8468b  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x84690  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x84695  ldarg.0
0x84696  ldc.i4.s 0x18
0x84698  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x8469d  ldloc.3
0x8469e  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateConstExpression(string value)
0x846a3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x846a8  br.s     loc_846C7
0x846aa  ldarg.0
0x846ab  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x846b0  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x846b5  ldarg.0
0x846b6  ldc.i4.s 0x18
0x846b8  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x846bd  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateEmptyExpression()
0x846c2  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x846c7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x846cc  ldarg.0
0x846cd  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportEnumProperty`1<valuetype Microsoft.ReportingServices.OnDemandReportRendering.FontStyles> Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_FontStyle()
0x846d2  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x846d7  ldc.i4.0
0x846d8  ceq
0x846da  ldstr    aThisFontstyleI// "(!this.FontStyle.IsExpression)"
0x846df  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x846e4  ldloc.0
0x846e5  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.StyleInstance::get_IsFontStyleAssigned()
0x846ea  brfalse.s loc_84720
0x846ec  ldarg.0
0x846ed  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x846f2  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x846f7  ldarg.0
0x846f8  ldc.i4.s 0x10
0x846fa  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x846ff  ldloc.0
0x84700  callvirt instance valuetype Microsoft.ReportingServices.OnDemandReportRendering.FontStyles Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_FontStyle()
0x84705  stloc.s  4
0x84707  ldloca.s 4
0x84709  constrained. Microsoft.ReportingServices.OnDemandReportRendering.FontStyles
0x8470f  callvirt instance string [mscorlib]System.Object::ToString()
0x84714  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateConstExpression(string value)
0x84719  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x8471e  br.s     loc_8473D
0x84720  ldarg.0
0x84721  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x84726  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x8472b  ldarg.0
0x8472c  ldc.i4.s 0x10
0x8472e  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x84733  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateEmptyExpression()
0x84738  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x8473d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x84742  ldarg.0
0x84743  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportStringProperty Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_FontFamily()
0x84748  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x8474d  ldc.i4.0
0x8474e  ceq
0x84750  ldstr    aThisFontfamily// "(!this.FontFamily.IsExpression)"
0x84755  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8475a  ldloc.0
0x8475b  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.StyleInstance::get_IsFontFamilyAssigned()
0x84760  brfalse.s loc_84787
0x84762  ldarg.0
0x84763  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x84768  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x8476d  ldarg.0
0x8476e  ldc.i4.s 0x11
0x84770  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x84775  ldloc.0
0x84776  callvirt instance string Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_FontFamily()
0x8477b  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateConstExpression(string value)
0x84780  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x84785  br.s     loc_847A4
0x84787  ldarg.0
0x84788  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x8478d  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x84792  ldarg.0
0x84793  ldc.i4.s 0x11
0x84795  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x8479a  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateEmptyExpression()
0x8479f  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x847a4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x847a9  ldarg.0
0x847aa  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportEnumProperty`1<valuetype Microsoft.ReportingServices.OnDemandReportRendering.FontWeights> Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_FontWeight()
0x847af  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x847b4  ldc.i4.0
0x847b5  ceq
0x847b7  ldstr    aThisFontweight// "(!this.FontWeight.IsExpression)"
0x847bc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x847c1  ldloc.0
0x847c2  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.StyleInstance::get_IsFontWeightAssigned()
0x847c7  brfalse.s loc_847FD
0x847c9  ldarg.0
0x847ca  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x847cf  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x847d4  ldarg.0
0x847d5  ldc.i4.s 0x13
0x847d7  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x847dc  ldloc.0
0x847dd  callvirt instance valuetype Microsoft.ReportingServices.OnDemandReportRendering.FontWeights Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_FontWeight()
0x847e2  stloc.s  5
0x847e4  ldloca.s 5
0x847e6  constrained. Microsoft.ReportingServices.OnDemandReportRendering.FontWeights
0x847ec  callvirt instance string [mscorlib]System.Object::ToString()
0x847f1  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateConstExpression(string value)
0x847f6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x847fb  br.s     loc_8481A
0x847fd  ldarg.0
0x847fe  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x84803  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x84808  ldarg.0
0x84809  ldc.i4.s 0x13
0x8480b  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x84810  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateEmptyExpression()
0x84815  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x8481a  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x8481f  ldarg.0
0x84820  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.ReportStringProperty Microsoft.ReportingServices.OnDemandReportRendering.StyleBase::get_Format()
0x84825  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.ReportProperty::get_IsExpression()
0x8482a  ldc.i4.0
0x8482b  ceq
0x8482d  ldstr    aThisFormatIsex// "(!this.Format.IsExpression)"
0x84832  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x84837  ldloc.0
0x84838  callvirt instance bool Microsoft.ReportingServices.OnDemandReportRendering.StyleInstance::get_IsFormatAssigned()
0x8483d  brfalse.s loc_84864
0x8483f  ldarg.0
0x84840  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
0x84845  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer::get_StyleClass()
0x8484a  ldarg.0
0x8484b  ldc.i4.s 0x14
0x8484d  call     instance string Microsoft.ReportingServices.OnDemandReportRendering.Style::GetStyleStringFromEnum(valuetype Microsoft.ReportingServices.OnDemandReportRendering.StyleAttributeNames style)
0x84852  ldloc.0
0x84853  callvirt instance string Microsoft.ReportingServices.OnDemandReportRendering.StyleBaseInstance::get_Format()
0x84858  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateConstExpression(string value)
0x8485d  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::AddAttribute(string name, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x84862  br.s     loc_84881
0x84864  ldarg.0
0x84865  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.IStyleContainer Microsoft.ReportingServices.OnDemandReportRendering.Style::m_iStyleContainer
  ... truncated ...
```
