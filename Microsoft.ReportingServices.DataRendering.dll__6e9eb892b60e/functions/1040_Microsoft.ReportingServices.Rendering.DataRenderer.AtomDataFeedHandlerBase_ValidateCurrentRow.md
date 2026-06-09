# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::ValidateCurrentRow

- ea: `0x1040`
- end: `0x1054`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::ValidateCurrentRow`
- size: `20`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1060`
- `0x1090`
- `0x10d0`
- `0x1100`
- `0x1130`
- `0x1250`
- `0x15c0`

## callees

- `0x1040`
- `0x3250`

## pseudocode

```c

```

## disassembly

```asm
0x1040  ldarg.1
0x1041  ldc.i4.0
0x1042  ceq
0x1044  ldarg.2
0x1045  and
0x1046  brfalse.s loc_1053
0x1048  ldarg.0
0x1049  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x104e  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::DiscardRow()
0x1053  ret
```
