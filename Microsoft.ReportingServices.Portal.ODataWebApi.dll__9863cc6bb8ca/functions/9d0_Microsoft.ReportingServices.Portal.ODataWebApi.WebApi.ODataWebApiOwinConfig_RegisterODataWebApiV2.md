# Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::RegisterODataWebApiV2

- ea: `0x9d0`
- end: `0xb76`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::RegisterODataWebApiV2`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x60`
- `0x9d0`
- `0x11c0`
- `0x19a0`
- `0x6480`
- `0xd450`
- `0xd470`

## pseudocode

```c

```

## disassembly

```asm
0x9d0  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x9d5  stloc.0
0x9d6  ldloc.0
0x9d7  ldarg.1
0x9d8  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger <>c__DisplayClass1_0::logger
0x9dd  newobj   instance void <>c__DisplayClass1_1::.ctor()
0x9e2  stloc.1
0x9e3  ldloc.1
0x9e4  ldloc.0
0x9e5  stfld    class <>c__DisplayClass1_0 <>c__DisplayClass1_1::CS$<>8__locals1
0x9ea  ldloc.1
0x9eb  newobj   instance void [System.Web.Http]System.Web.Http.HttpConfiguration::.ctor()
0x9f0  stfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0x9f5  ldloc.1
0x9f6  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0x9fb  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::Count(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xa00  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::Filter(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xa05  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::OrderBy(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xa0a  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::Expand(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xa0f  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::Select(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xa14  ldloca.s 2
0xa16  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xa1c  ldloc.2
0xa1d  call     class [System.Web.Http]System.Web.Http.HttpConfiguration [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::MaxTop(class [System.Web.Http]System.Web.Http.HttpConfiguration, valuetype [mscorlib]System.Nullable`1<int32>)
0xa22  pop
0xa23  ldloc.1
0xa24  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xa29  call     void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::AddODataQueryFilter(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xa2e  ldloc.1
0xa2f  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xa34  callvirt instance class [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Filters()
0xa39  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.V2.Filters.PortalExceptionFilter::.ctor()
0xa3e  dup
0xa3f  ldloc.1
0xa40  ldfld    class <>c__DisplayClass1_0 <>c__DisplayClass1_1::CS$<>8__locals1
0xa45  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger <>c__DisplayClass1_0::logger
0xa4a  callvirt instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Filters.PortalExceptionFilter::set_Logger(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger value)
0xa4f  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection::Add(class [System.Web.Http]System.Web.Http.Filters.IFilter)
0xa54  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0xa59  ldc.i4.s 0xC
0xa5b  ldc.i4.0
0xa5c  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::IsConfigSwitchEnabled(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitches, bool)
0xa61  brfalse.s loc_A71
0xa63  ldloc.1
0xa64  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xa69  ldc.i4.2
0xa6a  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::set_IncludeErrorDetailPolicy(valuetype [System.Web.Http]System.Web.Http.IncludeErrorDetailPolicy)
0xa6f  br.s     loc_A7D
0xa71  ldloc.1
0xa72  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xa77  ldc.i4.3
0xa78  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::set_IncludeErrorDetailPolicy(valuetype [System.Web.Http]System.Web.Http.IncludeErrorDetailPolicy)
0xa7d  ldloc.1
0xa7e  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.ReportingServices.Portal.ODataWebApi.WebApi.ODataWebApiOwinConfig::GetEdmModelV2()
0xa83  stfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel <>c__DisplayClass1_1::edmModel
0xa88  ldloc.1
0xa89  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xa8e  ldstr    aOdatav2// "odataV2"
0xa93  ldstr    aApiV20// "api/v2.0"
0xa98  ldloc.1
0xa99  ldftn    instance void <>c__DisplayClass1_1::<RegisterODataWebApiV2>b__0(class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder builder)
0xa9f  newobj   instance void class [mscorlib]System.Action`1<class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder>::.ctor(object, native int)
0xaa4  call     class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataRoute [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::MapODataServiceRoute(class [System.Web.Http]System.Web.Http.HttpConfiguration, string, string, class [mscorlib]System.Action`1<class [Microsoft.OData.Core]Microsoft.OData.IContainerBuilder>)
0xaa9  pop
0xaaa  ldloc.1
0xaab  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xab0  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0xab5  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerActivator
0xaba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xabf  ldarg.3
0xac0  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0xac5  ldloc.1
0xac6  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xacb  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0xad0  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver
0xad5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xada  ldarg.2
0xadb  ldc.i4.2
0xadc  newarr   [mscorlib]System.Reflection.Assembly
0xae1  dup
0xae2  ldc.i4.0
0xae3  ldtoken  [Microsoft.AspNet.OData]Microsoft.AspNet.OData.MetadataController
0xae8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaed  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xaf2  stelem.ref
0xaf3  dup
0xaf4  ldc.i4.1
0xaf5  ldtoken  Microsoft.ReportingServices.Portal.ODataWebApi.UnboundFunctionRoutingConvention
0xafa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaff  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xb04  stelem.ref
0xb05  callvirt instance class [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.WebApi.IAssembliesResolverFactory::Create(class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Reflection.Assembly>)
0xb0a  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0xb0f  ldloc.1
0xb10  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xb15  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0xb1a  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerSelector
0xb1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb24  ldloc.1
0xb25  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xb2a  newobj   instance void Microsoft.ReportingServices.Portal.ODataWebApi.NamespaceHttpControllerSelector::.ctor(class [System.Web.Http]System.Web.Http.HttpConfiguration config)
0xb2f  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0xb34  ldloc.1
0xb35  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xb3a  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::EnsureInitialized()
0xb3f  ldloc.1
0xb40  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xb45  call     void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Extensions.HttpConfigurationExtensions::EnableDependencyInjection(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xb4a  ldarg.0
0xb4b  ldloc.1
0xb4c  ldfld    class [System.Web.Http]System.Web.Http.HttpConfiguration <>c__DisplayClass1_1::config
0xb51  call     class [Owin]Owin.IAppBuilder [System.Web.Http.Owin]Owin.WebApiAppBuilderExtensions::UseWebApi(class [Owin]Owin.IAppBuilder, class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xb56  pop
0xb57  leave.s  loc_B75
0xb59  stloc.3
0xb5a  ldloc.0
0xb5b  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger <>c__DisplayClass1_0::logger
0xb60  ldc.i4.1
0xb61  ldloc.3
0xb62  dup
0xb63  ldvirtftn instance string [mscorlib]System.Object::ToString()
0xb69  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0xb6e  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, class [mscorlib]System.Func`1<string>)
0xb73  rethrow
0xb75  ret
```
