# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::Evaluate

- ea: `0x40`
- end: `0x52`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::Evaluate`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2c0`
- `0x3b0`

## pseudocode

```c

```

## disassembly

```asm
0x40  ldarg.0
0x41  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::_reportProcessingContext
0x46  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext reportContext)
0x4b  ldarg.1
0x4c  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x51  ret
```
