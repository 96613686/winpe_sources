# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraphUtils::TraverseGraph

- ea: `0x16a0`
- end: `0x16d8`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraphUtils::TraverseGraph`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x16a0`

## pseudocode

```c

```

## disassembly

```asm
0x16a0  ldarg.0
0x16a1  brtrue.s loc_16AE
0x16a3  ldstr    aGraph// "graph"
0x16a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16ad  throw
0x16ae  ldarg.2
0x16af  brtrue.s loc_16BC
0x16b1  ldstr    aGraphvertexpro// "graphVertexProcessor"
0x16b6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16bb  throw
0x16bc  ldarg.0
0x16bd  callvirt instance int32 class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::get_VertexCount()
0x16c2  ldarg.0
0x16c3  callvirt instance class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::get_Comparer()
0x16c8  newobj   instance void class ColoredDFSMarkerRecords`1<mvar<u1>>::.ctor(int32, class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x16cd  stloc.0
0x16ce  ldarg.0
0x16cf  ldarg.1
0x16d0  ldloc.0
0x16d1  ldarg.2
0x16d2  call     T0x2B000004
0x16d7  ret
```
