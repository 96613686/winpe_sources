# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType_0

- ea: `0x4e00`
- end: `0x4e0e`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType_0`
- size: `14`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ab0`
- `0x4db0`
- `0x1cfa0`
- `0x1e600`

## callees

- `0x4e10`
- `0x10330`

## pseudocode

```c

```

## disassembly

```asm
0x4e00  ldarg.0
0x4e01  ldarg.1
0x4e02  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType Microsoft.ReportingServices.Portal.Services.ODataExtensions.CatalogItemTypeExtensions::ToCatalogItemType(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType itemType)
0x4e07  ldarg.2
0x4e08  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType type, string path)
0x4e0d  ret
```
