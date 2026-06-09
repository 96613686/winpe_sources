# Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateRdlFunction

- ea: `0x1644a0`
- end: `0x1645a1`
- name: `Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateRdlFunction`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x163f60`

## callees

- `0x117c60`
- `0x119990`
- `0x1199b0`
- `0x163f60`
- `0x1640c0`
- `0x1644a0`
- `0x1662f0`
- `0x166320`
- `0x166350`

## string_xrefs

- `0x1644e5`: `Rdl function argument is complex.`

## pseudocode

```c

```

## disassembly

```asm
0x1644a0  ldarg.1
0x1644a1  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_RdlFunctionInfo()
0x1644a6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo> Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo::get_Expressions()
0x1644ab  stloc.0
0x1644ac  ldloc.0
0x1644ad  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo>::get_Count()
0x1644b2  newarr   [mscorlib]System.Object
0x1644b7  stloc.1
0x1644b8  ldc.i4.0
0x1644b9  stloc.2
0x1644ba  br.s     loc_16450C
0x1644bc  ldarg.0
0x1644bd  ldloc.0
0x1644be  ldloc.2
0x1644bf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo>::get_Item(!!T0)
0x1644c4  ldloca.s 3
0x1644c6  call     instance bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateSimpleExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, [out] valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result)
0x1644cb  brtrue.s loc_1644EF
0x1644cd  ldarg.0
0x1644ce  ldloc.0
0x1644cf  ldloc.2
0x1644d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo>::get_Item(!!T0)
0x1644d5  ldloca.s 3
0x1644d7  ldnull
0x1644d8  call     instance bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateComplexExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy exprHost)
0x1644dd  brtrue.s loc_1644EF
0x1644df  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x1644e4  ldc.i4.0
0x1644e5  ldstr    aRdlFunctionArg// "Rdl function argument is complex."
0x1644ea  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1644ef  ldloc.1
0x1644f0  ldloc.2
0x1644f1  ldloc.3
0x1644f2  ldfld    object Microsoft.ReportingServices.RdlExpressions.VariantResult::Value
0x1644f7  stelem.ref
0x1644f8  ldloc.3
0x1644f9  ldfld    bool Microsoft.ReportingServices.RdlExpressions.VariantResult::ErrorOccurred
0x1644fe  brfalse.s loc_164508
0x164500  ldarg.2
0x164501  ldloc.3
0x164502  stobj    Microsoft.ReportingServices.RdlExpressions.VariantResult
0x164507  ret
0x164508  ldloc.2
0x164509  ldc.i4.1
0x16450a  add
0x16450b  stloc.2
0x16450c  ldloc.2
0x16450d  ldloc.0
0x16450e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo>::get_Count()
0x164513  blt.s    loc_1644BC
0x164515  ldarg.1
0x164516  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_RdlFunctionInfo()
0x16451b  callvirt instance valuetype RdlFunctionType Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo::get_FunctionType()
0x164520  stloc.s  4
0x164522  ldloc.s  4
0x164524  switch   loc_16453F, loc_16454D, loc_16455B, loc_16455B, loc_164569
0x16453d  br.s     loc_164571
0x16453f  ldarg.2
0x164540  ldarg.0
0x164541  ldloc.1
0x164542  call     instance object Microsoft.ReportingServices.RdlExpressions.ReportRuntime::MinValue(object[] arguments)
0x164547  stfld    object Microsoft.ReportingServices.RdlExpressions.VariantResult::Value
0x16454c  ret
0x16454d  ldarg.2
0x16454e  ldarg.0
0x16454f  ldloc.1
0x164550  call     instance object Microsoft.ReportingServices.RdlExpressions.ReportRuntime::MaxValue(object[] arguments)
0x164555  stfld    object Microsoft.ReportingServices.RdlExpressions.VariantResult::Value
0x16455a  ret
0x16455b  ldarg.2
0x16455c  ldarg.0
0x16455d  ldloc.1
0x16455e  call     instance object Microsoft.ReportingServices.RdlExpressions.ReportRuntime::Comparable(object[] arguments)
0x164563  stfld    object Microsoft.ReportingServices.RdlExpressions.VariantResult::Value
0x164568  ret
0x164569  ldarg.2
0x16456a  ldloc.1
0x16456b  stfld    object Microsoft.ReportingServices.RdlExpressions.VariantResult::Value
0x164570  ret
0x164571  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x164576  ldc.i4.0
0x164577  ldstr    aNoCaseFor// "No case for: "
0x16457c  ldarg.1
0x16457d  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_RdlFunctionInfo()
0x164582  callvirt instance valuetype RdlFunctionType Microsoft.ReportingServices.ReportIntermediateFormat.RdlFunctionInfo::get_FunctionType()
0x164587  stloc.s  5
0x164589  ldloca.s 5
0x16458b  constrained. RdlFunctionType
0x164591  callvirt instance string [mscorlib]System.Object::ToString()
0x164596  call     string [mscorlib]System.String::Concat(string, string)
0x16459b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x1645a0  ret
```
