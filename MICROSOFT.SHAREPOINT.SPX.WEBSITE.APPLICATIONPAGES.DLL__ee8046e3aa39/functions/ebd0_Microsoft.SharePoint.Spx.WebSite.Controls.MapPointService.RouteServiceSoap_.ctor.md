# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::.ctor

- ea: `0xebd0`
- end: `0xec06`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::.ctor`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0xebd0`
- `0xec50`
- `0xec60`
- `0xeca0`
- `0xef10`

## string_xrefs

- `0xebd7`: `http://routev3.mappoint.net/Route-30/RouteService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0xebd0  ldarg.0
0xebd1  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::.ctor()
0xebd6  ldarg.0
0xebd7  ldstr    aHttpRoutev3Map// "http://routev3.mappoint.net/Route-30/Ro"...
0xebdc  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::set_Url(string value)
0xebe1  ldarg.0
0xebe2  ldarg.0
0xebe3  call     instance string Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::get_Url()
0xebe8  call     instance bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::IsLocalFileSystemWebService(string url)
0xebed  brfalse.s loc_EBFE
0xebef  ldarg.0
0xebf0  ldc.i4.1
0xebf1  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::set_UseDefaultCredentials(bool value)
0xebf6  ldarg.0
0xebf7  ldc.i4.0
0xebf8  stfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::useDefaultCredentialsSetExplicitly
0xebfd  ret
0xebfe  ldarg.0
0xebff  ldc.i4.1
0xec00  stfld    bool Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.RouteServiceSoap::useDefaultCredentialsSetExplicitly
0xec05  ret
```
