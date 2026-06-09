# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::Evaluate

- ea: `0x1560`
- end: `0x159c`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::Evaluate`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1e0`
- `0xb40`
- `0x1560`

## pseudocode

```c

```

## disassembly

```asm
0x1560  ldarg.0
0x1561  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::_host
0x1566  ldarg.1
0x1567  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_Condition()
0x156c  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x1571  call     bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VBConvert::ConvertToBoolean(object value)
0x1576  brfalse.s loc_158A
0x1578  ldarg.0
0x1579  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::_host
0x157e  ldarg.1
0x157f  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_WhenTrue()
0x1584  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x1589  ret
0x158a  ldarg.0
0x158b  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.TernaryConditionalExpressionVisitor::_host
0x1590  ldarg.1
0x1591  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.TernaryConditionalExpressionSyntax::get_WhenFalse()
0x1596  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x159b  ret
```
