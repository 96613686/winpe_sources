# Microsoft.ReportingServices.RdlExpressions.SafeExpressionsRuntime::EvaluateExpression

- ea: `0x166c90`
- end: `0x166d34`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressionsRuntime::EvaluateExpression`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x163ef0`

## callees

- `0x117cc0`
- `0x117cd0`
- `0x11a0f0`
- `0x11a100`
- `0x1668b0`
- `0x166c90`
- `0x166df0`
- `0x166e20`
- `0x166e40`
- `0x166f80`

## string_xrefs

- `0x166cf2`: `SafeExpressionRuntime: Attempted evaluation of unsupported expression. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x166c90  ldarg.1
0x166c91  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionStructureInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_ExpressionStructureInfo()
0x166c96  stloc.0
0x166c97  ldloc.0
0x166c98  brtrue.s loc_166CB5
0x166c9a  ldarg.1
0x166c9b  call     string Microsoft.ReportingServices.RdlExpressions.ExpressionInfoExtensions::GetExpressionString(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x166ca0  stloc.1
0x166ca1  ldarg.0
0x166ca2  ldloc.1
0x166ca3  call     instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax Microsoft.ReportingServices.RdlExpressions.SafeExpressionsRuntime::ParseExpressionString(string expressionString)
0x166ca8  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionStructureInfo::.ctor(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax expressionSyntax)
0x166cad  stloc.0
0x166cae  ldarg.1
0x166caf  ldloc.0
0x166cb0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::set_ExpressionStructureInfo(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionStructureInfo value)
0x166cb5  ldarg.0
0x166cb6  ldfld    class Microsoft.ReportingServices.RdlExpressions.PerformanceAggregator Microsoft.ReportingServices.RdlExpressions.SafeExpressionsRuntime::m_PerformanceAggregator
0x166cbb  ldc.i4.1
0x166cbc  callvirt instance valuetype PerformanceMeasurement Microsoft.ReportingServices.RdlExpressions.PerformanceAggregator::StartMeasurement(valuetype Microsoft.ReportingServices.RdlExpressions.PerformanceMetricType metricType)
0x166cc1  stloc.2
0x166cc2  ldarg.2
0x166cc3  ldarg.0
0x166cc4  ldfld    class [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressionsRuntime::m_ExpressionEvaluator
0x166cc9  ldloc.0
0x166cca  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionStructureInfo::get_ExpressionSyntax()
0x166ccf  callvirt instance object [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::Evaluate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax)
0x166cd4  stfld    object Microsoft.ReportingServices.RdlExpressions.VariantResult::Value
0x166cd9  leave.s  loc_166CE9
0x166cdb  ldloca.s 2
0x166cdd  constrained. PerformanceMeasurement
0x166ce3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x166ce8  endfinally
0x166ce9  leave.s  loc_166D33
0x166ceb  stloc.3
0x166cec  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x166cf1  ldc.i4.2
0x166cf2  ldstr    aSafeexpression// "SafeExpressionRuntime: Attempted evalua"...
0x166cf7  ldloc.3
0x166cf8  call     string [mscorlib]System.String::Format(string, object)
0x166cfd  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::TraceException(valuetype [System]System.Diagnostics.TraceLevel, string)
0x166d02  ldarg.1
0x166d03  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionStructureInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_ExpressionStructureInfo()
0x166d08  callvirt instance class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionStructureInfo::get_ExpressionSyntax()
0x166d0d  callvirt instance class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxTree [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode::get_SyntaxTree()
0x166d12  stloc.s  4
0x166d14  ldarg.0
0x166d15  ldloc.s  4
0x166d17  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressionsRuntime::TraceSyntaxTree(class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxTree syntaxTree)
0x166d1c  ldarg.0
0x166d1d  ldarg.2
0x166d1e  ldloc.3
0x166d1f  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressionsRuntime::SetResultToFailed(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [mscorlib]System.Exception exception)
0x166d24  leave.s  loc_166D33
0x166d26  stloc.s  5
0x166d28  ldarg.0
0x166d29  ldarg.2
0x166d2a  ldloc.s  5
0x166d2c  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressionsRuntime::SetResultToFailed(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [mscorlib]System.Exception exception)
0x166d31  leave.s  loc_166D33
0x166d33  ret
```
