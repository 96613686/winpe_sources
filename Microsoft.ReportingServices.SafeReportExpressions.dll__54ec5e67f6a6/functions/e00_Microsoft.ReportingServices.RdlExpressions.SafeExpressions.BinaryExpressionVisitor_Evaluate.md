# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::Evaluate

- ea: `0xe00`
- end: `0xe38`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::Evaluate`
- size: `56`
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
0xe00  ldarg.0
0xe01  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::_host
0xe06  ldarg.1
0xe07  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.BinaryExpressionSyntax::get_Left()
0xe0c  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0xe11  stloc.0
0xe12  ldarg.0
0xe13  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::_host
0xe18  ldarg.1
0xe19  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.BinaryExpressionSyntax::get_Right()
0xe1e  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0xe23  stloc.1
0xe24  ldarg.0
0xe25  ldfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IBinaryExpressionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::_evaluator
0xe2a  ldloc.0
0xe2b  ldloc.1
0xe2c  ldarg.1
0xe2d  callvirt instance valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxNode::Kind()
0xe32  callvirt instance object [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IBinaryExpressionEvaluator::Evaluate(object, object, valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind)
0xe37  ret
```
