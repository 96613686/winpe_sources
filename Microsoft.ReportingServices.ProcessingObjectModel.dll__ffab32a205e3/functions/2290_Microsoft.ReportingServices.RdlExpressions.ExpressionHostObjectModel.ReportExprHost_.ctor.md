# Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost::.ctor

- ea: `0x2290`
- end: `0x22a3`
- name: `Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportExprHost::.ctor`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1e10`
- `0x2ac0`

## pseudocode

```c

```

## disassembly

```asm
0x2290  ldarg.0
0x2291  call     instance void Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportItemExprHost::.ctor()
0x2296  ldarg.0
0x2297  ldarg.1
0x2298  castclass Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel
0x229d  call     instance void Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy::SetReportObjectModel(class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.OnDemandObjectModel reportObjectModel)
0x22a2  ret
```
