# Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartTickMarksType

- ea: `0xb8350`
- end: `0xb8391`
- name: `Microsoft.ReportingServices.ReportPublishing.Validator::ValidateChartTickMarksType`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xa22b0`

## callees

- `0xb8350`
- `0xb9aa0`
- `0xb9b10`

## string_xrefs

- `0xb835e`: `Inside`
- `0xb836b`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0xb8350  ldarg.0
0xb8351  ldstr    aNone// "None"
0xb8356  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb835b  brtrue.s loc_B8384
0xb835d  ldarg.0
0xb835e  ldstr    aInside// "Inside"
0xb8363  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb8368  brtrue.s loc_B8384
0xb836a  ldarg.0
0xb836b  ldstr    aOutside// "Outside"
0xb8370  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb8375  brtrue.s loc_B8384
0xb8377  ldarg.0
0xb8378  ldstr    aCross// "Cross"
0xb837d  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb8382  brfalse.s loc_B8386
0xb8384  ldc.i4.1
0xb8385  ret
0xb8386  ldarg.0
0xb8387  ldarg.1
0xb8388  ldarg.2
0xb8389  ldarg.3
0xb838a  call     void Microsoft.ReportingServices.ReportPublishing.Validator::RegisterInvalidEnumValueError(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xb838f  ldc.i4.0
0xb8390  ret
```
