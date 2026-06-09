# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddEdge

- ea: `0x1210`
- end: `0x121f`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddEdge`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1210  ldarg.0
0x1211  ldarg.0
0x1212  ldarg.1
0x1213  call     instance class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::GetOrCreateEdgesFromVertex(!!T0)
0x1218  ldarg.2
0x1219  call     instance bool class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::AddEdgeWithVertexCheck(class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0)
0x121e  ret
```
