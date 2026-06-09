# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::Validate

- ea: `0x1100`
- end: `0x1151`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::Validate`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x10d0`

## callees

- `0x1100`
- `0x11b0`
- `0x1680`

## pseudocode

```c

```

## disassembly

```asm
0x1100  ldarg.1
0x1101  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.InvocationExpressionSyntax::get_Expression()
0x1106  isinst   [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax
0x110b  stloc.0
0x110c  ldloc.0
0x110d  brfalse.s loc_1125
0x110f  ldarg.0
0x1110  ldloc.0
0x1111  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::EvaluateIdentifierName(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.IdentifierNameSyntax identifierNameSyntax)
0x1116  stloc.1
0x1117  ldarg.0
0x1118  ldloc.1
0x1119  ldarg.1
0x111a  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.InvocationExpressionSyntax::get_ArgumentList()
0x111f  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InvocationExpressionVisitor::ValidateFunctionInvocation(string functionName, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ArgumentListSyntax argumentListSyntax)
0x1124  ret
0x1125  ldstr    aExpressionOfTy// "Expression of type "
0x112a  ldarg.1
0x112b  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.InvocationExpressionSyntax::get_Expression()
0x1130  dup
0x1131  brtrue.s loc_1137
0x1133  pop
0x1134  ldnull
0x1135  br.s     loc_1141
0x1137  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x113c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1141  ldstr    aIsNotSupported_0// " is not supported"
0x1146  call     string [mscorlib]System.String::Concat(string, string, string)
0x114b  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1150  throw
```
