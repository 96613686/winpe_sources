# Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToWebApiModel

- ea: `0xfbf0`
- end: `0xfd8d`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToWebApiModel`
- size: `413`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7560`
- `0x1d640`
- `0x1f7f0`

## callees

- `0xe530`
- `0xfbf0`
- `0x10120`
- `0x102c0`
- `0x102e0`

## pseudocode

```c

```

## disassembly

```asm
0xfbf0  ldarg.0
0xfbf1  brtrue.s loc_FBFE
0xfbf3  ldstr    aLibrarysubscri// "librarySubscription"
0xfbf8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfbfd  throw
0xfbfe  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::.ctor()
0xfc03  dup
0xfc04  ldarg.0
0xfc05  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0xfc0a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Id(valuetype [mscorlib]System.Guid)
0xfc0f  dup
0xfc10  ldarg.0
0xfc11  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_Description()
0xfc16  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Description(string)
0xfc1b  dup
0xfc1c  ldarg.0
0xfc1d  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::IsActive()
0xfc22  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_IsActive(bool)
0xfc27  dup
0xfc28  ldarg.0
0xfc29  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_EventType()
0xfc2e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_EventType(string)
0xfc33  dup
0xfc34  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::.ctor()
0xfc39  dup
0xfc3a  ldarg.0
0xfc3b  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_SubscriptionData()
0xfc40  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ScheduleDefinitionFromScheduleRef(string matchData)
0xfc45  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::set_ScheduleID(string)
0xfc4a  dup
0xfc4b  ldarg.0
0xfc4c  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_SubscriptionData()
0xfc51  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ScheduleDefinitionFromMatchData(string matchData)
0xfc56  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::set_Definition(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition)
0xfc5b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Schedule(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference)
0xfc60  dup
0xfc61  ldarg.0
0xfc62  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastRunTime()
0xfc67  stloc.0
0xfc68  ldloca.s 0
0xfc6a  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xfc6f  brfalse.s loc_FC83
0xfc71  ldarg.0
0xfc72  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastRunTime()
0xfc77  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xfc7c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0xfc81  br.s     loc_FC8C
0xfc83  ldloca.s 1
0xfc85  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0xfc8b  ldloc.1
0xfc8c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_LastRunTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0xfc91  dup
0xfc92  ldarg.2
0xfc93  brtrue.s loc_FC98
0xfc95  ldnull
0xfc96  br.s     loc_FCAA
0xfc98  ldarg.2
0xfc99  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.SubscriptionProperties::ExtensionSettings
0xfc9e  dup
0xfc9f  brtrue.s loc_FCA5
0xfca1  pop
0xfca2  ldnull
0xfca3  br.s     loc_FCAA
0xfca5  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionSettingsExtensions::ToWebApiModel(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings soapExtensionSettings)
0xfcaa  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ExtensionSettings(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings)
0xfcaf  dup
0xfcb0  ldarg.2
0xfcb1  brtrue.s loc_FCB6
0xfcb3  ldnull
0xfcb4  br.s     loc_FCC8
0xfcb6  ldarg.2
0xfcb7  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.SubscriptionProperties::ExtensionSettings
0xfcbc  dup
0xfcbd  brtrue.s loc_FCC3
0xfcbf  pop
0xfcc0  ldnull
0xfcc1  br.s     loc_FCC8
0xfcc3  call     instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings::get_Extension()
0xfcc8  dup
0xfcc9  brtrue.s loc_FCD2
0xfccb  pop
0xfccc  ldarg.0
0xfccd  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_DeliveryExtension()
0xfcd2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_DeliveryExtension(string)
0xfcd7  dup
0xfcd8  ldarg.0
0xfcd9  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ReportName()
0xfcde  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Report(string)
0xfce3  dup
0xfce4  ldarg.0
0xfce5  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0xfcea  dup
0xfceb  brtrue.s loc_FCF1
0xfced  pop
0xfcee  ldnull
0xfcef  br.s     loc_FCF6
0xfcf1  call     instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0xfcf6  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Owner(string)
0xfcfb  dup
0xfcfc  ldarg.0
0xfcfd  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedBy()
0xfd02  dup
0xfd03  brtrue.s loc_FD09
0xfd05  pop
0xfd06  ldnull
0xfd07  br.s     loc_FD0E
0xfd09  call     instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0xfd0e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ModifiedBy(string)
0xfd13  dup
0xfd14  ldarg.0
0xfd15  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedDate()
0xfd1a  stloc.0
0xfd1b  ldloca.s 0
0xfd1d  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xfd22  brfalse.s loc_FD36
0xfd24  ldarg.0
0xfd25  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedDate()
0xfd2a  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xfd2f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0xfd34  br.s     loc_FD3F
0xfd36  ldloca.s 1
0xfd38  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0xfd3e  ldloc.1
0xfd3f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ModifiedDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0xfd44  dup
0xfd45  ldarg.0
0xfd46  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastStatus()
0xfd4b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_LastStatus(string)
0xfd50  dup
0xfd51  ldarg.0
0xfd52  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::IsDataDriven()
0xfd57  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_IsDataDriven(bool)
0xfd5c  dup
0xfd5d  ldnull
0xfd5e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_DataSource(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource)
0xfd63  dup
0xfd64  ldnull
0xfd65  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_DataQuery(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Query)
0xfd6a  dup
0xfd6b  ldarg.0
0xfd6c  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::m_parameters
0xfd71  brtrue.s loc_FD7A
0xfd73  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>::.ctor()
0xfd78  br.s     loc_FD87
0xfd7a  ldarg.0
0xfd7b  ldarg.1
0xfd7c  ldarg.0
0xfd7d  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_Culture()
0xfd82  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToReportPameterList(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl librarySubscription, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> parameterTypes, string culture)
0xfd87  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ParameterValues(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>)
0xfd8c  ret
```
