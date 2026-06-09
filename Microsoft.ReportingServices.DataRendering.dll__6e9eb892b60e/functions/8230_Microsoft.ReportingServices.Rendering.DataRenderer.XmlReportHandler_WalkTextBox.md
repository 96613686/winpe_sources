# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTextBox

- ea: `0x8230`
- end: `0x82c1`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkTextBox`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8130`

## callees

- `0x8230`
- `0xa050`
- `0xa060`
- `0xa090`
- `0xa0e0`

## pseudocode

```c

```

## disassembly

```asm
0x8230  ldarg.0
0x8231  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8236  ldarg.1
0x8237  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x823c  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::EncodeString(string aName)
0x8241  stloc.0
0x8242  ldloc.0
0x8243  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8248  brfalse.s loc_8256
0x824a  ldarg.0
0x824b  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x8250  callvirt instance string Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::getDefaultTextboxTag()
0x8255  stloc.0
0x8256  ldarg.1
0x8257  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Report/DataElementStyles [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox::get_DataElementStyle()
0x825c  ldc.i4.1
0x825d  ceq
0x825f  stloc.1
0x8260  ldloc.1
0x8261  ldarg.2
0x8262  bne.un.s loc_8266
0x8264  ldarg.2
0x8265  ret
0x8266  ldarg.0
0x8267  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_UseFormattedValues
0x826c  brfalse.s loc_8281
0x826e  ldarg.1
0x826f  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x8274  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance
0x8279  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance::get_Value()
0x827e  stloc.2
0x827f  br.s     loc_8292
0x8281  ldarg.1
0x8282  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x8287  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance
0x828c  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance::get_OriginalValue()
0x8291  stloc.2
0x8292  ldloc.1
0x8293  brfalse.s loc_82AB
0x8295  ldarg.0
0x8296  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x829b  ldloc.0
0x829c  ldloc.2
0x829d  ldarg.1
0x829e  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ID()
0x82a3  ldarg.3
0x82a4  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueElement(string name, object val, string ID, bool firstInstance)
0x82a9  br.s     loc_82BF
0x82ab  ldarg.0
0x82ac  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x82b1  ldloc.0
0x82b2  ldloc.2
0x82b3  ldarg.1
0x82b4  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElement::get_ID()
0x82b9  ldarg.3
0x82ba  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueAttribute(string name, object val, string ID, bool firstInstance)
0x82bf  ldc.i4.0
0x82c0  ret
```
