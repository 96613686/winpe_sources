# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::set_Url

- ea: `0xec60`
- end: `0xec8e`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::set_Url`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xebd0`

## callees

- `0xec60`
- `0xef10`

## pseudocode

```c

```

## disassembly

```asm
0xec60  ldarg.0
0xec61  ldarg.0
0xec62  call     instance string [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::get_Url()
0xec67  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::IsLocalFileSystemWebService(string url)
0xec6c  brfalse.s loc_EC86
0xec6e  ldarg.0
0xec6f  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::useDefaultCredentialsSetExplicitly
0xec74  brtrue.s loc_EC86
0xec76  ldarg.0
0xec77  ldarg.1
0xec78  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::IsLocalFileSystemWebService(string url)
0xec7d  brtrue.s loc_EC86
0xec7f  ldarg.0
0xec80  ldc.i4.0
0xec81  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_UseDefaultCredentials(bool)
0xec86  ldarg.0
0xec87  ldarg.1
0xec88  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0xec8d  ret
```
