# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::Evaluate

- ea: `0x1420`
- end: `0x14cb`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::Evaluate`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0xb40`
- `0xba0`
- `0x1370`
- `0x1420`
- `0x14d0`
- `0x1680`

## string_xrefs

- `0x14ab`: `Unsupported operator for member access expression. Operator syntax: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1420  ldarg.0
0x1421  ldarg.1
0x1422  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax node)
0x1427  ldarg.1
0x1428  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_OperatorToken()
0x142d  call     valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicExtensions::Kind(valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken)
0x1432  stloc.s  4
0x1434  ldloc.s  4
0x1436  ldc.i4   0x27A
0x143b  beq.s    loc_147E
0x143d  ldloc.s  4
0x143f  ldc.i4   0x28A
0x1444  bne.un.s loc_14AB
0x1446  ldarg.0
0x1447  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::_host
0x144c  ldarg.1
0x144d  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_Expression()
0x1452  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x1457  stloc.0
0x1458  ldarg.0
0x1459  ldarg.1
0x145a  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.SimpleNameSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_Name()
0x145f  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::GetSimpleNameText(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.SimpleNameSyntax simpleNameSyntax)
0x1464  stloc.1
0x1465  ldarg.0
0x1466  ldfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IObjectAccessEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::_objectAccessEvaluator
0x146b  ldloc.0
0x146c  ldloc.1
0x146d  ldarg.1
0x146e  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_OperatorToken()
0x1473  call     valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicExtensions::Kind(valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken)
0x1478  callvirt instance object [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IObjectAccessEvaluator::EvaluateProperty(object, string, valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind)
0x147d  ret
0x147e  ldarg.0
0x147f  ldarg.1
0x1480  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_Expression()
0x1485  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax
0x148a  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::EvaluateIdentifierName(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax identifierNameSyntax)
0x148f  stloc.2
0x1490  ldarg.0
0x1491  ldarg.1
0x1492  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.SimpleNameSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_Name()
0x1497  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::GetSimpleNameText(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.SimpleNameSyntax simpleNameSyntax)
0x149c  stloc.3
0x149d  ldarg.0
0x149e  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::_reportCollectionAccessor
0x14a3  ldloc.2
0x14a4  ldloc.3
0x14a5  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::GetValue(string collectionName, string itemName)
0x14aa  ret
0x14ab  ldstr    aUnsupportedOpe// "Unsupported operator for member access "...
0x14b0  ldarg.1
0x14b1  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_OperatorToken()
0x14b6  call     valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicExtensions::Kind(valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken)
0x14bb  box      [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind
0x14c0  call     string [mscorlib]System.String::Format(string, object)
0x14c5  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x14ca  throw
```
