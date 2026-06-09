# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::HasEdge

- ea: `0x11b0`
- end: `0x11c8`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1::HasEdge`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x11b0`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldarg.0
0x11b1  ldarg.1
0x11b2  ldloca.s 0
0x11b4  call     instance bool class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<var<u1>>::TryGetEdgesFromVertex(var<u1>, !!T0)
0x11b9  brfalse.s loc_11C6
0x11bb  ldloc.0
0x11bc  brfalse.s loc_11C6
0x11be  ldloc.0
0x11bf  ldarg.2
0x11c0  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>>::Contains(var<u1>)
0x11c5  ret
0x11c6  ldc.i4.0
0x11c7  ret
```
