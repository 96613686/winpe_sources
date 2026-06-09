# Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::CompareLegacyAndSafeExpressionsRuntimeResults

- ea: `0x167120`
- end: `0x16718d`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressionsComparator::CompareLegacyAndSafeExpressionsRuntimeResults`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x167000`

## callees

- `0x167120`

## string_xrefs

- `0x167152`: `<removed>`
- `0x16713a`: `SERT: Mismatch details for safe expression and legacy runtime results comparison: `
- `0x16716d`: `SERT: Unexpected exception thrown during expression result comparision, ExceptionType: {0}, StackTrace: {1}, Message: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x167120  ldarg.0
0x167121  ldarg.1
0x167122  newobj   instance void [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::.ctor(object, object)
0x167127  stloc.0
0x167128  ldc.i4.0
0x167129  stloc.1
0x16712a  ldloc.0
0x16712b  callvirt instance bool [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareExpressionResults()
0x167130  stloc.1
0x167131  ldloc.1
0x167132  brtrue.s loc_16714F
0x167134  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x167139  ldc.i4.3
0x16713a  ldstr    aSertMismatchDe// "SERT: Mismatch details for safe express"...
0x16713f  ldloc.0
0x167140  callvirt instance string [Microsoft.ReportingServices.SafeReportExpressions]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::get_MismatchDetail()
0x167145  call     string [mscorlib]System.String::Concat(string, string)
0x16714a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x16714f  leave.s  loc_16718B
0x167151  stloc.2
0x167152  ldstr    aRemoved// "<removed>"
0x167157  stloc.3
0x167158  ldloc.2
0x167159  isinst   [mscorlib]System.InvalidOperationException
0x16715e  brfalse.s loc_167167
0x167160  ldloc.2
0x167161  callvirt instance string [mscorlib]System.Exception::get_Message()
0x167166  stloc.3
0x167167  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0x16716c  ldc.i4.2
0x16716d  ldstr    aSertUnexpected_1// "SERT: Unexpected exception thrown durin"...
0x167172  ldloc.2
0x167173  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x167178  ldloc.2
0x167179  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x16717e  ldloc.3
0x16717f  call     string [mscorlib]System.String::Format(string, object, object, object)
0x167184  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x167189  leave.s  loc_16718B
0x16718b  ldloc.1
0x16718c  ret
```
