# Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetCountryRegionInfo

- ea: `0xdce0`
- end: `0xdd01`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CommonServiceSoap::GetCountryRegionInfo`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xcc40`
- `0xcdc0`
- `0xd4a0`

## pseudocode

```c

```

## disassembly

```asm
0xdce0  ldarg.0
0xdce1  ldstr    aGetcountryregi// "GetCountryRegionInfo"
0xdce6  ldc.i4.1
0xdce7  newarr   [mscorlib]System.Object
0xdcec  stloc.1
0xdced  ldloc.1
0xdcee  ldc.i4.0
0xdcef  ldarg.1
0xdcf0  stelem.ref
0xdcf1  ldloc.1
0xdcf2  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0xdcf7  stloc.0
0xdcf8  ldloc.0
0xdcf9  ldc.i4.0
0xdcfa  ldelem.ref
0xdcfb  castclass class Microsoft.SharePoint.Spx.WebSite.Controls.MapPointService.CountryRegionInfo[]
0xdd00  ret
```
