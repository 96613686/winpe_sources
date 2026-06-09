# Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateChartDataLabelPosition

- ea: `0x29a80`
- end: `0x29b48`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateChartDataLabelPosition`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5a8d0`
- `0x105a80`

## callees

- `0x29a80`
- `0xb9aa0`
- `0x17c2a0`

## string_xrefs

- `0x29b1e`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0x29a80  ldarg.0
0x29a81  brfalse  loc_29B46
0x29a86  ldarg.0
0x29a87  ldstr    aAuto// "Auto"
0x29a8c  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29a91  brfalse.s loc_29A95
0x29a93  ldc.i4.0
0x29a94  ret
0x29a95  ldarg.0
0x29a96  ldstr    aTop// "Top"
0x29a9b  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29aa0  brfalse.s loc_29AA4
0x29aa2  ldc.i4.1
0x29aa3  ret
0x29aa4  ldarg.0
0x29aa5  ldstr    aTopleft// "TopLeft"
0x29aaa  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29aaf  brfalse.s loc_29AB3
0x29ab1  ldc.i4.2
0x29ab2  ret
0x29ab3  ldarg.0
0x29ab4  ldstr    aTopright// "TopRight"
0x29ab9  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29abe  brfalse.s loc_29AC2
0x29ac0  ldc.i4.3
0x29ac1  ret
0x29ac2  ldarg.0
0x29ac3  ldstr    aLeft// "Left"
0x29ac8  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29acd  brfalse.s loc_29AD1
0x29acf  ldc.i4.4
0x29ad0  ret
0x29ad1  ldarg.0
0x29ad2  ldstr    aCenter// "Center"
0x29ad7  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29adc  brfalse.s loc_29AE0
0x29ade  ldc.i4.5
0x29adf  ret
0x29ae0  ldarg.0
0x29ae1  ldstr    aRight// "Right"
0x29ae6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29aeb  brfalse.s loc_29AEF
0x29aed  ldc.i4.6
0x29aee  ret
0x29aef  ldarg.0
0x29af0  ldstr    aBottomright// "BottomRight"
0x29af5  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29afa  brfalse.s loc_29AFE
0x29afc  ldc.i4.7
0x29afd  ret
0x29afe  ldarg.0
0x29aff  ldstr    aBottomleft// "BottomLeft"
0x29b04  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29b09  brfalse.s loc_29B0E
0x29b0b  ldc.i4.s 9
0x29b0d  ret
0x29b0e  ldarg.0
0x29b0f  ldstr    aBottom// "Bottom"
0x29b14  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29b19  brfalse.s loc_29B1D
0x29b1b  ldc.i4.8
0x29b1c  ret
0x29b1d  ldarg.0
0x29b1e  ldstr    aOutside// "Outside"
0x29b23  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x29b28  brfalse.s loc_29B2D
0x29b2a  ldc.i4.s 0xA
0x29b2c  ret
0x29b2d  ldarg.1
0x29b2e  brfalse.s loc_29B46
0x29b30  ldarg.1
0x29b31  ldc.i4   0x19F
0x29b36  ldc.i4.1
0x29b37  ldc.i4.1
0x29b38  newarr   [mscorlib]System.String
0x29b3d  dup
0x29b3e  ldc.i4.0
0x29b3f  ldarg.0
0x29b40  stelem.ref
0x29b41  callvirt instance void Microsoft.ReportingServices.ReportProcessing.IErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string[] arguments)
0x29b46  ldc.i4.0
0x29b47  ret
```
