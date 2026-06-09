# Microsoft.BIServer.RSHostingService.RsTraceConfig::ValidateTraceConfigFileExists

- ea: `0x330`
- end: `0x358`
- name: `Microsoft.BIServer.RSHostingService.RsTraceConfig::ValidateTraceConfigFileExists`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1030`
- `0x12b0`
- `0x2430`

## callees

- `0x330`

## string_xrefs

- `0x330`: `..\ReportServer\bin\ReportingServicesService.exe.config`
- `0x34b`: `..\ReportServer\bin\ReportingServicesService.exe.config`
- `0x33e`: `Cannot locate trace config filename: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x330  ldstr    aReportserverBi// "..\\ReportServer\\bin\\ReportingService"...
0x335  call     bool [mscorlib]System.IO.File::Exists(string)
0x33a  stloc.0
0x33b  ldloc.0
0x33c  brtrue.s loc_356
0x33e  ldstr    aCannotLocateTr// "Cannot locate trace config filename: {0"...
0x343  ldc.i4.1
0x344  newarr   [mscorlib]System.Object
0x349  dup
0x34a  ldc.i4.0
0x34b  ldstr    aReportserverBi// "..\\ReportServer\\bin\\ReportingService"...
0x350  stelem.ref
0x351  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x356  ldloc.0
0x357  ret
```
