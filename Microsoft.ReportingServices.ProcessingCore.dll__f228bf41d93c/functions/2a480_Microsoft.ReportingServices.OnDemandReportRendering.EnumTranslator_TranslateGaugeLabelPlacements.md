# Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateGaugeLabelPlacements

- ea: `0x2a480`
- end: `0x2a4d0`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateGaugeLabelPlacements`
- size: `80`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x32f10`
- `0x34c40`
- `0x39400`
- `0x3a540`
- `0xc6f20`
- `0xc8a80`
- `0xd0850`
- `0xd18b0`

## callees

- `0x2a480`
- `0xb9aa0`
- `0x17c2a0`

## string_xrefs

- `0x2a486`: `Inside`
- `0x2a495`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0x2a480  ldarg.0
0x2a481  brtrue.s loc_2A485
0x2a483  ldc.i4.0
0x2a484  ret
0x2a485  ldarg.0
0x2a486  ldstr    aInside// "Inside"
0x2a48b  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2a490  brfalse.s loc_2A494
0x2a492  ldc.i4.0
0x2a493  ret
0x2a494  ldarg.0
0x2a495  ldstr    aOutside// "Outside"
0x2a49a  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2a49f  brfalse.s loc_2A4A3
0x2a4a1  ldc.i4.1
0x2a4a2  ret
0x2a4a3  ldarg.0
0x2a4a4  ldstr    aCross// "Cross"
0x2a4a9  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2a4ae  brfalse.s loc_2A4B2
0x2a4b0  ldc.i4.2
0x2a4b1  ret
0x2a4b2  ldarg.1
0x2a4b3  brfalse.s loc_2A4CE
0x2a4b5  ldarg.1
0x2a4b6  brfalse.s loc_2A4CE
0x2a4b8  ldarg.1
0x2a4b9  ldc.i4   0x19F
0x2a4be  ldc.i4.1
0x2a4bf  ldc.i4.1
0x2a4c0  newarr   [mscorlib]System.String
0x2a4c5  dup
0x2a4c6  ldc.i4.0
0x2a4c7  ldarg.0
0x2a4c8  stelem.ref
0x2a4c9  callvirt instance void Microsoft.ReportingServices.ReportProcessing.IErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string[] arguments)
0x2a4ce  ldc.i4.0
0x2a4cf  ret
```
