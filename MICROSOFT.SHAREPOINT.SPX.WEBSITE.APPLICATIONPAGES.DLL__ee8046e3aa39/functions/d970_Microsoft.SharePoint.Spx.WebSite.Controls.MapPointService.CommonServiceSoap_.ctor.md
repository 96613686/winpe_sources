# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::.ctor

- ea: `0xd970`
- end: `0xd9ab`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::.ctor`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xcc40`
- `0xcdc0`
- `0xd4a0`

## callees

- `0xd970`
- `0xd9f0`
- `0xda00`
- `0xda40`
- `0xdff0`

## string_xrefs

- `0xd977`: `MapServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0xd970  ldarg.0
0xd971  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::.ctor()
0xd976  ldarg.0
0xd977  ldstr    aMapserviceurl// "MapServiceUrl"
0xd97c  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0xd981  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::set_Url(string value)
0xd986  ldarg.0
0xd987  ldarg.0
0xd988  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::get_Url()
0xd98d  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::IsLocalFileSystemWebService(string url)
0xd992  brfalse.s loc_D9A3
0xd994  ldarg.0
0xd995  ldc.i4.1
0xd996  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::set_UseDefaultCredentials(bool value)
0xd99b  ldarg.0
0xd99c  ldc.i4.0
0xd99d  stfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::useDefaultCredentialsSetExplicitly
0xd9a2  ret
0xd9a3  ldarg.0
0xd9a4  ldc.i4.1
0xd9a5  stfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::useDefaultCredentialsSetExplicitly
0xd9aa  ret
```
