# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::GetValue

- ea: `0xba0`
- end: `0xcef`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::GetValue`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1420`

## callees

- `0x120`
- `0x130`
- `0x140`
- `0x150`
- `0x160`
- `0x170`
- `0x180`
- `0xba0`

## pseudocode

```c

```

## disassembly

```asm
0xba0  ldarg.1
0xba1  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xba6  stloc.0
0xba7  ldloc.0
0xba8  brfalse  loc_CDE
0xbad  ldloc.0
0xbae  call     instance int32 [mscorlib]System.String::get_Length()
0xbb3  stloc.1
0xbb4  ldloc.1
0xbb5  ldc.i4.4
0xbb6  sub
0xbb7  switch   loc_C65, loc_CDE, loc_C32, loc_BF4, loc_CDE, loc_C74, loc_BDD
0xbd8  br       loc_CDE
0xbdd  ldloc.0
0xbde  ldc.i4.0
0xbdf  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbe4  stloc.2
0xbe5  ldloc.2
0xbe6  ldc.i4.s 0x41
0xbe8  beq.s    loc_C0B
0xbea  ldloc.2
0xbeb  ldc.i4.s 0x50
0xbed  beq.s    loc_C1D
0xbef  br       loc_CDE
0xbf4  ldloc.0
0xbf5  ldc.i4.0
0xbf6  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbfb  stloc.2
0xbfc  ldloc.2
0xbfd  ldc.i4.s 0x47
0xbff  beq.s    loc_C44
0xc01  ldloc.2
0xc02  ldc.i4.s 0x4C
0xc04  beq.s    loc_C56
0xc06  br       loc_CDE
0xc0b  ldloc.0
0xc0c  ldstr    aAggregates// "AGGREGATES"
0xc11  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc16  brtrue.s loc_C83
0xc18  br       loc_CDE
0xc1d  ldloc.0
0xc1e  ldstr    aParameters// "PARAMETERS"
0xc23  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc28  brtrue   loc_CB7
0xc2d  br       loc_CDE
0xc32  ldloc.0
0xc33  ldstr    aFields// "FIELDS"
0xc38  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc3d  brtrue.s loc_C90
0xc3f  br       loc_CDE
0xc44  ldloc.0
0xc45  ldstr    aGlobals// "GLOBALS"
0xc4a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc4f  brtrue.s loc_C9D
0xc51  br       loc_CDE
0xc56  ldloc.0
0xc57  ldstr    aLookups// "LOOKUPS"
0xc5c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc61  brtrue.s loc_CAA
0xc63  br.s     loc_CDE
0xc65  ldloc.0
0xc66  ldstr    aUser// "USER"
0xc6b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc70  brtrue.s loc_CC4
0xc72  br.s     loc_CDE
0xc74  ldloc.0
0xc75  ldstr    aVariables// "VARIABLES"
0xc7a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc7f  brtrue.s loc_CD1
0xc81  br.s     loc_CDE
0xc83  ldarg.0
0xc84  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::_safeExpressionsContext
0xc89  ldarg.2
0xc8a  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::GetAggregate(string aggregateName)
0xc8f  ret
0xc90  ldarg.0
0xc91  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::_safeExpressionsContext
0xc96  ldarg.2
0xc97  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::GetField(string fieldName)
0xc9c  ret
0xc9d  ldarg.0
0xc9e  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::_safeExpressionsContext
0xca3  ldarg.2
0xca4  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::GetGlobal(string globalName)
0xca9  ret
0xcaa  ldarg.0
0xcab  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::_safeExpressionsContext
0xcb0  ldarg.2
0xcb1  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::GetLookup(string lookupName)
0xcb6  ret
0xcb7  ldarg.0
0xcb8  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::_safeExpressionsContext
0xcbd  ldarg.2
0xcbe  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::GetParameter(string parameterName)
0xcc3  ret
0xcc4  ldarg.0
0xcc5  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::_safeExpressionsContext
0xcca  ldarg.2
0xccb  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::GetUser(string userParameterName)
0xcd0  ret
0xcd1  ldarg.0
0xcd2  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::_safeExpressionsContext
0xcd7  ldarg.2
0xcd8  callvirt instance object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext::GetVariable(string variableName)
0xcdd  ret
0xcde  ldstr    aTheSpecifiedNa// "The specified name of collection is not"...
0xce3  ldloc.0
0xce4  call     string [mscorlib]System.String::Concat(string, string)
0xce9  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xcee  throw
```
