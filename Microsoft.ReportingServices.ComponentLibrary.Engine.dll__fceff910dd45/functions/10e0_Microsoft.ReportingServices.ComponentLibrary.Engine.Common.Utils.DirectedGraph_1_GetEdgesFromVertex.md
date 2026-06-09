# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::GetEdgesFromVertex

- ea: `0x10e0`
- end: `0x10f3`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::GetEdgesFromVertex`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10e0`

## pseudocode

```c

```

## disassembly

```asm
0x10e0  ldarg.0
0x10e1  ldarg.1
0x10e2  ldloca.s 0
0x10e4  call     instance bool class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::TryGetEdgesFromVertex(var<u1>, !!T0)
0x10e9  brfalse.s loc_10ED
0x10eb  ldloc.0
0x10ec  ret
0x10ed  newobj   instance void [mscorlib]System.Collections.Generic.KeyNotFoundException::.ctor()
0x10f2  throw
```
