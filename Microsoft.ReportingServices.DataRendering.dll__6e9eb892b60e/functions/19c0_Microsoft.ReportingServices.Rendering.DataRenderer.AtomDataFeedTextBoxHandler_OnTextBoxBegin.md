# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedTextBoxHandler::OnTextBoxBegin

- ea: `0x19c0`
- end: `0x1a20`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedTextBoxHandler::OnTextBoxBegin`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x11e0`
- `0x19c0`
- `0x33f0`
- `0x35e0`

## pseudocode

```c

```

## disassembly

```asm
0x19c0  ldarg.1
0x19c1  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x19c6  ldc.i4.1
0x19c7  bne.un.s loc_19CA
0x19c9  ret
0x19ca  ldarg.3
0x19cb  ldc.i4.1
0x19cc  stind.i1
0x19cd  ldarg.2
0x19ce  brfalse.s loc_1A1F
0x19d0  ldarg.0
0x19d1  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedTextBoxHandler::m_visitor
0x19d6  ldarg.1
0x19d7  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x19dc  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::AddColumnName(string columnName)
0x19e1  ldnull
0x19e2  stloc.0
0x19e3  ldc.i4.s 0x12
0x19e5  stloc.1
0x19e6  ldarg.1
0x19e7  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x19ec  brfalse.s loc_1A06
0x19ee  ldarg.1
0x19ef  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x19f4  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance
0x19f9  dup
0x19fa  callvirt instance valuetype [mscorlib]System.TypeCode [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance::get_TypeCode()
0x19ff  stloc.1
0x1a00  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance::get_OriginalValue()
0x1a05  stloc.0
0x1a06  ldnull
0x1a07  stloc.2
0x1a08  ldloc.0
0x1a09  brfalse.s loc_1A12
0x1a0b  ldloc.0
0x1a0c  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x1a11  stloc.2
0x1a12  ldarg.0
0x1a13  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedTextBoxHandler::m_visitor
0x1a18  ldloc.2
0x1a19  ldloc.1
0x1a1a  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteFeedLevelValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x1a1f  ret
```
