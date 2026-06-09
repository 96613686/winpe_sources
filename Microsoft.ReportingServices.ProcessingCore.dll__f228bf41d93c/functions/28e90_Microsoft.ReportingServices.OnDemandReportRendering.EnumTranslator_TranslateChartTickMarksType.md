# Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateChartTickMarksType

- ea: `0x28e90`
- end: `0x28eea`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateChartTickMarksType`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5f290`
- `0x1080e0`

## callees

- `0x28e90`
- `0xb9aa0`
- `0x17c2a0`

## string_xrefs

- `0x28ea3`: `Inside`
- `0x28eb2`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0x28e90  ldarg.0
0x28e91  brfalse.s loc_28EE8
0x28e93  ldarg.0
0x28e94  ldstr    aNone// "None"
0x28e99  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x28e9e  brfalse.s loc_28EA2
0x28ea0  ldc.i4.0
0x28ea1  ret
0x28ea2  ldarg.0
0x28ea3  ldstr    aInside// "Inside"
0x28ea8  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x28ead  brfalse.s loc_28EB1
0x28eaf  ldc.i4.1
0x28eb0  ret
0x28eb1  ldarg.0
0x28eb2  ldstr    aOutside// "Outside"
0x28eb7  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x28ebc  brfalse.s loc_28EC0
0x28ebe  ldc.i4.2
0x28ebf  ret
0x28ec0  ldarg.0
0x28ec1  ldstr    aCross// "Cross"
0x28ec6  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x28ecb  brfalse.s loc_28ECF
0x28ecd  ldc.i4.3
0x28ece  ret
0x28ecf  ldarg.1
0x28ed0  brfalse.s loc_28EE8
0x28ed2  ldarg.1
0x28ed3  ldc.i4   0x19F
0x28ed8  ldc.i4.1
0x28ed9  ldc.i4.1
0x28eda  newarr   [mscorlib]System.String
0x28edf  dup
0x28ee0  ldc.i4.0
0x28ee1  ldarg.0
0x28ee2  stelem.ref
0x28ee3  callvirt instance void Microsoft.ReportingServices.ReportProcessing.IErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string[] arguments)
0x28ee8  ldc.i4.0
0x28ee9  ret
```
