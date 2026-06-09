# Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateKpiCatalogItem

- ea: `0x14e0`
- end: `0x154f`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateKpiCatalogItem`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xe40`

## callees

- `0x610`
- `0x1200`
- `0x14e0`
- `0x1730`
- `0x1ca50`

## pseudocode

```c

```

## disassembly

```asm
0x14e0  ldarg.0
0x14e1  ldfld    class [mscorlib]System.Security.Principal.IPrincipal Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_userPrincipal
0x14e6  ldarg.0
0x14e7  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_catalogRepository
0x14ec  newobj   instance void Model.KpiRepository::.ctor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository)
0x14f1  stloc.0
0x14f2  ldarg.2
0x14f3  ldloc.0
0x14f4  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::PopulateCommonFields(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem catalogItem)
0x14f9  ldarg.0
0x14fa  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_catalogRepository
0x14ff  ldarg.1
0x1500  ldloc.0
0x1501  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x1506  ldnull
0x1507  callvirt instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetItemProperties(class [mscorlib]System.Security.Principal.IPrincipal, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>)
0x150c  stloc.1
0x150d  ldarg.0
0x150e  ldloc.0
0x150f  ldloc.1
0x1510  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::PopulateKpiFromProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi modelKpi, class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> properties)
0x1515  leave.s  loc_154D
0x1517  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x151c  stloc.2
0x151d  stloc.3
0x151e  ldloc.2
0x151f  ldloc.3
0x1520  stfld    class [mscorlib]System.Exception <>c__DisplayClass14_0::ex
0x1525  ldloc.0
0x1526  ldnull
0x1527  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::set_Values(class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiValues)
0x152c  ldloc.0
0x152d  ldnull
0x152e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Kpi::set_Data(class [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiData)
0x1533  ldarg.0
0x1534  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::_logger
0x1539  ldc.i4.2
0x153a  ldloc.2
0x153b  ldftn    instance string <>c__DisplayClass14_0::<CreateKpiCatalogItem>b__0()
0x1541  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x1546  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x154b  leave.s  loc_154D
0x154d  ldloc.0
0x154e  ret
```
