# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::Evaluate

- ea: `0x3b0`
- end: `0x3c5`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::Evaluate`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x40`

## pseudocode

```c

```

## disassembly

```asm
0x3b0  ldarg.0
0x3b1  ldc.i4.0
0x3b2  stfld    valuetype Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TraversalType Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::_traversalType
0x3b7  ldarg.0
0x3b8  ldarg.1
0x3b9  callvirt instance void [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxVisitor::Visit(class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode)
0x3be  ldarg.0
0x3bf  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::_result
0x3c4  ret
```
