# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraphUtils::TraverseGraphVisit

- ea: `0x16e0`
- end: `0x1731`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraphUtils::TraverseGraphVisit`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x16e0`

## pseudocode

```c

```

## disassembly

```asm
0x16e0  ldarg.2
0x16e1  ldarg.1
0x16e2  ldc.i4.2
0x16e3  callvirt instance void class ColoredDFSMarkerRecords`1<mvar<u1>>::SetColor(var<u1>, !!T0)
0x16e8  ldarg.3
0x16e9  ldarg.1
0x16ea  callvirt instance void class [mscorlib]System.Action`1<mvar<u1>>::Invoke(var<u1>)
0x16ef  ldarg.0
0x16f0  ldarg.1
0x16f1  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.IDirectedGraph`1<mvar<u1>>::GetEdgesFromVertex(!!T0)
0x16f6  stloc.0
0x16f7  ldloc.0
0x16f8  brfalse.s loc_1730
0x16fa  ldloc.0
0x16fb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<mvar<u1>>::GetEnumerator()
0x1700  stloc.1
0x1701  br.s     loc_171C
0x1703  ldloc.1
0x1704  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<mvar<u1>>::get_Current()
0x1709  stloc.2
0x170a  ldarg.2
0x170b  ldloc.2
0x170c  callvirt instance valuetype ColoredDFSMarkerType class ColoredDFSMarkerRecords`1<mvar<u1>>::GetColor(var<u1>)
0x1711  brtrue.s loc_171C
0x1713  ldarg.0
0x1714  ldloc.2
0x1715  ldarg.2
0x1716  ldarg.3
0x1717  call     T0x2B000004
0x171c  ldloc.1
0x171d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1722  brtrue.s loc_1703
0x1724  leave.s  loc_1730
0x1726  ldloc.1
0x1727  brfalse.s loc_172F
0x1729  ldloc.1
0x172a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x172f  endfinally
0x1730  ret
```
