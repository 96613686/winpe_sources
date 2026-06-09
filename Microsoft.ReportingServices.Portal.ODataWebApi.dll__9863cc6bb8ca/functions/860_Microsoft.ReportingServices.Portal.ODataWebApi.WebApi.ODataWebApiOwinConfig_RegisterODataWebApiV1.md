# Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::RegisterODataWebApiV1

- ea: `0x860`
- end: `0x9c2`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::RegisterODataWebApiV1`
- size: `354`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x60`
- `0x860`
- `0xbd0`
- `0x6480`
- `0x6e90`
- `0xd2e0`
- `0xd310`

## pseudocode

```c

```

## disassembly

```asm
0x860  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x865  stloc.0
0x866  ldloc.0
0x867  ldarg.1
0x868  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger <>c__DisplayClass0_0::logger
0x86d  newobj   instance void <>c__DisplayClass0_1::.ctor()
0x872  stloc.1
0x873  ldloc.1
0x874  ldloc.0
0x875  stfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x87a  newobj   instance void [System.Web.Http]System.Web.Http.HttpConfiguration::.ctor()
0x87f  stloc.2
0x880  ldloc.2
0x881  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::Count(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x886  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::Filter(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x88b  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::OrderBy(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x890  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::Expand(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x895  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::Select(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x89a  ldloca.s 3
0x89c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x8a2  ldloc.3
0x8a3  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::MaxTop(class [System.Web.Http]System.Web.Http.HttpConfiguration, valuetype [mscorlib]System.Nullable`1<int32>)
0x8a8  pop
0x8a9  ldloc.2
0x8aa  call     void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::AddODataQueryFilter(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x8af  ldloc.2
0x8b0  callvirt instance class [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Filters()
0x8b5  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::.ctor()
0x8ba  dup
0x8bb  ldloc.1
0x8bc  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x8c1  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger <>c__DisplayClass0_0::logger
0x8c6  callvirt instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::set_Logger(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger value)
0x8cb  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection::Add(class [System.Web.Http]System.Web.Http.Filters.IFilter)
0x8d0  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0x8d5  ldc.i4.s 0xC
0x8d7  ldc.i4.0
0x8d8  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::IsConfigSwitchEnabled(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitches, bool)
0x8dd  brfalse.s loc_8E8
0x8df  ldloc.2
0x8e0  ldc.i4.2
0x8e1  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::set_IncludeErrorDetailPolicy(valuetype [System.Web.Http]System.Web.Http.IncludeErrorDetailPolicy)
0x8e6  br.s     loc_8EF
0x8e8  ldloc.2
0x8e9  ldc.i4.3
0x8ea  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::set_IncludeErrorDetailPolicy(valuetype [System.Web.Http]System.Web.Http.IncludeErrorDetailPolicy)
0x8ef  ldloc.1
0x8f0  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetEdmModelV1()
0x8f5  stfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel <>c__DisplayClass0_1::edmModel
0x8fa  ldloc.2
0x8fb  ldstr    aOdatav1// "odataV1"
0x900  ldstr    aApiV10// "api/v1.0"
0x905  ldloc.1
0x906  ldftn    instance void <>c__DisplayClass0_1::<RegisterODataWebApiV1>b__0(class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder builder)
0x90c  newobj   instance void class [mscorlib]System.Action`1<class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder>::.ctor(object, native int)
0x911  call     class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataRoute [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::MapODataServiceRoute(class [System.Web.Http]System.Web.Http.HttpConfiguration, string, string, class [mscorlib]System.Action`1<class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder>)
0x916  pop
0x917  ldloc.2
0x918  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x91d  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerActivator
0x922  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x927  ldarg.3
0x928  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x92d  ldloc.2
0x92e  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x933  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver
0x938  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93d  ldarg.2
0x93e  ldc.i4.2
0x93f  newarr   [mscorlib]System.Reflection.Assembly
0x944  dup
0x945  ldc.i4.0
0x946  ldtoken  [Microsoft.AspNet.OData]Microsoft.AspNet.OData.MetadataController
0x94b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x950  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x955  stelem.ref
0x956  dup
0x957  ldc.i4.1
0x958  ldtoken  Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention
0x95d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x962  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x967  stelem.ref
0x968  callvirt instance class [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.WebApi.IAssembliesResolverFactory::Create(class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Reflection.Assembly>)
0x96d  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x972  ldloc.2
0x973  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x978  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerSelector
0x97d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x982  ldloc.2
0x983  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::.ctor(class [System.Web.Http]System.Web.Http.HttpConfiguration config)
0x988  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x98d  ldloc.2
0x98e  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::EnsureInitialized()
0x993  ldloc.2
0x994  call     void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::EnableDependencyInjection(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x999  ldarg.0
0x99a  ldloc.2
0x99b  call     class [Owin]Owin.IAppBuilder [System.Web.Http.Owin]Owin.WebApiAppBuilderExtensions::UseWebApi(class [Owin]Owin.IAppBuilder, class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x9a0  pop
0x9a1  leave.s  loc_9C1
0x9a3  stloc.s  4
0x9a5  ldloc.0
0x9a6  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger <>c__DisplayClass0_0::logger
0x9ab  ldc.i4.1
0x9ac  ldloc.s  4
0x9ae  dup
0x9af  ldvirtftn instance string [mscorlib]System.Object::ToString()
0x9b5  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x9ba  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0x9bf  rethrow
0x9c1  ret
```
