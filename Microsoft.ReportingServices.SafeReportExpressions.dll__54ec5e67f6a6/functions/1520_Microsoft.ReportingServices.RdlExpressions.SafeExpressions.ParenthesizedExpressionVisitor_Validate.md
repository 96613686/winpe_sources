# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ParenthesizedExpressionVisitor::Validate

- ea: `0x1520`
- end: `0x1532`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ParenthesizedExpressionVisitor::Validate`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xb50`

## pseudocode

```c

```

## disassembly

```asm
0x1520  ldarg.0
0x1521  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ParenthesizedExpressionVisitor::_host
0x1526  ldarg.1
0x1527  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ParenthesizedExpressionSyntax::get_Expression()
0x152c  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x1531  ret
```
