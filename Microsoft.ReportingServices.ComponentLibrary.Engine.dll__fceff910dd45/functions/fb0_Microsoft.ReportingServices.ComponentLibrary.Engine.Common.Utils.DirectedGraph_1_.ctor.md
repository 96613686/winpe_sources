# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::.ctor

- ea: `0xfb0`
- end: `0xfd3`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::.ctor`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  ldarg.0
0xfb1  call     instance void [mscorlib]System.Object::.ctor()
0xfb6  ldarg.0
0xfb7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<var<u1>>::.ctor()
0xfbc  stfld    class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_vertices
0xfc1  ldarg.0
0xfc2  ldarg.0
0xfc3  callvirt instance class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::get_Comparer()
0xfc8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xfcd  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0xfd2  ret
```
