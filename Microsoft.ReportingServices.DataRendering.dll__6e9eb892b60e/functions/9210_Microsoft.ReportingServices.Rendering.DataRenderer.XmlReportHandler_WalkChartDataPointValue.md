# Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue

- ea: `0x9210`
- end: `0x9235`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::WalkChartDataPointValue`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x8f00`

## callees

- `0x9210`
- `0xa030`
- `0xa040`

## pseudocode

```c

```

## disassembly

```asm
0x9210  ldarg.3
0x9211  brfalse.s loc_9224
0x9213  ldarg.0
0x9214  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x9219  ldarg.1
0x921a  ldarg.2
0x921b  ldc.i4.1
0x921c  ldarg.s  4
0x921e  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueElement(string name, object val, valuetype [mscorlib]System.TypeCode tc, bool firstInstance)
0x9223  ret
0x9224  ldarg.0
0x9225  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor Microsoft.ReportingServices.Rendering.DataRenderer.XmlReportHandler::m_Visitor
0x922a  ldarg.1
0x922b  ldarg.2
0x922c  ldc.i4.1
0x922d  ldarg.s  4
0x922f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IXmlVisitor::ValueAttribute(string name, object val, valuetype [mscorlib]System.TypeCode tc, bool firstInstance)
0x9234  ret
```
