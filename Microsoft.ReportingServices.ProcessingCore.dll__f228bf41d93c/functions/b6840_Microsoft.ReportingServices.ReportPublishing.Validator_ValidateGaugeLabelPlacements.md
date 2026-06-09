# Microsoft.ReportingServices.ReportPublishing.Validator::ValidateGaugeLabelPlacements

- ea: `0xb6840`
- end: `0xb6874`
- name: `Microsoft.ReportingServices.ReportPublishing.Validator::ValidateGaugeLabelPlacements`
- size: `52`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x90070`
- `0x904c0`
- `0x90850`
- `0x93920`
- `0x952c0`
- `0x95650`

## callees

- `0xb6840`
- `0xb9aa0`
- `0xb9b10`

## string_xrefs

- `0xb6841`: `Inside`
- `0xb684e`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0xb6840  ldarg.0
0xb6841  ldstr    aInside// "Inside"
0xb6846  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb684b  brtrue.s loc_B6867
0xb684d  ldarg.0
0xb684e  ldstr    aOutside// "Outside"
0xb6853  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6858  brtrue.s loc_B6867
0xb685a  ldarg.0
0xb685b  ldstr    aCross// "Cross"
0xb6860  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0xb6865  brfalse.s loc_B6869
0xb6867  ldc.i4.1
0xb6868  ret
0xb6869  ldarg.0
0xb686a  ldarg.1
0xb686b  ldarg.2
0xb686c  ldarg.3
0xb686d  call     void Microsoft.ReportingServices.ReportPublishing.Validator::RegisterInvalidEnumValueError(string val, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, string propertyName)
0xb6872  ldc.i4.0
0xb6873  ret
```
