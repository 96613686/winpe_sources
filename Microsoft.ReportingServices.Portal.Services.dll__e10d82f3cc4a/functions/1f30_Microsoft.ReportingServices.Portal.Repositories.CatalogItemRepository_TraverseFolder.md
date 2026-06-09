# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::TraverseFolder

- ea: `0x1f30`
- end: `0x1fec`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::TraverseFolder`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1980`

## callees

- `0xde0`
- `0x1f30`
- `0x9e80`
- `0x1d0e0`

## pseudocode

```c

```

## disassembly

```asm
0x1f30  newobj   instance void <>c__DisplayClass31_0::.ctor()
0x1f35  stloc.0
0x1f36  ldloc.0
0x1f37  ldarg.0
0x1f38  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass31_0::<>4__this
0x1f3d  ldloc.0
0x1f3e  ldarg.1
0x1f3f  stfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass31_0::userPrincipal
0x1f44  ldloc.0
0x1f45  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass31_0::userPrincipal
0x1f4a  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x1f4f  ldloc.0
0x1f50  ldloc.0
0x1f51  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <>c__DisplayClass31_0::userPrincipal
0x1f56  ldarg.0
0x1f57  ldarg.0
0x1f58  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x1f5d  ldarg.0
0x1f5e  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x1f63  ldarg.0
0x1f64  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_systemService
0x1f69  newobj   instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::.ctor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor catalogAccessor, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService)
0x1f6e  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory <>c__DisplayClass31_0::catalogItemFactory
0x1f73  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListFavoriteableItemsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_ListFavoriteableItemsAction()
0x1f78  dup
0x1f79  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListFavoriteableItemsActionParameters>::get_ActionParameters()
0x1f7e  ldarg.3
0x1f7f  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListFavoriteableItemsActionParameters::set_Recursive(bool)
0x1f84  dup
0x1f85  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListFavoriteableItemsActionParameters>::get_ActionParameters()
0x1f8a  ldarg.2
0x1f8b  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListFavoriteableItemsActionParameters::set_ItemPath(string)
0x1f90  dup
0x1f91  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListFavoriteableItemsActionParameters>::Execute()
0x1f96  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListFavoriteableItemsActionParameters>::get_ActionParameters()
0x1f9b  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemList [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListFavoriteableItemsActionParameters::get_Items()
0x1fa0  ldloc.0
0x1fa1  ldftn    instance bool <>c__DisplayClass31_0::<TraverseFolder>b__0(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor i)
0x1fa7  newobj   instance void class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor, bool>::.ctor(object, native int)
0x1fac  call     T0x2B00000E
0x1fb1  ldloc.0
0x1fb2  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass31_0::<TraverseFolder>b__1(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor i)
0x1fb8  newobj   instance void class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.FavoriteableCatalogItemDescriptor, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::.ctor(object, native int)
0x1fbd  call     T0x2B00000F
0x1fc2  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool> <>c::<>9__31_2
0x1fc7  dup
0x1fc8  brtrue.s loc_1FE1
0x1fca  pop
0x1fcb  ldsfld   class <>c <>c::<>9
0x1fd0  ldftn    instance bool <>c::<TraverseFolder>b__31_2(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem c)
0x1fd6  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool>::.ctor(object, native int)
0x1fdb  dup
0x1fdc  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool> <>c::<>9__31_2
0x1fe1  call     T0x2B000010
0x1fe6  call     T0x2B00000A
0x1feb  ret
```
