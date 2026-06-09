# Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::.ctor_0

- ea: `0x930`
- end: `0x93c`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::.ctor_0`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1b0`

## callees

- `0x920`

## pseudocode

```c

```

## disassembly

```asm
0x930  ldarg.0
0x931  newobj   instance void [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ConfigurationInfoDataAccessor::.ctor()
0x936  call     instance void Microsoft.BIServer.Management.WebApi.Controllers.ConfigController::.ctor(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.IConfigurationInfoDataAccessor dataAccessor)
0x93b  ret
```
