# Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::TryEvaluateExpression

- ea: `0x167190`
- end: `0x1671fe`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::TryEvaluateExpression`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x167000`

## callees

- `0x1670d0`
- `0x167190`

## string_xrefs

- `0x1671a1`: `<removed>`
- `0x1671c4`: `SERT: Unexpected exception thrown during safe expression runtime evaluation, ExceptionType: {0}, StackTrace: {1}, Expression Syntax tree: {2}, Message: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x167190  ldarg.2
0x167191  ldnull
0x167192  stind.ref
0x167193  ldarg.2
0x167194  ldarg.0
0x167195  ldarg.1
0x167196  callvirt instance object [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax)
0x16719b  stind.ref
0x16719c  ldc.i4.1
0x16719d  stloc.0
0x16719e  leave.s  loc_1671FC
0x1671a0  stloc.1
0x1671a1  ldstr    aRemoved// "<removed>"
0x1671a6  stloc.2
0x1671a7  ldloc.1
0x1671a8  isinst   [mscorlib]System.NotImplementedException
0x1671ad  brtrue.s loc_1671B7
0x1671af  ldloc.1
0x1671b0  isinst   [mscorlib]System.NotSupportedException
0x1671b5  brfalse.s loc_1671BE
0x1671b7  ldloc.1
0x1671b8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1671bd  stloc.2
0x1671be  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x1671c3  ldc.i4.2
0x1671c4  ldstr    aSertUnexpected_2// "SERT: Unexpected exception thrown durin"...
0x1671c9  ldc.i4.4
0x1671ca  newarr   [mscorlib]System.Object
0x1671cf  dup
0x1671d0  ldc.i4.0
0x1671d1  ldloc.1
0x1671d2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1671d7  stelem.ref
0x1671d8  dup
0x1671d9  ldc.i4.1
0x1671da  ldloc.1
0x1671db  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x1671e0  stelem.ref
0x1671e1  dup
0x1671e2  ldc.i4.2
0x1671e3  ldarg.1
0x1671e4  call     string Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::SerializeSyntaxTree(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax expressionSyntax)
0x1671e9  stelem.ref
0x1671ea  dup
0x1671eb  ldc.i4.3
0x1671ec  ldloc.2
0x1671ed  stelem.ref
0x1671ee  call     string [mscorlib]System.String::Format(string, object[])
0x1671f3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1671f8  leave.s  loc_1671FA
0x1671fa  ldc.i4.0
0x1671fb  ret
0x1671fc  ldloc.0
0x1671fd  ret
```
