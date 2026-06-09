# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SearchItems_0

- ea: `0x5ec0`
- end: `0x5f60`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SearchItems_0`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5ea0`

## callees

- `0xde0`
- `0x5ec0`
- `0x9e80`
- `0x1e4d0`

## pseudocode

```c

```

## disassembly

```asm
0x5ec0  newobj   instance void <>c__DisplayClass153_0::.ctor()
0x5ec5  stloc.0
0x5ec6  ldloc.0
0x5ec7  ldarg.0
0x5ec8  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <>c__DisplayClass153_0::<>4__this
0x5ecd  ldloc.0
0x5ece  ldarg.1
0x5ecf  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x5ed4  stfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass153_0::rsService
0x5ed9  ldloc.0
0x5eda  ldarg.1
0x5edb  ldarg.0
0x5edc  ldarg.0
0x5edd  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_logger
0x5ee2  ldarg.0
0x5ee3  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_catalogAccessor
0x5ee8  ldarg.0
0x5ee9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_systemService
0x5eee  newobj   instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::.ctor(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataAccessor catalogAccessor, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService systemService)
0x5ef3  stfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory <>c__DisplayClass153_0::catalogItemFactory
0x5ef8  ldarg.2
0x5ef9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5efe  brfalse.s loc_5F07
0x5f00  ldstr    asc_25576// "/"
0x5f05  starg.s  2
0x5f07  ldloc.0
0x5f08  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService <>c__DisplayClass153_0::rsService
0x5f0d  ldarg.2
0x5f0e  ldarg.3
0x5f0f  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemList [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::FindItems(string, string)
0x5f14  ldloc.0
0x5f15  ldftn    instance bool <>c__DisplayClass153_0::<SearchItems>b__0(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor x)
0x5f1b  newobj   instance void class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor, bool>::.ctor(object, native int)
0x5f20  call     T0x2B00004C
0x5f25  ldloc.0
0x5f26  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem <>c__DisplayClass153_0::<SearchItems>b__1(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor x)
0x5f2c  newobj   instance void class [mscorlib]System.Func`2<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItemDescriptor, class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::.ctor(object, native int)
0x5f31  call     T0x2B00004D
0x5f36  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool> <>c::<>9__153_2
0x5f3b  dup
0x5f3c  brtrue.s loc_5F55
0x5f3e  pop
0x5f3f  ldsfld   class <>c <>c::<>9
0x5f44  ldftn    instance bool <>c::<SearchItems>b__153_2(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem c)
0x5f4a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool>::.ctor(object, native int)
0x5f4f  dup
0x5f50  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem, bool> <>c::<>9__153_2
0x5f55  call     T0x2B000010
0x5f5a  call     T0x2B00000A
0x5f5f  ret
```
