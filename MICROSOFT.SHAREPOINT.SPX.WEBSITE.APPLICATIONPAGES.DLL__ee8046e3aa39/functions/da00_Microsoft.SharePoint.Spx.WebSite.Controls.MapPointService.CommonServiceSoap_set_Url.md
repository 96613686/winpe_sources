# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::set_Url

- ea: `0xda00`
- end: `0xda2e`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::set_Url`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd970`

## callees

- `0xda00`
- `0xdff0`

## pseudocode

```c

```

## disassembly

```asm
0xda00  ldarg.0
0xda01  ldarg.0
0xda02  call     instance string [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::get_Url()
0xda07  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::IsLocalFileSystemWebService(string url)
0xda0c  brfalse.s loc_DA26
0xda0e  ldarg.0
0xda0f  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::useDefaultCredentialsSetExplicitly
0xda14  brtrue.s loc_DA26
0xda16  ldarg.0
0xda17  ldarg.1
0xda18  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::IsLocalFileSystemWebService(string url)
0xda1d  brtrue.s loc_DA26
0xda1f  ldarg.0
0xda20  ldc.i4.0
0xda21  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_UseDefaultCredentials(bool)
0xda26  ldarg.0
0xda27  ldarg.1
0xda28  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0xda2d  ret
```
