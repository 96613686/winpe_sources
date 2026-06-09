# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkRectangle

- ea: `0x7320`
- end: `0x7352`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkRectangle`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x57a0`
- `0x57b0`
- `0x7320`
- `0x7550`

## pseudocode

```c

```

## disassembly

```asm
0x7320  ldarg.1
0x7321  brtrue.s loc_7324
0x7323  ret
0x7324  ldc.i4.0
0x7325  stloc.0
0x7326  ldarg.0
0x7327  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x732c  ldarg.1
0x732d  ldloca.s 0
0x732f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::OnRectangleBegin(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle rectangle, bool& walkChildren)
0x7334  ldloc.0
0x7335  brfalse.s loc_7351
0x7337  ldarg.0
0x7338  ldarg.1
0x7339  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle::get_ReportItemCollection()
0x733e  ldarg.2
0x733f  ldarg.3
0x7340  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::WalkReportItemCollection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemCollection reportItemCollection, class Microsoft.ReportingServices.Rendering.DataRenderer.MemberState parentMemberState, bool outputMembers)
0x7345  ldarg.0
0x7346  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_reportHandler
0x734b  ldarg.1
0x734c  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.IReportHandler::OnRectangleEnd(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.Rectangle rectangle)
0x7351  ret
```
