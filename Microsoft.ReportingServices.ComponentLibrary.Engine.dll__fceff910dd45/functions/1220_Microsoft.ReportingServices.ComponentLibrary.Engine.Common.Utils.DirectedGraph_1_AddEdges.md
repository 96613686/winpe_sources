# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddEdges

- ea: `0x1220`
- end: `0x1261`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddEdges`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1220`

## pseudocode

```c

```

## disassembly

```asm
0x1220  ldc.i4.0
0x1221  stloc.0
0x1222  ldarg.0
0x1223  ldarg.1
0x1224  call     instance class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::GetOrCreateEdgesFromVertex(!!T0)
0x1229  stloc.1
0x122a  ldarg.2
0x122b  brfalse.s loc_125F
0x122d  ldarg.2
0x122e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>::GetEnumerator()
0x1233  stloc.2
0x1234  br.s     loc_124B
0x1236  ldloc.2
0x1237  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>>::get_Current()
0x123c  stloc.3
0x123d  ldarg.0
0x123e  ldloc.1
0x123f  ldloc.3
0x1240  call     instance bool class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::AddEdgeWithVertexCheck(class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0)
0x1245  brfalse.s loc_124B
0x1247  ldloc.0
0x1248  ldc.i4.1
0x1249  add
0x124a  stloc.0
0x124b  ldloc.2
0x124c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1251  brtrue.s loc_1236
0x1253  leave.s  loc_125F
0x1255  ldloc.2
0x1256  brfalse.s loc_125E
0x1258  ldloc.2
0x1259  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x125e  endfinally
0x125f  ldloc.0
0x1260  ret
```
