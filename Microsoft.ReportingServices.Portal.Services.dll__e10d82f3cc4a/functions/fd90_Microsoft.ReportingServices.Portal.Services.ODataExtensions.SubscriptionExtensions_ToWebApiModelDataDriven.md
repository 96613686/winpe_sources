# Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToWebApiModelDataDriven

- ea: `0xfd90`
- end: `0xff72`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToWebApiModelDataDriven`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7560`

## callees

- `0xe3a0`
- `0xe530`
- `0xfd90`
- `0x10120`
- `0x102c0`
- `0x102e0`
- `0x11380`

## pseudocode

```c

```

## disassembly

```asm
0xfd90  ldarg.0
0xfd91  brtrue.s loc_FD9E
0xfd93  ldstr    aLibrarysubscri// "librarySubscription"
0xfd98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfd9d  throw
0xfd9e  ldarg.2
0xfd9f  brtrue.s loc_FDAC
0xfda1  ldstr    aProperties// "properties"
0xfda6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfdab  throw
0xfdac  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::.ctor()
0xfdb1  dup
0xfdb2  ldarg.0
0xfdb3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0xfdb8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Id(valuetype [mscorlib]System.Guid)
0xfdbd  dup
0xfdbe  ldarg.0
0xfdbf  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_Description()
0xfdc4  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Description(string)
0xfdc9  dup
0xfdca  ldarg.0
0xfdcb  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::IsActive()
0xfdd0  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_IsActive(bool)
0xfdd5  dup
0xfdd6  ldarg.0
0xfdd7  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_EventType()
0xfddc  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_EventType(string)
0xfde1  dup
0xfde2  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::.ctor()
0xfde7  dup
0xfde8  ldarg.0
0xfde9  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_SubscriptionData()
0xfdee  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ScheduleDefinitionFromMatchData(string matchData)
0xfdf3  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::set_Definition(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition)
0xfdf8  dup
0xfdf9  ldarg.0
0xfdfa  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_SubscriptionData()
0xfdff  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ScheduleDefinitionFromScheduleRef(string matchData)
0xfe04  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::set_ScheduleID(string)
0xfe09  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Schedule(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference)
0xfe0e  dup
0xfe0f  ldarg.0
0xfe10  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastRunTime()
0xfe15  stloc.0
0xfe16  ldloca.s 0
0xfe18  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xfe1d  brfalse.s loc_FE31
0xfe1f  ldarg.0
0xfe20  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastRunTime()
0xfe25  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xfe2a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0xfe2f  br.s     loc_FE3A
0xfe31  ldloca.s 1
0xfe33  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0xfe39  ldloc.1
0xfe3a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_LastRunTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0xfe3f  dup
0xfe40  ldarg.2
0xfe41  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::ExtensionSettings
0xfe46  brfalse.s loc_FE55
0xfe48  ldarg.2
0xfe49  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::ExtensionSettings
0xfe4e  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionSettingsExtensions::ToWebApiModel(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings soapExtensionSettings)
0xfe53  br.s     loc_FE56
0xfe55  ldnull
0xfe56  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ExtensionSettings(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings)
0xfe5b  dup
0xfe5c  ldarg.2
0xfe5d  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::ExtensionSettings
0xfe62  brfalse.s loc_FE71
0xfe64  ldarg.2
0xfe65  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::ExtensionSettings
0xfe6a  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings::get_Extension()
0xfe6f  br.s     loc_FE77
0xfe71  ldarg.0
0xfe72  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_DeliveryExtension()
0xfe77  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_DeliveryExtension(string)
0xfe7c  dup
0xfe7d  ldarg.0
0xfe7e  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ReportName()
0xfe83  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Report(string)
0xfe88  dup
0xfe89  ldarg.0
0xfe8a  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0xfe8f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0xfe94  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Owner(string)
0xfe99  dup
0xfe9a  ldarg.0
0xfe9b  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedBy()
0xfea0  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0xfea5  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ModifiedBy(string)
0xfeaa  dup
0xfeab  ldarg.0
0xfeac  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedDate()
0xfeb1  stloc.0
0xfeb2  ldloca.s 0
0xfeb4  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xfeb9  brfalse.s loc_FECD
0xfebb  ldarg.0
0xfebc  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedDate()
0xfec1  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xfec6  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0xfecb  br.s     loc_FED6
0xfecd  ldloca.s 1
0xfecf  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0xfed5  ldloc.1
0xfed6  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ModifiedDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0xfedb  dup
0xfedc  ldarg.0
0xfedd  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastStatus()
0xfee2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_LastStatus(string)
0xfee7  dup
0xfee8  ldarg.0
0xfee9  callvirt instance bool [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::IsDataDriven()
0xfeee  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_IsDataDriven(bool)
0xfef3  dup
0xfef4  ldarg.2
0xfef5  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::DataSettings
0xfefa  brfalse.s loc_FF09
0xfefc  ldarg.2
0xfefd  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::DataSettings
0xff02  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinitionOrReference [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::get_Item()
0xff07  brtrue.s loc_FF0C
0xff09  ldnull
0xff0a  br.s     loc_FF1C
0xff0c  ldarg.2
0xff0d  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::DataSettings
0xff12  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinitionOrReference [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::get_Item()
0xff17  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::ToDataSource(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSourceDefinitionOrReference dataSourceDefinitionOrReference)
0xff1c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_DataSource(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource)
0xff21  dup
0xff22  ldarg.2
0xff23  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::DataSettings
0xff28  brfalse.s loc_FF37
0xff2a  ldarg.2
0xff2b  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::DataSettings
0xff30  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::get_DataSet()
0xff35  brtrue.s loc_FF3A
0xff37  ldnull
0xff38  br.s     loc_FF4A
0xff3a  ldarg.2
0xff3b  ldfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.SoapProxy.DataDrivenSubscriptionProperties::DataSettings
0xff40  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan::get_DataSet()
0xff45  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.Query Microsoft.ReportingServices.Portal.Services.ODataExtensions.QueryExtensions::ToQueryDefinition(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataSetDefinition datasetDefinition)
0xff4a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_DataQuery(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Query)
0xff4f  dup
0xff50  ldarg.0
0xff51  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::m_parameters
0xff56  brtrue.s loc_FF5F
0xff58  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>::.ctor()
0xff5d  br.s     loc_FF6C
0xff5f  ldarg.0
0xff60  ldarg.1
0xff61  ldarg.0
0xff62  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_Culture()
0xff67  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToReportPameterList(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl librarySubscription, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> parameterTypes, string culture)
0xff6c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ParameterValues(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>)
0xff71  ret
```
