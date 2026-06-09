# Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateCustomLabelAllowUpsideDownExpression

- ea: `0x1566f0`
- end: `0x156751`
- name: `Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateCustomLabelAllowUpsideDownExpression`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xc6e90`

## callees

- `0xc64d0`
- `0xc6600`
- `0x1566f0`
- `0x163f10`
- `0x164200`
- `0x164870`
- `0x233530`

## string_xrefs

- `0x15670c`: `AllowUpsideDown`

## pseudocode

```c

```

## disassembly

```asm
0x1566f0  newobj   instance void <>c__DisplayClass114_0::.ctor()
0x1566f5  stloc.0
0x1566f6  ldloc.0
0x1566f7  ldarg.1
0x1566f8  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel <>c__DisplayClass114_0::customLabel
0x1566fd  ldarg.0
0x1566fe  ldloc.0
0x1566ff  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel <>c__DisplayClass114_0::customLabel
0x156704  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::get_AllowUpsideDown()
0x156709  ldc.i4.s 0xE
0x15670b  ldarg.2
0x15670c  ldstr    aAllowupsidedow// "AllowUpsideDown"
0x156711  ldloca.s 1
0x156713  call     instance bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateSimpleExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, [out] valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result)
0x156718  brtrue.s loc_156744
0x15671a  ldarg.0
0x15671b  ldloc.0
0x15671c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel <>c__DisplayClass114_0::customLabel
0x156721  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::get_AllowUpsideDown()
0x156726  ldloca.s 1
0x156728  ldloc.0
0x156729  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel <>c__DisplayClass114_0::customLabel
0x15672e  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.CustomLabelExprHost Microsoft.ReportingServices.ReportIntermediateFormat.CustomLabel::get_ExprHost()
0x156733  ldloc.0
0x156734  ldftn    instance object <>c__DisplayClass114_0::<EvaluateCustomLabelAllowUpsideDownExpression>b__0()
0x15673a  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x15673f  call     instance void Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateComplexExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy exprHost, class [mscorlib]System.Func`1<object> expressionExecution)
0x156744  ldarg.0
0x156745  ldloc.1
0x156746  call     instance valuetype Microsoft.ReportingServices.RdlExpressions.BooleanResult Microsoft.ReportingServices.RdlExpressions.ReportRuntime::ProcessBooleanResult(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult result)
0x15674b  ldfld    bool Microsoft.ReportingServices.RdlExpressions.BooleanResult::Value
0x156750  ret
```
