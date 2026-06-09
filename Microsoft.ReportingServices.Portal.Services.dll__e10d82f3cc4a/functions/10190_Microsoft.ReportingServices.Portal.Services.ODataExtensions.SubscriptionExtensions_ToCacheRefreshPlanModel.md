# Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToCacheRefreshPlanModel

- ea: `0x10190`
- end: `0x102b3`
- name: `Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToCacheRefreshPlanModel`
- size: `291`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7b90`
- `0x1d210`
- `0x1d690`

## callees

- `0x10120`
- `0x10190`
- `0x102c0`
- `0x102e0`

## pseudocode

```c

```

## disassembly

```asm
0x10190  ldarg.0
0x10191  brtrue.s loc_1019E
0x10193  ldstr    aLibrarysubscri// "librarySubscription"
0x10198  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1019d  throw
0x1019e  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::.ctor()
0x101a3  dup
0x101a4  ldarg.0
0x101a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0x101aa  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_Id(valuetype [mscorlib]System.Guid)
0x101af  dup
0x101b0  ldarg.0
0x101b1  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_Description()
0x101b6  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_Description(string)
0x101bb  dup
0x101bc  ldarg.0
0x101bd  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_EventType()
0x101c2  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_EventType(string)
0x101c7  dup
0x101c8  ldarg.0
0x101c9  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ReportName()
0x101ce  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_CatalogItemPath(string)
0x101d3  dup
0x101d4  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::.ctor()
0x101d9  dup
0x101da  ldarg.0
0x101db  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_SubscriptionData()
0x101e0  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ScheduleDefinitionFromMatchData(string matchData)
0x101e5  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::set_Definition(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleDefinition)
0x101ea  dup
0x101eb  ldarg.0
0x101ec  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_SubscriptionData()
0x101f1  call     string Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ScheduleDefinitionFromScheduleRef(string matchData)
0x101f6  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference::set_ScheduleID(string)
0x101fb  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_Schedule(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ScheduleReference)
0x10200  dup
0x10201  ldarg.0
0x10202  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastRunTime()
0x10207  stloc.0
0x10208  ldloca.s 0
0x1020a  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1020f  brfalse.s loc_10223
0x10211  ldarg.0
0x10212  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastRunTime()
0x10217  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0x1021c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0x10221  br.s     loc_1022C
0x10223  ldloca.s 1
0x10225  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0x1022b  ldloc.1
0x1022c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_LastRunTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0x10231  dup
0x10232  ldarg.0
0x10233  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x10238  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x1023d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_Owner(string)
0x10242  dup
0x10243  ldarg.0
0x10244  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedBy()
0x10249  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x1024e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_ModifiedBy(string)
0x10253  dup
0x10254  ldarg.0
0x10255  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedDate()
0x1025a  stloc.0
0x1025b  ldloca.s 0
0x1025d  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x10262  brfalse.s loc_10276
0x10264  ldarg.0
0x10265  callvirt instance valuetype [mscorlib]System.DateTime [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedDate()
0x1026a  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0x1026f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>::.ctor(var<u1>)
0x10274  br.s     loc_1027F
0x10276  ldloca.s 1
0x10278  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>
0x1027e  ldloc.1
0x1027f  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_ModifiedDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset>)
0x10284  dup
0x10285  ldarg.0
0x10286  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastStatus()
0x1028b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_LastStatus(string)
0x10290  dup
0x10291  ldarg.0
0x10292  ldfld    class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::m_parameters
0x10297  brtrue.s loc_102A0
0x10299  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>::.ctor()
0x1029e  br.s     loc_102AD
0x102a0  ldarg.0
0x102a1  ldarg.1
0x102a2  ldarg.0
0x102a3  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl::get_Culture()
0x102a8  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue> Microsoft.ReportingServices.Portal.Services.ODataExtensions.SubscriptionExtensions::ToReportPameterList(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SubscriptionImpl librarySubscription, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterType> parameterTypes, string culture)
0x102ad  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.CacheRefreshPlan::set_ParameterValues(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>)
0x102b2  ret
```
