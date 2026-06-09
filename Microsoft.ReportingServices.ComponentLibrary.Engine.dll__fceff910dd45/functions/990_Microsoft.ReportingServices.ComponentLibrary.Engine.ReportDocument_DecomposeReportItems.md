# Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeReportItems

- ea: `0x990`
- end: `0x9c9`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeReportItems`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x860`

## callees

- `0x990`
- `0xbe0`
- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0x990  ldarg.1
0x991  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem>::GetEnumerator()
0x996  stloc.0
0x997  br.s     loc_9B4
0x999  ldloc.0
0x99a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem>::get_Current()
0x99f  stloc.1
0x9a0  ldloc.1
0x9a1  call     bool Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.ComponentUtils::IsSupportedReportItem(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem item)
0x9a6  brfalse.s loc_9B4
0x9a8  ldarg.2
0x9a9  ldloc.1
0x9aa  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::.ctor(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject dependency)
0x9af  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::Add(var<u1>)
0x9b4  ldloc.0
0x9b5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9ba  brtrue.s loc_999
0x9bc  leave.s  loc_9C8
0x9be  ldloc.0
0x9bf  brfalse.s loc_9C7
0x9c1  ldloc.0
0x9c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c7  endfinally
0x9c8  ret
```
