# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapDockableSubItemElement

- ea: `0x98570`
- end: `0x98687`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapDockableSubItemElement`
- size: `279`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x98e20`
- `0x99240`
- `0x99350`
- `0x99530`

## callees

- `0x983e0`
- `0x98570`
- `0x9f8c0`
- `0xac750`
- `0xb7340`
- `0xdee60`
- `0xdeeb0`
- `0xdeec0`
- `0xdeee0`
- `0xdef00`
- `0xdef20`
- `0x1177f0`
- `0x117880`

## string_xrefs

- `0x98597`: `DockOutsideViewport`

## pseudocode

```c

```

## disassembly

```asm
0x98570  ldarg.0
0x98571  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x98576  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9857b  stloc.1
0x9857c  ldloc.1
0x9857d  ldstr    aActioninfo// "ActionInfo"
0x98582  call     bool [mscorlib]System.String::op_Equality(string, string)
0x98587  brtrue.s loc_985CB
0x98589  ldloc.1
0x9858a  ldstr    aPosition// "Position"
0x9858f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x98594  brtrue.s loc_985DF
0x98596  ldloc.1
0x98597  ldstr    aDockoutsidevie// "DockOutsideViewport"
0x9859c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x985a1  brtrue   loc_9862B
0x985a6  ldloc.1
0x985a7  ldstr    aHidden// "Hidden"
0x985ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x985b1  brtrue   loc_98646
0x985b6  ldloc.1
0x985b7  ldstr    aTooltip// "ToolTip"
0x985bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x985c1  brtrue   loc_98661
0x985c6  br       loc_9867D
0x985cb  ldc.i4.0
0x985cc  stloc.0
0x985cd  ldarg.2
0x985ce  ldarg.0
0x985cf  ldarg.3
0x985d0  ldc.i4.s 0x11
0x985d2  ldloca.s 0
0x985d4  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Action Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadActionInfo(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType styleOwnerType, [out] bool& computed)
0x985d9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::set_Action(class Microsoft.ReportingServices.ReportIntermediateFormat.Action value)
0x985de  ret
0x985df  ldarg.2
0x985e0  ldarg.0
0x985e1  ldarg.0
0x985e2  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x985e7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x985ec  ldc.i4.0
0x985ed  ldc.i4.s 0x12
0x985ef  ldarg.3
0x985f0  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x985f5  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::set_Position(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x985fa  ldarg.2
0x985fb  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::get_Position()
0x98600  callvirt instance bool Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_IsExpression()
0x98605  brtrue.s loc_98686
0x98607  ldarg.2
0x98608  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::get_Position()
0x9860d  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0x98612  ldarg.0
0x98613  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_errorContext
0x98618  ldarg.3
0x98619  ldarg.0
0x9861a  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9861f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x98624  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::ValidateMapPosition(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0x98629  pop
0x9862a  ret
0x9862b  ldarg.2
0x9862c  ldarg.0
0x9862d  ldarg.0
0x9862e  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x98633  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x98638  ldc.i4.0
0x98639  ldc.i4.3
0x9863a  ldarg.3
0x9863b  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x98640  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::set_DockOutsideViewport(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x98645  ret
0x98646  ldarg.2
0x98647  ldarg.0
0x98648  ldarg.0
0x98649  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9864e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x98653  ldc.i4.0
0x98654  ldc.i4.3
0x98655  ldarg.3
0x98656  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x9865b  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::set_Hidden(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x98660  ret
0x98661  ldarg.2
0x98662  ldarg.0
0x98663  ldarg.0
0x98664  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x98669  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9866e  ldc.i4.0
0x9866f  ldc.i4.s 0x12
0x98671  ldarg.3
0x98672  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x98677  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::set_ToolTip(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9867c  ret
0x9867d  ldarg.0
0x9867e  ldarg.1
0x9867f  ldarg.2
0x98680  ldarg.3
0x98681  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadMapSubItemElement(class Microsoft.ReportingServices.ReportIntermediateFormat.Map map, class Microsoft.ReportingServices.ReportIntermediateFormat.MapSubItem mapSubItem, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context)
0x98686  ret
```
