# Microsoft.ReportingServices.Library.NotificationQueueWorker::HandleNotification

- ea: `0x11f60`
- end: `0x12405`
- name: `Microsoft.ReportingServices.Library.NotificationQueueWorker::HandleNotification`
- size: `1189`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x11f50`

## callees

- `0x11c20`
- `0x11d60`
- `0x11d70`
- `0x11f60`
- `0x157f0`
- `0x19730`
- `0x1c3a0`
- `0x1c3f0`
- `0x1e210`
- `0x1e3e0`
- `0x51bc0`
- `0x51be0`
- `0x54d80`
- `0x711a0`

## string_xrefs

- `0x12174`: `Extension {0} did not load, extension factory returned null`
- `0x12196`: `Extension {0} did not load, extension factory threw exception: {1}`
- `0x1223f`: `Handling subscription {0} to report {1}, owner: {2}, delivery extension: {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x11f60  ldarg.1
0x11f61  castclass Microsoft.ReportingServices.Library.NotificationQueueItem
0x11f66  stloc.0
0x11f67  ldloc.0
0x11f68  ldfld    class Microsoft.ReportingServices.Library.NotificationImpl Microsoft.ReportingServices.Library.NotificationQueueItem::Notification
0x11f6d  stloc.1
0x11f6e  ldloc.1
0x11f6f  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.NotificationImpl::get_Path()
0x11f74  brtrue.s loc_11F78
0x11f76  ldc.i4.1
0x11f77  ret
0x11f78  ldloc.1
0x11f79  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_Owner()
0x11f7e  ldloc.1
0x11f7f  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType Microsoft.ReportingServices.Library.NotificationImpl::get_AuthType()
0x11f84  ldloc.1
0x11f85  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.NotificationImpl::get_Path()
0x11f8a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x11f8f  newobj   instance void Microsoft.ReportingServices.Library.RSService::.ctor(string userName, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType, string scopeUrl)
0x11f94  stloc.2
0x11f95  ldloc.2
0x11f96  callvirt instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x11f9b  ldloc.0
0x11f9c  ldfld    class Microsoft.ReportingServices.Library.NotificationImpl Microsoft.ReportingServices.Library.NotificationQueueItem::Notification
0x11fa1  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_IsDataDriven()
0x11fa6  brfalse.s loc_11FE1
0x11fa8  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x11fad  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x11fb2  ldc.i4.s 0xD
0x11fb4  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures)
0x11fb9  brtrue.s loc_11FE1
0x11fbb  ldarg.0
0x11fbc  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.NotificationQueueWorker::m_tracer
0x11fc1  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x11fc6  brfalse.s loc_11FD9
0x11fc8  ldarg.0
0x11fc9  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.NotificationQueueWorker::m_tracer
0x11fce  ldc.i4.1
0x11fcf  ldstr    aDataDrivenNoti_0// "Data Driven notification found for inva"...
0x11fd4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x11fd9  ldc.i4.1
0x11fda  stloc.s  9
0x11fdc  leave    loc_12402
0x11fe1  ldc.i4.1
0x11fe2  newarr   [mscorlib]System.String
0x11fe7  dup
0x11fe8  ldc.i4.0
0x11fe9  ldloc.1
0x11fea  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_subscriptionLocale
0x11fef  stelem.ref
0x11ff0  ldc.i4.0
0x11ff1  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::SetCultureFromPriorityList(string[], bool)
0x11ff6  call     void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CachedSystemProperties::InvalidateCache()
0x11ffb  ldloc.2
0x11ffc  ldloc.1
0x11ffd  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.NotificationImpl::m_path
0x12002  ldloc.1
0x12003  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_parameters
0x12008  call     class Microsoft.ReportingServices.Library.Soap.ParameterValue[] Microsoft.ReportingServices.Library.Soap.ParameterValue::XmlToThisArray(string xml)
0x1200d  stloc.s  0xA
0x1200f  ldloc.s  0xA
0x12011  ldloc.1
0x12012  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_IsDataDriven()
0x12017  callvirt instance void Microsoft.ReportingServices.Library.RSService::ValidateSubscriptionParameters(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath path, class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] subscriptionParameters, bool isDataDriven)
0x1201c  leave    loc_120C0
0x12021  stloc.s  0xB
0x12023  newobj   instance void [mscorlib]System.Exception::.ctor()
0x12028  stloc.s  0xC
0x1202a  ldloc.s  0xB
0x1202c  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x12031  brfalse.s loc_1203C
0x12033  ldloc.s  0xB
0x12035  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x1203a  stloc.s  0xC
0x1203c  ldloc.0
0x1203d  ldc.i4.1
0x1203e  stfld    bool Microsoft.ReportingServices.Library.NotificationQueueItem::DeleteAsErrorForDataDrivenNotification
0x12043  ldloc.s  0xB
0x12045  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportParameterValueNotSetException
0x1204a  brtrue.s loc_12055
0x1204c  ldloc.s  0xC
0x1204e  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportParameterValueNotSetException
0x12053  brfalse.s loc_1205A
0x12055  ldc.i4.4
0x12056  stloc.s  0xD
0x12058  br.s     loc_1209D
0x1205a  ldloc.s  0xB
0x1205c  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportParameterTypeMismatchException
0x12061  brtrue.s loc_1207E
0x12063  ldloc.s  0xC
0x12065  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportParameterTypeMismatchException
0x1206a  brtrue.s loc_1207E
0x1206c  ldloc.s  0xB
0x1206e  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidReportParameterException
0x12073  brtrue.s loc_1207E
0x12075  ldloc.s  0xC
0x12077  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidReportParameterException
0x1207c  brfalse.s loc_12083
0x1207e  ldc.i4.8
0x1207f  stloc.s  0xD
0x12081  br.s     loc_1209D
0x12083  ldloc.s  0xB
0x12085  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownReportParameterException
0x1208a  brtrue.s loc_12095
0x1208c  ldloc.s  0xC
0x1208e  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownReportParameterException
0x12093  brfalse.s loc_1209B
0x12095  ldc.i4.s 0x10
0x12097  stloc.s  0xD
0x12099  br.s     loc_1209D
0x1209b  rethrow
0x1209d  ldloc.1
0x1209e  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_IsDataDriven()
0x120a3  brtrue.s loc_120B8
0x120a5  ldloc.2
0x120a6  ldloc.1
0x120a7  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.NotificationImpl::m_subscriptionID
0x120ac  ldloc.s  0xD
0x120ae  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_SubscriptionParametersInvalid()
0x120b3  callvirt instance void Microsoft.ReportingServices.Library.RSService::InvalidateSubscription(valuetype [mscorlib]System.Guid subscriptionID, valuetype Microsoft.ReportingServices.Library.InActiveFlags inactiveFlag, string status)
0x120b8  ldc.i4.1
0x120b9  stloc.s  9
0x120bb  leave    loc_12402
0x120c0  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParamValues::.ctor()
0x120c5  stloc.3
0x120c6  ldloc.3
0x120c7  ldloc.1
0x120c8  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_parameters
0x120cd  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParamValues::FromXml(string)
0x120d2  ldloc.1
0x120d3  ldloc.3
0x120d4  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParamValues::ToOldParameterXml()
0x120d9  stfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_parameters
0x120de  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x120e3  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_Extensions()
0x120e8  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration/ExtensionArray [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Delivery()
0x120ed  ldloc.1
0x120ee  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_deliveryExtension
0x120f3  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Extension [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration/ExtensionArray::get_Item(string)
0x120f8  castclass [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.DeliveryExtension
0x120fd  stloc.s  4
0x120ff  ldloc.s  4
0x12101  brtrue.s loc_12112
0x12103  ldloc.0
0x12104  ldc.i4.1
0x12105  stfld    bool Microsoft.ReportingServices.Library.NotificationQueueItem::DeleteAsErrorForDataDrivenNotification
0x1210a  ldc.i4.1
0x1210b  stloc.s  9
0x1210d  leave    loc_12402
0x12112  ldloc.0
0x12113  ldloc.s  4
0x12115  callvirt instance int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.DeliveryExtension::get_SecondsBeforeRetry()
0x1211a  stfld    int32 Microsoft.ReportingServices.Library.NotificationQueueItem::SecondsBeforeRetry
0x1211f  ldnull
0x12120  stloc.s  5
0x12122  ldnull
0x12123  stloc.s  6
0x12125  ldloc.1
0x12126  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_deliveryExtension
0x1212b  ldstr    aDelivery// "Delivery"
0x12130  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IExtension [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetNewInstanceExtensionClass(string, string)
0x12135  stloc.s  5
0x12137  leave.s  loc_12140
0x12139  stloc.s  6
0x1213b  ldnull
0x1213c  stloc.s  5
0x1213e  leave.s  loc_12140
0x12140  ldloc.s  5
0x12142  brtrue.s loc_121C1
0x12144  ldloc.1
0x12145  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_DeliveryExtensionFailedToLoad()
0x1214a  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Status(string)
0x1214f  ldloc.1
0x12150  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::Save()
0x12155  ldloc.0
0x12156  ldc.i4.1
0x12157  stfld    bool Microsoft.ReportingServices.Library.NotificationQueueItem::DeleteAsErrorForDataDrivenNotification
0x1215c  ldarg.0
0x1215d  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.NotificationQueueWorker::m_tracer
0x12162  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x12167  brfalse.s loc_121B9
0x12169  ldloc.s  6
0x1216b  brtrue.s loc_1218F
0x1216d  ldarg.0
0x1216e  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.NotificationQueueWorker::m_tracer
0x12173  ldc.i4.1
0x12174  ldstr    aExtension0DidN// "Extension {0} did not load, extension f"...
0x12179  ldc.i4.1
0x1217a  newarr   [mscorlib]System.Object
0x1217f  dup
0x12180  ldc.i4.0
0x12181  ldloc.1
0x12182  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_deliveryExtension
0x12187  stelem.ref
0x12188  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1218d  br.s     loc_121B9
0x1218f  ldarg.0
0x12190  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.NotificationQueueWorker::m_tracer
0x12195  ldc.i4.1
0x12196  ldstr    aExtension0DidN_0// "Extension {0} did not load, extension f"...
0x1219b  ldc.i4.2
0x1219c  newarr   [mscorlib]System.Object
0x121a1  dup
0x121a2  ldc.i4.0
0x121a3  ldloc.1
0x121a4  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_deliveryExtension
0x121a9  stelem.ref
0x121aa  dup
0x121ab  ldc.i4.1
0x121ac  ldloc.s  6
0x121ae  callvirt instance string [mscorlib]System.Object::ToString()
0x121b3  stelem.ref
0x121b4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x121b9  ldc.i4.1
0x121ba  stloc.s  9
0x121bc  leave    loc_12402
0x121c1  ldc.i4.0
0x121c2  stloc.s  7
0x121c4  ldloc.s  5
0x121c6  castclass [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension
0x121cb  stloc.s  8
0x121cd  ldloc.s  8
0x121cf  ldc.i4.1
0x121d0  ldloc.2
0x121d1  ldloc.1
0x121d2  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.NotificationImpl::get_Path()
0x121d7  call     class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Library.ProviderManager::InitDeliveryExtension(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension extension, bool isPrivileged, class Microsoft.ReportingServices.Library.RSService rsService, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath itemPath)
0x121dc  ldloc.1
0x121dd  ldflda   class Microsoft.ReportingServices.Library.Soap.ParameterValue[] Microsoft.ReportingServices.Library.NotificationImpl::m_extensionSettings
0x121e2  ldloc.1
0x121e3  callvirt instance int32 Microsoft.ReportingServices.Library.NotificationImpl::get_Version()
0x121e8  call     void Microsoft.ReportingServices.Library.SubscriptionManager::PrepareSubscriptionSettingsForUse(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settingsMetaData, class Microsoft.ReportingServices.Library.Soap.ParameterValue[]& values, int32 version)
0x121ed  ldloc.1
0x121ee  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_Attempt()
0x121f3  ldloc.s  4
0x121f5  callvirt instance int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.DeliveryExtension::get_MaxRetries()
0x121fa  ldc.i4.1
0x121fb  add
0x121fc  ble.s    loc_1220D
0x121fe  ldloc.0
0x121ff  ldc.i4.1
0x12200  stfld    bool Microsoft.ReportingServices.Library.NotificationQueueItem::DeleteAsErrorForDataDrivenNotification
0x12205  ldc.i4.1
0x12206  stloc.s  9
0x12208  leave    loc_12402
0x1220d  ldloc.1
0x1220e  ldloc.s  4
0x12210  callvirt instance int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.DeliveryExtension::get_MaxRetries()
0x12215  stfld    int32 Microsoft.ReportingServices.Library.NotificationImpl::m_maxRetries
0x1221a  ldarg.0
0x1221b  call     instance bool [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.PollWorker::get_ContinueWorking()
0x12220  brtrue.s loc_1222A
0x12222  ldc.i4.0
0x12223  stloc.s  9
0x12225  leave    loc_12402
0x1222a  nop
0x1222b  ldarg.0
0x1222c  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.NotificationQueueWorker::m_tracer
0x12231  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x12236  brfalse.s loc_1227D
0x12238  ldarg.0
0x12239  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.NotificationQueueWorker::m_tracer
0x1223e  ldc.i4.3
0x1223f  ldstr    aHandlingSubscr// "Handling subscription {0} to report {1}"...
0x12244  ldc.i4.4
0x12245  newarr   [mscorlib]System.Object
0x1224a  dup
0x1224b  ldc.i4.0
0x1224c  ldloc.1
0x1224d  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.NotificationImpl::m_subscriptionID
0x12252  box      [mscorlib]System.Guid
0x12257  stelem.ref
0x12258  dup
0x12259  ldc.i4.1
0x1225a  ldloc.1
0x1225b  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Report [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_Report()
0x12260  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Report::get_Name()
0x12265  stelem.ref
0x12266  dup
0x12267  ldc.i4.2
0x12268  ldloc.1
0x12269  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_Owner()
0x1226e  stelem.ref
0x1226f  dup
0x12270  ldc.i4.3
0x12271  ldloc.1
0x12272  ldfld    string Microsoft.ReportingServices.Library.NotificationImpl::m_deliveryExtension
0x12277  stelem.ref
0x12278  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1227d  ldloc.1
0x1227e  ldfld    class Microsoft.ReportingServices.Library.ReportImpl Microsoft.ReportingServices.Library.NotificationImpl::m_report
0x12283  callvirt instance void Microsoft.ReportingServices.Library.ReportImpl::OpenStreamFactory()
0x12288  ldloc.s  8
0x1228a  ldloc.1
0x1228b  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryExtension::Deliver(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification)
0x12290  stloc.s  7
0x12292  ldloc.s  7
0x12294  brtrue.s loc_122D1
0x12296  ldarg.0
0x12297  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.NotificationQueueWorker::m_tracer
  ... truncated ...
```
