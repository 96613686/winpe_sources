# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::.ctor

- ea: `0xe060`
- end: `0xe096`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::.ctor`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xcb80`

## callees

- `0xe060`
- `0xe0e0`
- `0xe0f0`
- `0xe130`
- `0xeb80`

## string_xrefs

- `0xe067`: `http://findv3.mappoint.net/Find-30/FindService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0xe060  ldarg.0
0xe061  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::.ctor()
0xe066  ldarg.0
0xe067  ldstr    aHttpFindv3Mapp// "http://findv3.mappoint.net/Find-30/Find"...
0xe06c  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::set_Url(string value)
0xe071  ldarg.0
0xe072  ldarg.0
0xe073  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::get_Url()
0xe078  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::IsLocalFileSystemWebService(string url)
0xe07d  brfalse.s loc_E08E
0xe07f  ldarg.0
0xe080  ldc.i4.1
0xe081  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::set_UseDefaultCredentials(bool value)
0xe086  ldarg.0
0xe087  ldc.i4.0
0xe088  stfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::useDefaultCredentialsSetExplicitly
0xe08d  ret
0xe08e  ldarg.0
0xe08f  ldc.i4.1
0xe090  stfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.FindServiceSoap::useDefaultCredentialsSetExplicitly
0xe095  ret
```
