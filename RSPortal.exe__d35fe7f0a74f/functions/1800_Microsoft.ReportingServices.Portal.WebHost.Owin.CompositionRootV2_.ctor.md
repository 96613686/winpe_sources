# Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV2::.ctor

- ea: `0x1800`
- end: `0x1b61`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV2::.ctor`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3660`

## callees

- `0x1800`
- `0x3d80`

## pseudocode

```c

```

## disassembly

```asm
0x1800  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x1805  stloc.0
0x1806  ldloc.0
0x1807  ldarg.s  4
0x1809  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISubscriptionService <>c__DisplayClass1_0::subscriptionService
0x180e  ldloc.0
0x180f  ldarg.s  5
0x1811  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger <>c__DisplayClass1_0::logger
0x1816  ldloc.0
0x1817  ldarg.3
0x1818  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository <>c__DisplayClass1_0::catalogRepository
0x181d  ldloc.0
0x181e  ldarg.2
0x181f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService <>c__DisplayClass1_0::systemService
0x1824  ldloc.0
0x1825  ldarg.s  6
0x1827  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService <>c__DisplayClass1_0::dataService
0x182c  ldloc.0
0x182d  ldarg.s  7
0x182f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.IEncryptionService <>c__DisplayClass1_0::encryptionService
0x1834  ldloc.0
0x1835  ldarg.s  8
0x1837  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager <>c__DisplayClass1_0::portalConfigurationManager
0x183c  ldloc.0
0x183d  ldarg.s  9
0x183f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService <>c__DisplayClass1_0::userInfoService
0x1844  ldloc.0
0x1845  ldarg.s  0xA
0x1847  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.INotificationService <>c__DisplayClass1_0::notificationService
0x184c  ldloc.0
0x184d  ldarg.s  0xC
0x184f  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService <>c__DisplayClass1_0::systemResourceService
0x1854  ldloc.0
0x1855  ldarg.s  0xD
0x1857  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ITelemetryService <>c__DisplayClass1_0::telemetryService
0x185c  ldloc.0
0x185d  ldarg.s  0xE
0x185f  stfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration <>c__DisplayClass1_0::serverConfiguration
0x1864  ldarg.0
0x1865  call     instance void [mscorlib]System.Object::.ctor()
0x186a  ldarg.0
0x186b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::.ctor()
0x1870  dup
0x1871  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CacheRefreshPlansController
0x1876  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x187b  ldloc.0
0x187c  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__0()
0x1882  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1887  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x188c  dup
0x188d  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController
0x1892  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1897  ldloc.0
0x1898  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__1()
0x189e  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x18a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x18a8  dup
0x18a9  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CommentsController
0x18ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18b3  ldloc.0
0x18b4  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__2()
0x18ba  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x18bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x18c4  dup
0x18c5  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ComponentsController
0x18ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18cf  ldloc.0
0x18d0  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__3()
0x18d6  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x18db  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x18e0  dup
0x18e1  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController
0x18e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18eb  ldloc.0
0x18ec  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__4()
0x18f2  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x18f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x18fc  dup
0x18fd  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSourcesController
0x1902  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1907  ldloc.0
0x1908  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__5()
0x190e  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1913  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1918  dup
0x1919  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExcelWorkbooksController
0x191e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1923  ldloc.0
0x1924  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__6()
0x192a  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x192f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1934  dup
0x1935  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController
0x193a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x193f  ldloc.0
0x1940  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__7()
0x1946  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x194b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1950  dup
0x1951  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.FavoriteItemsController
0x1956  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x195b  ldloc.0
0x195c  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__8()
0x1962  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1967  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x196c  dup
0x196d  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.FoldersController
0x1972  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1977  ldloc.0
0x1978  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__9()
0x197e  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1983  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1988  dup
0x1989  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.KpisController
0x198e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1993  ldloc.0
0x1994  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__10()
0x199a  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x199f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x19a4  dup
0x19a5  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.LinkedReportsController
0x19aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19af  ldloc.0
0x19b0  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__11()
0x19b6  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x19bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x19c0  dup
0x19c1  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.MeController
0x19c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19cb  ldloc.0
0x19cc  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__12()
0x19d2  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x19d7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x19dc  dup
0x19dd  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.NotificationsController
0x19e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19e7  ldloc.0
0x19e8  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__13()
0x19ee  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x19f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x19f8  dup
0x19f9  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController
0x19fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a03  ldloc.0
0x1a04  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__14()
0x1a0a  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1a0f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1a14  dup
0x1a15  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController
0x1a1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a1f  ldloc.0
0x1a20  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__15()
0x1a26  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1a2b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1a30  dup
0x1a31  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ReportsController
0x1a36  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a3b  ldloc.0
0x1a3c  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__16()
0x1a42  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1a47  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1a4c  dup
0x1a4d  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ResourcesController
0x1a52  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a57  ldloc.0
0x1a58  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__17()
0x1a5e  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1a63  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1a68  dup
0x1a69  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SchedulesController
0x1a6e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a73  ldloc.0
0x1a74  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__18()
0x1a7a  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1a7f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1a84  dup
0x1a85  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SubscriptionsController
0x1a8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a8f  ldloc.0
0x1a90  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__19()
0x1a96  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1a9b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1aa0  dup
0x1aa1  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemResourcesController
0x1aa6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1aab  ldloc.0
0x1aac  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__20()
0x1ab2  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1ab7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1abc  dup
0x1abd  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.TelemetryController
0x1ac2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ac7  ldloc.0
0x1ac8  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__21()
0x1ace  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1ad3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1ad8  dup
0x1ad9  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UnboundFunctionController
0x1ade  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ae3  ldloc.0
0x1ae4  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__22()
0x1aea  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1aef  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1af4  dup
0x1af5  ldtoken  [Microsoft.ReportingServices.Portal.ODataWebApi]Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UserSettingsController
0x1afa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1aff  ldloc.0
0x1b00  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__23()
0x1b06  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1b0b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1b10  dup
0x1b11  ldtoken  [Microsoft.ReportingServices.Portal.WebApi]Microsoft.ReportingServices.Portal.WebApi.V2.Controllers.SessionController
0x1b16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b1b  ldloc.0
0x1b1c  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c__DisplayClass1_0::<.ctor>b__24()
0x1b22  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1b27  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1b2c  dup
0x1b2d  ldtoken  [Microsoft.AspNet.OData]Microsoft.AspNet.OData.MetadataController
0x1b32  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b37  ldsfld   class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController> <>c::<>9__1_25
0x1b3c  dup
0x1b3d  brtrue.s loc_1B56
0x1b3f  pop
0x1b40  ldsfld   class <>c <>c::<>9
0x1b45  ldftn    instance class [System.Web.Http]System.Web.Http.Controllers.IHttpController <>c::<.ctor>b__1_25()
0x1b4b  newobj   instance void class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>::.ctor(object, native int)
0x1b50  dup
0x1b51  stsfld   class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController> <>c::<>9__1_25
0x1b56  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>>::Add(var<u1>, !!T0)
0x1b5b  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, class [mscorlib]System.Func`1<class [System.Web.Http]System.Web.Http.Controllers.IHttpController>> Microsoft.ReportingServices.Portal.WebHost.Owin.CompositionRootV2::_controllerFactoryMap
0x1b60  ret
```
