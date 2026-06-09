# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::Validate

- ea: `0x1370`
- end: `0x1418`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::Validate`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1420`

## callees

- `0xb50`
- `0xb80`
- `0x1370`
- `0x1680`

## string_xrefs

- `0x13ab`: `Unsupported expression for member access expression and '.' operator.`
- `0x13ed`: `Unsupported expression for member access expression and '!' operator.`
- `0x13f8`: `Unsupported operator for member access expression. Operator syntax: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1370  ldarg.1
0x1371  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_OperatorToken()
0x1376  call     valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicExtensions::Kind(valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken)
0x137b  stloc.1
0x137c  ldloc.1
0x137d  ldc.i4   0x27A
0x1382  beq.s    loc_13B6
0x1384  ldloc.1
0x1385  ldc.i4   0x28A
0x138a  bne.un.s loc_13F8
0x138c  ldarg.1
0x138d  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_Expression()
0x1392  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax
0x1397  brfalse.s loc_13AB
0x1399  ldarg.0
0x139a  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::_host
0x139f  ldarg.1
0x13a0  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_Expression()
0x13a5  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x13aa  ret
0x13ab  ldstr    aUnsupportedExp// "Unsupported expression for member acces"...
0x13b0  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x13b5  throw
0x13b6  ldarg.1
0x13b7  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_Expression()
0x13bc  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax
0x13c1  stloc.0
0x13c2  ldloc.0
0x13c3  brfalse.s loc_13ED
0x13c5  ldarg.0
0x13c6  ldloc.0
0x13c7  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::EvaluateIdentifierName(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax identifierNameSyntax)
0x13cc  stloc.2
0x13cd  ldarg.0
0x13ce  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor Microsoft.ReportingServices.RdlExpressions.SafeExpressions.MemberAccessExpressionVisitor::_reportCollectionAccessor
0x13d3  ldloc.2
0x13d4  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::IsValidCollectionName(string collectionName)
0x13d9  brtrue.s loc_13EC
0x13db  ldstr    aTheSpecifiedCo// "The specified collection name is not su"...
0x13e0  ldloc.2
0x13e1  call     string [mscorlib]System.String::Concat(string, string)
0x13e6  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x13eb  throw
0x13ec  ret
0x13ed  ldstr    aUnsupportedExp_0// "Unsupported expression for member acces"...
0x13f2  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x13f7  throw
0x13f8  ldstr    aUnsupportedOpe// "Unsupported operator for member access "...
0x13fd  ldarg.1
0x13fe  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.MemberAccessExpressionSyntax::get_OperatorToken()
0x1403  call     valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicExtensions::Kind(valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxToken)
0x1408  box      [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind
0x140d  call     string [mscorlib]System.String::Format(string, object)
0x1412  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1417  throw
```
