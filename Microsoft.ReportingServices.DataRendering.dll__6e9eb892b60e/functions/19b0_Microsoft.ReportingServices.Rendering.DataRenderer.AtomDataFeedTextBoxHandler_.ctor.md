# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedTextBoxHandler::.ctor

- ea: `0x19b0`
- end: `0x19be`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedTextBoxHandler::.ctor`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1d70`
- `0x1e90`

## callees

- `0x5720`

## pseudocode

```c

```

## disassembly

```asm
0x19b0  ldarg.0
0x19b1  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::.ctor()
0x19b6  ldarg.0
0x19b7  ldarg.1
0x19b8  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedTextBoxHandler::m_visitor
0x19bd  ret
```
