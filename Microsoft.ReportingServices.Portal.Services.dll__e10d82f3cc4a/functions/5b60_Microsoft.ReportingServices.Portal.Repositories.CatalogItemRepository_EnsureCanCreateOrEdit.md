# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCanCreateOrEdit

- ea: `0x5b60`
- end: `0x5b96`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCanCreateOrEdit`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x3e40`
- `0x3e80`
- `0x5b60`

## string_xrefs

- `0x5b73`: `Item already exists, check if we can edit: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5b60  ldarg.0
0x5b61  ldarg.2
0x5b62  ldarg.3
0x5b63  ldarg.1
0x5b64  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemCanBeCreated(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string parentPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem item)
0x5b69  leave.s  loc_5B95
0x5b6b  stloc.0
0x5b6c  ldarg.0
0x5b6d  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x5b72  ldc.i4.3
0x5b73  ldstr    aItemAlreadyExi// "Item already exists, check if we can ed"...
0x5b78  ldloc.0
0x5b79  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5b7e  call     string [mscorlib]System.String::Format(string, object)
0x5b83  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5b88  ldarg.0
0x5b89  ldarg.2
0x5b8a  ldarg.3
0x5b8b  ldarg.1
0x5b8c  ldarg.3
0x5b8d  ldarg.1
0x5b8e  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::EnsureCatalogItemCanBeEdited(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string originalParentPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem originalItem, string newParentPath, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem newCatalogItem)
0x5b93  leave.s  loc_5B95
0x5b95  ret
```
