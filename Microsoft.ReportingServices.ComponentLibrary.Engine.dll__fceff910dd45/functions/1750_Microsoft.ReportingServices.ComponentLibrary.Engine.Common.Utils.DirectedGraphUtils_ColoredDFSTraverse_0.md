# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraphUtils::ColoredDFSTraverse_0

- ea: `0x1750`
- end: `0x17e8`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraphUtils::ColoredDFSTraverse_0`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1750`

## pseudocode

```c

```

## disassembly

```asm
0x1750  ldnull
0x1751  stloc.0
0x1752  ldarg.0
0x1753  callvirt instance int32 class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::get_VertexCount()
0x1758  ldc.i4.0
0x1759  ble.s    loc_17CE
0x175b  newobj   instance void class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::.ctor()
0x1760  stloc.0
0x1761  ldarg.0
0x1762  callvirt instance int32 class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::get_VertexCount()
0x1767  ldarg.0
0x1768  callvirt instance class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::get_Comparer()
0x176d  newobj   instance void class ColoredDFSMarkerRecords`1<mvar<u1>>::.ctor(int32, class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1772  stloc.1
0x1773  ldc.i4.0
0x1774  stloc.2
0x1775  br.s     loc_17C5
0x1777  ldarg.0
0x1778  ldloc.2
0x1779  callvirt instance var<u1> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::GetVertex(!!T0)
0x177e  stloc.3
0x177f  ldloc.1
0x1780  ldloc.3
0x1781  callvirt instance valuetype ColoredDFSMarkerType class ColoredDFSMarkerRecords`1<mvar<u1>>::GetColor(var<u1>)
0x1786  brtrue.s loc_17C1
0x1788  ldarg.0
0x1789  ldloc.3
0x178a  ldloc.1
0x178b  ldloc.0
0x178c  ldarg.1
0x178d  call     T0x2B000006
0x1792  brfalse.s loc_17C1
0x1794  ldarg.0
0x1795  callvirt instance class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::get_Comparer()
0x179a  ldloc.0
0x179b  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::get_First()
0x17a0  callvirt instance var<u1> class [System]System.Collections.Generic.LinkedListNode`1<mvar<u1>>::get_Value()
0x17a5  ldloc.0
0x17a6  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::get_Last()
0x17ab  callvirt instance var<u1> class [System]System.Collections.Generic.LinkedListNode`1<mvar<u1>>::get_Value()
0x17b0  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<mvar<u1>>::Equals(var<u1>, !!T0)
0x17b5  brtrue.s loc_17CE
0x17b7  ldloc.0
0x17b8  ldloc.3
0x17b9  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::AddFirst(!!T0)
0x17be  pop
0x17bf  br.s     loc_17CE
0x17c1  ldloc.2
0x17c2  ldc.i4.1
0x17c3  add
0x17c4  stloc.2
0x17c5  ldloc.2
0x17c6  ldarg.0
0x17c7  callvirt instance int32 class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::get_VertexCount()
0x17cc  blt.s    loc_1777
0x17ce  ldloc.0
0x17cf  brfalse.s loc_17DA
0x17d1  ldloc.0
0x17d2  callvirt instance int32 class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::get_Count()
0x17d7  ldc.i4.0
0x17d8  bgt.s    loc_17DC
0x17da  ldnull
0x17db  ret
0x17dc  ldloc.0
0x17dd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<mvar<u1>>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x17e2  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<mvar<u1>>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x17e7  ret
```
