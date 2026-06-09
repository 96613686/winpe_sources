# Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeDataSets

- ea: `0x910`
- end: `0x94b`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::DecomposeDataSets`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x860`

## callees

- `0x910`
- `0xbe0`

## pseudocode

```c

```

## disassembly

```asm
0x910  ldarg.0
0x911  ldfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report Microsoft.ReportingServices.ComponentLibrary.Engine.ReportDocument::m_report
0x916  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_DataSets()
0x91b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet>::GetEnumerator()
0x920  stloc.0
0x921  br.s     loc_936
0x923  ldloc.0
0x924  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.DataSet>::get_Current()
0x929  stloc.1
0x92a  ldarg.1
0x92b  ldloc.1
0x92c  newobj   instance void Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::.ctor(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject dependency)
0x931  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode>::Add(var<u1>)
0x936  ldloc.0
0x937  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x93c  brtrue.s loc_923
0x93e  leave.s  loc_94A
0x940  ldloc.0
0x941  brfalse.s loc_949
0x943  ldloc.0
0x944  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x949  endfinally
0x94a  ret
```
