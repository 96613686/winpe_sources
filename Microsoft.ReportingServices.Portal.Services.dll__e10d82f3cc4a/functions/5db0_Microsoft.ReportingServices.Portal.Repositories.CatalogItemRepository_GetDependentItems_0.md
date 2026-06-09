# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDependentItems_0

- ea: `0x5db0`
- end: `0x5e9c`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetDependentItems_0`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d90`

## callees

- `0xde0`
- `0x5db0`
- `0x9e80`
- `0x1e450`

## pseudocode

```c

```

## disassembly

```asm
0x5db0  newobj   instance void <>c__DisplayClass151_0::.ctor()
0x5db5  stloc.0
0x5db6  ldloc.0
0x5db7  ldarg.0
0x5db8  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass151_0::<>4__this
0x5dbd  ldloc.0
0x5dbe  ldarg.1
0x5dbf  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x5dc4  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass151_0::rsService
0x5dc9  ldloc.0
0x5dca  ldarg.1
0x5dcb  ldarg.0
0x5dcc  ldarg.0
0x5dcd  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x5dd2  ldarg.0
0x5dd3  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x5dd8  ldarg.0
0x5dd9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_systemService
0x5dde  newobj   instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::.ctor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor catalogAccessor, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService)
0x5de3  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory <>c__DisplayClass151_0::catalogItemFactory
0x5de8  ldloc.0
0x5de9  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass151_0::rsService
0x5dee  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListDependentItemsAction [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_ListDependentItemsAction()
0x5df3  dup
0x5df4  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListDependentItemsActionParameters>::get_ActionParameters()
0x5df9  ldarg.2
0x5dfa  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListDependentItemsActionParameters::set_ItemPath(string)
0x5dff  dup
0x5e00  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListDependentItemsActionParameters>::get_ActionParameters()
0x5e05  ldc.i4.1
0x5e06  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListDependentItemsActionParameters::set_DirectDependentItemsOnly(bool)
0x5e0b  dup
0x5e0c  callvirt instance void class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListDependentItemsActionParameters>::Execute()
0x5e11  callvirt instance var<u1> class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSSoapAction`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListDependentItemsActionParameters>::get_ActionParameters()
0x5e16  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemList [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ListDependentItemsActionParameters::get_DependentItems()
0x5e1b  ldsfld   class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor, string> <>c::<>9__151_0
0x5e20  dup
0x5e21  brtrue.s loc_5E3A
0x5e23  pop
0x5e24  ldsfld   class <>c <>c::<>9
0x5e29  ldftn    instance string <>c::<GetDependentItems>b__151_0(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor d)
0x5e2f  newobj   instance void class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor, string>::.ctor(object, native int)
0x5e34  dup
0x5e35  stsfld   class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor, string> <>c::<>9__151_0
0x5e3a  call     T0x2B000048
0x5e3f  ldloc.0
0x5e40  ldftn    instance bool <>c__DisplayClass151_0::<GetDependentItems>b__1(class [System.Core]System.Linq.IGrouping`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor> g)
0x5e46  newobj   instance void class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor>, bool>::.ctor(object, native int)
0x5e4b  call     T0x2B000049
0x5e50  ldloc.0
0x5e51  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass151_0::<GetDependentItems>b__2(class [System.Core]System.Linq.IGrouping`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor> g)
0x5e57  newobj   instance void class [mscorlib]System.Func`2<class [System.Core]System.Linq.IGrouping`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor>, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::.ctor(object, native int)
0x5e5c  call     T0x2B00004A
0x5e61  ldloc.0
0x5e62  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass151_0::<GetDependentItems>b__3(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem x)
0x5e68  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::.ctor(object, native int)
0x5e6d  call     T0x2B00004B
0x5e72  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool> <>c::<>9__151_4
0x5e77  dup
0x5e78  brtrue.s loc_5E91
0x5e7a  pop
0x5e7b  ldsfld   class <>c <>c::<>9
0x5e80  ldftn    instance bool <>c::<GetDependentItems>b__151_4(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem c)
0x5e86  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool>::.ctor(object, native int)
0x5e8b  dup
0x5e8c  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool> <>c::<>9__151_4
0x5e91  call     T0x2B000010
0x5e96  call     T0x2B00000A
0x5e9b  ret
```
