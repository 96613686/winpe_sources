# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitParenthesizedExpression

- ea: `0x380`
- end: `0x390`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitParenthesizedExpression`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14f0`

## pseudocode

```c

```

## disassembly

```asm
0x380  ldarg.0
0x381  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ParenthesizedExpressionVisitor::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost host)
0x386  stloc.0
0x387  ldarg.0
0x388  ldloc.0
0x389  ldarg.1
0x38a  call     T0x2B000007
0x38f  ret
```
