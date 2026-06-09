# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::Evaluate

- ea: `0x1610`
- end: `0x1635`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::Evaluate`
- size: `37`
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
0x1610  ldarg.0
0x1611  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::_host
0x1616  ldarg.1
0x1617  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.UnaryExpressionSyntax::get_Operand()
0x161c  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x1621  stloc.0
0x1622  ldarg.0
0x1623  ldfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IUnaryExpressionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.UnaryExpressionVisitor::_evaluator
0x1628  ldloc.0
0x1629  ldarg.1
0x162a  callvirt instance valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxNode::Kind()
0x162f  callvirt instance object [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IUnaryExpressionEvaluator::Evaluate(object, valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind)
0x1634  ret
```
