# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitCollectionInitializer

- ea: `0x3a0`
- end: `0x3b0`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::VisitCollectionInitializer`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xf00`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  ldarg.0
0x3a1  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.CollectionInitializerVisitor::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost host)
0x3a6  stloc.0
0x3a7  ldarg.0
0x3a8  ldloc.0
0x3a9  ldarg.1
0x3aa  call     T0x2B000009
0x3af  ret
```
