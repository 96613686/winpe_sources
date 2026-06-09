# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::IsRestrictedItemType

- ea: `0x4d80`
- end: `0x4d8d`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::IsRestrictedItemType`
- size: `13`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d0f0`
- `0x1d510`
- `0x1e390`
- `0x1e460`
- `0x1e4e0`

## callees

- `0x4d90`
- `0x10330`

## pseudocode

```c

```

## disassembly

```asm
0x4d80  ldarg.0
0x4d81  ldarg.1
0x4d82  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType Microsoft.ReportingServices.Portal.Services.ODataExtensions.CatalogItemTypeExtensions::ToCatalogItemType(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType itemType)
0x4d87  call     instance bool Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::IsRestrictedItemType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType type)
0x4d8c  ret
```
