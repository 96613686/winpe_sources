# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.CollectionInitializerVisitor::Evaluate

- ea: `0xf10`
- end: `0xf55`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.CollectionInitializerVisitor::Evaluate`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xb40`
- `0xf10`

## pseudocode

```c

```

## disassembly

```asm
0xf10  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0xf15  stloc.0
0xf16  ldarg.1
0xf17  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax> [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.CollectionInitializerSyntax::get_Initializers()
0xf1c  stloc.2
0xf1d  ldloca.s 2
0xf1f  call     instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1/Enumerator<var<u1>> valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::GetEnumerator()
0xf24  stloc.1
0xf25  br.s     loc_F45
0xf27  ldloca.s 1
0xf29  call     instance var<u1> valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Current()
0xf2e  stloc.3
0xf2f  ldarg.0
0xf30  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.CollectionInitializerVisitor::_host
0xf35  ldloc.3
0xf36  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0xf3b  stloc.s  4
0xf3d  ldloc.0
0xf3e  ldloc.s  4
0xf40  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0xf45  ldloca.s 1
0xf47  call     instance bool valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::MoveNext()
0xf4c  brtrue.s loc_F27
0xf4e  ldloc.0
0xf4f  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<object>::ToArray()
0xf54  ret
```
