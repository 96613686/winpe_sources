# Microsoft.ReportingServices.Library.DataDrivenSubscriptionHandler::DataDrivenSubscriptionWorker

- ea: `0x3d10`
- end: `0x446a`
- name: `Microsoft.ReportingServices.Library.DataDrivenSubscriptionHandler::DataDrivenSubscriptionWorker`
- size: `1882`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x24c0`
- `0x24d0`
- `0x2650`
- `0x26e0`
- `0x2720`
- `0x3840`
- `0x3890`
- `0x3ab0`
- `0x3ac0`
- `0x3d10`
- `0xc340`
- `0xc440`
- `0xc500`
- `0xc560`
- `0xc810`
- `0x157f0`
- `0x19730`
- `0x197a0`
- `0x19b50`
- `0x1bb70`
- `0x1e400`
- `0x1e460`
- `0x500e0`
- `0x51fe0`
- `0x51ff0`
- `0x52160`
- `0x52650`
- `0x52660`
- `0x52670`
- `0x526a0`
- `0x52840`
- `0x52870`
- `0x52a20`
- `0x53040`
- `0x54e80`
- `0x70f40`

## string_xrefs

- `0x3dd5`: `Handling data-driven subscription {0} to report {1}, owner: {2}, delivery extension: {3}.`
- `0x3fff`: `Data Driven subscription not found.  It may have been deleted before the event was processed`
- `0x4282`: `Data Driven Subscription {0} has been deleted. Stopping further subscription processing and generating notifications.`

## pseudocode

```c

```

## disassembly

```asm
0x3d10  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d15  stloc.0
0x3d16  ldarg.1
0x3d17  unbox.any [mscorlib]System.Guid
0x3d1c  stloc.0
0x3d1d  newobj   instance void Microsoft.ReportingServices.Library.SubscriptionDB::.ctor()
0x3d22  stloc.1
0x3d23  ldloc.1
0x3d24  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x3d29  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x3d2e  ldloc.1
0x3d2f  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x3d34  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x3d39  ldloc.1
0x3d3a  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x3d3f  newobj   instance void Microsoft.ReportingServices.Library.ActiveSubscription::.ctor(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager connManager)
0x3d44  stloc.2
0x3d45  ldnull
0x3d46  stloc.3
0x3d47  ldnull
0x3d48  stloc.s  4
0x3d4a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d4f  stloc.s  5
0x3d51  ldloc.1
0x3d52  ldloc.0
0x3d53  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_SubscriptionPending()
0x3d58  callvirt instance void Microsoft.ReportingServices.Library.SubscriptionDB::UpdateSubscriptionStatus(valuetype [mscorlib]System.Guid id, string status)
0x3d5d  ldloc.1
0x3d5e  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Commit()
0x3d63  leave.s  loc_3D6E
0x3d65  pop
0x3d66  ldloc.1
0x3d67  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::AbortTransaction()
0x3d6c  rethrow
0x3d6e  ldnull
0x3d6f  stloc.s  6
0x3d71  ldnull
0x3d72  stloc.s  7
0x3d74  ldnull
0x3d75  stloc.s  8
0x3d77  ldnull
0x3d78  stloc.s  9
0x3d7a  ldnull
0x3d7b  stloc.s  0xA
0x3d7d  newobj   instance void Microsoft.ReportingServices.Library.SubscriptionDB::.ctor()
0x3d82  stloc.s  9
0x3d84  ldloc.s  9
0x3d86  ldc.i4.1
0x3d87  ldc.i4   0x1000
0x3d8c  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x3d91  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x3d96  ldloc.s  9
0x3d98  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x3d9d  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x3da2  ldloc.s  9
0x3da4  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x3da9  newobj   instance void Microsoft.ReportingServices.Library.ActiveSubscription::.ctor(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager connManager)
0x3dae  stloc.s  0xE
0x3db0  ldc.i4.0
0x3db1  newobj   instance void Microsoft.ReportingServices.Library.RSService::.ctor(bool checkSecurity)
0x3db6  stloc.3
0x3db7  ldloc.s  9
0x3db9  ldloc.0
0x3dba  ldloc.3
0x3dbb  ldc.i4.0
0x3dbc  callvirt instance class Microsoft.ReportingServices.Library.SubscriptionImpl Microsoft.ReportingServices.Library.SubscriptionDB::GetSubscription(valuetype [mscorlib]System.Guid id, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator pathTranslator, bool isCacheRefreshPlanExpected)
0x3dc1  stloc.s  4
0x3dc3  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x3dc8  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x3dcd  brfalse.s loc_3E17
0x3dcf  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x3dd4  ldc.i4.3
0x3dd5  ldstr    aHandlingDataDr// "Handling data-driven subscription {0} t"...
0x3dda  ldc.i4.4
0x3ddb  newarr   [mscorlib]System.Object
0x3de0  dup
0x3de1  ldc.i4.0
0x3de2  ldloc.s  4
0x3de4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0x3de9  box      [mscorlib]System.Guid
0x3dee  stelem.ref
0x3def  dup
0x3df0  ldc.i4.1
0x3df1  ldloc.s  4
0x3df3  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.SubscriptionImpl::get_ItemPath()
0x3df8  stelem.ref
0x3df9  dup
0x3dfa  ldc.i4.2
0x3dfb  ldloc.s  4
0x3dfd  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x3e02  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x3e07  stelem.ref
0x3e08  dup
0x3e09  ldc.i4.3
0x3e0a  ldloc.s  4
0x3e0c  callvirt instance string Microsoft.ReportingServices.Library.SubscriptionImpl::get_DeliveryExtension()
0x3e11  stelem.ref
0x3e12  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x3e17  ldc.i4.1
0x3e18  newarr   [mscorlib]System.String
0x3e1d  dup
0x3e1e  ldc.i4.0
0x3e1f  ldloc.s  4
0x3e21  callvirt instance string Microsoft.ReportingServices.Library.SubscriptionImpl::get_Culture()
0x3e26  stelem.ref
0x3e27  ldc.i4.0
0x3e28  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::SetCultureFromPriorityList(string[], bool)
0x3e2d  ldloc.s  4
0x3e2f  callvirt instance bool Microsoft.ReportingServices.Library.SubscriptionImpl::IsDataDriven()
0x3e34  brtrue.s loc_3E6C
0x3e36  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x3e3b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x3e40  brfalse.s loc_3E67
0x3e42  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x3e47  ldc.i4.1
0x3e48  ldstr    aNonDataDrivenS// "Non data driven subscription {0} passed"...
0x3e4d  ldc.i4.1
0x3e4e  newarr   [mscorlib]System.Object
0x3e53  dup
0x3e54  ldc.i4.0
0x3e55  ldloc.s  4
0x3e57  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0x3e5c  box      [mscorlib]System.Guid
0x3e61  stelem.ref
0x3e62  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x3e67  leave    loc_4469
0x3e6c  ldloc.s  4
0x3e6e  callvirt instance bool Microsoft.ReportingServices.Library.SubscriptionImpl::IsActive()
0x3e73  brtrue.s loc_3E9A
0x3e75  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x3e7a  ldc.i4.2
0x3e7b  ldstr    aSkippingProces// "Skipping processing data driven subscri"...
0x3e80  ldc.i4.1
0x3e81  newarr   [mscorlib]System.Object
0x3e86  dup
0x3e87  ldc.i4.0
0x3e88  ldloc.s  4
0x3e8a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0x3e8f  box      [mscorlib]System.Guid
0x3e94  stelem.ref
0x3e95  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x3e9a  ldloc.s  4
0x3e9c  callvirt instance string Microsoft.ReportingServices.Library.SubscriptionImpl::get_DeliveryExtension()
0x3ea1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3ea6  brtrue.s loc_3EC0
0x3ea8  ldloc.s  4
0x3eaa  callvirt instance string Microsoft.ReportingServices.Library.SubscriptionImpl::get_DeliveryExtension()
0x3eaf  ldstr    aDelivery// "Delivery"
0x3eb4  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetNewInstanceExtensionClass(string, string)
0x3eb9  castclass [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension
0x3ebe  stloc.s  0xA
0x3ec0  ldloc.s  0xA
0x3ec2  brtrue.s loc_3ECA
0x3ec4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.DeliveryExtensionNotFoundException::.ctor()
0x3ec9  throw
0x3eca  ldloc.s  4
0x3ecc  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x3ed1  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x3ed6  ldloc.s  4
0x3ed8  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_Owner()
0x3edd  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x3ee2  ldloc.s  4
0x3ee4  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ReportName()
0x3ee9  newobj   instance void Microsoft.ReportingServices.Library.RSService::.ctor(string userName, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType, string scopeUrl)
0x3eee  stloc.3
0x3eef  ldloc.3
0x3ef0  ldloc.s  9
0x3ef2  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x3ef7  callvirt instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager connectionManager)
0x3efc  call     void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CachedSystemProperties::InvalidateCache()
0x3f01  ldloc.3
0x3f02  newobj   instance void Microsoft.ReportingServices.Library.SubscriptionManager::.ctor(class Microsoft.ReportingServices.Library.RSService service)
0x3f07  ldloc.s  4
0x3f09  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.SubscriptionImpl::m_itemName
0x3f0e  ldloc.s  4
0x3f10  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SubscriptionImpl::m_parameters
0x3f15  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobType::get_SystemJobType()
0x3f1a  callvirt instance class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SubscriptionManager::ValidateSubscriptionParameters(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath reportName, class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] subscriptionParameters, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobType jobType)
0x3f1f  pop
0x3f20  ldloc.3
0x3f21  ldloc.s  4
0x3f23  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo Microsoft.ReportingServices.Library.SubscriptionImpl::m_dataSource
0x3f28  ldloc.3
0x3f29  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessing/CreateDataExtensionInstance Microsoft.ReportingServices.Library.RSService::get_HowToCreateDataExtensionInstance()
0x3f2e  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection Microsoft.ReportingServices.Library.RSService::OpenDataSourceConnection(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourceInfo dataSourceInfo, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessing/CreateDataExtensionInstance createDataExtensionInstanceFunction)
0x3f33  stloc.s  6
0x3f35  newobj   instance void Microsoft.ReportingServices.Library.DataSet::.ctor()
0x3f3a  stloc.s  7
0x3f3c  ldloc.s  7
0x3f3e  ldloc.s  4
0x3f40  ldfld    class Microsoft.ReportingServices.Library.Soap.DataSetDefinition Microsoft.ReportingServices.Library.SubscriptionImpl::m_dataSet
0x3f45  callvirt instance void Microsoft.ReportingServices.Library.DataSet::FromSoapDataSet(class Microsoft.ReportingServices.Library.Soap.DataSetDefinition soapDataSet)
0x3f4a  ldloc.s  6
0x3f4c  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection::CreateCommand()
0x3f51  stloc.s  0xF
0x3f53  ldloc.s  0xF
0x3f55  ldloc.s  7
0x3f57  ldfld    class Microsoft.ReportingServices.Library.Query Microsoft.ReportingServices.Library.DataSet::Query
0x3f5c  ldfld    string Microsoft.ReportingServices.Library.Query::CommandText
0x3f61  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand::set_CommandText(string)
0x3f66  ldloc.s  0xF
0x3f68  ldc.i4.1
0x3f69  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand::set_CommandType(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.CommandType)
0x3f6e  ldloc.s  0xF
0x3f70  ldloc.s  7
0x3f72  ldfld    class Microsoft.ReportingServices.Library.Query Microsoft.ReportingServices.Library.DataSet::Query
0x3f77  ldfld    int32 Microsoft.ReportingServices.Library.Query::Timeout
0x3f7c  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand::set_CommandTimeout(int32)
0x3f81  ldloc.s  0xF
0x3f83  ldc.i4.1
0x3f84  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReader [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbCommand::ExecuteReader(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.CommandBehavior)
0x3f89  stloc.s  8
0x3f8b  ldloc.s  8
0x3f8d  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDataReader::get_FieldCount()
0x3f92  brtrue.s loc_3FC0
0x3f94  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f99  ldstr    aDataDrivenSubs_0// "Data-driven subscription {0} query did "...
0x3f9e  ldloc.0
0x3f9f  box      [mscorlib]System.Guid
0x3fa4  ldloc.s  4
0x3fa6  ldfld    class Microsoft.ReportingServices.Library.Soap.DataSetDefinition Microsoft.ReportingServices.Library.SubscriptionImpl::m_dataSet
0x3fab  ldfld    class Microsoft.ReportingServices.Library.Soap.QueryDefinition Microsoft.ReportingServices.Library.Soap.DataSetDefinition::Query
0x3fb0  ldfld    string Microsoft.ReportingServices.Library.Soap.QueryDefinition::CommandText
0x3fb5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x3fba  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CannotPrepareQueryException::.ctor(string)
0x3fbf  throw
0x3fc0  leave.s  loc_3FCE
0x3fc2  ldloc.s  0xF
0x3fc4  brfalse.s loc_3FCD
0x3fc6  ldloc.s  0xF
0x3fc8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3fcd  endfinally
0x3fce  ldloc.s  4
0x3fd0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3fd5  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SubscriptionImpl::m_lastRunTime
0x3fda  ldloc.s  0xE
0x3fdc  ldloc.0
0x3fdd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.ActiveSubscription::CreateNewActiveSubscription(valuetype [mscorlib]System.Guid subscriptionID)
0x3fe2  stloc.s  5
0x3fe4  leave.s  loc_4032
0x3fe6  pop
0x3fe7  ldloc.1
0x3fe8  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::AbortTransaction()
0x3fed  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x3ff2  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x3ff7  brfalse.s loc_4009
0x3ff9  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x3ffe  ldc.i4.3
0x3fff  ldstr    aDataDrivenSubs_1// "Data Driven subscription not found.  It"...
0x4004  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x4009  ldloc.s  6
0x400b  brfalse.s loc_4014
0x400d  ldloc.s  6
0x400f  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.DataProcessing.IDbConnection::Close()
0x4014  ldloc.s  8
0x4016  brfalse.s loc_401F
0x4018  ldloc.s  8
0x401a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x401f  leave    loc_4469
0x4024  pop
0x4025  ldloc.s  8
0x4027  brfalse.s loc_4030
0x4029  ldloc.s  8
0x402b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4030  rethrow
0x4032  leave.s  loc_4053
0x4034  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::Reset()
0x4039  ldloc.s  9
0x403b  brfalse.s loc_4052
0x403d  ldloc.s  9
0x403f  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x4044  brfalse.s loc_4052
0x4046  ldloc.s  9
0x4048  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x404d  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x4052  endfinally
0x4053  newobj   instance void Microsoft.ReportingServices.Library.Settings::.ctor()
0x4058  stloc.s  0xB
0x405a  ldloc.s  0xB
0x405c  ldloc.s  4
0x405e  ldfld    class Microsoft.ReportingServices.Library.Soap.ExtensionSettings Microsoft.ReportingServices.Library.SubscriptionImpl::m_extensionSettings
0x4063  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.Soap.ExtensionSettings::ParameterValues
0x4068  callvirt instance void Microsoft.ReportingServices.Library.Settings::FromSoapParameterValueArray(class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] parameters)
0x406d  ldloc.s  0xA
0x406f  ldc.i4.1
0x4070  ldnull
0x4071  ldnull
0x4072  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Library.ProviderManager::InitDeliveryExtension(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension extension, bool isPrivileged, class Microsoft.ReportingServices.Library.RSService rsService, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0x4077  stloc.s  0x10
0x4079  ldc.i4.0
0x407a  stloc.s  0x11
0x407c  br.s     loc_40B0
0x407e  ldloc.s  0x10
0x4080  ldloc.s  0x11
0x4082  ldelem.ref
0x4083  stloc.s  0x12
0x4085  ldloc.s  0x12
0x4087  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Encrypted()
0x408c  brfalse.s loc_40AA
0x408e  ldloc.s  0xB
  ... truncated ...
```
