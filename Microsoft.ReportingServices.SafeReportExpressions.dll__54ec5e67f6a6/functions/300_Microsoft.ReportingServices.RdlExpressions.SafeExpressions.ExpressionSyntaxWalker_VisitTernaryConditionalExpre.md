# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitTernaryConditionalExpression

- ea: `0x300`
- end: `0x310`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitTernaryConditionalExpression`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1550`

## pseudocode

```c

```

## disassembly

```asm
0x300  ldarg.0
0x301  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost host)
0x306  stloc.0
0x307  ldarg.0
0x308  ldloc.0
0x309  ldarg.1
0x30a  call     T0x2B000001
0x30f  ret
```
