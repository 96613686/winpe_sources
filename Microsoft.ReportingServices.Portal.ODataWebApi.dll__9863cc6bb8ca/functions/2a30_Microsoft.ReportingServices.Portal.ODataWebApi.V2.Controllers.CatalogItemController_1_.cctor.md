# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::.cctor

- ea: `0x2a30`
- end: `0x2a46`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::.cctor`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2a35`: `DeletePbixUploadTempFileDays`

## pseudocode

```c

```

## disassembly

```asm
0x2a30  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x2a35  ldstr    aDeletepbixuplo// "DeletePbixUploadTempFileDays"
0x2a3a  ldc.i4.1
0x2a3b  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x2a40  stsfld   int32 class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::DeleteTempFileDays
0x2a45  ret
```
