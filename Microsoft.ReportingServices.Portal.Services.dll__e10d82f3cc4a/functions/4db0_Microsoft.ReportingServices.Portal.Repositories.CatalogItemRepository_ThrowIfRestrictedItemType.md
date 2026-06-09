# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType

- ea: `0x4db0`
- end: `0x4dfd`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x22b0`
- `0x2370`
- `0x5430`

## callees

- `0x4db0`
- `0x4e00`

## pseudocode

```c

```

## disassembly

```asm
0x4db0  ldarg.1
0x4db1  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSServiceStorageAccess::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService)
0x4db6  stloc.0
0x4db7  ldarg.1
0x4db8  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator)
0x4dbd  stloc.2
0x4dbe  ldloc.2
0x4dbf  ldarg.2
0x4dc0  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetPath(string)
0x4dc5  brtrue.s loc_4DCE
0x4dc7  ldarg.2
0x4dc8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemPathException::.ctor(string)
0x4dcd  throw
0x4dce  ldarg.1
0x4dcf  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_Storage()
0x4dd4  ldarg.1
0x4dd5  ldloc.2
0x4dd6  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::get_CatalogItemPath()
0x4ddb  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::CatalogToExternal(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath)
0x4de0  ldloca.s 1
0x4de2  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType&)
0x4de7  pop
0x4de8  ldarg.0
0x4de9  ldloc.1
0x4dea  ldarg.2
0x4deb  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType type, string path)
0x4df0  leave.s  loc_4DFC
0x4df2  ldloc.0
0x4df3  brfalse.s loc_4DFB
0x4df5  ldloc.0
0x4df6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4dfb  endfinally
0x4dfc  ret
```
