# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::IsVertexCountConsistent

- ea: `0x1430`
- end: `0x1449`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::IsVertexCountConsistent`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1430  ldarg.0
0x1431  ldfld    class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_vertices
0x1436  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<var<u1>>::get_Count()
0x143b  ldarg.0
0x143c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x1441  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::get_Count()
0x1446  ceq
0x1448  ret
```
