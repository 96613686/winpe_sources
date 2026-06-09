# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::Traverse

- ea: `0x3e0`
- end: `0x3fe`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::Traverse`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3e0`

## pseudocode

```c

```

## disassembly

```asm
0x3e0  ldarg.0
0x3e1  ldfld    valuetype Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TraversalType Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::_traversalType
0x3e6  brtrue.s loc_3F6
0x3e8  ldarg.0
0x3e9  ldarg.1
0x3ea  ldarg.2
0x3eb  callvirt instance object class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionSyntaxVisitor`1<mvar<u1>>::Evaluate(var<u1>)
0x3f0  stfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::_result
0x3f5  ret
0x3f6  ldarg.1
0x3f7  ldarg.2
0x3f8  callvirt instance void class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionSyntaxVisitor`1<mvar<u1>>::Validate(var<u1>)
0x3fd  ret
```
