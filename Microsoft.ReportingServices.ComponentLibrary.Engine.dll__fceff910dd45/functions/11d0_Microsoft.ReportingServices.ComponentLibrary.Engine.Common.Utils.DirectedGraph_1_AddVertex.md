# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddVertex

- ea: `0x11d0`
- end: `0x11f4`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::AddVertex`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x11d0`

## pseudocode

```c

```

## disassembly

```asm
0x11d0  ldc.i4.0
0x11d1  stloc.0
0x11d2  ldarg.0
0x11d3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x11d8  ldarg.1
0x11d9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::ContainsKey(var<u1>)
0x11de  brtrue.s loc_11F2
0x11e0  ldarg.0
0x11e1  ldarg.1
0x11e2  ldloca.s 1
0x11e4  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>
0x11ea  ldloc.1
0x11eb  call     instance void class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::AddVertexCore(var<u1>, !!T0)
0x11f0  ldc.i4.1
0x11f1  stloc.0
0x11f2  ldloc.0
0x11f3  ret
```
