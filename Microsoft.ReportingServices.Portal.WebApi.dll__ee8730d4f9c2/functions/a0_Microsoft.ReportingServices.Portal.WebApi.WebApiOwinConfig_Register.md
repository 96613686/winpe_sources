# Microsoft.ReportingServices.Portal.WebApi.WebApiOwinConfig::Register

- ea: `0xa0`
- end: `0x12c`
- name: `Microsoft.ReportingServices.Portal.WebApi.WebApiOwinConfig::Register`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xa0  newobj   instance void [System.Web.Http]System.Web.Http.HttpConfiguration::.ctor()
0xa5  stloc.0
0xa6  ldloc.0
0xa7  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Formatters()
0xac  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.JsonMediaTypeFormatter [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection::get_JsonFormatter()
0xb1  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings [System.Net.Http.Formatting]System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::get_SerializerSettings()
0xb6  ldc.i4.1
0xb7  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_NullValueHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.NullValueHandling)
0xbc  ldloc.0
0xbd  call     void [System.Web.Http]System.Web.Http.HttpConfigurationExtensions::MapHttpAttributeRoutes(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0xc2  ldloc.0
0xc3  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::EnsureInitialized()
0xc8  ldloc.0
0xc9  ldarg.0
0xca  ldfld    class [System.Web.Http]System.Web.Http.Dependencies.IDependencyResolver Microsoft.ReportingServices.Portal.WebApi.WebApiOwinConfig::_dependencyResolver
0xcf  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::set_DependencyResolver(class [System.Web.Http]System.Web.Http.Dependencies.IDependencyResolver)
0xd4  ldloc.0
0xd5  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0xda  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver
0xdf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe4  ldarg.0
0xe5  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.WebApi.IAssembliesResolverFactory Microsoft.ReportingServices.Portal.WebApi.WebApiOwinConfig::_assembliesResolverFactory
0xea  ldc.i4.1
0xeb  newarr   [mscorlib]System.Reflection.Assembly
0xf0  dup
0xf1  ldc.i4.0
0xf2  ldarg.0
0xf3  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf8  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xfd  stelem.ref
0xfe  callvirt instance class [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.WebApi.IAssembliesResolverFactory::Create(class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Reflection.Assembly>)
0x103  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x108  ldloc.0
0x109  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x10e  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerSelector
0x113  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x118  ldloc.0
0x119  newobj   instance void [System.Web.Http]System.Web.Http.Dispatcher.DefaultHttpControllerSelector::.ctor(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x11e  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x123  ldarg.1
0x124  ldloc.0
0x125  call     class [Owin]Owin.IAppBuilder [System.Web.Http.Owin]Owin.WebApiAppBuilderExtensions::UseWebApi(class [Owin]Owin.IAppBuilder, class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x12a  pop
0x12b  ret
```
