# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::GetOrCreateEdgesFromVertex

- ea: `0x1490`
- end: `0x14f4`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::GetOrCreateEdgesFromVertex`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1490`

## pseudocode

```c

```

## disassembly

```asm
0x1490  ldloca.s 0
0x1492  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>
0x1498  ldarg.0
0x1499  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x149e  ldarg.1
0x149f  ldloca.s 0
0x14a1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::TryGetValue(var<u1>, !!T0)
0x14a6  brtrue.s loc_14C0
0x14a8  ldloca.s 0
0x14aa  ldarg.0
0x14ab  ldarg.1
0x14ac  call     instance valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::CreateInitialEdgesFromVertex(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>)
0x14b1  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::.ctor(var<u1>)
0x14b6  ldarg.0
0x14b7  ldarg.1
0x14b8  ldloc.0
0x14b9  call     instance void class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::AddVertexCore(var<u1>, !!T0)
0x14be  br.s     loc_14E4
0x14c0  ldloca.s 0
0x14c2  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_HasValue()
0x14c7  brtrue.s loc_14E4
0x14c9  ldloca.s 0
0x14cb  ldarg.0
0x14cc  ldarg.1
0x14cd  call     instance valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::CreateInitialEdgesFromVertex(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>)
0x14d2  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::.ctor(var<u1>)
0x14d7  ldarg.0
0x14d8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::m_edges
0x14dd  ldarg.1
0x14de  ldloc.0
0x14df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<var<u1>, !!T0>::set_Item(var<u1>, !!T0)
0x14e4  ldloca.s 0
0x14e6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>>::get_Value()
0x14eb  stloc.1
0x14ec  ldloca.s 1
0x14ee  call     instance var<u1> valuetype Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.MutableReadonlyPair`2<class [mscorlib]System.Collections.Generic.List`1<var<u1>>, !!T0>::get_MutableObj()
0x14f3  ret
```
