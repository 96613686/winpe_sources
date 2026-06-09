# Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::Compare

- ea: `0x167000`
- end: `0x1670c3`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::Compare`
- size: `195`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x15c180`
- `0x164200`
- `0x164260`
- `0x1642f0`
- `0x164360`
- `0x1643d0`
- `0x164430`

## callees

- `0x166b40`
- `0x166f80`
- `0x167000`
- `0x1670d0`
- `0x167120`
- `0x167190`
- `0x167200`

## string_xrefs

- `0x167079`: `<removed>`
- `0x1670a1`: `SERT: Unexpected exception thrown during expression parsing, ExceptionType: {0}, StackTrace: {1}, Message: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x167000  ldarg.2
0x167001  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressionsReportContext::.ctor(class Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.ObjectModelImpl reportProcessingObjectModel)
0x167006  newobj   instance void [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::.ctor(class [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext)
0x16700b  stloc.0
0x16700c  ldloc.0
0x16700d  ldarg.0
0x16700e  call     string Microsoft.ReportingServices.RdlExpressions.ExpressionInfoExtensions::GetExpressionString(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x167013  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::ParseExpression(string)
0x167018  stloc.1
0x167019  ldloc.0
0x16701a  ldloc.1
0x16701b  call     bool Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::IsSupportedForSafeExpressions(class [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator expressionEvaluator, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax expressionSyntax)
0x167020  brfalse.s loc_167075
0x167022  ldc.i4.0
0x167023  stloc.2
0x167024  ldloc.0
0x167025  ldloc.1
0x167026  ldloca.s 3
0x167028  call     bool Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::TryEvaluateExpression(class [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator expressionEvaluator, class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax expressionSyntax, [out] object& result)
0x16702d  brfalse.s loc_167037
0x16702f  ldarg.1
0x167030  ldloc.3
0x167031  call     bool Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::CompareLegacyAndSafeExpressionsRuntimeResults(object legacyRuntimeResult, object safeExpressionsRuntimeResult)
0x167036  stloc.2
0x167037  ldloc.2
0x167038  brtrue.s loc_167075
0x16703a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x16703f  ldc.i4.3
0x167040  ldstr    aSertMismatchIn// "SERT: Mismatch in safe expression and l"...
0x167045  ldloc.1
0x167046  call     string Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::SerializeSyntaxTree(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax expressionSyntax)
0x16704b  call     string [mscorlib]System.String::Concat(string, string)
0x167050  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x167055  ldstr    aExpression0Leg// "Expression: '{0}', LegacyResult: '{1}',"...
0x16705a  ldarg.0
0x16705b  call     string Microsoft.ReportingServices.RdlExpressions.ExpressionInfoExtensions::GetExpressionString(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x167060  ldarg.1
0x167061  ldloc.3
0x167062  call     string [mscorlib]System.String::Format(string, object, object, object)
0x167067  stloc.s  4
0x167069  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x16706e  ldloc.s  4
0x167070  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContextBase::TraceCustomerContentByHost(string)
0x167075  leave.s  loc_1670C2
0x167077  stloc.s  5
0x167079  ldstr    aRemoved// "<removed>"
0x16707e  stloc.s  6
0x167080  ldloc.s  5
0x167082  isinst   [mscorlib]System.NotImplementedException
0x167087  brtrue.s loc_167092
0x167089  ldloc.s  5
0x16708b  isinst   [mscorlib]System.NotSupportedException
0x167090  brfalse.s loc_16709B
0x167092  ldloc.s  5
0x167094  callvirt instance string [mscorlib]System.Exception::get_Message()
0x167099  stloc.s  6
0x16709b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x1670a0  ldc.i4.2
0x1670a1  ldstr    aSertUnexpected// "SERT: Unexpected exception thrown durin"...
0x1670a6  ldloc.s  5
0x1670a8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1670ad  ldloc.s  5
0x1670af  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x1670b4  ldloc.s  6
0x1670b6  call     string [mscorlib]System.String::Format(string, object, object, object)
0x1670bb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1670c0  leave.s  loc_1670C2
0x1670c2  ret
```
