# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::.ctor

- ea: `0x1340`
- end: `0x1365`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::.ctor`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x340`

## callees

- `0x280`
- `0xb70`
- `0x1690`

## pseudocode

```c

```

## disassembly

```asm
0x1340  ldarg.0
0x1341  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::.ctor()
0x1346  ldarg.0
0x1347  ldarg.1
0x1348  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::_host
0x134d  ldarg.0
0x134e  call     class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IObjectAccessEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvaluatorFactory::CreateObjectAccessEvaluator()
0x1353  stfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IObjectAccessEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::_objectAccessEvaluator
0x1358  ldarg.0
0x1359  ldarg.2
0x135a  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext safeExpressionsReportContext)
0x135f  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::_reportCollectionAccessor
0x1364  ret
```
