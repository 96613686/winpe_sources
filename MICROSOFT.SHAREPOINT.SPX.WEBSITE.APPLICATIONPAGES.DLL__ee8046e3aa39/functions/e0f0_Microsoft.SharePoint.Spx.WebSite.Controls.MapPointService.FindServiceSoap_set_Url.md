# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::set_Url

- ea: `0xe0f0`
- end: `0xe11e`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::set_Url`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xe060`

## callees

- `0xe0f0`
- `0xeb80`

## pseudocode

```c

```

## disassembly

```asm
0xe0f0  ldarg.0
0xe0f1  ldarg.0
0xe0f2  call     instance string [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::get_Url()
0xe0f7  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::IsLocalFileSystemWebService(string url)
0xe0fc  brfalse.s loc_E116
0xe0fe  ldarg.0
0xe0ff  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::useDefaultCredentialsSetExplicitly
0xe104  brtrue.s loc_E116
0xe106  ldarg.0
0xe107  ldarg.1
0xe108  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::IsLocalFileSystemWebService(string url)
0xe10d  brtrue.s loc_E116
0xe10f  ldarg.0
0xe110  ldc.i4.0
0xe111  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_UseDefaultCredentials(bool)
0xe116  ldarg.0
0xe117  ldarg.1
0xe118  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0xe11d  ret
```
