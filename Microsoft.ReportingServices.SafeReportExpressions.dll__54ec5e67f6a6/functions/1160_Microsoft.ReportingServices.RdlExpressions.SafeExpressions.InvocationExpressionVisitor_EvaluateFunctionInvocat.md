# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::EvaluateFunctionInvocation

- ea: `0x1160`
- end: `0x11a5`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::EvaluateFunctionInvocation`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x10d0`

## callees

- `0x580`
- `0x960`
- `0x970`
- `0x1160`
- `0x1250`
- `0x1290`

## pseudocode

```c

```

## disassembly

```asm
0x1160  ldarg.0
0x1161  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::_functionFactory
0x1166  ldarg.1
0x1167  ldloca.s 0
0x1169  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::TryGet(string functionName, [out] class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction& argumentValidator)
0x116e  brtrue.s loc_1186
0x1170  ldstr    aFunctionOfType// "Function of type "
0x1175  ldarg.1
0x1176  ldstr    aIsNotSupported_0// " is not supported"
0x117b  call     string [mscorlib]System.String::Concat(string, string, string)
0x1180  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1185  throw
0x1186  ldarg.0
0x1187  ldarg.2
0x1188  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::GetArgumentExpressions(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax argumentListSyntax)
0x118d  stloc.1
0x118e  ldloc.0
0x118f  ldloc.1
0x1190  callvirt instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction::ValidateArguments(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax> argumentExpressions)
0x1195  ldarg.0
0x1196  ldloc.1
0x1197  call     instance class [mscorlib]System.Collections.Generic.List`1<object> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::EvaluateExpressions(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax> expressions)
0x119c  stloc.2
0x119d  ldloc.0
0x119e  ldloc.2
0x119f  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction::Evaluate(class [mscorlib]System.Collections.Generic.List`1<object> arguments)
0x11a4  ret
```
