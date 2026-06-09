# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue_0

- ea: `0x9ad0`
- end: `0x9b61`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue_0`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9840`
- `0x9a80`

## callees

- `0x9ad0`
- `0xa030`
- `0xa040`
- `0xa090`

## pseudocode

```c

```

## disassembly

```asm
0x9ad0  ldarg.2
0x9ad1  brfalse.s loc_9ADC
0x9ad3  ldarg.2
0x9ad4  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_DataElementOutput()
0x9ad9  ldc.i4.1
0x9ada  bne.un.s loc_9ADD
0x9adc  ret
0x9add  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x9ae2  ldarg.2
0x9ae3  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_DataElementOutput()
0x9ae8  ldc.i4.0
0x9ae9  ceq
0x9aeb  ldstr    aGaugeinputvalu_1// "GaugeInputValue.DataElementOutput = "
0x9af0  ldarg.2
0x9af1  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_DataElementOutput()
0x9af6  stloc.1
0x9af7  ldloca.s 1
0x9af9  constrained. [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes
0x9aff  callvirt instance string [mscorlib]System.Object::ToString()
0x9b04  ldstr    aIsNotSupported// " is not supported"
0x9b09  call     string [mscorlib]System.String::Concat(string, string, string)
0x9b0e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x9b13  ldarg.0
0x9b14  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9b19  ldarg.2
0x9b1a  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue::get_DataElementName()
0x9b1f  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x9b24  stloc.0
0x9b25  ldloc.0
0x9b26  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9b2b  brfalse.s loc_9B2F
0x9b2d  ldarg.1
0x9b2e  stloc.0
0x9b2f  ldarg.0
0x9b30  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x9b35  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_DataElementStyle()
0x9b3a  ldc.i4.1
0x9b3b  ceq
0x9b3d  brfalse.s loc_9B50
0x9b3f  ldarg.0
0x9b40  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9b45  ldloc.0
0x9b46  ldarg.s  4
0x9b48  ldc.i4.1
0x9b49  ldarg.3
0x9b4a  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueElement(string name, object val, valuetype [mscorlib]System.TypeCode tc, bool firstInstance)
0x9b4f  ret
0x9b50  ldarg.0
0x9b51  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9b56  ldloc.0
0x9b57  ldarg.s  4
0x9b59  ldc.i4.1
0x9b5a  ldarg.3
0x9b5b  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueAttribute(string name, object val, valuetype [mscorlib]System.TypeCode tc, bool firstInstance)
0x9b60  ret
```
