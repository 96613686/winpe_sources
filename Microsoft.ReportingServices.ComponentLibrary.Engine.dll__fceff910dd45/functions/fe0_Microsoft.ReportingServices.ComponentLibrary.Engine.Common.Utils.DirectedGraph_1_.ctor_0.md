# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::.ctor_0

- ea: `0xfe0`
- end: `0x1004`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::.ctor_0`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xfe0  ldarg.0
0xfe1  call     instance void [mscorlib]System.Object::.ctor()
0xfe6  ldarg.0
0xfe7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<var<u1>>::.ctor()
0xfec  stfld    class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_vertices
0xff1  ldarg.0
0xff2  ldarg.1
0xff3  ldarg.0
0xff4  callvirt instance class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::get_Comparer()
0xff9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::.ctor(int32, class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xffe  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x1003  ret
```
