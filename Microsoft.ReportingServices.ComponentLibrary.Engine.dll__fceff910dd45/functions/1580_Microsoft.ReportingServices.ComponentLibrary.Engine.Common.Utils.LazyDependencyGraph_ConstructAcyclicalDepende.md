# Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::ConstructAcyclicalDependencyGraph

- ea: `0x1580`
- end: `0x15c8`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::ConstructAcyclicalDependencyGraph`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x5e0`
- `0x860`

## callees

- `0x1570`
- `0x1580`
- `0x1a20`

## pseudocode

```c

```

## disassembly

```asm
0x1580  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.LazyDependencyGraph::.ctor()
0x1585  stloc.0
0x1586  ldarg.0
0x1587  brfalse.s loc_15B5
0x1589  ldarg.0
0x158a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::GetEnumerator()
0x158f  stloc.2
0x1590  br.s     loc_15A1
0x1592  ldloc.2
0x1593  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::get_Current()
0x1598  stloc.3
0x1599  ldloc.0
0x159a  ldloc.3
0x159b  callvirt instance bool class Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.DirectedGraph`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::AddVertex(var<u1>)
0x15a0  pop
0x15a1  ldloc.2
0x15a2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15a7  brtrue.s loc_1592
0x15a9  leave.s  loc_15B5
0x15ab  ldloc.2
0x15ac  brfalse.s loc_15B4
0x15ae  ldloc.2
0x15af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15b4  endfinally
0x15b5  ldloc.0
0x15b6  call     T0x2B000003
0x15bb  stloc.1
0x15bc  ldloc.1
0x15bd  brfalse.s loc_15C6
0x15bf  ldloc.1
0x15c0  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Exceptions.CircularDependencyException::.ctor(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode> circularPath)
0x15c5  throw
0x15c6  ldloc.0
0x15c7  ret
```
