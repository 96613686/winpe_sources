# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkTextBox

- ea: `0x7360`
- end: `0x738d`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkTextBox`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x57c0`
- `0x57d0`
- `0x7360`

## pseudocode

```c

```

## disassembly

```asm
0x7360  ldarg.1
0x7361  brtrue.s loc_7364
0x7363  ret
0x7364  ldc.i4.0
0x7365  stloc.0
0x7366  ldarg.0
0x7367  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_renderOutDataInWalk
0x736c  brfalse.s loc_737D
0x736e  ldarg.0
0x736f  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x7374  ldarg.1
0x7375  ldarg.2
0x7376  ldloca.s 0
0x7378  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::OnTextBoxBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox textBox, bool output, bool& render)
0x737d  ldloc.0
0x737e  brfalse.s loc_738C
0x7380  ldarg.0
0x7381  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x7386  ldarg.1
0x7387  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::OnTextBoxEnd(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBox textBox)
0x738c  ret
```
