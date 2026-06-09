# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalWebApi::Register

- ea: `0x3020`
- end: `0x30af`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalWebApi::Register`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3660`

## pseudocode

```c

```

## disassembly

```asm
0x3020  newobj   instance void [System.Web.Http]System.Web.Http.HttpConfiguration::.ctor()
0x3025  stloc.0
0x3026  ldloc.0
0x3027  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Formatters()
0x302c  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.JsonMediaTypeFormatter [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection::get_JsonFormatter()
0x3031  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings [System.Net.Http.Formatting]System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::get_SerializerSettings()
0x3036  ldc.i4.1
0x3037  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_NullValueHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.NullValueHandling)
0x303c  ldloc.0
0x303d  call     void [System.Web.Http]System.Web.Http.HttpConfigurationExtensions::MapHttpAttributeRoutes(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x3042  ldloc.0
0x3043  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x3048  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerActivator
0x304d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3052  ldarg.1
0x3053  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x3058  ldloc.0
0x3059  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x305e  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver
0x3063  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3068  ldarg.2
0x3069  ldc.i4.1
0x306a  newarr   [mscorlib]System.Reflection.Assembly
0x306f  dup
0x3070  ldc.i4.0
0x3071  ldtoken  [Microsoft.ReportingServices.Portal.WebApi]Microsoft.ReportingServices.Portal.WebApi.VX.Controllers.EndpointsController
0x3076  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x307b  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3080  stelem.ref
0x3081  callvirt instance class [System.Web.Http]System.Web.Http.Dispatcher.IAssembliesResolver [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.WebApi.IAssembliesResolverFactory::Create(class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.Reflection.Assembly>)
0x3086  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x308b  ldloc.0
0x308c  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x3091  ldtoken  [System.Web.Http]System.Web.Http.Dispatcher.IHttpControllerSelector
0x3096  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x309b  ldloc.0
0x309c  newobj   instance void [System.Web.Http]System.Web.Http.Dispatcher.DefaultHttpControllerSelector::.ctor(class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x30a1  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Replace(class [mscorlib]System.Type, object)
0x30a6  ldarg.0
0x30a7  ldloc.0
0x30a8  call     class [Owin]Owin.IAppBuilder [System.Web.Http.Owin]Owin.WebApiAppBuilderExtensions::UseWebApi(class [Owin]Owin.IAppBuilder, class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x30ad  pop
0x30ae  ret
```
