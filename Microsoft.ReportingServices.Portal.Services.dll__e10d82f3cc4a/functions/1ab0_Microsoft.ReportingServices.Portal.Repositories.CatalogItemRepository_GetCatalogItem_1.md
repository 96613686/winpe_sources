# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem_1

- ea: `0x1ab0`
- end: `0x1b29`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogItem_1`
- size: `121`
- prototype: ``
- caller_count: `13`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a70`
- `0x1a90`
- `0x1b30`
- `0x2200`
- `0x24a0`
- `0x2850`
- `0x2950`
- `0x3510`
- `0x37a0`
- `0x3c20`
- `0x5040`
- `0x51f0`
- `0x5390`

## callees

- `0xde0`
- `0xe20`
- `0x1ab0`
- `0x1ba0`
- `0x2410`
- `0x4e00`
- `0x4f70`
- `0x4fe0`

## pseudocode

```c

```

## disassembly

```asm
0x1ab0  ldarg.2
0x1ab1  ldarg.0
0x1ab2  ldarg.0
0x1ab3  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x1ab8  ldarg.0
0x1ab9  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x1abe  ldarg.0
0x1abf  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_systemService
0x1ac4  newobj   instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::.ctor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor catalogAccessor, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService)
0x1ac9  stloc.0
0x1aca  ldarg.0
0x1acb  ldarg.2
0x1acc  ldarg.1
0x1acd  ldarg.3
0x1ace  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemDescriptor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string path)
0x1ad3  stloc.1
0x1ad4  ldarg.0
0x1ad5  ldloc.1
0x1ad6  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Type()
0x1adb  ldarg.3
0x1adc  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ThrowIfRestrictedItemType(valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType type, string path)
0x1ae1  ldloc.1
0x1ae2  callvirt instance valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_Type()
0x1ae7  stloc.2
0x1ae8  ldloc.2
0x1ae9  ldc.i4.4
0x1aea  sub
0x1aeb  switch   loc_1B0F, loc_1B06, loc_1B21, loc_1B21, loc_1B18
0x1b04  br.s     loc_1B21
0x1b06  ldarg.0
0x1b07  ldarg.2
0x1b08  ldarg.3
0x1b09  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataSource(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x1b0e  ret
0x1b0f  ldarg.0
0x1b10  ldarg.2
0x1b11  ldarg.3
0x1b12  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLinkedReport(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x1b17  ret
0x1b18  ldarg.0
0x1b19  ldarg.2
0x1b1a  ldarg.3
0x1b1b  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataSet(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path)
0x1b20  ret
0x1b21  ldloc.0
0x1b22  ldloc.1
0x1b23  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::Create(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor itemDescriptor)
0x1b28  ret
```
