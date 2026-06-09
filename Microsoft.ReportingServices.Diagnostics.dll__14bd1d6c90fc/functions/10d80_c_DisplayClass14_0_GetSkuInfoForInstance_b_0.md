# <>c__DisplayClass14_0::<GetSkuInfoForInstance>b__0

- ea: `0x10d80`
- end: `0x10e34`
- name: `<>c__DisplayClass14_0::<GetSkuInfoForInstance>b__0`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x10d80`

## string_xrefs

- `0x10e1a`: `Evaluation copy: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x10d80  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ResourceUtilTrace()
0x10d85  stloc.0
0x10d86  newobj   instance void [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::.ctor()
0x10d8b  ldarg.0
0x10d8c  ldfld    string <>c__DisplayClass14_0::instanceId
0x10d91  callvirt instance class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::Load(string)
0x10d96  stloc.1
0x10d97  ldarg.0
0x10d98  ldloc.1
0x10d99  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_SkuType()
0x10d9e  stfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType <>c__DisplayClass14_0::skuType
0x10da3  ldarg.0
0x10da4  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType <>c__DisplayClass14_0::skuType
0x10da9  brtrue.s loc_10DB6
0x10dab  ldstr    aUnexpectedSkuV// "unexpected SKU value"
0x10db0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x10db5  throw
0x10db6  ldloc.0
0x10db7  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x10dbc  brfalse.s loc_10DE3
0x10dbe  ldloc.0
0x10dbf  ldc.i4.3
0x10dc0  ldstr    aSku0// "SKU: {0}"
0x10dc5  ldc.i4.1
0x10dc6  newarr   [mscorlib]System.Object
0x10dcb  dup
0x10dcc  ldc.i4.0
0x10dcd  ldloc.1
0x10dce  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_SkuType()
0x10dd3  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetStrings(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x10dd8  ldfld    string [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings::FullName
0x10ddd  stelem.ref
0x10dde  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x10de3  ldloc.1
0x10de4  callvirt instance class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuTimebomb [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_Timebomb()
0x10de9  callvirt instance bool [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuTimebomb::HasExpired()
0x10dee  brfalse.s loc_10E06
0x10df0  ldsfld   bool Microsoft.ReportingServices.Diagnostics.Sku::IgnoreExpirationCheck
0x10df5  brfalse.s loc_10E00
0x10df7  ldarg.0
0x10df8  ldc.i4.1
0x10df9  stfld    bool <>c__DisplayClass14_0::isExpired
0x10dfe  br.s     loc_10E06
0x10e00  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.EvaluationCopyExpiredException::.ctor()
0x10e05  throw
0x10e06  ldarg.0
0x10e07  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType <>c__DisplayClass14_0::skuType
0x10e0c  ldc.i4.s 0x14
0x10e0e  bne.un.s loc_10E33
0x10e10  ldloc.0
0x10e11  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x10e16  brfalse.s loc_10E33
0x10e18  ldloc.0
0x10e19  ldc.i4.3
0x10e1a  ldstr    aEvaluationCopy// "Evaluation copy: {0}."
0x10e1f  ldc.i4.1
0x10e20  newarr   [mscorlib]System.Object
0x10e25  dup
0x10e26  ldc.i4.0
0x10e27  ldloc.1
0x10e28  callvirt instance class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuTimebomb [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_Timebomb()
0x10e2d  stelem.ref
0x10e2e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x10e33  ret
```
