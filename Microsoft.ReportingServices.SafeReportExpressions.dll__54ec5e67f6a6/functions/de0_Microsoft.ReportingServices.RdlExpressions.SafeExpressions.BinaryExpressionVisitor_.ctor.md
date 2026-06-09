# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::.ctor

- ea: `0xde0`
- end: `0xdf9`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x310`

## callees

- `0x230`

## pseudocode

```c

```

## disassembly

```asm
0xde0  ldarg.0
0xde1  call     instance void [mscorlib]System.Object::.ctor()
0xde6  ldarg.0
0xde7  ldarg.1
0xde8  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::_host
0xded  ldarg.0
0xdee  call     class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IBinaryExpressionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvaluatorFactory::CreateBinaryExpressionEvaluator()
0xdf3  stfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IBinaryExpressionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::_evaluator
0xdf8  ret
```
