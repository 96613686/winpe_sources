# Microsoft.ReportingServices.Library.CacheRefreshPlanHandler::PerformActionHandler

- ea: `0x58f30`
- end: `0x592d7`
- name: `Microsoft.ReportingServices.Library.CacheRefreshPlanHandler::PerformActionHandler`
- size: `935`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x197a0`
- `0x199e0`
- `0x1c3a0`
- `0x1c3f0`
- `0x1c440`
- `0x1d6f0`
- `0x1d8a0`
- `0x1e210`
- `0x1e370`
- `0x1e3e0`
- `0x1e460`
- `0x27ce0`
- `0x27d30`
- `0x3b500`
- `0x3b510`
- `0x3b530`
- `0x3b550`
- `0x3b5b0`
- `0x526a0`
- `0x52a20`
- `0x555a0`
- `0x58f30`
- `0x71100`

## string_xrefs

- `0x5902b`: `Updating cache for report {0}`
- `0x590aa`: `Updating cache for data  set {0}`

## pseudocode

```c

```

## disassembly

```asm
0x58f30  ldc.i4.0
0x58f31  newobj   instance void Microsoft.ReportingServices.Library.RSService::.ctor(bool checkSecurity)
0x58f36  stloc.0
0x58f37  ldloc.0
0x58f38  callvirt instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x58f3d  ldnull
0x58f3e  stloc.1
0x58f3f  ldc.i4.0
0x58f40  stloc.2
0x58f41  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_RefreshCachePlanSuccess()
0x58f46  stloc.3
0x58f47  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x58f4c  stloc.s  4
0x58f4e  call     void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.CachedSystemProperties::InvalidateCache()
0x58f53  ldarg.2
0x58f54  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x58f59  stloc.s  5
0x58f5b  br       loc_591B6
0x58f60  ldloc.s  5
0x58f62  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x58f67  castclass Microsoft.ReportingServices.Library.ItemScheduleAction
0x58f6c  stloc.s  6
0x58f6e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SubscriptionTracer()
0x58f73  ldloc.s  6
0x58f75  ldfld    valuetype Microsoft.ReportingServices.Library.ReportScheduleActions Microsoft.ReportingServices.Library.ItemScheduleAction::Action
0x58f7a  ldc.i4.5
0x58f7b  ceq
0x58f7d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x58f82  ldloc.s  6
0x58f84  ldfld    valuetype Microsoft.ReportingServices.Library.ItemType Microsoft.ReportingServices.Library.ItemScheduleAction::ItemType
0x58f89  ldloc.s  6
0x58f8b  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.ItemScheduleAction::ItemPath
0x58f90  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x58f95  call     void Microsoft.ReportingServices.Library.RSService::EnsureItemTypeIsReportOrDataSet(valuetype Microsoft.ReportingServices.Library.ItemType actualType, string path)
0x58f9a  newobj   instance void Microsoft.ReportingServices.Library.SubscriptionDB::.ctor()
0x58f9f  dup
0x58fa0  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x58fa5  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x58faa  dup
0x58fab  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x58fb0  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x58fb5  ldloc.s  6
0x58fb7  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.ItemScheduleAction::SubscriptionID
0x58fbc  ldloc.0
0x58fbd  ldc.i4.1
0x58fbe  callvirt instance class Microsoft.ReportingServices.Library.SubscriptionImpl Microsoft.ReportingServices.Library.SubscriptionDB::GetSubscription(valuetype [mscorlib]System.Guid id, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator pathTranslator, bool isCacheRefreshPlanExpected)
0x58fc3  stloc.1
0x58fc4  ldloc.0
0x58fc5  ldloc.0
0x58fc6  ldloc.s  6
0x58fc8  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.ItemScheduleAction::ItemPath
0x58fcd  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.RSService::CatalogToExternal(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath source)
0x58fd2  ldloc.1
0x58fd3  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SubscriptionImpl::m_parameters
0x58fd8  ldc.i4.0
0x58fd9  callvirt instance void Microsoft.ReportingServices.Library.RSService::ValidateSubscriptionParameters(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath path, class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] subscriptionParameters, bool isDataDriven)
0x58fde  ldloc.1
0x58fdf  ldfld    class Microsoft.ReportingServices.Library.Soap.ParameterValueOrFieldReference[] Microsoft.ReportingServices.Library.SubscriptionImpl::m_parameters
0x58fe4  castclass class Microsoft.ReportingServices.Library.Soap.ParameterValue[]
0x58fe9  call     class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Library.Soap.ParameterValue::ThisArrayToNameValueCollection(class Microsoft.ReportingServices.Library.Soap.ParameterValue[] parameters)
0x58fee  stloc.s  7
0x58ff0  ldc.i4.0
0x58ff1  newobj   instance void Microsoft.ReportingServices.Library.RSService::.ctor(bool checkSecurity)
0x58ff6  stloc.s  8
0x58ff8  ldloc.s  8
0x58ffa  newobj   instance void Microsoft.ReportingServices.Library.MemoryThenFileStreamFactory::.ctor()
0x58fff  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.RSService::SetStreamFactory(class Microsoft.ReportingServices.Library.StreamFactoryBase streamFactory)
0x59004  stloc.s  9
0x59006  ldc.i4.2
0x59007  ldloc.s  6
0x59009  ldfld    valuetype Microsoft.ReportingServices.Library.ItemType Microsoft.ReportingServices.Library.ItemScheduleAction::ItemType
0x5900e  beq.s    loc_5901A
0x59010  ldc.i4.4
0x59011  ldloc.s  6
0x59013  ldfld    valuetype Microsoft.ReportingServices.Library.ItemType Microsoft.ReportingServices.Library.ItemScheduleAction::ItemType
0x59018  bne.un.s loc_5908C
0x5901a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x5901f  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x59024  brfalse.s loc_59045
0x59026  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x5902b  ldstr    aUpdatingCacheF// "Updating cache for report {0}"
0x59030  ldc.i4.1
0x59031  newarr   [mscorlib]System.Object
0x59036  dup
0x59037  ldc.i4.0
0x59038  ldloc.s  6
0x5903a  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.ItemScheduleAction::ItemPath
0x5903f  stelem.ref
0x59040  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x59045  ldloc.s  8
0x59047  newobj   instance void Microsoft.ReportingServices.Library.UpdateReportCacheAction::.ctor(class Microsoft.ReportingServices.Library.RSService service)
0x5904c  dup
0x5904d  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x59052  ldloc.0
0x59053  ldloc.s  6
0x59055  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.ItemScheduleAction::ItemPath
0x5905a  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.RSService::CatalogToExternal(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath source)
0x5905f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x59064  callvirt instance void Microsoft.ReportingServices.Library.UpdateCacheActionParameters::set_ItemPath(string value)
0x59069  dup
0x5906a  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x5906f  ldloc.s  7
0x59071  callvirt instance void Microsoft.ReportingServices.Library.UpdateCacheActionParameters::set_Parameters(class [System]System.Collections.Specialized.NameValueCollection value)
0x59076  dup
0x59077  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x5907c  ldc.i4.1
0x5907d  callvirt instance void Microsoft.ReportingServices.Library.UpdateCacheActionParameters::set_JobType(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobTypeEnum value)
0x59082  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::Execute()
0x59087  br       loc_59198
0x5908c  ldc.i4.8
0x5908d  ldloc.s  6
0x5908f  ldfld    valuetype Microsoft.ReportingServices.Library.ItemType Microsoft.ReportingServices.Library.ItemScheduleAction::ItemType
0x59094  bne.un   loc_59198
0x59099  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x5909e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x590a3  brfalse.s loc_590C4
0x590a5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x590aa  ldstr    aUpdatingCacheF_0// "Updating cache for data  set {0}"
0x590af  ldc.i4.1
0x590b0  newarr   [mscorlib]System.Object
0x590b5  dup
0x590b6  ldc.i4.0
0x590b7  ldloc.s  6
0x590b9  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.ItemScheduleAction::ItemPath
0x590be  stelem.ref
0x590bf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x590c4  ldloc.s  8
0x590c6  newobj   instance void Microsoft.ReportingServices.Library.UpdateDataSetCacheAction::.ctor(class Microsoft.ReportingServices.Library.RSService service)
0x590cb  stloc.s  0xA
0x590cd  ldloc.s  0xA
0x590cf  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x590d4  ldloc.0
0x590d5  ldloc.s  6
0x590d7  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.ItemScheduleAction::ItemPath
0x590dc  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.RSService::CatalogToExternal(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath source)
0x590e1  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x590e6  callvirt instance void Microsoft.ReportingServices.Library.UpdateCacheActionParameters::set_ItemPath(string value)
0x590eb  ldloc.s  0xA
0x590ed  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x590f2  ldloc.s  7
0x590f4  callvirt instance void Microsoft.ReportingServices.Library.UpdateCacheActionParameters::set_Parameters(class [System]System.Collections.Specialized.NameValueCollection value)
0x590f9  ldloc.s  0xA
0x590fb  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x59100  ldc.i4.1
0x59101  callvirt instance void Microsoft.ReportingServices.Library.UpdateCacheActionParameters::set_JobType(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobTypeEnum value)
0x59106  ldloc.s  0xA
0x59108  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::Execute()
0x5910d  ldloc.s  8
0x5910f  newobj   instance void Microsoft.ReportingServices.Library.UpdateDataSetJsonCacheAction::.ctor(class Microsoft.ReportingServices.Library.RSService service)
0x59114  dup
0x59115  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x5911a  ldloc.s  0xA
0x5911c  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x59121  callvirt instance string Microsoft.ReportingServices.Library.UpdateCacheActionParameters::get_ItemPath()
0x59126  callvirt instance void Microsoft.ReportingServices.Library.UpdateCacheActionParameters::set_ItemPath(string value)
0x5912b  dup
0x5912c  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x59131  ldloc.s  7
0x59133  callvirt instance void Microsoft.ReportingServices.Library.UpdateCacheActionParameters::set_Parameters(class [System]System.Collections.Specialized.NameValueCollection value)
0x59138  dup
0x59139  callvirt instance var<u1> class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::get_ActionParameters()
0x5913e  ldc.i4.1
0x5913f  callvirt instance void Microsoft.ReportingServices.Library.UpdateCacheActionParameters::set_JobType(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobTypeEnum value)
0x59144  callvirt instance void class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.UpdateCacheActionParameters>::Execute()
0x59149  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x5914e  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x59153  ldc.i4.s 0x19
0x59155  call     bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures)
0x5915a  brfalse.s loc_59198
0x5915c  ldloc.s  8
0x5915e  callvirt instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x59163  ldloc.s  8
0x59165  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.EventManager Microsoft.ReportingServices.Library.RSService::get_EventManager()
0x5916a  ldloc.s  6
0x5916c  ldfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.ItemScheduleAction::ItemID
0x59171  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.EventManager::FireSharedDatasetCacheUpdate(valuetype [mscorlib]System.Guid)
0x59176  leave.s  loc_5918E
0x59178  stloc.s  0xB
0x5917a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x5917f  ldc.i4.1
0x59180  ldloc.s  0xB
0x59182  callvirt instance string [mscorlib]System.Exception::get_Message()
0x59187  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::TraceException(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5918c  leave.s  loc_5918E
0x5918e  leave.s  loc_59198
0x59190  ldloc.s  8
0x59192  callvirt instance void Microsoft.ReportingServices.Library.RSService::DisconnectStorage()
0x59197  endfinally
0x59198  leave.s  loc_591A6
0x5919a  ldloc.s  9
0x5919c  brfalse.s loc_591A5
0x5919e  ldloc.s  9
0x591a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x591a5  endfinally
0x591a6  ldloc.0
0x591a7  ldloc.1
0x591a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0x591ad  ldloc.2
0x591ae  ldloc.s  4
0x591b0  ldloc.3
0x591b1  callvirt instance void Microsoft.ReportingServices.Library.RSService::UpdateSubscriptionLastRunInfo(valuetype [mscorlib]System.Guid subscriptionID, valuetype Microsoft.ReportingServices.Library.InActiveFlags stateFlag, valuetype [mscorlib]System.DateTime lastRunTime, string status)
0x591b6  ldloc.s  5
0x591b8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x591bd  brtrue   loc_58F60
0x591c2  leave.s  loc_591D9
0x591c4  ldloc.s  5
0x591c6  isinst   [mscorlib]System.IDisposable
0x591cb  stloc.s  9
0x591cd  ldloc.s  9
0x591cf  brfalse.s loc_591D8
0x591d1  ldloc.s  9
0x591d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x591d8  endfinally
0x591d9  leave    loc_592D6
0x591de  stloc.s  0xC
0x591e0  ldloc.1
0x591e1  brtrue.s loc_591E5
0x591e3  rethrow
0x591e5  newobj   instance void [mscorlib]System.Exception::.ctor()
0x591ea  stloc.s  0xD
0x591ec  ldloc.s  0xC
0x591ee  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x591f3  brfalse.s loc_591FE
0x591f5  ldloc.s  0xC
0x591f7  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x591fc  stloc.s  0xD
0x591fe  ldloc.s  0xC
0x59200  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportParameterValueNotSetException
0x59205  brtrue.s loc_59210
0x59207  ldloc.s  0xD
0x59209  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportParameterValueNotSetException
0x5920e  brfalse.s loc_5921D
0x59210  ldc.i4.4
0x59211  stloc.2
0x59212  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_RefreshCachePlanParametersInvalid()
0x59217  stloc.3
0x59218  br       loc_592BA
0x5921d  ldloc.s  0xC
0x5921f  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportParameterTypeMismatchException
0x59224  brtrue.s loc_59241
0x59226  ldloc.s  0xD
0x59228  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportParameterTypeMismatchException
0x5922d  brtrue.s loc_59241
0x5922f  ldloc.s  0xC
0x59231  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidReportParameterException
0x59236  brtrue.s loc_59241
0x59238  ldloc.s  0xD
0x5923a  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidReportParameterException
0x5923f  brfalse.s loc_5924B
0x59241  ldc.i4.8
0x59242  stloc.2
0x59243  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_RefreshCachePlanParametersInvalid()
0x59248  stloc.3
0x59249  br.s     loc_592BA
0x5924b  ldloc.s  0xC
0x5924d  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownReportParameterException
0x59252  brtrue.s loc_5925D
0x59254  ldloc.s  0xD
0x59256  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownReportParameterException
0x5925b  brfalse.s loc_59268
0x5925d  ldc.i4.s 0x10
0x5925f  stloc.2
0x59260  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_RefreshCachePlanParametersInvalid()
0x59265  stloc.3
0x59266  br.s     loc_592BA
0x59268  ldloc.s  0xC
0x5926a  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceReferenceException
0x5926f  brtrue.s loc_5927A
0x59271  ldloc.s  0xD
0x59273  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidDataSourceReferenceException
0x59278  brfalse.s loc_59290
0x5927a  ldloc.1
0x5927b  dup
0x5927c  ldfld    valuetype Microsoft.ReportingServices.Library.InActiveFlags Microsoft.ReportingServices.Library.SubscriptionImpl::m_inactiveFlags
0x59281  ldc.i4.2
0x59282  or
0x59283  stfld    valuetype Microsoft.ReportingServices.Library.InActiveFlags Microsoft.ReportingServices.Library.SubscriptionImpl::m_inactiveFlags
0x59288  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_RefreshCachePlanSharedDataSourceRemoved()
0x5928d  stloc.3
0x5928e  br.s     loc_592BA
0x59290  ldloc.s  0xC
0x59292  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CachingNotEnabledException
0x59297  brtrue.s loc_592A2
0x59299  ldloc.s  0xD
0x5929b  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.CachingNotEnabledException
0x592a0  brfalse.s loc_592AD
0x592a2  ldc.i4.s 0x40
0x592a4  stloc.2
0x592a5  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::get_RefreshCachePlanCachingIsNotEnabled()
0x592aa  stloc.3
0x592ab  br.s     loc_592BA
0x592ad  ldloc.s  0xC
0x592af  callvirt instance string [mscorlib]System.Exception::get_Message()
0x592b4  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.RepLibRes::RefreshCachePlanError(string)
0x592b9  stloc.3
0x592ba  ldloc.0
0x592bb  ldloc.1
0x592bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.Subscription::get_ID()
0x592c1  ldloc.2
0x592c2  ldloc.3
  ... truncated ...
```
