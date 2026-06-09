# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkStateIndicatorName

- ea: `0x99e0`
- end: `0x9a76`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkStateIndicatorName`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x9540`

## callees

- `0x99e0`
- `0xa030`
- `0xa040`
- `0xa090`

## pseudocode

```c

```

## disassembly

```asm
0x99e0  ldarg.2
0x99e1  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_CompiledStateName()
0x99e6  stloc.0
0x99e7  ldarg.2
0x99e8  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_StateDataElementOutput()
0x99ed  ldc.i4.1
0x99ee  beq.s    loc_99F3
0x99f0  ldloc.0
0x99f1  brtrue.s loc_99F4
0x99f3  ret
0x99f4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x99f9  ldarg.2
0x99fa  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_StateDataElementOutput()
0x99ff  ldc.i4.0
0x9a00  ceq
0x9a02  ldstr    aStateindicator// "stateIndicator.StateDataElementOutput ="...
0x9a07  ldarg.2
0x9a08  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_StateDataElementOutput()
0x9a0d  stloc.2
0x9a0e  ldloca.s 2
0x9a10  constrained. [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes
0x9a16  callvirt instance string [mscorlib]System.Object::ToString()
0x9a1b  ldstr    aIsNotSupported// " is not supported"
0x9a20  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a25  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x9a2a  ldarg.0
0x9a2b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9a30  ldarg.2
0x9a31  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator::get_StateDataElementName()
0x9a36  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x9a3b  stloc.1
0x9a3c  ldloc.1
0x9a3d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9a42  brfalse.s loc_9A46
0x9a44  ldarg.1
0x9a45  stloc.1
0x9a46  ldarg.0
0x9a47  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_CurrentReport
0x9a4c  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report::get_DataElementStyle()
0x9a51  ldc.i4.1
0x9a52  ceq
0x9a54  brfalse.s loc_9A66
0x9a56  ldarg.0
0x9a57  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9a5c  ldloc.1
0x9a5d  ldloc.0
0x9a5e  ldc.i4.1
0x9a5f  ldarg.3
0x9a60  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueElement(string name, object val, valuetype [mscorlib]System.TypeCode tc, bool firstInstance)
0x9a65  ret
0x9a66  ldarg.0
0x9a67  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9a6c  ldloc.1
0x9a6d  ldloc.0
0x9a6e  ldc.i4.1
0x9a6f  ldarg.3
0x9a70  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueAttribute(string name, object val, valuetype [mscorlib]System.TypeCode tc, bool firstInstance)
0x9a75  ret
```
