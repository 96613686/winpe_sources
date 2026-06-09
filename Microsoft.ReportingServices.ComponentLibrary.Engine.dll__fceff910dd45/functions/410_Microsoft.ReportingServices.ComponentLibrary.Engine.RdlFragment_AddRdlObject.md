# Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::AddRdlObject

- ea: `0x410`
- end: `0x437`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::AddRdlObject`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x80`
- `0x380`

## callees

- `0x410`
- `0xda0`

## pseudocode

```c

```

## disassembly

```asm
0x410  ldarg.1
0x411  brtrue.s loc_41E
0x413  ldstr    aRdlobject// "rdlObject"
0x418  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x41d  throw
0x41e  ldarg.0
0x41f  ldfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::m_rdlObject
0x424  isinst   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report
0x429  stloc.0
0x42a  ldloc.0
0x42b  brfalse.s loc_435
0x42d  ldloc.0
0x42e  ldarg.1
0x42f  call     bool Microsoft.ReportingServices.ComponentLibrary.Engine.Common.Utils.ComponentUtils::AddRdlObjectToReport(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report report, class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject rdlObject)
0x434  ret
0x435  ldc.i4.0
0x436  ret
```
