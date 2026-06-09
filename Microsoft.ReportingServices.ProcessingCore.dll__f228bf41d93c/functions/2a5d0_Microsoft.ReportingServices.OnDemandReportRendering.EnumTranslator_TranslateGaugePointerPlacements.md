# Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateGaugePointerPlacements

- ea: `0x2a5d0`
- end: `0x2a620`
- name: `Microsoft.ReportingServices.OnDemandReportRendering.EnumTranslator::TranslateGaugePointerPlacements`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x37720`
- `0xccff0`

## callees

- `0x2a5d0`
- `0xb9aa0`
- `0x17c2a0`

## string_xrefs

- `0x2a5f4`: `Inside`
- `0x2a5e5`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0x2a5d0  ldarg.0
0x2a5d1  brtrue.s loc_2A5D5
0x2a5d3  ldc.i4.0
0x2a5d4  ret
0x2a5d5  ldarg.0
0x2a5d6  ldstr    aCross// "Cross"
0x2a5db  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2a5e0  brfalse.s loc_2A5E4
0x2a5e2  ldc.i4.0
0x2a5e3  ret
0x2a5e4  ldarg.0
0x2a5e5  ldstr    aOutside// "Outside"
0x2a5ea  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2a5ef  brfalse.s loc_2A5F3
0x2a5f1  ldc.i4.1
0x2a5f2  ret
0x2a5f3  ldarg.0
0x2a5f4  ldstr    aInside// "Inside"
0x2a5f9  call     bool Microsoft.ReportingServices.ReportPublishing.Validator::CompareWithInvariantCulture(string strOne, string strTwo)
0x2a5fe  brfalse.s loc_2A602
0x2a600  ldc.i4.2
0x2a601  ret
0x2a602  ldarg.1
0x2a603  brfalse.s loc_2A61E
0x2a605  ldarg.1
0x2a606  brfalse.s loc_2A61E
0x2a608  ldarg.1
0x2a609  ldc.i4   0x19F
0x2a60e  ldc.i4.1
0x2a60f  ldc.i4.1
0x2a610  newarr   [mscorlib]System.String
0x2a615  dup
0x2a616  ldc.i4.0
0x2a617  ldarg.0
0x2a618  stelem.ref
0x2a619  callvirt instance void Microsoft.ReportingServices.ReportProcessing.IErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, string[] arguments)
0x2a61e  ldc.i4.0
0x2a61f  ret
```
