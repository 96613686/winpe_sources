# Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSubscription

- ea: `0x7560`
- end: `0x7600`
- name: `Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSubscription`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7490`
- `0x76d0`

## callees

- `0x7560`
- `0x9e80`
- `0xfbf0`
- `0xfd90`

## pseudocode

```c

```

## disassembly

```asm
0x7560  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x7565  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x756a  ldc.i4.s 0xC
0x756c  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::ThrowIfFeatureNotEnabled(string, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures)
0x7571  ldarg.1
0x7572  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x7577  dup
0x7578  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x757d  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionManager [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_SubscriptionManager()
0x7582  ldarg.2
0x7583  ldc.i4.0
0x7584  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionManager::GetSubscription(valuetype [mscorlib]System.Guid, bool)
0x7589  stloc.0
0x758a  ldnull
0x758b  stloc.1
0x758c  ldloc.0
0x758d  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::IsDataDriven()
0x7592  brfalse.s loc_75CA
0x7594  ldarg.0
0x7595  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x759a  ldarg.1
0x759b  ldarga.s 2
0x759d  constrained. [mscorlib]System.Guid
0x75a3  callvirt instance string [mscorlib]System.Object::ToString()
0x75a8  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::GetDataDrivenSubscriptionProperties(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x75ad  stloc.2
0x75ae  ldloc.0
0x75af  ldarg.0
0x75b0  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x75b5  ldarg.1
0x75b6  ldloc.0
0x75b7  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ReportName()
0x75bc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::GetParameterTypes(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x75c1  ldloc.2
0x75c2  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToWebApiModelDataDriven(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl librarySubscription, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> parameterTypes, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties properties)
0x75c7  stloc.1
0x75c8  br.s     loc_75FE
0x75ca  ldarg.0
0x75cb  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x75d0  ldarg.1
0x75d1  ldarga.s 2
0x75d3  constrained. [mscorlib]System.Guid
0x75d9  callvirt instance string [mscorlib]System.Object::ToString()
0x75de  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.SubscriptionProperties [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::GetSubscriptionProperties(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x75e3  stloc.3
0x75e4  ldloc.0
0x75e5  ldarg.0
0x75e6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x75eb  ldarg.1
0x75ec  ldloc.0
0x75ed  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ReportName()
0x75f2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::GetParameterTypes(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x75f7  ldloc.3
0x75f8  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToWebApiModel(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl librarySubscription, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> parameterTypes, [opt] class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.SubscriptionProperties properties)
0x75fd  stloc.1
0x75fe  ldloc.1
0x75ff  ret
```
