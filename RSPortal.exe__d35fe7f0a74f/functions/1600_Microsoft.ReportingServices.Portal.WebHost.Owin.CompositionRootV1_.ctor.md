# Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV1::.ctor

- ea: `0x1600`
- end: `0x17c9`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV1::.ctor`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3660`

## callees

- `0x1600`
- `0x3bb0`

## pseudocode

```c

```

## disassembly

```asm
0x1600  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x1605  stloc.0
0x1606  ldloc.0
0x1607  ldarg.s  4
0x1609  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService <>c__DisplayClass1_0::subscriptionService
0x160e  ldloc.0
0x160f  ldarg.2
0x1610  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService <>c__DisplayClass1_0::systemService
0x1615  ldloc.0
0x1616  ldarg.s  5
0x1618  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger <>c__DisplayClass1_0::logger
0x161d  ldloc.0
0x161e  ldarg.3
0x161f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository <>c__DisplayClass1_0::catalogRepository
0x1624  ldloc.0
0x1625  ldarg.s  6
0x1627  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService <>c__DisplayClass1_0::dataService
0x162c  ldloc.0
0x162d  ldarg.s  8
0x162f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager <>c__DisplayClass1_0::portalConfigurationManager
0x1634  ldloc.0
0x1635  ldarg.s  9
0x1637  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService <>c__DisplayClass1_0::userInfoService
0x163c  ldloc.0
0x163d  ldarg.s  0xA
0x163f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.INotificationService <>c__DisplayClass1_0::notificationService
0x1644  ldloc.0
0x1645  ldarg.s  0xC
0x1647  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService <>c__DisplayClass1_0::systemResourceService
0x164c  ldloc.0
0x164d  ldarg.s  0xD
0x164f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryService <>c__DisplayClass1_0::telemetryService
0x1654  ldarg.0
0x1655  call     instance void [mscorlib]System.Object::.ctor()
0x165a  ldarg.0
0x165b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::.ctor()
0x1660  dup
0x1661  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CacheRefreshPlanController
0x1666  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x166b  ldloc.0
0x166c  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__0()
0x1672  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1677  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x167c  dup
0x167d  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController
0x1682  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1687  ldloc.0
0x1688  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__1()
0x168e  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1693  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1698  dup
0x1699  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController
0x169e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16a3  ldloc.0
0x16a4  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__2()
0x16aa  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x16af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x16b4  dup
0x16b5  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController
0x16ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16bf  ldloc.0
0x16c0  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__3()
0x16c6  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x16cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x16d0  dup
0x16d1  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.NotificationsController
0x16d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16db  ldloc.0
0x16dc  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__4()
0x16e2  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x16e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x16ec  dup
0x16ed  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController
0x16f2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f7  ldloc.0
0x16f8  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__5()
0x16fe  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1703  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1708  dup
0x1709  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SchedulesController
0x170e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1713  ldloc.0
0x1714  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__6()
0x171a  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x171f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1724  dup
0x1725  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SubscriptionsController
0x172a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x172f  ldloc.0
0x1730  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__7()
0x1736  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x173b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1740  dup
0x1741  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController
0x1746  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x174b  ldloc.0
0x174c  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__8()
0x1752  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1757  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x175c  dup
0x175d  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.TelemetryController
0x1762  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1767  ldloc.0
0x1768  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__9()
0x176e  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1773  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1778  dup
0x1779  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController
0x177e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1783  ldloc.0
0x1784  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__10()
0x178a  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x178f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1794  dup
0x1795  ldtoken  [Microsoft.AspNet.OData]Microsoft.AspNet.OData.MetadataController
0x179a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x179f  ldsfld   class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController> <>c::<>9__1_11
0x17a4  dup
0x17a5  brtrue.s loc_17BE
0x17a7  pop
0x17a8  ldsfld   class <>c <>c::<>9
0x17ad  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c::<.ctor>b__1_11()
0x17b3  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x17b8  dup
0x17b9  stsfld   class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController> <>c::<>9__1_11
0x17be  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x17c3  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>> Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV1::_controllerFactoryMap
0x17c8  ret
```
