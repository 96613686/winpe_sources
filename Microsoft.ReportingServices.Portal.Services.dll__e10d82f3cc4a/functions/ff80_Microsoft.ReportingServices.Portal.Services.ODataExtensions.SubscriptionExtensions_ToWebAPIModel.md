# Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToWebAPIModel

- ea: `0xff80`
- end: `0x100ae`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToWebAPIModel`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1d200`

## callees

- `0xe530`
- `0xff80`
- `0x100b0`

## pseudocode

```c

```

## disassembly

```asm
0xff80  ldarg.0
0xff81  brtrue.s loc_FF8E
0xff83  ldstr    aProxysubscript// "proxySubscription"
0xff88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xff8d  throw
0xff8e  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::.ctor()
0xff93  dup
0xff94  ldarg.0
0xff95  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_SubscriptionID()
0xff9a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xff9f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Id(valuetype [mscorlib]System.Guid)
0xffa4  dup
0xffa5  ldarg.0
0xffa6  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_Description()
0xffab  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Description(string)
0xffb0  dup
0xffb1  ldarg.0
0xffb2  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ActiveState [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_Active()
0xffb7  call     bool Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::IsActive(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ActiveState activeState)
0xffbc  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_IsActive(bool)
0xffc1  dup
0xffc2  ldarg.0
0xffc3  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_EventType()
0xffc8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_EventType(string)
0xffcd  dup
0xffce  ldnull
0xffcf  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Schedule(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference)
0xffd4  dup
0xffd5  ldarg.0
0xffd6  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_LastExecuted()
0xffdb  stloc.0
0xffdc  ldloca.s 0
0xffde  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xffe3  brfalse.s loc_FFF7
0xffe5  ldarg.0
0xffe6  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_LastExecuted()
0xffeb  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xfff0  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0xfff5  br.s     loc_10000
0xfff7  ldloca.s 1
0xfff9  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0xffff  ldloc.1
0x10000  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_LastRunTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0x10005  dup
0x10006  ldarg.0
0x10007  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_DeliverySettings()
0x1000c  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings Microsoft.ReportingServices.Portal.Services.ODataExtensions.ExtensionSettingsExtensions::ToWebApiModel(class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings soapExtensionSettings)
0x10011  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ExtensionSettings(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExtensionSettings)
0x10016  dup
0x10017  ldarg.0
0x10018  callvirt instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_DeliverySettings()
0x1001d  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings::get_Extension()
0x10022  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_DeliveryExtension(string)
0x10027  dup
0x10028  ldarg.0
0x10029  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_Path()
0x1002e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Report(string)
0x10033  dup
0x10034  ldarg.0
0x10035  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_Owner()
0x1003a  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_Owner(string)
0x1003f  dup
0x10040  ldarg.0
0x10041  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_ModifiedBy()
0x10046  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ModifiedBy(string)
0x1004b  dup
0x1004c  ldarg.0
0x1004d  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_ModifiedDate()
0x10052  stloc.0
0x10053  ldloca.s 0
0x10055  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1005a  brfalse.s loc_1006E
0x1005c  ldarg.0
0x1005d  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_ModifiedDate()
0x10062  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0x10067  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0x1006c  br.s     loc_10077
0x1006e  ldloca.s 1
0x10070  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0x10076  ldloc.1
0x10077  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ModifiedDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0x1007c  dup
0x1007d  ldarg.0
0x1007e  callvirt instance string [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_Status()
0x10083  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_LastStatus(string)
0x10088  dup
0x10089  ldarg.0
0x1008a  callvirt instance bool [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Subscription::get_IsDataDriven()
0x1008f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_IsDataDriven(bool)
0x10094  dup
0x10095  ldnull
0x10096  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_DataSource(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource)
0x1009b  dup
0x1009c  ldnull
0x1009d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_DataQuery(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Query)
0x100a2  dup
0x100a3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>::.ctor()
0x100a8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Subscription::set_ParameterValues(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>)
0x100ad  ret
```
