# Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeReportParameters

- ea: `0x950`
- end: `0x98b`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeReportParameters`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x860`

## callees

- `0x950`
- `0xbe0`

## pseudocode

```c

```

## disassembly

```asm
0x950  ldarg.0
0x951  ldfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::m_report
0x956  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_ReportParameters()
0x95b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter>::GetEnumerator()
0x960  stloc.0
0x961  br.s     loc_976
0x963  ldloc.0
0x964  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportParameter>::get_Current()
0x969  stloc.1
0x96a  ldarg.1
0x96b  ldloc.1
0x96c  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::.ctor(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject dependency)
0x971  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::Add(var<u1>)
0x976  ldloc.0
0x977  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x97c  brtrue.s loc_963
0x97e  leave.s  loc_98A
0x980  ldloc.0
0x981  brfalse.s loc_989
0x983  ldloc.0
0x984  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x989  endfinally
0x98a  ret
```
