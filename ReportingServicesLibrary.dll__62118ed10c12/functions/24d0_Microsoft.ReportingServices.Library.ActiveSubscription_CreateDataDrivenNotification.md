# Microsoft.ReportingServices.Library.ActiveSubscription::CreateDataDrivenNotification

- ea: `0x24d0`
- end: `0x2649`
- name: `Microsoft.ReportingServices.Library.ActiveSubscription::CreateDataDrivenNotification`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x3d10`

## callees

- `0x24d0`
- `0xc5a0`
- `0xf570`
- `0x51ff0`
- `0x70f40`

## string_xrefs

- `0x255d`: `@ExtensionSettings`
- `0x24d1`: `CreateDataDrivenNotification`
- `0x25aa`: `@DeliveryExtension`
- `0x25c3`: `@OwnerSid`

## pseudocode

```c

```

## disassembly

```asm
0x24d0  ldarg.0
0x24d1  ldstr    aCreatedatadriv// "CreateDataDrivenNotification"
0x24d6  ldnull
0x24d7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x24dc  stloc.0
0x24dd  ldloc.0
0x24de  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x24e3  ldstr    aSubscriptionid// "@SubscriptionID"
0x24e8  ldarg.1
0x24e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0x24ee  box      [mscorlib]System.Guid
0x24f3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x24f8  pop
0x24f9  ldloc.0
0x24fa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x24ff  ldstr    aActiveationid// "@ActiveationID"
0x2504  ldarg.2
0x2505  box      [mscorlib]System.Guid
0x250a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x250f  pop
0x2510  ldloc.0
0x2511  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2516  ldstr    aReportid// "@ReportID"
0x251b  ldarg.1
0x251c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ItemID()
0x2521  box      [mscorlib]System.Guid
0x2526  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x252b  pop
0x252c  ldloc.0
0x252d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2532  ldstr    aReportzone// "@ReportZone"
0x2537  ldarg.1
0x2538  ldfld    int32 Microsoft.ReportingServices.Library.SubscriptionImpl::m_itemZone
0x253d  box      [mscorlib]System.Int32
0x2542  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2547  pop
0x2548  ldloc.0
0x2549  ldstr    aLocale// "@Locale"
0x254e  ldc.i4.s 0xC
0x2550  ldarg.1
0x2551  ldfld    string Microsoft.ReportingServices.Library.SubscriptionImpl::m_subscriptionCulture
0x2556  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x255b  pop
0x255c  ldloc.0
0x255d  ldstr    aExtensionsetti// "@ExtensionSettings"
0x2562  ldc.i4.s 0xB
0x2564  ldarg.3
0x2565  callvirt instance class Microsoft.ReportingServices.Library.Soap.ParameterValue[] Microsoft.ReportingServices.Library.Settings::ToSoapParameterValueArray()
0x256a  stloc.1
0x256b  ldloc.1
0x256c  call     string Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::ThisArrayToXml(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x2571  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x2576  pop
0x2577  ldloc.0
0x2578  ldstr    aParameters// "@Parameters"
0x257d  ldc.i4.s 0xB
0x257f  ldarg.s  4
0x2581  ldc.i4.0
0x2582  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParamValues::ToXml(bool)
0x2587  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x258c  pop
0x258d  ldloc.0
0x258e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2593  ldstr    aLastruntime// "@LastRunTime"
0x2598  ldarg.1
0x2599  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SubscriptionImpl::m_lastRunTime
0x259e  box      [mscorlib]System.DateTime
0x25a3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x25a8  pop
0x25a9  ldloc.0
0x25aa  ldstr    aDeliveryextens// "@DeliveryExtension"
0x25af  ldc.i4.s 0xC
0x25b1  ldarg.1
0x25b2  callvirt instance string Microsoft.ReportingServices.Library.SubscriptionImpl::get_DeliveryExtension()
0x25b7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x25bc  pop
0x25bd  ldloc.0
0x25be  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x25c3  ldstr    aOwnersid// "@OwnerSid"
0x25c8  ldarg.1
0x25c9  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x25ce  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x25d3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x25d8  ldc.i4.s 0x15
0x25da  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x25df  ldloc.0
0x25e0  ldstr    aOwnername// "@OwnerName"
0x25e5  ldc.i4.s 0xC
0x25e7  ldarg.1
0x25e8  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x25ed  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x25f2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x25f7  pop
0x25f8  ldloc.0
0x25f9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x25fe  ldstr    aOwnerauthtype// "@OwnerAuthType"
0x2603  ldarg.1
0x2604  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x2609  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x260e  box      [mscorlib]System.Int32
0x2613  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2618  pop
0x2619  ldloc.0
0x261a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x261f  ldstr    aVersion// "@Version"
0x2624  ldarg.1
0x2625  ldfld    int32 Microsoft.ReportingServices.Library.SubscriptionImpl::m_version
0x262a  box      [mscorlib]System.Int32
0x262f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2634  pop
0x2635  ldloc.0
0x2636  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x263b  pop
0x263c  leave.s  loc_2648
0x263e  ldloc.0
0x263f  brfalse.s loc_2647
0x2641  ldloc.0
0x2642  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2647  endfinally
0x2648  ret
```
