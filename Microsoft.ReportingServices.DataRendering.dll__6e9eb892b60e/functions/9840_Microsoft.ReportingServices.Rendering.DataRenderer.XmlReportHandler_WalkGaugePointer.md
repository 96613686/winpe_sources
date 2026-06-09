# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugePointer

- ea: `0x9840`
- end: `0x9923`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugePointer`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x97a0`
- `0x97f0`

## callees

- `0x9840`
- `0x9a80`
- `0x9ad0`
- `0x9fa0`
- `0xa020`
- `0xa240`
- `0xa250`

## pseudocode

```c

```

## disassembly

```asm
0x9840  ldarg.1
0x9841  brtrue.s loc_9844
0x9843  ret
0x9844  ldarg.1
0x9845  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugePointerInstance[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePointer::get_CompiledInstances()
0x984a  brfalse  loc_98E6
0x984f  ldarg.0
0x9850  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9855  ldarg.2
0x9856  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugePointerTag(int32 aGaugePointerIndex)
0x985b  stloc.0
0x985c  ldarg.0
0x985d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9862  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugeInputValueTag()
0x9867  stloc.1
0x9868  ldc.i4.0
0x9869  stloc.2
0x986a  br.s     loc_98DA
0x986c  ldarg.0
0x986d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9872  ldloc.0
0x9873  ldarg.3
0x9874  brfalse.s loc_987C
0x9876  ldloc.2
0x9877  ldc.i4.0
0x9878  ceq
0x987a  br.s     loc_987D
0x987c  ldc.i4.0
0x987d  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartGroup(string name, bool firstInstance)
0x9882  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RenderingTracer()
0x9887  ldarg.1
0x9888  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugePointerInstance[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePointer::get_CompiledInstances()
0x988d  ldloc.2
0x988e  ldelem.ref
0x988f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugePointerInstance::get_GaugeInputValue()
0x9894  ldnull
0x9895  cgt.un
0x9897  ldstr    aGaugeinputvalu// "GaugeInputValue Instance cannot be null"...
0x989c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x98a1  ldarg.0
0x98a2  ldloc.1
0x98a3  ldarg.1
0x98a4  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePointer::get_GaugeInputValue()
0x98a9  ldarg.3
0x98aa  ldarg.1
0x98ab  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugePointerInstance[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePointer::get_CompiledInstances()
0x98b0  ldloc.2
0x98b1  ldelem.ref
0x98b2  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugePointerInstance::get_GaugeInputValue()
0x98b7  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugeInputValueInstance::get_Value()
0x98bc  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance, object value)
0x98c1  ldarg.0
0x98c2  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x98c7  ldarg.3
0x98c8  brfalse.s loc_98D0
0x98ca  ldloc.2
0x98cb  ldc.i4.0
0x98cc  ceq
0x98ce  br.s     loc_98D1
0x98d0  ldc.i4.0
0x98d1  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x98d6  ldloc.2
0x98d7  ldc.i4.1
0x98d8  add
0x98d9  stloc.2
0x98da  ldloc.2
0x98db  ldarg.1
0x98dc  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CompiledGaugePointerInstance[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePointer::get_CompiledInstances()
0x98e1  ldlen
0x98e2  conv.i4
0x98e3  blt.s    loc_986C
0x98e5  ret
0x98e6  ldarg.0
0x98e7  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x98ec  ldarg.0
0x98ed  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x98f2  ldarg.2
0x98f3  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getGaugePointerTag(int32 aGaugePointerIndex)
0x98f8  ldarg.3
0x98f9  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartGroup(string name, bool firstInstance)
0x98fe  ldarg.0
0x98ff  ldarg.0
0x9900  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9905  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugeInputValueTag()
0x990a  ldarg.1
0x990b  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePointer::get_GaugeInputValue()
0x9910  ldarg.3
0x9911  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugeInputValue(string defaultTag, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugeInputValue gaugeInputValue, bool firstInstance)
0x9916  ldarg.0
0x9917  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x991c  ldarg.3
0x991d  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x9922  ret
```
