# Microsoft.ReportingServices.ReportPublishing.Validator::ValidateScaleRangePlacements

- ea: `0xb6b70`
- end: `0xb6ba4`
- name: `Microsoft.ReportingServices.ReportPublishing.Validator::ValidateScaleRangePlacements`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x95aa0`

## callees

- `0xb6b70`
- `0xb9aa0`
- `0xb9b10`

## string_xrefs

- `0xb6b71`: `Inside`
- `0xb6b7e`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0xb6b70  ldarg.0
0xb6b71  ldstr    aInside// "Inside"
0xb6b76  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6b7b  brtrue.s loc_B6B97
0xb6b7d  ldarg.0
0xb6b7e  ldstr    aOutside// "Outside"
0xb6b83  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6b88  brtrue.s loc_B6B97
0xb6b8a  ldarg.0
0xb6b8b  ldstr    aCross// "Cross"
0xb6b90  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6b95  brfalse.s loc_B6B99
0xb6b97  ldc.i4.1
0xb6b98  ret
0xb6b99  ldarg.0
0xb6b9a  ldarg.1
0xb6b9b  ldarg.2
0xb6b9c  ldarg.3
0xb6b9d  call     void Microsoft.ReportingServices.ReportPublishing.Validator::RegisterInvalidEnumValueError(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xb6ba2  ldc.i4.0
0xb6ba3  ret
```
