# Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Hyperlink

- ea: `0x56580`
- end: `0x56695`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.Action::get_Hyperlink`
- size: `277`
- prototype: ``
- caller_count: `7`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x3c820`
- `0x3ca30`
- `0x56820`
- `0x57050`
- `0x57160`
- `0x57290`
- `0x57460`

## callees

- `0x61a0`
- `0x6840`
- `0x55aa0`
- `0x55ad0`
- `0x55ae0`
- `0x56580`
- `0x56710`
- `0x72540`
- `0x72580`
- `0x726a0`
- `0x75120`
- `0xeeda0`
- `0x1177f0`
- `0x117880`
- `0x1179c0`
- `0x19a5c0`
- `0x1a7490`
- `0x1a7500`
- `0x1fb4c0`

## string_xrefs

- `0x56650`: `Hyperlink`

## pseudocode

```c

```

## disassembly

```asm
0x56580  ldarg.0
0x56581  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportUrlProperty Microsoft.ReportingServices.OnDemandReportRendering.Action::m_hyperlink
0x56586  brtrue   loc_5668E
0x5658b  ldarg.0
0x5658c  call     instance bool Microsoft.ReportingServices.OnDemandReportRendering.Action::get_IsOldSnapshot()
0x56591  brfalse.s loc_5660C
0x56593  ldarg.0
0x56594  ldfld    class Microsoft.ReportingServices.ReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.Action::m_renderAction
0x56599  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ActionItem Microsoft.ReportingServices.ReportRendering.Action::get_ActionDefinition()
0x5659e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::get_HyperLinkURL()
0x565a3  brfalse  loc_5668E
0x565a8  ldarg.0
0x565a9  ldarg.0
0x565aa  ldfld    class Microsoft.ReportingServices.ReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.Action::m_renderAction
0x565af  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ActionItem Microsoft.ReportingServices.ReportRendering.Action::get_ActionDefinition()
0x565b4  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::get_HyperLinkURL()
0x565b9  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::get_IsExpression()
0x565be  ldarg.0
0x565bf  ldfld    class Microsoft.ReportingServices.ReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.Action::m_renderAction
0x565c4  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ActionItem Microsoft.ReportingServices.ReportRendering.Action::get_ActionDefinition()
0x565c9  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::get_HyperLinkURL()
0x565ce  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::get_OriginalText()
0x565d3  ldarg.0
0x565d4  ldfld    class Microsoft.ReportingServices.ReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.Action::m_renderAction
0x565d9  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ActionItem Microsoft.ReportingServices.ReportRendering.Action::get_ActionDefinition()
0x565de  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ActionItem::get_HyperLinkURL()
0x565e3  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::get_IsExpression()
0x565e8  brtrue.s loc_565FC
0x565ea  ldarg.0
0x565eb  ldfld    class Microsoft.ReportingServices.ReportRendering.Action Microsoft.ReportingServices.OnDemandReportRendering.Action::m_renderAction
0x565f0  callvirt instance class Microsoft.ReportingServices.ReportRendering.ReportUrl Microsoft.ReportingServices.ReportRendering.Action::get_HyperLinkURL()
0x565f5  newobj   instance void Microsoft.ReportingServices.OnDemandReportRendering.ReportUrl::.ctor(class Microsoft.ReportingServices.ReportRendering.ReportUrl renderUrl)
0x565fa  br.s     loc_565FD
0x565fc  ldnull
0x565fd  newobj   instance void Microsoft.ReportingServices.OnDemandReportRendering.ReportUrlProperty::.ctor(bool isExpression, string expressionString, class Microsoft.ReportingServices.OnDemandReportRendering.ReportUrl reportUrl)
0x56602  stfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportUrlProperty Microsoft.ReportingServices.OnDemandReportRendering.Action::m_hyperlink
0x56607  br       loc_5668E
0x5660c  ldarg.0
0x5660d  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem Microsoft.ReportingServices.OnDemandReportRendering.Action::m_actionItemDef
0x56612  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::get_HyperLinkURL()
0x56617  brfalse.s loc_5668E
0x56619  ldnull
0x5661a  stloc.0
0x5661b  ldarg.0
0x5661c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem Microsoft.ReportingServices.OnDemandReportRendering.Action::m_actionItemDef
0x56621  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::get_HyperLinkURL()
0x56626  stloc.1
0x56627  ldloc.1
0x56628  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0x5662d  brtrue.s loc_56676
0x5662f  ldarg.0
0x56630  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ActionInfo Microsoft.ReportingServices.OnDemandReportRendering.Action::m_owner
0x56635  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext Microsoft.ReportingServices.OnDemandReportRendering.ActionInfo::get_RenderingContext()
0x5663a  ldarg.0
0x5663b  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ActionInfo Microsoft.ReportingServices.OnDemandReportRendering.Action::m_owner
0x56640  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.OnDemandReportRendering.ActionInfo::get_ObjectType()
0x56645  ldarg.0
0x56646  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ActionInfo Microsoft.ReportingServices.OnDemandReportRendering.Action::m_owner
0x5664b  callvirt instance string Microsoft.ReportingServices.OnDemandReportRendering.ActionInfo::get_ObjectName()
0x56650  ldstr    aHyperlink// "Hyperlink"
0x56655  ldarg.0
0x56656  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ActionInfo Microsoft.ReportingServices.OnDemandReportRendering.Action::m_owner
0x5665b  callvirt instance class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext Microsoft.ReportingServices.OnDemandReportRendering.ActionInfo::get_RenderingContext()
0x56660  callvirt instance class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext::get_OdpContext()
0x56665  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ReportContext()
0x5666a  ldloc.1
0x5666b  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0x56670  call     class Microsoft.ReportingServices.OnDemandReportRendering.ReportUrl Microsoft.ReportingServices.OnDemandReportRendering.ReportUrl::BuildHyperlinkUrl(class Microsoft.ReportingServices.OnDemandReportRendering.RenderingContext renderingContext, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ICatalogItemContext itemContext, string initialUrl)
0x56675  stloc.0
0x56676  ldarg.0
0x56677  ldloc.1
0x56678  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0x5667d  ldloc.1
0x5667e  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_OriginalText()
0x56683  ldloc.0
0x56684  newobj   instance void Microsoft.ReportingServices.OnDemandReportRendering.ReportUrlProperty::.ctor(bool isExpression, string expressionString, class Microsoft.ReportingServices.OnDemandReportRendering.ReportUrl reportUrl)
0x56689  stfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportUrlProperty Microsoft.ReportingServices.OnDemandReportRendering.Action::m_hyperlink
0x5668e  ldarg.0
0x5668f  ldfld    class Microsoft.ReportingServices.OnDemandReportRendering.ReportUrlProperty Microsoft.ReportingServices.OnDemandReportRendering.Action::m_hyperlink
0x56694  ret
```
