# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataSource_0

- ea: `0x4fe0`
- end: `0x5037`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataSource_0`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ab0`
- `0x4e30`

## callees

- `0x480`
- `0x1730`
- `0x1ba0`
- `0x9e80`
- `0x110d0`

## pseudocode

```c

```

## disassembly

```asm
0x4fe0  ldarg.1
0x4fe1  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x4fe6  stloc.0
0x4fe7  ldarg.0
0x4fe8  ldarg.1
0x4fe9  ldloc.0
0x4fea  ldarg.2
0x4feb  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemDescriptor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string path)
0x4ff0  stloc.1
0x4ff1  ldloc.0
0x4ff2  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetDataSourceContentsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_GetDataSourceContentsAction()
0x4ff7  dup
0x4ff8  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetDataSourceContentsActionParameters>::get_ActionParameters()
0x4ffd  ldarg.2
0x4ffe  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetDataSourceContentsActionParameters::set_DataSourcePath(string)
0x5003  dup
0x5004  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetDataSourceContentsActionParameters>::Execute()
0x5009  ldarg.1
0x500a  ldarg.0
0x500b  newobj   instance void Model.DataSourceRepository::.ctor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository)
0x5010  stloc.2
0x5011  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetDataSourceContentsActionParameters>::get_ActionParameters()
0x5016  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetDataSourceContentsActionParameters::get_DataSourceDefinition()
0x501b  ldloc.2
0x501c  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSource(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap2005.DataSourceDefinition dsd, class Model.DataSourceRepository dsr)
0x5021  stloc.3
0x5022  ldloc.1
0x5023  ldloc.3
0x5024  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::PopulateCommonFields(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem catalogItem)
0x5029  ldloc.3
0x502a  ldloc.1
0x502b  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor::get_IsFavorite()
0x5030  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_IsFavorite(bool)
0x5035  ldloc.3
0x5036  ret
```
