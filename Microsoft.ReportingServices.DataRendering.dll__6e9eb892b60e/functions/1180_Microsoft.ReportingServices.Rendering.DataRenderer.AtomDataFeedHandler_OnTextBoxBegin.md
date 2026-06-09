# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnTextBoxBegin

- ea: `0x1180`
- end: `0x11d3`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnTextBoxBegin`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1180`
- `0x11e0`
- `0x3370`

## pseudocode

```c

```

## disassembly

```asm
0x1180  ldarg.1
0x1181  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x1186  ldc.i4.1
0x1187  bne.un.s loc_118A
0x1189  ret
0x118a  ldarg.3
0x118b  ldc.i4.1
0x118c  stind.i1
0x118d  ldnull
0x118e  stloc.0
0x118f  ldc.i4.0
0x1190  stloc.1
0x1191  ldarg.2
0x1192  brfalse.s loc_11C5
0x1194  ldnull
0x1195  stloc.2
0x1196  ldarg.1
0x1197  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x119c  brfalse.s loc_11AF
0x119e  ldarg.1
0x119f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x11a4  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance
0x11a9  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance::get_OriginalValue()
0x11ae  stloc.2
0x11af  ldloc.2
0x11b0  brfalse.s loc_11C5
0x11b2  ldloc.2
0x11b3  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x11b8  stloc.0
0x11b9  ldloc.2
0x11ba  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11bf  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x11c4  stloc.1
0x11c5  ldarg.0
0x11c6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x11cb  ldloc.0
0x11cc  ldloc.1
0x11cd  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x11d2  ret
```
