# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::ValidateFunctionInvocation

- ea: `0x11b0`
- end: `0x1244`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::ValidateFunctionInvocation`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1100`

## callees

- `0x590`
- `0xb50`
- `0x11b0`
- `0x1250`
- `0x1680`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldarg.0
0x11b1  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::_functionFactory
0x11b6  ldarg.1
0x11b7  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Supports(string functionName)
0x11bc  brtrue.s loc_11D4
0x11be  ldstr    aFunctionOfType// "Function of type "
0x11c3  ldarg.1
0x11c4  ldstr    aIsNotSupported_0// " is not supported"
0x11c9  call     string [mscorlib]System.String::Concat(string, string, string)
0x11ce  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x11d3  throw
0x11d4  ldarg.0
0x11d5  ldarg.2
0x11d6  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::GetArgumentExpressions(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax argumentListSyntax)
0x11db  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::GetEnumerator()
0x11e0  stloc.0
0x11e1  br.s     loc_122A
0x11e3  ldloca.s 0
0x11e5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::get_Current()
0x11ea  stloc.1
0x11eb  ldloc.1
0x11ec  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax
0x11f1  stloc.2
0x11f2  ldloc.2
0x11f3  brfalse.s loc_121E
0x11f5  ldarg.0
0x11f6  ldloc.2
0x11f7  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::EvaluateIdentifierName(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax identifierNameSyntax)
0x11fc  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1201  stloc.3
0x1202  ldarg.0
0x1203  ldfld    string[] Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::BuiltInFunctionArgIdentifiers
0x1208  ldloc.3
0x1209  call     T0x2B00000A
0x120e  brtrue.s loc_122A
0x1210  ldarg.0
0x1211  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::_host
0x1216  ldloc.2
0x1217  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x121c  br.s     loc_122A
0x121e  ldarg.0
0x121f  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::_host
0x1224  ldloc.1
0x1225  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IExpressionVisitorHost::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax node)
0x122a  ldloca.s 0
0x122c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>::MoveNext()
0x1231  brtrue.s loc_11E3
0x1233  leave.s  loc_1243
0x1235  ldloca.s 0
0x1237  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax>
0x123d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1242  endfinally
0x1243  ret
```
