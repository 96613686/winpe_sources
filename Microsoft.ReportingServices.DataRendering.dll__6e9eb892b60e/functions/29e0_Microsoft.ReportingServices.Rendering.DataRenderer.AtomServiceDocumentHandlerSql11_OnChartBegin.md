# Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::OnChartBegin

- ea: `0x29e0`
- end: `0x2a11`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::OnChartBegin`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x24f0`
- `0x29e0`
- `0x2a20`
- `0xb760`

## pseudocode

```c

```

## disassembly

```asm
0x29e0  ldarg.0
0x29e1  ldarg.1
0x29e2  call     instance bool Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandlerSql11::IsStaticChart(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart)
0x29e7  stloc.0
0x29e8  ldloc.0
0x29e9  brfalse.s loc_2A01
0x29eb  ldarg.0
0x29ec  ldfld    class [System]System.Collections.Generic.Stack`1<class DynamicElement> Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::m_dynamicElementScope
0x29f1  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class DynamicElement>::Peek()
0x29f6  callvirt instance bool DynamicElement::IsRoot()
0x29fb  brtrue.s loc_2A01
0x29fd  ldarg.3
0x29fe  ldc.i4.0
0x29ff  stind.i1
0x2a00  ret
0x2a01  ldarg.0
0x2a02  ldarg.1
0x2a03  ldarg.2
0x2a04  ldarg.3
0x2a05  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomServiceDocumentHandler::OnChartBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Chart chart, bool outputChart, bool& walkChart)
0x2a0a  ldloc.0
0x2a0b  brfalse.s loc_2A10
0x2a0d  ldarg.3
0x2a0e  ldc.i4.0
0x2a0f  stind.i1
0x2a10  ret
```
