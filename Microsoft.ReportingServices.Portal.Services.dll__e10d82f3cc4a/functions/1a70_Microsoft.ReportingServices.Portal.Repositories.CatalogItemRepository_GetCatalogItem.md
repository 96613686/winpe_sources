# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem

- ea: `0x1a70`
- end: `0x1a89`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem`
- size: `25`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x6240`
- `0x1d110`
- `0x1d560`
- `0x1e6d0`

## callees

- `0x1a00`
- `0x1ab0`
- `0x9e80`

## pseudocode

```c

```

## disassembly

```asm
0x1a70  ldarg.1
0x1a71  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x1a76  stloc.0
0x1a77  ldloc.0
0x1a78  ldarg.2
0x1a79  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x1a7e  stloc.1
0x1a7f  ldarg.0
0x1a80  ldloc.0
0x1a81  ldarg.1
0x1a82  ldloc.1
0x1a83  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x1a88  ret
```
