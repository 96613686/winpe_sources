# Microsoft.ReportingServices.Diagnostics.Globals::get_CanTranslateIncomingHttpRequest

- ea: `0xab10`
- end: `0xab3a`
- name: `Microsoft.ReportingServices.Diagnostics.Globals::get_CanTranslateIncomingHttpRequest`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x6c30`

## callees

- `0x6c10`
- `0xa930`
- `0xa950`
- `0xa960`
- `0xab10`

## pseudocode

```c

```

## disassembly

```asm
0xab10  ldc.i4.0
0xab11  stloc.0
0xab12  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0xab17  ldc.i4.1
0xab18  bne.un.s loc_AB2C
0xab1a  call     bool Microsoft.ReportingServices.Diagnostics.Globals::get_IsConfigurationInitialized()
0xab1f  brfalse.s loc_AB2C
0xab21  call     class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0xab26  callvirt instance bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_CanTranslateReportServerRequest()
0xab2b  stloc.0
0xab2c  ldloc.0
0xab2d  brfalse.s loc_AB38
0xab2f  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xab34  ldnull
0xab35  cgt.un
0xab37  ret
0xab38  ldc.i4.0
0xab39  ret
```
