# Microsoft.ReportingServices.ReportPublishing.Validator::ValidateGaugePointerPlacements

- ea: `0xb6950`
- end: `0xb6984`
- name: `Microsoft.ReportingServices.ReportPublishing.Validator::ValidateGaugePointerPlacements`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x91f00`
- `0x94430`

## callees

- `0xb6950`
- `0xb9aa0`
- `0xb9b10`

## string_xrefs

- `0xb696b`: `Inside`
- `0xb695e`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0xb6950  ldarg.0
0xb6951  ldstr    aCross// "Cross"
0xb6956  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb695b  brtrue.s loc_B6977
0xb695d  ldarg.0
0xb695e  ldstr    aOutside// "Outside"
0xb6963  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6968  brtrue.s loc_B6977
0xb696a  ldarg.0
0xb696b  ldstr    aInside// "Inside"
0xb6970  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6975  brfalse.s loc_B6979
0xb6977  ldc.i4.1
0xb6978  ret
0xb6979  ldarg.0
0xb697a  ldarg.1
0xb697b  ldarg.2
0xb697c  ldarg.3
0xb697d  call     void Microsoft.ReportingServices.ReportPublishing.Validator::RegisterInvalidEnumValueError(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xb6982  ldc.i4.0
0xb6983  ret
```
