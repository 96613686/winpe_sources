# Microsoft.ReportingServices.Library.SubscriptionManager::DeleteSubscription

- ea: `0x541f0`
- end: `0x54355`
- name: `Microsoft.ReportingServices.Library.SubscriptionManager::DeleteSubscription`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x44940`

## callees

- `0x1e2e0`
- `0x4a7e0`
- `0x52160`
- `0x52670`
- `0x526b0`
- `0x52a20`
- `0x530a0`
- `0x530c0`
- `0x541f0`
- `0x54ff0`

## string_xrefs

- `0x54267`: `SnapshotUpdated`
- `0x54325`: `Subscription {0} deleted at {1} by {2}`

## pseudocode

```c

```

## disassembly

```asm
0x541f0  ldarg.0
0x541f1  ldfld    class Microsoft.ReportingServices.Library.SubscriptionDB Microsoft.ReportingServices.Library.SubscriptionManager::m_db
0x541f6  ldarg.1
0x541f7  ldarg.0
0x541f8  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.SubscriptionManager::m_service
0x541fd  ldarg.2
0x541fe  callvirt instance class Microsoft.ReportingServices.Library.SubscriptionImpl Microsoft.ReportingServices.Library.SubscriptionDB::GetSubscription(valuetype [mscorlib]System.Guid id, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator pathTranslator, bool isCacheRefreshPlanExpected)
0x54203  stloc.0
0x54204  ldarg.2
0x54205  brfalse.s loc_54252
0x54207  ldloc.0
0x54208  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_EventType()
0x5420d  ldc.i4.5
0x5420e  stloc.1
0x5420f  ldloca.s 1
0x54211  constrained. Microsoft.ReportingServices.Library.ReportScheduleActions
0x54217  callvirt instance string [mscorlib]System.Object::ToString()
0x5421c  callvirt instance bool [mscorlib]System.String::Equals(string)
0x54221  brtrue.s loc_54252
0x54223  ldloc.0
0x54224  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_EventType()
0x54229  ldc.i4.8
0x5422a  stloc.1
0x5422b  ldloca.s 1
0x5422d  constrained. Microsoft.ReportingServices.Library.ReportScheduleActions
0x54233  callvirt instance string [mscorlib]System.Object::ToString()
0x54238  callvirt instance bool [mscorlib]System.String::Equals(string)
0x5423d  brtrue.s loc_54252
0x5423f  ldarga.s 1
0x54241  constrained. [mscorlib]System.Guid
0x54247  callvirt instance string [mscorlib]System.Object::ToString()
0x5424c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CacheRefreshPlanNotFoundException::.ctor(string)
0x54251  throw
0x54252  ldarg.2
0x54253  brtrue.s loc_5428C
0x54255  ldstr    aTimedsubscript// "TimedSubscription"
0x5425a  ldloc.0
0x5425b  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_EventType()
0x54260  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x54265  brfalse.s loc_5428C
0x54267  ldstr    aSnapshotupdate// "SnapshotUpdated"
0x5426c  ldloc.0
0x5426d  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_EventType()
0x54272  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x54277  brfalse.s loc_5428C
0x54279  ldarga.s 1
0x5427b  constrained. [mscorlib]System.Guid
0x54281  callvirt instance string [mscorlib]System.Object::ToString()
0x54286  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.SubscriptionNotFoundException::.ctor(string)
0x5428b  throw
0x5428c  ldarg.0
0x5428d  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.SubscriptionManager::m_service
0x54292  callvirt instance class Microsoft.ReportingServices.Library.Security Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0x54297  ldc.i4.2
0x54298  ldloc.0
0x54299  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.SubscriptionImpl::m_securityDesc
0x5429e  ldc.i4.s 0x10
0x542a0  ldloc.0
0x542a1  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.SubscriptionImpl::get_ItemPath()
0x542a6  callvirt instance bool Microsoft.ReportingServices.Library.Security::CheckAccess(valuetype Microsoft.ReportingServices.Library.ItemType catItemType, unsigned int8[] secDesc, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation rptOper, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath reportPath)
0x542ab  brtrue.s loc_54306
0x542ad  ldarg.0
0x542ae  ldloc.0
0x542af  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x542b4  ldarg.0
0x542b5  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SubscriptionManager::get_UserContext()
0x542ba  call     instance bool Microsoft.ReportingServices.Library.SubscriptionManager::IsSameUser(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user1, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user2)
0x542bf  brfalse.s loc_542F8
0x542c1  ldloc.0
0x542c2  callvirt instance bool Microsoft.ReportingServices.Library.SubscriptionImpl::IsDataDriven()
0x542c7  brtrue.s loc_542F8
0x542c9  ldarg.0
0x542ca  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.SubscriptionManager::m_service
0x542cf  callvirt instance class Microsoft.ReportingServices.Library.Security Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0x542d4  ldc.i4.2
0x542d5  ldloc.0
0x542d6  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.SubscriptionImpl::m_securityDesc
0x542db  ldc.i4.s 0xA
0x542dd  ldloc.0
0x542de  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.SubscriptionImpl::get_ItemPath()
0x542e3  callvirt instance bool Microsoft.ReportingServices.Library.Security::CheckAccess(valuetype Microsoft.ReportingServices.Library.ItemType catItemType, unsigned int8[] secDesc, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation rptOper, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath reportPath)
0x542e8  brtrue.s loc_54306
0x542ea  ldarg.0
0x542eb  call     instance string Microsoft.ReportingServices.Library.SubscriptionManager::get_UserName()
0x542f0  ldc.i4.s 0x59
0x542f2  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.AccessDeniedException::.ctor(string, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode)
0x542f7  throw
0x542f8  ldarg.0
0x542f9  call     instance string Microsoft.ReportingServices.Library.SubscriptionManager::get_UserName()
0x542fe  ldc.i4.s 0x59
0x54300  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.AccessDeniedException::.ctor(string, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode)
0x54305  throw
0x54306  ldarg.0
0x54307  ldfld    class Microsoft.ReportingServices.Library.SubscriptionDB Microsoft.ReportingServices.Library.SubscriptionManager::m_db
0x5430c  ldarg.1
0x5430d  callvirt instance void Microsoft.ReportingServices.Library.SubscriptionDB::DeleteSubscription(valuetype [mscorlib]System.Guid id)
0x54312  ldarg.0
0x54313  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SubscriptionManager::m_tracer
0x54318  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x5431d  brfalse.s loc_54354
0x5431f  ldarg.0
0x54320  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SubscriptionManager::m_tracer
0x54325  ldstr    aSubscription0D_0// "Subscription {0} deleted at {1} by {2}"
0x5432a  ldc.i4.3
0x5432b  newarr   [mscorlib]System.Object
0x54330  dup
0x54331  ldc.i4.0
0x54332  ldarg.1
0x54333  box      [mscorlib]System.Guid
0x54338  stelem.ref
0x54339  dup
0x5433a  ldc.i4.1
0x5433b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x54340  box      [mscorlib]System.DateTime
0x54345  stelem.ref
0x54346  dup
0x54347  ldc.i4.2
0x54348  ldarg.0
0x54349  call     instance string Microsoft.ReportingServices.Library.SubscriptionManager::get_UserName()
0x5434e  stelem.ref
0x5434f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x54354  ret
```
