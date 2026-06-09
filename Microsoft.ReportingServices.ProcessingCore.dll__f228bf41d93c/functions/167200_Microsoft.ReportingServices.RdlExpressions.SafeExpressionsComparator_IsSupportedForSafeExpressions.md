# Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::IsSupportedForSafeExpressions

- ea: `0x167200`
- end: `0x167268`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::IsSupportedForSafeExpressions`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x167000`

## callees

- `0x1670d0`
- `0x167200`

## string_xrefs

- `0x16720b`: `<removed>`
- `0x16722e`: `SERT: Unexpected exception thrown during safe expression runtime validation, ExceptionType: {0}, StackTrace: {1}, Expression Syntax tree: {2}, Message: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x167200  ldarg.0
0x167201  ldarg.1
0x167202  callvirt instance bool [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::Validate(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax)
0x167207  stloc.0
0x167208  leave.s  loc_167266
0x16720a  stloc.1
0x16720b  ldstr    aRemoved// "<removed>"
0x167210  stloc.2
0x167211  ldloc.1
0x167212  isinst   [mscorlib]System.NotImplementedException
0x167217  brtrue.s loc_167221
0x167219  ldloc.1
0x16721a  isinst   [mscorlib]System.NotSupportedException
0x16721f  brfalse.s loc_167228
0x167221  ldloc.1
0x167222  callvirt instance string [mscorlib]System.Exception::get_Message()
0x167227  stloc.2
0x167228  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x16722d  ldc.i4.2
0x16722e  ldstr    aSertUnexpected_3// "SERT: Unexpected exception thrown durin"...
0x167233  ldc.i4.4
0x167234  newarr   [mscorlib]System.Object
0x167239  dup
0x16723a  ldc.i4.0
0x16723b  ldloc.1
0x16723c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x167241  stelem.ref
0x167242  dup
0x167243  ldc.i4.1
0x167244  ldloc.1
0x167245  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x16724a  stelem.ref
0x16724b  dup
0x16724c  ldc.i4.2
0x16724d  ldarg.1
0x16724e  call     string Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::SerializeSyntaxTree(class [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.Syntax.ExpressionSyntax expressionSyntax)
0x167253  stelem.ref
0x167254  dup
0x167255  ldc.i4.3
0x167256  ldloc.2
0x167257  stelem.ref
0x167258  call     string [mscorlib]System.String::Format(string, object[])
0x16725d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x167262  leave.s  loc_167264
0x167264  ldc.i4.0
0x167265  ret
0x167266  ldloc.0
0x167267  ret
```
