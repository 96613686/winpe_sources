# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentPermissions_0

- ea: `0x65f0`
- end: `0x6617`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentPermissions_0`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x61b0`
- `0x65d0`

## callees

- `0x5ff0`
- `0x65f0`
- `0x6620`

## pseudocode

```c

```

## disassembly

```asm
0x65f0  ldarg.0
0x65f1  ldarg.1
0x65f2  ldarg.2
0x65f3  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string itemPath)
0x65f8  stloc.0
0x65f9  ldarg.0
0x65fa  ldloc.0
0x65fb  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::get_ThisItemType()
0x6600  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentsAllowedOnType(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType itemType)
0x6605  ldloc.0
0x6606  ldc.i4.6
0x6607  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfNoAccess(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CommonOperation)
0x660c  ldarg.3
0x660d  brfalse.s loc_6616
0x660f  ldloc.0
0x6610  ldc.i4.7
0x6611  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfNoAccess(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CommonOperation)
0x6616  ret
```
