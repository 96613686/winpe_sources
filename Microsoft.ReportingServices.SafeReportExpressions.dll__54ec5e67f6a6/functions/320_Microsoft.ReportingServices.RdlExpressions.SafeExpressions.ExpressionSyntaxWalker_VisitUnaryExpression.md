# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitUnaryExpression

- ea: `0x320`
- end: `0x330`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitUnaryExpression`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x15f0`

## pseudocode

```c

```

## disassembly

```asm
0x320  ldarg.0
0x321  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost host)
0x326  stloc.0
0x327  ldarg.0
0x328  ldloc.0
0x329  ldarg.1
0x32a  call     T0x2B000003
0x32f  ret
```
