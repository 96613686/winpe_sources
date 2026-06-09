# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::.ctor

- ea: `0xfe0`
- end: `0xff5`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::.ctor`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1170`
- `0x16c0`

## callees

- `0x5720`

## pseudocode

```c

```

## disassembly

```asm
0xfe0  ldarg.0
0xfe1  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.HandlerBase::.ctor()
0xfe6  ldarg.0
0xfe7  ldarg.1
0xfe8  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0xfed  ldarg.0
0xfee  ldarg.2
0xfef  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_definitionPathSteps
0xff4  ret
```
