# Microsoft.BIServer.Configuration.RsService::Stop

- ea: `0x3360`
- end: `0x338c`
- name: `Microsoft.BIServer.Configuration.RsService::Stop`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3360`
- `0x3390`
- `0x34b0`

## string_xrefs

- `0x3376`: `Report server not responding to shutdown commands. Forcing an end to the report server service.`

## pseudocode

```c

```

## disassembly

```asm
0x3360  ldarg.0
0x3361  ldc.r8   180.0
0x336a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x336f  call     instance bool Microsoft.BIServer.Configuration.RsService::AskReportServerToShutDown(valuetype [mscorlib]System.TimeSpan timeout)
0x3374  brtrue.s loc_338B
0x3376  ldstr    aReportServerNo// "Report server not responding to shutdow"...
0x337b  call     T0x2B000015
0x3380  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x3385  ldarg.0
0x3386  call     instance void Microsoft.BIServer.Configuration.RsService::ForcibleShutdownReportServer()
0x338b  ret
```
