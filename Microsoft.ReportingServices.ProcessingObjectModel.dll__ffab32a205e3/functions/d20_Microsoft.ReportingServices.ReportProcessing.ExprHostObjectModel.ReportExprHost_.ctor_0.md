# Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportExprHost::.ctor_0

- ea: `0xd20`
- end: `0xd33`
- name: `Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportExprHost::.ctor_0`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xa60`
- `0x1690`

## pseudocode

```c

```

## disassembly

```asm
0xd20  ldarg.0
0xd21  call     instance void Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportItemExprHost::.ctor()
0xd26  ldarg.0
0xd27  ldarg.1
0xd28  castclass Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel
0xd2d  call     instance void Microsoft.ReportingServices.ReportProcessing.ExprHostObjectModel.ReportObjectModelProxy::SetReportObjectModel(class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModel reportObjectModel)
0xd32  ret
```
