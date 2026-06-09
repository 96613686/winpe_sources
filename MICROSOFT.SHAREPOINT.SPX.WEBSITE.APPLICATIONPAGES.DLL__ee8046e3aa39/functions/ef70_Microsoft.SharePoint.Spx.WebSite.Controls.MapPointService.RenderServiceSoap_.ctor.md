# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::.ctor

- ea: `0xef70`
- end: `0xefa6`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::.ctor`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xcbe0`

## callees

- `0xef70`
- `0xeff0`
- `0xf000`
- `0xf040`
- `0xf660`

## string_xrefs

- `0xef77`: `http://renderv3.mappoint.net/Render-30/RenderService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0xef70  ldarg.0
0xef71  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::.ctor()
0xef76  ldarg.0
0xef77  ldstr    aHttpRenderv3Ma// "http://renderv3.mappoint.net/Render-30/"...
0xef7c  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::set_Url(string value)
0xef81  ldarg.0
0xef82  ldarg.0
0xef83  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::get_Url()
0xef88  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::IsLocalFileSystemWebService(string url)
0xef8d  brfalse.s loc_EF9E
0xef8f  ldarg.0
0xef90  ldc.i4.1
0xef91  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::set_UseDefaultCredentials(bool value)
0xef96  ldarg.0
0xef97  ldc.i4.0
0xef98  stfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::useDefaultCredentialsSetExplicitly
0xef9d  ret
0xef9e  ldarg.0
0xef9f  ldc.i4.1
0xefa0  stfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RenderServiceSoap::useDefaultCredentialsSetExplicitly
0xefa5  ret
```
