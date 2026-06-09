# Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::Create_0

- ea: `0xe20`
- end: `0xe3a`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::Create_0`
- size: `26`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ab0`
- `0x1d110`
- `0x1d560`
- `0x1e3b0`

## callees

- `0xe20`
- `0xe40`

## pseudocode

```c

```

## disassembly

```asm
0xe20  ldarg.0
0xe21  ldarg.1
0xe22  ldnull
0xe23  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::Create(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor, class [mscorlib]System.Action`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> rsLoader)
0xe28  stloc.0
0xe29  ldloc.0
0xe2a  brfalse.s loc_E38
0xe2c  ldloc.0
0xe2d  ldarg.1
0xe2e  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor::get_IsFavorite()
0xe33  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_IsFavorite(bool)
0xe38  ldloc.0
0xe39  ret
```
