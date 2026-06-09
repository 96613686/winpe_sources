# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::Evaluate

- ea: `0x10d0`
- end: `0x10f7`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::Evaluate`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1100`
- `0x1160`
- `0x1680`

## pseudocode

```c

```

## disassembly

```asm
0x10d0  ldarg.0
0x10d1  ldarg.1
0x10d2  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.InvocationExpressionSyntax node)
0x10d7  ldarg.0
0x10d8  ldarg.1
0x10d9  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.InvocationExpressionSyntax::get_Expression()
0x10de  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax
0x10e3  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::EvaluateIdentifierName(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax identifierNameSyntax)
0x10e8  stloc.0
0x10e9  ldarg.0
0x10ea  ldloc.0
0x10eb  ldarg.1
0x10ec  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.InvocationExpressionSyntax::get_ArgumentList()
0x10f1  call     instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::EvaluateFunctionInvocation(string functionName, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax argumentListSyntax)
0x10f6  ret
```
