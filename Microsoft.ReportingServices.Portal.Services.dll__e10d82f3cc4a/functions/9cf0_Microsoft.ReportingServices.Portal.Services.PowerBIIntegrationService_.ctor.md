# Microsoft.ReportingServices.Portal.Services.PowerBIIntegrationService::.ctor

- ea: `0x9cf0`
- end: `0x9d09`
- name: `Microsoft.ReportingServices.Portal.Services.PowerBIIntegrationService::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9cf1`: `AADAuthToken`

## pseudocode

```c

```

## disassembly

```asm
0x9cf0  ldarg.0
0x9cf1  ldstr    aAadauthtoken// "AADAuthToken"
0x9cf6  stfld    string Microsoft.ReportingServices.Portal.Services.PowerBIIntegrationService::aadAuthToken
0x9cfb  ldarg.0
0x9cfc  call     instance void [mscorlib]System.Object::.ctor()
0x9d01  ldarg.0
0x9d02  ldarg.1
0x9d03  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Services.PowerBIIntegrationService::logger
0x9d08  ret
```
