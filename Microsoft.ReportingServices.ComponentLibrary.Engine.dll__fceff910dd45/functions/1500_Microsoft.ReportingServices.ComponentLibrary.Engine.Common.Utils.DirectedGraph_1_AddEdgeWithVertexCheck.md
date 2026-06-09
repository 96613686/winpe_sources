# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddEdgeWithVertexCheck

- ea: `0x1500`
- end: `0x1532`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddEdgeWithVertexCheck`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1500`

## pseudocode

```c

```

## disassembly

```asm
0x1500  ldarg.1
0x1501  ldarg.2
0x1502  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<var<u1>>::Contains(var<u1>)
0x1507  brtrue.s loc_1530
0x1509  ldarg.1
0x150a  ldarg.2
0x150b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<var<u1>>::Add(var<u1>)
0x1510  ldarg.0
0x1511  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x1516  ldarg.2
0x1517  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::ContainsKey(var<u1>)
0x151c  brtrue.s loc_152E
0x151e  ldarg.0
0x151f  ldarg.2
0x1520  ldloca.s 0
0x1522  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>
0x1528  ldloc.0
0x1529  call     instance void class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::AddVertexCore(var<u1>, !!T0)
0x152e  ldc.i4.1
0x152f  ret
0x1530  ldc.i4.0
0x1531  ret
```
