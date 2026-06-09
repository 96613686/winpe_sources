# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLinkedReport

- ea: `0x4f70`
- end: `0x4fd4`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLinkedReport`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ab0`

## callees

- `0x660`
- `0x1730`
- `0x1ba0`
- `0x9e80`

## pseudocode

```c

```

## disassembly

```asm
0x4f70  ldarg.1
0x4f71  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x4f76  stloc.0
0x4f77  ldloc.0
0x4f78  ldc.i4.1
0x4f79  call     valuetype [System.Data]System.Data.IsolationLevel [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_DefaultIsolationLevel()
0x4f7e  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::SetDatabaseConnectionSettings(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x4f83  ldloc.0
0x4f84  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetReportLinkAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_GetReportLinkAction()
0x4f89  stloc.1
0x4f8a  ldloc.1
0x4f8b  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetReportLinkActionParameters>::get_ActionParameters()
0x4f90  ldarg.2
0x4f91  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetReportLinkActionParameters::set_ReportPath(string)
0x4f96  ldloc.1
0x4f97  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetReportLinkActionParameters>::Execute()
0x4f9c  ldarg.1
0x4f9d  ldarg.0
0x4f9e  newobj   instance void Model.LinkedReportRepository::.ctor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository)
0x4fa3  stloc.2
0x4fa4  ldloc.2
0x4fa5  ldloc.1
0x4fa6  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetReportLinkActionParameters>::get_ActionParameters()
0x4fab  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.GetReportLinkActionParameters::get_LinkPath()
0x4fb0  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport::set_Link(string)
0x4fb5  ldarg.0
0x4fb6  ldarg.1
0x4fb7  ldloc.0
0x4fb8  ldarg.2
0x4fb9  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemDescriptor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string path)
0x4fbe  stloc.3
0x4fbf  ldloc.3
0x4fc0  ldloc.2
0x4fc1  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::PopulateCommonFields(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem catalogItem)
0x4fc6  ldloc.2
0x4fc7  ldloc.3
0x4fc8  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_HasParameters()
0x4fcd  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.LinkedReport::set_HasParameters(bool)
0x4fd2  ldloc.2
0x4fd3  ret
```
