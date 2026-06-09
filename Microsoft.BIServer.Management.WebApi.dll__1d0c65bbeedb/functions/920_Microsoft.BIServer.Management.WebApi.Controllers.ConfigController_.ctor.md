# Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::.ctor

- ea: `0x920`
- end: `0x92e`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x930`

## callees

- `0x950`

## pseudocode

```c

```

## disassembly

```asm
0x920  ldarg.0
0x921  call     instance void [System.Web.Http]System.Web.Http.ApiController::.ctor()
0x926  ldarg.0
0x927  ldarg.1
0x928  call     instance void Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::set_DataAccessor(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.IConfigurationInfoDataAccessor value)
0x92d  ret
```
