# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitInvocationExpression

- ea: `0x360`
- end: `0x376`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitInvocationExpression`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1030`

## pseudocode

```c

```

## disassembly

```asm
0x360  ldarg.0
0x361  ldarg.0
0x362  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::_reportContext
0x367  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost host, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext safeExpressionsReportContext)
0x36c  stloc.0
0x36d  ldarg.0
0x36e  ldloc.0
0x36f  ldarg.1
0x370  call     T0x2B000006
0x375  ret
```
