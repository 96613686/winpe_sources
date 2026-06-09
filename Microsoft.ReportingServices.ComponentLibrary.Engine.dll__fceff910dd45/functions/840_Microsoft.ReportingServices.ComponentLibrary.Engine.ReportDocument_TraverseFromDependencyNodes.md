# Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::TraverseFromDependencyNodes

- ea: `0x840`
- end: `0x85c`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::TraverseFromDependencyNodes`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e0`

## callees

- `0x840`

## pseudocode

```c

```

## disassembly

```asm
0x840  ldarg.1
0x841  brtrue.s loc_84E
0x843  ldstr    aHandler// "handler"
0x848  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x84d  throw
0x84e  ldarg.0
0x84f  ldfld    class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::m_graph
0x854  ldarg.1
0x855  call     T0x2B000002
0x85a  pop
0x85b  ret
```
