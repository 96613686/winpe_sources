# Microsoft.BIServer.Management.WebHost.WebApiConfigFactory::CreateWebApiConfig

- ea: `0x2f0`
- end: `0x3a0`
- name: `Microsoft.BIServer.Management.WebHost.WebApiConfigFactory::CreateWebApiConfig`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1b0`

## callees

- `0x60`
- `0x2f0`

## string_xrefs

- `0x388`: `Unhandled exception during webApi creation`

## pseudocode

```c

```

## disassembly

```asm
0x2f0  newobj   instance void [System.Web.Http]System.Web.Http.HttpConfiguration::.ctor()
0x2f5  stloc.0
0x2f6  ldloc.0
0x2f7  call     void [System.Web.Http]System.Web.Http.HttpConfigurationExtensions::MapHttpAttributeRoutes(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x2fc  ldloc.0
0x2fd  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x302  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver
0x307  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30c  newobj   instance void Microsoft.BIServer.Management.WebHost.AssembliesResolver::.ctor()
0x311  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x316  ldloc.0
0x317  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x31c  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerSelector
0x321  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x326  ldloc.0
0x327  newobj   instance void [System.Web.Http]System.Web.Http.Dispatcher.DefaultHttpControllerSelector::.ctor(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x32c  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x331  ldloc.0
0x332  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x337  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerActivator
0x33c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x341  newobj   instance void [Microsoft.BIServer.Management.WebApi]Microsoft.BIServer.Management.WebApi.WebApiActivator::.ctor()
0x346  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x34b  ldloc.0
0x34c  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x351  ldtoken  [System.Web.Http]System.Web.Http.ExceptionHandling.IExceptionLogger
0x356  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35b  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.WebApiExceptionLogger::.ctor()
0x360  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Add(class [mscorlib]System.Type, object)
0x365  ldloc.0
0x366  callvirt instance class [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Filters()
0x36b  newobj   instance void [Microsoft.BIServer.Management.WebApi]Microsoft.BIServer.Management.WebApi.Authorization.AuthorizeLocalhostOnlyAttribute::.ctor()
0x370  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection::Add(class [System.Web.Http]System.Web.Http.Filters.IFilter)
0x375  ldloc.0
0x376  callvirt instance class [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Filters()
0x37b  newobj   instance void [Microsoft.BIServer.Management.WebApi]Microsoft.BIServer.Management.WebApi.WebApiExceptionFilterAttribute::.ctor()
0x380  callvirt instance void [System.Web.Http]System.Web.Http.Filters.HttpFilterCollection::Add(class [System.Web.Http]System.Web.Http.Filters.IFilter)
0x385  leave.s  loc_39E
0x387  dup
0x388  ldstr    aUnhandledExcep// "Unhandled exception during webApi creat"...
0x38d  call     T0x2B000001
0x392  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x397  call     void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Dumper::DumpHere(class [mscorlib]System.Exception)
0x39c  leave.s  loc_39E
0x39e  ldloc.0
0x39f  ret
```
