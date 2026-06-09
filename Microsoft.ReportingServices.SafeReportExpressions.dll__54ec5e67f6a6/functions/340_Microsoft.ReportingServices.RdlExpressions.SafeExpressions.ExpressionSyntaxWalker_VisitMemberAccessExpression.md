# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitMemberAccessExpression

- ea: `0x340`
- end: `0x356`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitMemberAccessExpression`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1340`

## pseudocode

```c

```

## disassembly

```asm
0x340  ldarg.0
0x341  ldarg.0
0x342  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::_reportContext
0x347  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost host, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext safeExpressionsReportContext)
0x34c  stloc.0
0x34d  ldarg.0
0x34e  ldloc.0
0x34f  ldarg.1
0x350  call     T0x2B000005
0x355  ret
```
