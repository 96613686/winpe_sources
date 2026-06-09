# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::CreateInitialEdgesFromVertexOverride

- ea: `0x15e0`
- end: `0x15f0`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::CreateInitialEdgesFromVertexOverride`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1630`

## pseudocode

```c

```

## disassembly

```asm
0x15e0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::.ctor()
0x15e5  stloc.0
0x15e6  ldarg.0
0x15e7  ldarg.1
0x15e8  ldloc.0
0x15e9  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::GetSemanticDependencies(class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode fromVertex, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> dependencies)
0x15ee  ldloc.0
0x15ef  ret
```
