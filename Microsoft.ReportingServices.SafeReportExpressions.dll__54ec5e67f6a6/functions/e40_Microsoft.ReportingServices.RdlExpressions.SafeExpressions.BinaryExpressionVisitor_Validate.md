# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::Validate

- ea: `0xe40`
- end: `0xee4`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::Validate`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xb50`
- `0xe40`

## pseudocode

```c

```

## disassembly

```asm
0xe40  ldarg.0
0xe41  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::_host
0xe46  ldarg.1
0xe47  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.BinaryExpressionSyntax::get_Left()
0xe4c  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0xe51  ldarg.0
0xe52  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BinaryExpressionVisitor::_host
0xe57  ldarg.1
0xe58  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.BinaryExpressionSyntax::get_Right()
0xe5d  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0xe62  ldarg.1
0xe63  callvirt instance valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxNode::Kind()
0xe68  stloc.0
0xe69  ldloc.0
0xe6a  ldc.i4   0x133
0xe6f  sub
0xe70  switch   loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EDD, loc_EDD, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EDD, loc_EDD, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3, loc_EE3
0xedd  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xee2  throw
0xee3  ret
```
