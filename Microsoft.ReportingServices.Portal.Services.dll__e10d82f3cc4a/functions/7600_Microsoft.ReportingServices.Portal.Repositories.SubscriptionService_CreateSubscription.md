# Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::CreateSubscription

- ea: `0x7600`
- end: `0x76cb`
- name: `Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::CreateSubscription`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x7600`
- `0x7990`
- `0x7da0`
- `0x7e20`
- `0x7e60`
- `0x7e90`

## pseudocode

```c

```

## disassembly

```asm
0x7600  ldsfld   string [mscorlib]System.String::Empty
0x7605  pop
0x7606  newobj   instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings::.ctor()
0x760b  dup
0x760c  ldarg.2
0x760d  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_DeliveryExtension()
0x7612  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings::set_Extension(string)
0x7617  dup
0x7618  ldarg.0
0x7619  ldarg.2
0x761a  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_ExtensionSettings()
0x761f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings::get_ParameterValues()
0x7624  call     instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSoapParameterValueOfFieldReferences(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> parameters)
0x7629  callvirt instance void [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings::set_ParameterValues(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference[])
0x762e  stloc.0
0x762f  ldarg.2
0x7630  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_IsDataDriven()
0x7635  brfalse.s loc_7686
0x7637  ldarg.0
0x7638  ldarg.1
0x7639  ldarg.2
0x763a  call     instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetDataRetrievalPlan(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription subscription)
0x763f  stloc.1
0x7640  ldarg.0
0x7641  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x7646  ldarg.1
0x7647  ldarg.2
0x7648  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Report()
0x764d  ldloc.0
0x764e  ldloc.1
0x764f  ldarg.2
0x7650  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Description()
0x7655  ldarg.2
0x7656  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_EventType()
0x765b  ldarg.0
0x765c  ldarg.2
0x765d  call     instance string Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetMatchData(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription subscription)
0x7662  ldarg.0
0x7663  ldarg.2
0x7664  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_ParameterValues()
0x7669  ldarg.0
0x766a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x766f  ldarg.1
0x7670  ldarg.2
0x7671  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Report()
0x7676  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::GetParameterTypes(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x767b  call     instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSoapParameterValuesOrFieldReference(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> parameters, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> parameterTypes)
0x7680  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::CreateDataDrivenSubscription(class [mscorlib]System.Security.Principal.IPrincipal, string, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan, string, string, string, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference[])
0x7685  ret
0x7686  ldarg.0
0x7687  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x768c  ldarg.1
0x768d  ldarg.2
0x768e  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Report()
0x7693  ldloc.0
0x7694  ldarg.2
0x7695  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Description()
0x769a  ldarg.2
0x769b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_EventType()
0x76a0  ldarg.0
0x76a1  ldarg.2
0x76a2  call     instance string Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetMatchData(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription subscription)
0x76a7  ldarg.0
0x76a8  ldarg.2
0x76a9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_ParameterValues()
0x76ae  ldarg.0
0x76af  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::_soapRS2010Proxy
0x76b4  ldarg.1
0x76b5  ldarg.2
0x76b6  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::get_Report()
0x76bb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::GetParameterTypes(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x76c0  call     instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue[] Microsoft.ReportingServices.Portal.Repositories.SubscriptionService::GetSoapParameterValues(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> parameters, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> parameterTypes)
0x76c5  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.ISoapRS2010Proxy::CreateSubscription(class [mscorlib]System.Security.Principal.IPrincipal, string, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings, string, string, string, class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValue[])
0x76ca  ret
```
