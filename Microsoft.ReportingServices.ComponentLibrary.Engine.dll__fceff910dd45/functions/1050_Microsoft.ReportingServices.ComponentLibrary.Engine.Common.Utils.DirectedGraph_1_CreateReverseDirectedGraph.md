# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::CreateReverseDirectedGraph

- ea: `0x1050`
- end: `0x10c3`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::CreateReverseDirectedGraph`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1050`

## pseudocode

```c

```

## disassembly

```asm
0x1050  ldarg.0
0x1051  brtrue.s loc_1055
0x1053  ldnull
0x1054  ret
0x1055  ldarg.0
0x1056  callvirt instance int32 class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<var<u1>>::get_VertexCount()
0x105b  newobj   instance void class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::.ctor(int32)
0x1060  stloc.0
0x1061  ldc.i4.0
0x1062  stloc.1
0x1063  br.s     loc_10B8
0x1065  ldarg.0
0x1066  ldloc.1
0x1067  callvirt instance var<u1> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<var<u1>>::GetVertex(!!T0)
0x106c  stloc.2
0x106d  ldloc.0
0x106e  ldloc.2
0x106f  callvirt instance bool class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::AddVertex(var<u1>)
0x1074  pop
0x1075  ldarg.0
0x1076  ldloc.2
0x1077  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<var<u1>>::GetEdgesFromVertex(!!T0)
0x107c  stloc.3
0x107d  ldloc.3
0x107e  brfalse.s loc_10B4
0x1080  ldloc.3
0x1081  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>::GetEnumerator()
0x1086  stloc.s  4
0x1088  br.s     loc_109D
0x108a  ldloc.s  4
0x108c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>>::get_Current()
0x1091  stloc.s  5
0x1093  ldloc.0
0x1094  ldloc.s  5
0x1096  ldloc.2
0x1097  callvirt instance bool class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::AddEdge(var<u1>, !!T0)
0x109c  pop
0x109d  ldloc.s  4
0x109f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10a4  brtrue.s loc_108A
0x10a6  leave.s  loc_10B4
0x10a8  ldloc.s  4
0x10aa  brfalse.s loc_10B3
0x10ac  ldloc.s  4
0x10ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10b3  endfinally
0x10b4  ldloc.1
0x10b5  ldc.i4.1
0x10b6  add
0x10b7  stloc.1
0x10b8  ldloc.1
0x10b9  ldarg.0
0x10ba  callvirt instance int32 class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<var<u1>>::get_VertexCount()
0x10bf  blt.s    loc_1065
0x10c1  ldloc.0
0x10c2  ret
```
