# Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::.ctor

- ea: `0xde0`
- end: `0xe0c`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::.ctor`
- size: `44`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ab0`
- `0x1f30`
- `0x1ff0`
- `0x59a0`
- `0x5db0`
- `0x5ec0`

## pseudocode

```c

```

## disassembly

```asm
0xde0  ldarg.0
0xde1  call     instance void [mscorlib]System.Object::.ctor()
0xde6  ldarg.0
0xde7  ldarg.3
0xde8  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_logger
0xded  ldarg.0
0xdee  ldarg.1
0xdef  stfld    class [mscorlib]System.Security.Principal.IPrincipal Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_userPrincipal
0xdf4  ldarg.0
0xdf5  ldarg.2
0xdf6  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_catalogRepository
0xdfb  ldarg.0
0xdfc  ldarg.s  4
0xdfe  stfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_catalogAccessor
0xe03  ldarg.0
0xe04  ldarg.s  5
0xe06  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_systemService
0xe0b  ret
```
