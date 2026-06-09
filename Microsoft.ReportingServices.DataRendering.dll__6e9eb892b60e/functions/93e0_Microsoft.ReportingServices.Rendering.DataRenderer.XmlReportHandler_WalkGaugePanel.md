# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugePanel

- ea: `0x93e0`
- end: `0x94db`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGaugePanel`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8130`

## callees

- `0x93e0`
- `0x94e0`
- `0x9540`
- `0x9f90`
- `0xa020`
- `0xa090`
- `0xa1b0`

## pseudocode

```c

```

## disassembly

```asm
0x93e0  ldarg.1
0x93e1  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.DataElementOutputTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementOutput()
0x93e6  ldc.i4.1
0x93e7  bne.un.s loc_93EA
0x93e9  ret
0x93ea  ldarg.0
0x93eb  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x93f0  ldarg.1
0x93f1  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x93f6  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x93fb  stloc.0
0x93fc  ldloc.0
0x93fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9402  brfalse.s loc_9410
0x9404  ldarg.0
0x9405  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x940a  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultGaugePanelTag()
0x940f  stloc.0
0x9410  ldarg.0
0x9411  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9416  ldloc.0
0x9417  ldarg.2
0x9418  ldarg.2
0x9419  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::StartDataRegion(string name, bool firstInstance, bool optional)
0x941e  ldc.i4.0
0x941f  stloc.1
0x9420  ldarg.1
0x9421  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearGaugeCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel::get_LinearGauges()
0x9426  brfalse.s loc_9456
0x9428  ldc.i4.0
0x9429  stloc.3
0x942a  br.s     loc_9448
0x942c  ldarg.0
0x942d  ldarg.1
0x942e  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearGaugeCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel::get_LinearGauges()
0x9433  ldloc.3
0x9434  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearGauge>::get_Item(!!T0)
0x9439  ldloc.1
0x943a  dup
0x943b  ldc.i4.1
0x943c  add
0x943d  stloc.1
0x943e  ldarg.2
0x943f  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGauge(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Gauge gauge, int32 gaugeIndex, bool firstInstance)
0x9444  ldloc.3
0x9445  ldc.i4.1
0x9446  add
0x9447  stloc.3
0x9448  ldloc.3
0x9449  ldarg.1
0x944a  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearGaugeCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel::get_LinearGauges()
0x944f  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.LinearGauge>::get_Count()
0x9454  blt.s    loc_942C
0x9456  ldarg.1
0x9457  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialGaugeCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel::get_RadialGauges()
0x945c  brfalse.s loc_9491
0x945e  ldc.i4.0
0x945f  stloc.s  4
0x9461  br.s     loc_9482
0x9463  ldarg.0
0x9464  ldarg.1
0x9465  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialGaugeCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel::get_RadialGauges()
0x946a  ldloc.s  4
0x946c  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialGauge>::get_Item(!!T0)
0x9471  ldloc.1
0x9472  dup
0x9473  ldc.i4.1
0x9474  add
0x9475  stloc.1
0x9476  ldarg.2
0x9477  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkGauge(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Gauge gauge, int32 gaugeIndex, bool firstInstance)
0x947c  ldloc.s  4
0x947e  ldc.i4.1
0x947f  add
0x9480  stloc.s  4
0x9482  ldloc.s  4
0x9484  ldarg.1
0x9485  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialGaugeCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel::get_RadialGauges()
0x948a  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.RadialGauge>::get_Count()
0x948f  blt.s    loc_9463
0x9491  ldc.i4.0
0x9492  stloc.2
0x9493  ldarg.1
0x9494  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicatorCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel::get_StateIndicators()
0x9499  brfalse.s loc_94CE
0x949b  ldc.i4.0
0x949c  stloc.s  5
0x949e  br.s     loc_94BF
0x94a0  ldarg.0
0x94a1  ldarg.1
0x94a2  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicatorCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel::get_StateIndicators()
0x94a7  ldloc.s  5
0x94a9  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator>::get_Item(!!T0)
0x94ae  ldloc.2
0x94af  dup
0x94b0  ldc.i4.1
0x94b1  add
0x94b2  stloc.2
0x94b3  ldarg.2
0x94b4  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkStateIndicator(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator stateIndicator, int32 stateIndicatorIndex, bool firstInstance)
0x94b9  ldloc.s  5
0x94bb  ldc.i4.1
0x94bc  add
0x94bd  stloc.s  5
0x94bf  ldloc.s  5
0x94c1  ldarg.1
0x94c2  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicatorCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanel::get_StateIndicators()
0x94c7  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.GaugePanelObjectCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.StateIndicator>::get_Count()
0x94cc  blt.s    loc_94A0
0x94ce  ldarg.0
0x94cf  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x94d4  ldarg.2
0x94d5  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EndElement(bool firstInstance)
0x94da  ret
```
