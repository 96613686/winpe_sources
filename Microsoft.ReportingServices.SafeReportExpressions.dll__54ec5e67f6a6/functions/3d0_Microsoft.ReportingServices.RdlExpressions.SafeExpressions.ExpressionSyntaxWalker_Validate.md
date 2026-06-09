# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::Validate

- ea: `0x3d0`
- end: `0x3df`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::Validate`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x60`

## pseudocode

```c

```

## disassembly

```asm
0x3d0  ldarg.0
0x3d1  ldc.i4.1
0x3d2  stfld    valuetype Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TraversalType Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::_traversalType
0x3d7  ldarg.0
0x3d8  ldarg.1
0x3d9  callvirt instance void [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxVisitor::Visit(class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode)
0x3de  ret
```
