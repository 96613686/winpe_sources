# Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::.ctor

- ea: `0x3d0`
- end: `0x3e2`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::.ctor`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x60`
- `0x80`

## pseudocode

```c

```

## disassembly

```asm
0x3d0  ldarg.0
0x3d1  call     instance void [mscorlib]System.Object::.ctor()
0x3d6  ldarg.0
0x3d7  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::.ctor()
0x3dc  stfld    class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.RdlFragment::m_rdlObject
0x3e1  ret
```
