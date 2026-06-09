# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::Validate

- ea: `0x15a0`
- end: `0x15d4`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::Validate`
- size: `52`
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
0x15a0  ldarg.0
0x15a1  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::_host
0x15a6  ldarg.1
0x15a7  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_Condition()
0x15ac  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x15b1  ldarg.0
0x15b2  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::_host
0x15b7  ldarg.1
0x15b8  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_WhenTrue()
0x15bd  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x15c2  ldarg.0
0x15c3  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::_host
0x15c8  ldarg.1
0x15c9  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_WhenFalse()
0x15ce  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x15d3  ret
```
