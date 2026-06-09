# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ParenthesizedExpressionVisitor::Evaluate

- ea: `0x1500`
- end: `0x1512`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ParenthesizedExpressionVisitor::Evaluate`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xb40`

## pseudocode

```c

```

## disassembly

```asm
0x1500  ldarg.0
0x1501  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ParenthesizedExpressionVisitor::_host
0x1506  ldarg.1
0x1507  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ParenthesizedExpressionSyntax::get_Expression()
0x150c  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x1511  ret
```
