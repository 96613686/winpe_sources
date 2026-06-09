# Microsoft.ReportingServices.Diagnostics.SkuResources::RestrictedFeatureName

- ea: `0xcef0`
- end: `0xd036`
- name: `Microsoft.ReportingServices.Diagnostics.SkuResources::RestrictedFeatureName`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xced0`
- `0xcee0`

## callees

- `0xcef0`

## pseudocode

```c

```

## disassembly

```asm
0xcef0  ldarg.0
0xcef1  switch   loc_CF77, loc_CF7D, loc_CF83, loc_CF89, loc_CF8F, loc_CF95, loc_CF9B, loc_CFA1, loc_CFA7, loc_CFAD, loc_CFB3, loc_CFB9, loc_CFBF, loc_CFC5, loc_CFCB, loc_CFD1, loc_CFD7, loc_CFDD, loc_CFE3, loc_CFE9, loc_CFEF, loc_CFF5, loc_CFFB, loc_D001, loc_D007, loc_D00D, loc_D019, loc_D019, loc_D019, loc_D019, loc_D013
0xcf72  br       loc_D019
0xcf77  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuNonSqlDataSources()
0xcf7c  ret
0xcf7d  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuOtherSkuDatasources()
0xcf82  ret
0xcf83  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuRemoteDataSources()
0xcf88  ret
0xcf89  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuCaching()
0xcf8e  ret
0xcf8f  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuExecutionSnapshots()
0xcf94  ret
0xcf95  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuHistory()
0xcf9a  ret
0xcf9b  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuDelivery()
0xcfa0  ret
0xcfa1  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuScheduling()
0xcfa6  ret
0xcfa7  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuExtensibility()
0xcfac  ret
0xcfad  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuCustomAuth()
0xcfb2  ret
0xcfb3  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuSharepoint()
0xcfb8  ret
0xcfb9  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuScaleOut()
0xcfbe  ret
0xcfbf  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuSubscriptions()
0xcfc4  ret
0xcfc5  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuDataDrivenSubscriptions()
0xcfca  ret
0xcfcb  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuCustomRolesSecurity()
0xcfd0  ret
0xcfd1  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuReportBuilder()
0xcfd6  ret
0xcfd7  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuModelItemSecurity()
0xcfdc  ret
0xcfdd  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuDynamicDrillthrough()
0xcfe2  ret
0xcfe3  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuNoCpuThrottling()
0xcfe8  ret
0xcfe9  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuNoMemoryThrottling()
0xcfee  ret
0xcfef  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuEventGeneration()
0xcff4  ret
0xcff5  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuComponentLibrary()
0xcffa  ret
0xcffb  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuSharedDataset()
0xd000  ret
0xd001  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuDataAlerting()
0xd006  ret
0xd007  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuCrescent()
0xd00c  ret
0xd00d  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuKpiItems()
0xd012  ret
0xd013  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_SkuCommentAlerting()
0xd018  ret
0xd019  ldstr    aUnexpectedFeat_0// "Unexpected feature"
0xd01e  ldarga.s 0
0xd020  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures
0xd026  callvirt instance string [mscorlib]System.Object::ToString()
0xd02b  call     string [mscorlib]System.String::Concat(string, string)
0xd030  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0xd035  throw
```
