# Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateMapDockableSubItemDockOutsideViewportExpression

- ea: `0x158210`
- end: `0x158271`
- name: `Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateMapDockableSubItemDockOutsideViewportExpression`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xdf3b0`

## callees

- `0xdeed0`
- `0xdef30`
- `0x158210`
- `0x163f10`
- `0x164200`
- `0x164870`
- `0x234630`

## string_xrefs

- `0x15822c`: `DockOutsideViewport`

## pseudocode

```c

```

## disassembly

```asm
0x158210  newobj   instance void <>c__DisplayClass176_0::.ctor()
0x158215  stloc.0
0x158216  ldloc.0
0x158217  ldarg.1
0x158218  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem <>c__DisplayClass176_0::mapDockableSubItem
0x15821d  ldarg.0
0x15821e  ldloc.0
0x15821f  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem <>c__DisplayClass176_0::mapDockableSubItem
0x158224  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::get_DockOutsideViewport()
0x158229  ldc.i4.s 0x23
0x15822b  ldarg.2
0x15822c  ldstr    aDockoutsidevie// "DockOutsideViewport"
0x158231  ldloca.s 1
0x158233  call     instance bool Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateSimpleExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, [out] valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result)
0x158238  brtrue.s loc_158264
0x15823a  ldarg.0
0x15823b  ldloc.0
0x15823c  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem <>c__DisplayClass176_0::mapDockableSubItem
0x158241  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::get_DockOutsideViewport()
0x158246  ldloca.s 1
0x158248  ldloc.0
0x158249  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem <>c__DisplayClass176_0::mapDockableSubItem
0x15824e  callvirt instance class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.MapDockableSubItemExprHost Microsoft.ReportingServices.ReportIntermediateFormat.MapDockableSubItem::get_ExprHost()
0x158253  ldloc.0
0x158254  ldftn    instance object <>c__DisplayClass176_0::<EvaluateMapDockableSubItemDockOutsideViewportExpression>b__0()
0x15825a  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x15825f  call     instance void Microsoft.ReportingServices.RdlExpressions.ReportRuntime::EvaluateComplexExpression(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expression, valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult& result, class [Microsoft.ReportingServices.ProcessingObjectModel]Microsoft.ReportingServices.RdlExpressions.ExpressionHostObjectModel.ReportObjectModelProxy exprHost, class [mscorlib]System.Func`1<object> expressionExecution)
0x158264  ldarg.0
0x158265  ldloc.1
0x158266  call     instance valuetype Microsoft.ReportingServices.RdlExpressions.BooleanResult Microsoft.ReportingServices.RdlExpressions.ReportRuntime::ProcessBooleanResult(valuetype Microsoft.ReportingServices.RdlExpressions.VariantResult result)
0x15826b  ldfld    bool Microsoft.ReportingServices.RdlExpressions.BooleanResult::Value
0x158270  ret
```
