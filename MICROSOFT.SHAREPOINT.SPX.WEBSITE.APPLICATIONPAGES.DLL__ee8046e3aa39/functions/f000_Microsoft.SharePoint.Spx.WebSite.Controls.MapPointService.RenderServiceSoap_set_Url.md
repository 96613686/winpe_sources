# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::set_Url

- ea: `0xf000`
- end: `0xf02e`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::set_Url`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xef70`

## callees

- `0xf000`
- `0xf660`

## pseudocode

```c

```

## disassembly

```asm
0xf000  ldarg.0
0xf001  ldarg.0
0xf002  call     instance string [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::get_Url()
0xf007  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::IsLocalFileSystemWebService(string url)
0xf00c  brfalse.s loc_F026
0xf00e  ldarg.0
0xf00f  ldfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::useDefaultCredentialsSetExplicitly
0xf014  brtrue.s loc_F026
0xf016  ldarg.0
0xf017  ldarg.1
0xf018  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::IsLocalFileSystemWebService(string url)
0xf01d  brtrue.s loc_F026
0xf01f  ldarg.0
0xf020  ldc.i4.0
0xf021  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_UseDefaultCredentials(bool)
0xf026  ldarg.0
0xf027  ldarg.1
0xf028  call     instance void [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::set_Url(string)
0xf02d  ret
```
