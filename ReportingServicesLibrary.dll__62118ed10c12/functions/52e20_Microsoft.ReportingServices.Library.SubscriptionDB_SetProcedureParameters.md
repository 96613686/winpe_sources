# Microsoft.ReportingServices.Library.SubscriptionDB::SetProcedureParameters

- ea: `0x52e20`
- end: `0x53025`
- name: `Microsoft.ReportingServices.Library.SubscriptionDB::SetProcedureParameters`
- size: `517`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x527a0`
- `0x52840`

## callees

- `0xf570`
- `0x51fb0`
- `0x51ff0`
- `0x52610`
- `0x52e20`
- `0x70f40`
- `0x734e0`

## string_xrefs

- `0x52f8d`: `@ExtensionSettings`
- `0x52ea7`: `@DeliveryExtension`
- `0x52e42`: `@OwnerSid`
- `0x52edc`: `@ModifiedBySid`

## pseudocode

```c

```

## disassembly

```asm
0x52e20  ldarg.1
0x52e21  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52e26  ldstr    aId_0// "@id"
0x52e2b  ldarg.2
0x52e2c  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SubscriptionImpl::m_id
0x52e31  box      [mscorlib]System.Guid
0x52e36  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52e3b  pop
0x52e3c  ldarg.1
0x52e3d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52e42  ldstr    aOwnersid// "@OwnerSid"
0x52e47  ldarg.2
0x52e48  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x52e4d  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x52e52  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52e57  pop
0x52e58  ldarg.1
0x52e59  ldstr    aOwnername// "@OwnerName"
0x52e5e  ldc.i4.s 0xC
0x52e60  ldarg.2
0x52e61  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x52e66  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x52e6b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52e70  pop
0x52e71  ldarg.1
0x52e72  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52e77  ldstr    aOwnerauthtype// "@OwnerAuthType"
0x52e7c  ldarg.2
0x52e7d  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x52e82  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x52e87  box      [mscorlib]System.Int32
0x52e8c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52e91  pop
0x52e92  ldarg.1
0x52e93  ldstr    aLocale// "@Locale"
0x52e98  ldc.i4.s 0xC
0x52e9a  ldarg.2
0x52e9b  ldfld    string Microsoft.ReportingServices.Library.SubscriptionImpl::m_subscriptionCulture
0x52ea0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52ea5  pop
0x52ea6  ldarg.1
0x52ea7  ldstr    aDeliveryextens// "@DeliveryExtension"
0x52eac  ldc.i4.s 0xC
0x52eae  ldarg.2
0x52eaf  callvirt instance string Microsoft.ReportingServices.Library.SubscriptionImpl::get_DeliveryExtension()
0x52eb4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52eb9  pop
0x52eba  ldarg.1
0x52ebb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52ec0  ldstr    aInactiveflags// "@InactiveFlags"
0x52ec5  ldarg.2
0x52ec6  ldfld    valuetype Microsoft.ReportingServices.Library.InActiveFlags Microsoft.ReportingServices.Library.SubscriptionImpl::m_inactiveFlags
0x52ecb  box      [mscorlib]System.Int32
0x52ed0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52ed5  pop
0x52ed6  ldarg.1
0x52ed7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52edc  ldstr    aModifiedbysid// "@ModifiedBySid"
0x52ee1  ldarg.2
0x52ee2  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedBy()
0x52ee7  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x52eec  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52ef1  pop
0x52ef2  ldarg.1
0x52ef3  ldstr    aModifiedbyname// "@ModifiedByName"
0x52ef8  ldc.i4.s 0xC
0x52efa  ldarg.2
0x52efb  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedBy()
0x52f00  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x52f05  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52f0a  pop
0x52f0b  ldarg.1
0x52f0c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52f11  ldstr    aModifiedbyauth// "@ModifiedByAuthType"
0x52f16  ldarg.2
0x52f17  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SubscriptionImpl::get_ModifiedBy()
0x52f1c  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x52f21  box      [mscorlib]System.Int32
0x52f26  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52f2b  pop
0x52f2c  ldarg.1
0x52f2d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x52f32  ldstr    aModifieddate// "@ModifiedDate"
0x52f37  ldarg.2
0x52f38  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SubscriptionImpl::m_modifiedDate
0x52f3d  box      [mscorlib]System.DateTime
0x52f42  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x52f47  pop
0x52f48  ldarg.1
0x52f49  ldstr    aDescription// "@Description"
0x52f4e  ldc.i4.s 0xC
0x52f50  ldarg.2
0x52f51  ldfld    string Microsoft.ReportingServices.Library.SubscriptionImpl::m_description
0x52f56  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52f5b  pop
0x52f5c  ldarg.1
0x52f5d  ldstr    aLaststatus// "@LastStatus"
0x52f62  ldc.i4.s 0xC
0x52f64  ldarg.2
0x52f65  callvirt instance string Microsoft.ReportingServices.Library.SubscriptionImpl::get_LastStatus()
0x52f6a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52f6f  pop
0x52f70  ldarg.1
0x52f71  ldstr    aEventtype_0// "@EventType"
0x52f76  ldc.i4.s 0xC
0x52f78  ldarg.2
0x52f79  ldfld    string Microsoft.ReportingServices.Library.SubscriptionImpl::m_eventType
0x52f7e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52f83  pop
0x52f84  ldarg.2
0x52f85  ldfld    class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SubscriptionImpl::m_extensionSettings
0x52f8a  brfalse.s loc_52FAA
0x52f8c  ldarg.1
0x52f8d  ldstr    aExtensionsetti// "@ExtensionSettings"
0x52f92  ldc.i4.s 0xB
0x52f94  ldarg.2
0x52f95  ldfld    class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SubscriptionImpl::m_extensionSettings
0x52f9a  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ParameterValues
0x52f9f  call     string Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::ThisArrayToXml(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x52fa4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52fa9  pop
0x52faa  ldarg.2
0x52fab  ldfld    string Microsoft.ReportingServices.Library.SubscriptionImpl::m_matchData
0x52fb0  brfalse.s loc_52FC6
0x52fb2  ldarg.1
0x52fb3  ldstr    aMatchdata_0// "@MatchData"
0x52fb8  ldc.i4.s 0xB
0x52fba  ldarg.2
0x52fbb  ldfld    string Microsoft.ReportingServices.Library.SubscriptionImpl::m_matchData
0x52fc0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52fc5  pop
0x52fc6  ldarg.2
0x52fc7  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SubscriptionImpl::m_parameters
0x52fcc  brfalse.s loc_52FE7
0x52fce  ldarg.1
0x52fcf  ldstr    aParameters// "@Parameters"
0x52fd4  ldc.i4.s 0xB
0x52fd6  ldarg.2
0x52fd7  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SubscriptionImpl::m_parameters
0x52fdc  call     string Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference::ThisArrayToXml(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x52fe1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x52fe6  pop
0x52fe7  ldarg.2
0x52fe8  ldfld    class Microsoft.ReportingServices.Library.Soap.DataSetDefinition Microsoft.ReportingServices.Library.SubscriptionImpl::m_dataSet
0x52fed  brfalse.s loc_53008
0x52fef  ldarg.1
0x52ff0  ldstr    aDatasettings_1// "@DataSettings"
0x52ff5  ldc.i4.s 0xB
0x52ff7  ldarg.2
0x52ff8  ldfld    class Microsoft.ReportingServices.Library.Soap.DataSetDefinition Microsoft.ReportingServices.Library.SubscriptionImpl::m_dataSet
0x52ffd  call     string Microsoft.ReportingServices.Library.Soap.DataSetDefinition::ThisToXml(class Microsoft.ReportingServices.Library.Soap.DataSetDefinition dataSet)
0x53002  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x53007  pop
0x53008  ldarg.1
0x53009  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5300e  ldstr    aVersion// "@Version"
0x53013  ldarg.2
0x53014  ldfld    int32 Microsoft.ReportingServices.Library.SubscriptionImpl::m_version
0x53019  box      [mscorlib]System.Int32
0x5301e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x53023  pop
0x53024  ret
```
