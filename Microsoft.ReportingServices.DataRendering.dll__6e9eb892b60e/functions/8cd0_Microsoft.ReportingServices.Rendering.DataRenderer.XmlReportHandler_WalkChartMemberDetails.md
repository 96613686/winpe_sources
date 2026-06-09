# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberDetails

- ea: `0x8cd0`
- end: `0x8d22`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartMemberDetails`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8cb0`
- `0x8d30`

## callees

- `0x8cd0`
- `0xa030`
- `0xa040`
- `0xa1a0`

## pseudocode

```c

```

## disassembly

```asm
0x8cd0  ldarg.0
0x8cd1  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x8cd6  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_DataElementStyle()
0x8cdb  ldc.i4.1
0x8cdc  ceq
0x8cde  stloc.0
0x8cdf  ldloc.0
0x8ce0  ldarg.2
0x8ce1  bne.un.s loc_8CE5
0x8ce3  ldarg.2
0x8ce4  ret
0x8ce5  ldarg.1
0x8ce6  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMember::get_Instance()
0x8ceb  ldarg.0
0x8cec  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8cf1  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getChartMemberLabelTag()
0x8cf6  stloc.1
0x8cf7  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartMemberInstance::get_Label()
0x8cfc  stloc.2
0x8cfd  ldloc.0
0x8cfe  brfalse.s loc_8D11
0x8d00  ldarg.0
0x8d01  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8d06  ldloc.1
0x8d07  ldloc.2
0x8d08  ldc.i4.1
0x8d09  ldarg.3
0x8d0a  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueElement(string name, object val, valuetype [mscorlib]System.TypeCode tc, bool firstInstance)
0x8d0f  br.s     loc_8D20
0x8d11  ldarg.0
0x8d12  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8d17  ldloc.1
0x8d18  ldloc.2
0x8d19  ldc.i4.1
0x8d1a  ldarg.3
0x8d1b  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueAttribute(string name, object val, valuetype [mscorlib]System.TypeCode tc, bool firstInstance)
0x8d20  ldc.i4.0
0x8d21  ret
```
