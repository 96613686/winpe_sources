# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem_0

- ea: `0x1a90`
- end: `0x1aa1`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem_0`
- size: `17`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1980`
- `0x1c20`
- `0x2a20`
- `0x2ee0`
- `0x3000`
- `0x32c0`

## callees

- `0x1ab0`
- `0x9e80`

## pseudocode

```c

```

## disassembly

```asm
0x1a90  ldarg.1
0x1a91  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x1a96  stloc.0
0x1a97  ldarg.0
0x1a98  ldloc.0
0x1a99  ldarg.1
0x1a9a  ldarg.2
0x1a9b  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x1aa0  ret
```
