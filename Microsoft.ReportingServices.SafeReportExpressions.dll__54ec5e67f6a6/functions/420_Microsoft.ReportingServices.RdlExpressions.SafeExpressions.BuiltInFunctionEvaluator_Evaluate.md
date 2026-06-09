# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::Evaluate

- ea: `0x420`
- end: `0x4ad`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::Evaluate`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x190`
- `0x1a0`
- `0x420`
- `0x4b0`

## pseudocode

```c

```

## disassembly

```asm
0x420  ldarg.1
0x421  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x426  stloc.1
0x427  ldloc.1
0x428  ldstr    aLevel// "LEVEL"
0x42d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x432  brtrue.s loc_443
0x434  ldloc.1
0x435  ldstr    aInscope// "INSCOPE"
0x43a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43f  brtrue.s loc_482
0x441  br.s     loc_4A7
0x443  ldarg.2
0x444  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<object>::get_Count()
0x449  brtrue.s loc_45D
0x44b  ldarg.0
0x44c  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::_safeExpressionsReportContext
0x451  ldnull
0x452  callvirt instance int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::GetLevel(string scope)
0x457  box      [mscorlib]System.Int32
0x45c  ret
0x45d  ldarg.0
0x45e  ldstr    aLevel_0// "Level"
0x463  ldarg.2
0x464  ldc.i4.0
0x465  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x46a  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::GetAsString(string functionName, object value)
0x46f  stloc.2
0x470  ldarg.0
0x471  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::_safeExpressionsReportContext
0x476  ldloc.2
0x477  callvirt instance int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::GetLevel(string scope)
0x47c  box      [mscorlib]System.Int32
0x481  ret
0x482  ldarg.0
0x483  ldstr    aInscope_0// "InScope"
0x488  ldarg.2
0x489  ldc.i4.0
0x48a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object>::get_Item(!!T0)
0x48f  call     instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::GetAsString(string functionName, object value)
0x494  stloc.0
0x495  ldarg.0
0x496  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctionEvaluator::_safeExpressionsReportContext
0x49b  ldloc.0
0x49c  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::InScope(string scope)
0x4a1  box      [mscorlib]System.Boolean
0x4a6  ret
0x4a7  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x4ac  throw
```
