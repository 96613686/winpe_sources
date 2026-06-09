# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraphUtils::ColoredDFSVisit

- ea: `0x17f0`
- end: `0x1913`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraphUtils::ColoredDFSVisit`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x17f0`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldc.i4.0
0x17f1  stloc.0
0x17f2  newobj   instance void class [System]System.Collections.Generic.Stack`1<valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>>::.ctor()
0x17f7  stloc.1
0x17f8  ldarg.2
0x17f9  ldarg.1
0x17fa  ldc.i4.1
0x17fb  callvirt instance void class ColoredDFSMarkerRecords`1<mvar<u1>>::SetColor(var<u1>, !!T0)
0x1800  ldloc.1
0x1801  ldarg.1
0x1802  ldarg.0
0x1803  ldarg.1
0x1804  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::GetEdgesFromVertex(!!T0)
0x1809  ldc.i4.0
0x180a  newobj   instance void valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::.ctor(var<u1>, !!T0, class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>)
0x180f  callvirt instance void class [System]System.Collections.Generic.Stack`1<valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>>::Push(var<u1>)
0x1814  br       loc_1905
0x1819  ldloc.1
0x181a  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>>::Pop()
0x181f  stloc.2
0x1820  ldloc.0
0x1821  brtrue   loc_18D5
0x1826  ldloc.2
0x1827  ldfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::Edges
0x182c  brfalse  loc_18B5
0x1831  ldloc.2
0x1832  ldfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::Edges
0x1837  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<mvar<u1>>::get_Count()
0x183c  ldloc.2
0x183d  ldfld    int32 valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::NextNeighbourToVisit
0x1842  ble.s    loc_18B5
0x1844  ldloc.2
0x1845  ldfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::Edges
0x184a  ldloc.2
0x184b  ldfld    int32 valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::NextNeighbourToVisit
0x1850  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<mvar<u1>>::get_Item(!!T0)
0x1855  stloc.3
0x1856  ldarg.2
0x1857  ldloc.3
0x1858  callvirt instance valuetype ColoredDFSMarkerType class ColoredDFSMarkerRecords`1<mvar<u1>>::GetColor(var<u1>)
0x185d  stloc.s  4
0x185f  ldloc.s  4
0x1861  ldc.i4.1
0x1862  bne.un.s loc_1880
0x1864  ldarg.3
0x1865  ldloc.2
0x1866  ldfld    var<u1> valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::CurrentVertex
0x186b  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::AddFirst(!!T0)
0x1870  pop
0x1871  ldarg.3
0x1872  ldloc.3
0x1873  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::AddLast(!!T0)
0x1878  pop
0x1879  ldc.i4.1
0x187a  stloc.0
0x187b  br       loc_1905
0x1880  ldloca.s 2
0x1882  ldflda   int32 valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::NextNeighbourToVisit
0x1887  dup
0x1888  ldind.i4
0x1889  ldc.i4.1
0x188a  add
0x188b  stind.i4
0x188c  ldloc.1
0x188d  ldloc.2
0x188e  callvirt instance void class [System]System.Collections.Generic.Stack`1<valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>>::Push(var<u1>)
0x1893  ldloc.s  4
0x1895  brtrue.s loc_1905
0x1897  ldarg.2
0x1898  ldloc.3
0x1899  ldc.i4.1
0x189a  callvirt instance void class ColoredDFSMarkerRecords`1<mvar<u1>>::SetColor(var<u1>, !!T0)
0x189f  ldloc.1
0x18a0  ldloc.3
0x18a1  ldarg.0
0x18a2  ldloc.3
0x18a3  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::GetEdgesFromVertex(!!T0)
0x18a8  ldc.i4.0
0x18a9  newobj   instance void valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::.ctor(var<u1>, !!T0, class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>)
0x18ae  callvirt instance void class [System]System.Collections.Generic.Stack`1<valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>>::Push(var<u1>)
0x18b3  br.s     loc_1905
0x18b5  ldarg.2
0x18b6  ldloc.2
0x18b7  ldfld    var<u1> valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::CurrentVertex
0x18bc  ldc.i4.2
0x18bd  callvirt instance void class ColoredDFSMarkerRecords`1<mvar<u1>>::SetColor(var<u1>, !!T0)
0x18c2  ldarg.s  4
0x18c4  brfalse.s loc_1905
0x18c6  ldarg.s  4
0x18c8  ldloc.2
0x18c9  ldfld    var<u1> valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::CurrentVertex
0x18ce  callvirt instance void class [mscorlib]System.Action`1<mvar<u1>>::Invoke(var<u1>)
0x18d3  br.s     loc_1905
0x18d5  ldarg.0
0x18d6  callvirt instance class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::get_Comparer()
0x18db  ldarg.3
0x18dc  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::get_First()
0x18e1  callvirt instance var<u1> class [System]System.Collections.Generic.LinkedListNode`1<mvar<u1>>::get_Value()
0x18e6  ldarg.3
0x18e7  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::get_Last()
0x18ec  callvirt instance var<u1> class [System]System.Collections.Generic.LinkedListNode`1<mvar<u1>>::get_Value()
0x18f1  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<mvar<u1>>::Equals(var<u1>, !!T0)
0x18f6  brtrue.s loc_1905
0x18f8  ldarg.3
0x18f9  ldloc.2
0x18fa  ldfld    var<u1> valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>::CurrentVertex
0x18ff  callvirt instance class [System]System.Collections.Generic.LinkedListNode`1<var<u1>> class [System]System.Collections.Generic.LinkedList`1<mvar<u1>>::AddFirst(!!T0)
0x1904  pop
0x1905  ldloc.1
0x1906  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<valuetype ColoredDFSVisitStackFrame`1<mvar<u1>>>::get_Count()
0x190b  ldc.i4.0
0x190c  bgt      loc_1819
0x1911  ldloc.0
0x1912  ret
```
