# Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateScaleRangePlacements

- ea: `0x2a890`
- end: `0x2a8e0`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateScaleRangePlacements`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x3b570`
- `0xd4890`

## callees

- `0x2a890`
- `0xb9aa0`
- `0x17c2a0`

## string_xrefs

- `0x2a896`: `Inside`
- `0x2a8a5`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0x2a890  ldarg.0
0x2a891  brtrue.s loc_2A895
0x2a893  ldc.i4.0
0x2a894  ret
0x2a895  ldarg.0
0x2a896  ldstr    aInside// "Inside"
0x2a89b  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2a8a0  brfalse.s loc_2A8A4
0x2a8a2  ldc.i4.0
0x2a8a3  ret
0x2a8a4  ldarg.0
0x2a8a5  ldstr    aOutside// "Outside"
0x2a8aa  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2a8af  brfalse.s loc_2A8B3
0x2a8b1  ldc.i4.1
0x2a8b2  ret
0x2a8b3  ldarg.0
0x2a8b4  ldstr    aCross// "Cross"
0x2a8b9  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2a8be  brfalse.s loc_2A8C2
0x2a8c0  ldc.i4.2
0x2a8c1  ret
0x2a8c2  ldarg.1
0x2a8c3  brfalse.s loc_2A8DE
0x2a8c5  ldarg.1
0x2a8c6  brfalse.s loc_2A8DE
0x2a8c8  ldarg.1
0x2a8c9  ldc.i4   0x19F
0x2a8ce  ldc.i4.1
0x2a8cf  ldc.i4.1
0x2a8d0  newarr   [mscorlib]System.String
0x2a8d5  dup
0x2a8d6  ldc.i4.0
0x2a8d7  ldarg.0
0x2a8d8  stelem.ref
0x2a8d9  callvirt instance void Microsoft.ReportingServices.ReportProcessing.IErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string[] arguments)
0x2a8de  ldc.i4.0
0x2a8df  ret
```
