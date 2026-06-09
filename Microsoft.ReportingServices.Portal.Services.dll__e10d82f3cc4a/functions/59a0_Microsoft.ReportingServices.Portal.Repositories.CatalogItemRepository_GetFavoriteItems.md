# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetFavoriteItems

- ea: `0x59a0`
- end: `0x5a46`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetFavoriteItems`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xde0`
- `0x59a0`
- `0x9e80`
- `0x1e380`

## pseudocode

```c

```

## disassembly

```asm
0x59a0  newobj   instance void <>c__DisplayClass138_0::.ctor()
0x59a5  stloc.0
0x59a6  ldloc.0
0x59a7  ldarg.0
0x59a8  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass138_0::<>4__this
0x59ad  ldarg.1
0x59ae  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x59b3  stloc.1
0x59b4  ldloc.0
0x59b5  ldarg.1
0x59b6  ldarg.0
0x59b7  ldarg.0
0x59b8  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x59bd  ldarg.0
0x59be  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x59c3  ldarg.0
0x59c4  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_systemService
0x59c9  newobj   instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::.ctor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor catalogAccessor, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService)
0x59ce  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory <>c__DisplayClass138_0::catalogItemFactory
0x59d3  ldloc.1
0x59d4  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSServiceStorageAccess::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService)
0x59d9  stloc.2
0x59da  ldloc.1
0x59db  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_Storage()
0x59e0  ldloc.1
0x59e1  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Security [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0x59e6  ldloc.1
0x59e7  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemList [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface::GetAllFavoriteItems(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Security, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator)
0x59ec  ldloc.0
0x59ed  ldftn    instance bool <>c__DisplayClass138_0::<GetFavoriteItems>b__0(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor i)
0x59f3  newobj   instance void class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor, bool>::.ctor(object, native int)
0x59f8  call     T0x2B00000E
0x59fd  ldloc.0
0x59fe  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass138_0::<GetFavoriteItems>b__1(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor i)
0x5a04  newobj   instance void class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::.ctor(object, native int)
0x5a09  call     T0x2B00000F
0x5a0e  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool> <>c::<>9__138_2
0x5a13  dup
0x5a14  brtrue.s loc_5A2D
0x5a16  pop
0x5a17  ldsfld   class <>c <>c::<>9
0x5a1c  ldftn    instance bool <>c::<GetFavoriteItems>b__138_2(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem c)
0x5a22  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool>::.ctor(object, native int)
0x5a27  dup
0x5a28  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool> <>c::<>9__138_2
0x5a2d  call     T0x2B000010
0x5a32  call     T0x2B00000A
0x5a37  stloc.3
0x5a38  leave.s  loc_5A44
0x5a3a  ldloc.2
0x5a3b  brfalse.s loc_5A43
0x5a3d  ldloc.2
0x5a3e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a43  endfinally
0x5a44  ldloc.3
0x5a45  ret
```
