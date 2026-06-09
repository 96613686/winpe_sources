# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitBinaryExpression

- ea: `0x310`
- end: `0x320`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitBinaryExpression`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xde0`

## pseudocode

```c

```

## disassembly

```asm
0x310  ldarg.0
0x311  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost host)
0x316  stloc.0
0x317  ldarg.0
0x318  ldloc.0
0x319  ldarg.1
0x31a  call     T0x2B000002
0x31f  ret
```
