# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::GetArgumentExpressions

- ea: `0x1250`
- end: `0x1286`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::GetArgumentExpressions`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1160`
- `0x11b0`

## callees

- `0x1250`

## pseudocode

```c

```

## disassembly

```asm
0x1250  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::.ctor()
0x1255  stloc.0
0x1256  ldarg.1
0x1257  callvirt instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentSyntax> [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax::get_Arguments()
0x125c  stloc.2
0x125d  ldloca.s 2
0x125f  call     instance valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1/Enumerator<var<u1>> valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentSyntax>::GetEnumerator()
0x1264  stloc.1
0x1265  br.s     loc_127B
0x1267  ldloca.s 1
0x1269  call     instance var<u1> valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentSyntax>::get_Current()
0x126e  stloc.3
0x126f  ldloc.0
0x1270  ldloc.3
0x1271  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentSyntax::GetExpression()
0x1276  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::Add(var<u1>)
0x127b  ldloca.s 1
0x127d  call     instance bool valuetype [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SeparatedSyntaxList`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentSyntax>::MoveNext()
0x1282  brtrue.s loc_1267
0x1284  ldloc.0
0x1285  ret
```
