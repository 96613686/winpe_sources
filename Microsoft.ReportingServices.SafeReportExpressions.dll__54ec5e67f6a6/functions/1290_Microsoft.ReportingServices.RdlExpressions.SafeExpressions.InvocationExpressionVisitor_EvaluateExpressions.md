# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::EvaluateExpressions

- ea: `0x1290`
- end: `0x12d4`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::EvaluateExpressions`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1160`

## callees

- `0xb40`
- `0x1290`

## pseudocode

```c

```

## disassembly

```asm
0x1290  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x1295  stloc.0
0x1296  ldarg.1
0x1297  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::GetEnumerator()
0x129c  stloc.1
0x129d  br.s     loc_12B9
0x129f  ldloca.s 1
0x12a1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Current()
0x12a6  stloc.2
0x12a7  ldloc.0
0x12a8  ldarg.0
0x12a9  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::_host
0x12ae  ldloc.2
0x12af  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x12b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x12b9  ldloca.s 1
0x12bb  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::MoveNext()
0x12c0  brtrue.s loc_129F
0x12c2  leave.s  loc_12D2
0x12c4  ldloca.s 1
0x12c6  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>
0x12cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12d1  endfinally
0x12d2  ldloc.0
0x12d3  ret
```
