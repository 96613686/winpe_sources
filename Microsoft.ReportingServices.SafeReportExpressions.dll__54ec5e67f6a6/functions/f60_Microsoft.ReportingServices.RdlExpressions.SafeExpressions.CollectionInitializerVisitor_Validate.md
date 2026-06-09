# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.CollectionInitializerVisitor::Validate

- ea: `0xf60`
- end: `0xf8f`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.CollectionInitializerVisitor::Validate`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xb50`
- `0xf60`

## pseudocode

```c

```

## disassembly

```asm
0xf60  ldarg.1
0xf61  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax> [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.CollectionInitializerSyntax::get_Initializers()
0xf66  stloc.1
0xf67  ldloca.s 1
0xf69  call     instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1/Enumerator<var<u1>> valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::GetEnumerator()
0xf6e  stloc.0
0xf6f  br.s     loc_F85
0xf71  ldloca.s 0
0xf73  call     instance var<u1> valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Current()
0xf78  stloc.2
0xf79  ldarg.0
0xf7a  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.CollectionInitializerVisitor::_host
0xf7f  ldloc.2
0xf80  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0xf85  ldloca.s 0
0xf87  call     instance bool valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::MoveNext()
0xf8c  brtrue.s loc_F71
0xf8e  ret
```
