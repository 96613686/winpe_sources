# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::.ctor

- ea: `0x15f0`
- end: `0x1609`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x320`

## callees

- `0x240`

## pseudocode

```c

```

## disassembly

```asm
0x15f0  ldarg.0
0x15f1  call     instance void [mscorlib]System.Object::.ctor()
0x15f6  ldarg.0
0x15f7  ldarg.1
0x15f8  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::_host
0x15fd  ldarg.0
0x15fe  call     class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IUnaryExpressionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvaluatorFactory::CreateUnaryExpressionEvaluator()
0x1603  stfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IUnaryExpressionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::_evaluator
0x1608  ret
```
