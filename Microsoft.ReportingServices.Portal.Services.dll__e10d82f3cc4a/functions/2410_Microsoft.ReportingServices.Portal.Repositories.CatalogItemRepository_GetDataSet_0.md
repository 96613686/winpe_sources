# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataSet_0

- ea: `0x2410`
- end: `0x2491`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDataSet_0`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ab0`
- `0x23f0`
- `0x4eb0`

## callees

- `0x3d0`
- `0x1730`
- `0x1ba0`
- `0x2270`
- `0x2410`
- `0x9e80`

## pseudocode

```c

```

## disassembly

```asm
0x2410  ldarg.1
0x2411  ldarg.0
0x2412  newobj   instance void Model.DataSetRepository::.ctor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository)
0x2417  stloc.0
0x2418  ldarg.1
0x2419  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x241e  stloc.1
0x241f  ldarg.0
0x2420  ldarg.1
0x2421  ldloc.1
0x2422  ldarg.2
0x2423  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemDescriptor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string path)
0x2428  stloc.2
0x2429  ldloc.2
0x242a  ldloc.0
0x242b  call     void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::PopulateCommonFields(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor itemDescriptor, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem catalogItem)
0x2430  ldloc.0
0x2431  ldloc.2
0x2432  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor::get_HasParameters()
0x2437  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet::set_HasParameters(bool)
0x243c  ldloc.0
0x243d  ldloc.2
0x243e  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor::get_IsFavorite()
0x2443  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::set_IsFavorite(bool)
0x2448  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor()
0x244d  stloc.3
0x244e  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::.ctor()
0x2453  dup
0x2454  ldstr    aQueryexecution// "QueryExecutionTimeOut"
0x2459  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::set_Name(string)
0x245e  stloc.s  4
0x2460  ldloc.3
0x2461  ldloc.s  4
0x2463  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::Add(var<u1>)
0x2468  ldarg.0
0x2469  ldarg.1
0x246a  ldarg.2
0x246b  ldloc.3
0x246c  call     instance class [System.Core]System.Linq.IQueryable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemProperties(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string path, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> requestedPropertiesproperties)
0x2471  ldc.i4.0
0x2472  stloc.s  5
0x2474  call     T0x2B00001D
0x2479  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0x247e  ldloca.s 5
0x2480  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x2485  brfalse.s loc_248F
0x2487  ldloc.0
0x2488  ldloc.s  5
0x248a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet::set_QueryExecutionTimeOut(int32)
0x248f  ldloc.0
0x2490  ret
```
