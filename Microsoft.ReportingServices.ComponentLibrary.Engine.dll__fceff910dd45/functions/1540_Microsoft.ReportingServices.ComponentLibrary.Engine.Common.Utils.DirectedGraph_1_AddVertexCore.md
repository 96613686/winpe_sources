# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddVertexCore

- ea: `0x1540`
- end: `0x155a`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddVertexCore`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1540  ldarg.0
0x1541  ldfld    class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_vertices
0x1546  ldarg.1
0x1547  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<var<u1>>::Add(var<u1>)
0x154c  ldarg.0
0x154d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x1552  ldarg.1
0x1553  ldarg.2
0x1554  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::Add(var<u1>, !!T0)
0x1559  ret
```
