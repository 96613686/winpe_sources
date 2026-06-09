# Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::DoTaskCore

- ea: `0x214820`
- end: `0x2152e3`
- name: `Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::DoTaskCore`
- size: `2755`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2147b0`

## callees

- `0x206830`
- `0x206840`
- `0x206850`
- `0x206860`
- `0x206880`
- `0x208810`
- `0x210fd0`
- `0x211010`
- `0x211030`
- `0x211070`
- `0x211080`
- `0x211090`
- `0x211230`
- `0x211e70`
- `0x2136d0`
- `0x213720`
- `0x214820`
- `0x2152f0`
- `0x215390`
- `0x2155c0`
- `0x232050`
- `0x25c460`
- `0x269af0`
- `0x3192a0`
- `0x320eb0`
- `0x372780`
- `0x373560`
- `0x4e2e10`
- `0x4e2f20`
- `0x5966b0`
- `0x5b2a40`
- `0x7b57a0`
- `0x7be4d0`
- `0x7be4f0`
- `0x7be510`
- `0x7be540`
- `0x7be580`
- `0x7beb40`
- `0x8ecdb0`
- `0x93d4f0`
- `0x93dae0`
- `0x957770`

## string_xrefs

- `0x21492d`: `TaskId`
- `0x214c24`: `TaskId`
- `0x214d28`: `TaskId`
- `0x214e79`: `TaskId`
- `0x214fe5`: `TaskId`
- `0x215202`: `TaskId`
- `0x21496a`: `IsRollback`
- `0x214c61`: `IsRollback`
- `0x214d65`: `IsRollback`
- `0x214eb6`: `IsRollback`
- `0x215022`: `IsRollback`
- `0x21523f`: `IsRollback`
- `0x2149cf`: `Starting operation {3} task {0} of type {2} retry {1} IsRollback {4} sitesubscription {5}`
- `0x214a52`: `MonitoredTaskExecution - ExecuteTaskOperation - {0} - {1}`
- `0x214b12`: `operation {4} task {0} of type {3} in job {2} was successful on retry {1}`
- `0x214ca3`: `Exception while logging app usage. Suppressing to keep from raising to timer service. This exception is possible if site is deleted as new SPSite() will throw. Details: {0}`
- `0x214d97`: `operation {4} task {0} of type {3} in job {2} was not successful on retry {1}`
- `0x214f03`: `operation {4} task {0} of type {3} in job {2} returned an async handle on retry {1}`
- `0x21508b`: `AppLifeCycleTaskExecutionException`
- `0x2150da`: `Exception while executing task {0} of type {3} in job {2} for instance {4} sitesubscription {6}, rollback = {5}: {1}`
- `0x2152aa`: `Exception while logging a failure. Suppressing to keep from raising to timer service. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x214820  ldstr    aApplifecycleev// "AppLifecycleEvent"
0x214825  ldc.i4   0x120735E
0x21482a  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x21482f  ldc.i4   0x120735F
0x214834  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x214839  ldc.i4   0x1207360
0x21483e  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x214843  ldc.i4.1
0x214844  ldnull
0x214845  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x21484a  stloc.0
0x21484b  ldarg.0
0x21484c  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214851  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214856  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Lifecycle.Task::get_JobId()
0x21485b  ldc.i4.s 0xA
0x21485d  newobj   instance void Microsoft.SharePoint.Utilities.SPAsyncThreadDiagnosticsContext::.ctor(valuetype [mscorlib]System.Guid correlationId, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel traceLevel)
0x214862  stloc.1
0x214863  ldarg.0
0x214864  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214869  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x21486e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Lifecycle.Task::get_SiteSubscriptionId()
0x214873  stloc.2
0x214874  ldloc.2
0x214875  newobj   instance void Microsoft.SharePoint.SPSiteSubscriptionIdentifier::.ctor(valuetype [mscorlib]System.Guid siteSubscriptionId)
0x21487a  stloc.3
0x21487b  ldarg.0
0x21487c  ldfld    class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::database
0x214881  callvirt instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPContentDatabase::get_WebApplication()
0x214886  callvirt instance class Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup Microsoft.SharePoint.Administration.SPWebApplication::get_ServiceApplicationProxyGroup()
0x21488b  stloc.s  4
0x21488d  ldloc.s  4
0x21488f  ldloc.3
0x214890  call     class Microsoft.SharePoint.SPServiceContext Microsoft.SharePoint.SPServiceContext::GetContext(class Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup serviceApplicationProxyGroup, class Microsoft.SharePoint.SPSiteSubscriptionIdentifier siteSubscriptionId)
0x214895  stloc.s  5
0x214897  ldarg.0
0x214898  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x21489d  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x2148a2  ldarg.0
0x2148a3  ldfld    class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::database
0x2148a8  newobj   instance void Microsoft.SharePoint.Lifecycle.TaskContext::.ctor(class Microsoft.SharePoint.Lifecycle.Task t, class Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase)
0x2148ad  stloc.s  0x16
0x2148af  ldloc.s  5
0x2148b1  newobj   instance void Microsoft.SharePoint.SPServiceContextScope::.ctor(class Microsoft.SharePoint.SPServiceContext context)
0x2148b6  stloc.s  0x17
0x2148b8  ldarg.0
0x2148b9  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x2148be  callvirt instance valuetype Microsoft.SharePoint.Administration.SPAppTaskOperation Microsoft.SharePoint.Administration.SPAppTask::get_Operation()
0x2148c3  box      Microsoft.SharePoint.Administration.SPAppTaskOperation
0x2148c8  callvirt instance string [mscorlib]System.Object::ToString()
0x2148cd  stloc.s  6
0x2148cf  ldstr    aApplifecycleop// "AppLifeCycleOperationStart"
0x2148d4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2148d9  stloc.s  0x10
0x2148db  ldloc.s  0x10
0x2148dd  ldstr    aOperation_0// "Operation"
0x2148e2  ldloc.s  6
0x2148e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2148e9  ldloc.s  0x10
0x2148eb  ldstr    aJobid_0// "JobId"
0x2148f0  ldarg.0
0x2148f1  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x2148f6  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x2148fb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Lifecycle.Task::get_JobId()
0x214900  box      [mscorlib]System.Guid
0x214905  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x21490a  ldloc.s  0x10
0x21490c  ldstr    aRetries// "Retries"
0x214911  ldarg.0
0x214912  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214917  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x21491c  callvirt instance int32 Microsoft.SharePoint.Lifecycle.Task::get_Retries()
0x214921  box      [mscorlib]System.Int32
0x214926  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x21492b  ldloc.s  0x10
0x21492d  ldstr    aTaskid_0// "TaskId"
0x214932  ldarg.0
0x214933  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214938  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPAppTask::get_TaskId()
0x21493d  box      [mscorlib]System.Guid
0x214942  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x214947  ldloc.s  0x10
0x214949  ldstr    aType// "Type"
0x21494e  ldarg.0
0x21494f  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214954  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214959  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x21495e  callvirt instance string [mscorlib]System.Type::get_FullName()
0x214963  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x214968  ldloc.s  0x10
0x21496a  ldstr    aIsrollback_0// "IsRollback"
0x21496f  ldarg.0
0x214970  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214975  callvirt instance bool Microsoft.SharePoint.Administration.SPAppTask::get_IsRollback()
0x21497a  box      [mscorlib]System.Boolean
0x21497f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x214984  ldloc.s  0x10
0x214986  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x21498b  ldstr    aAccsrvUsername// "AccSrv UserName"
0x214990  ldarg.0
0x214991  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214996  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x21499b  callvirt instance class Microsoft.SharePoint.SPUser Microsoft.SharePoint.Lifecycle.Task::get_User()
0x2149a0  brfalse.s loc_2149B9
0x2149a2  ldarg.0
0x2149a3  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x2149a8  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x2149ad  callvirt instance class Microsoft.SharePoint.SPUser Microsoft.SharePoint.Lifecycle.Task::get_User()
0x2149b2  callvirt instance string Microsoft.SharePoint.SPUser::get_Email()
0x2149b7  br.s     loc_2149BE
0x2149b9  ldstr    aNull_2// "null"
0x2149be  call     void Microsoft.SharePoint.Diagnostics.ULS::CorrelationAdd(string key, string value)
0x2149c3  ldc.i4   0xC1449
0x2149c8  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x2149cd  ldc.i4.s 0x32
0x2149cf  ldstr    aStartingOperat// "Starting operation {3} task {0} of type"...
0x2149d4  ldc.i4.6
0x2149d5  newarr   [mscorlib]System.Object
0x2149da  stloc.s  0x18
0x2149dc  ldloc.s  0x18
0x2149de  ldc.i4.0
0x2149df  ldarg.0
0x2149e0  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x2149e5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPAppTask::get_TaskId()
0x2149ea  box      [mscorlib]System.Guid
0x2149ef  stelem.ref
0x2149f0  ldloc.s  0x18
0x2149f2  ldc.i4.1
0x2149f3  ldarg.0
0x2149f4  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x2149f9  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x2149fe  callvirt instance int32 Microsoft.SharePoint.Lifecycle.Task::get_Retries()
0x214a03  box      [mscorlib]System.Int32
0x214a08  stelem.ref
0x214a09  ldloc.s  0x18
0x214a0b  ldc.i4.2
0x214a0c  ldarg.0
0x214a0d  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214a12  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214a17  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x214a1c  callvirt instance string [mscorlib]System.Type::get_FullName()
0x214a21  stelem.ref
0x214a22  ldloc.s  0x18
0x214a24  ldc.i4.3
0x214a25  ldloc.s  6
0x214a27  stelem.ref
0x214a28  ldloc.s  0x18
0x214a2a  ldc.i4.4
0x214a2b  ldarg.0
0x214a2c  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214a31  callvirt instance bool Microsoft.SharePoint.Administration.SPAppTask::get_IsRollback()
0x214a36  box      [mscorlib]System.Boolean
0x214a3b  stelem.ref
0x214a3c  ldloc.s  0x18
0x214a3e  ldc.i4.5
0x214a3f  ldloc.2
0x214a40  box      [mscorlib]System.Guid
0x214a45  stelem.ref
0x214a46  ldloc.s  0x18
0x214a48  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x214a4d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x214a52  ldstr    aMonitoredtaske// "MonitoredTaskExecution - ExecuteTaskOpe"...
0x214a57  ldc.i4.2
0x214a58  newarr   [mscorlib]System.Object
0x214a5d  stloc.s  0x19
0x214a5f  ldloc.s  0x19
0x214a61  ldc.i4.0
0x214a62  ldarg.0
0x214a63  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214a68  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214a6d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x214a72  callvirt instance string [mscorlib]System.Type::get_FullName()
0x214a77  stelem.ref
0x214a78  ldloc.s  0x19
0x214a7a  ldc.i4.1
0x214a7b  ldarg.0
0x214a7c  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214a81  callvirt instance valuetype Microsoft.SharePoint.Administration.SPAppTaskOperation Microsoft.SharePoint.Administration.SPAppTask::get_Operation()
0x214a86  box      Microsoft.SharePoint.Administration.SPAppTaskOperation
0x214a8b  stelem.ref
0x214a8c  ldloc.s  0x19
0x214a8e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x214a93  ldc.i4.s 0x32
0x214a95  ldnull
0x214a96  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x214a9b  stloc.s  0x1A
0x214a9d  ldc.i4.1
0x214a9e  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.SPEventExecutionScope::CreateEventExecutionExceptionTrackingScope(bool eventExceptionTrackingEnabled)
0x214aa3  stloc.s  0x1B
0x214aa5  ldarg.0
0x214aa6  call     class Microsoft.SharePoint.SPEventExecutionScopeData Microsoft.SharePoint.SPEventExecutionScopeData::get_Current()
0x214aab  stfld    class Microsoft.SharePoint.SPEventExecutionScopeData Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::eventExecutionScopeData
0x214ab0  ldarg.0
0x214ab1  ldarg.0
0x214ab2  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214ab7  callvirt instance class Microsoft.SharePoint.Lifecycle.TaskSuccess Microsoft.SharePoint.Administration.SPAppTask::ExecuteOperation()
0x214abc  stfld    class Microsoft.SharePoint.Lifecycle.TaskSuccess Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::taskSuccess
0x214ac1  leave.s  loc_214ACF
0x214ac3  ldloc.s  0x1B
0x214ac5  brfalse.s loc_214ACE
0x214ac7  ldloc.s  0x1B
0x214ac9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x214ace  endfinally
0x214acf  leave.s  loc_214ADD
0x214ad1  ldloc.s  0x1A
0x214ad3  brfalse.s loc_214ADC
0x214ad5  ldloc.s  0x1A
0x214ad7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x214adc  endfinally
0x214add  ldarg.0
0x214ade  ldfld    class Microsoft.SharePoint.Lifecycle.TaskSuccess Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::taskSuccess
0x214ae3  isinst   Microsoft.SharePoint.Lifecycle.BooleanTaskSuccess
0x214ae8  stloc.s  7
0x214aea  ldloc.s  7
0x214aec  brfalse  loc_214EF7
0x214af1  ldloc.s  7
0x214af3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.SharePoint.Lifecycle.TaskSuccess::GetSuccess()
0x214af8  stloc.s  8
0x214afa  ldloca.s 8
0x214afc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x214b01  brfalse  loc_214D8B
0x214b06  ldc.i4   0x6D713676
0x214b0b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x214b10  ldc.i4.s 0x32
0x214b12  ldstr    aOperation4Task// "operation {4} task {0} of type {3} in j"...
0x214b17  ldc.i4.5
0x214b18  newarr   [mscorlib]System.Object
0x214b1d  stloc.s  0x1C
0x214b1f  ldloc.s  0x1C
0x214b21  ldc.i4.0
0x214b22  ldarg.0
0x214b23  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214b28  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPAppTask::get_TaskId()
0x214b2d  box      [mscorlib]System.Guid
0x214b32  stelem.ref
0x214b33  ldloc.s  0x1C
0x214b35  ldc.i4.1
0x214b36  ldarg.0
0x214b37  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214b3c  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214b41  callvirt instance int32 Microsoft.SharePoint.Lifecycle.Task::get_Retries()
0x214b46  box      [mscorlib]System.Int32
0x214b4b  stelem.ref
0x214b4c  ldloc.s  0x1C
0x214b4e  ldc.i4.2
0x214b4f  ldarg.0
0x214b50  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214b55  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214b5a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Lifecycle.Task::get_JobId()
0x214b5f  box      [mscorlib]System.Guid
0x214b64  stelem.ref
0x214b65  ldloc.s  0x1C
0x214b67  ldc.i4.3
0x214b68  ldarg.0
0x214b69  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214b6e  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214b73  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x214b78  callvirt instance string [mscorlib]System.Type::get_FullName()
0x214b7d  stelem.ref
0x214b7e  ldloc.s  0x1C
0x214b80  ldc.i4.4
0x214b81  ldloc.s  6
0x214b83  stelem.ref
0x214b84  ldloc.s  0x1C
0x214b86  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x214b8b  ldarg.0
0x214b8c  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214b91  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214b96  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Lifecycle.Task::get_SiteId()
0x214b9b  newobj   instance void Microsoft.SharePoint.SPSite::.ctor(valuetype [mscorlib]System.Guid id)
0x214ba0  stloc.s  9
0x214ba2  ldloc.s  9
0x214ba4  ldarg.0
0x214ba5  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214baa  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214baf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Lifecycle.Task::get_AppInstanceId()
0x214bb4  ldloca.s 0xA
0x214bb6  call     bool Microsoft.SharePoint.Administration.SPAppCatalog::TryGetAppInstance(class Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid appInstanceId, [out] class Microsoft.SharePoint.Administration.SPAppInstance& instance)
0x214bbb  brfalse  loc_214C82
0x214bc0  ldloc.s  6
0x214bc2  ldloc.s  0xA
0x214bc4  ldnull
0x214bc5  call     void Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::LogAppUsage(string eventName, class Microsoft.SharePoint.Administration.SPAppInstance instance, [opt] string errorMessage)
0x214bca  ldloc.0
0x214bcb  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x214bd0  stloc.s  0xB
0x214bd2  ldloc.s  0xB
0x214bd4  ldstr    aOperation_0// "Operation"
0x214bd9  ldloc.s  6
0x214bdb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x214be0  ldloc.s  0xB
0x214be2  ldstr    aJobid_0// "JobId"
0x214be7  ldarg.0
0x214be8  ldfld    class Microsoft.SharePoint.Administration.SPAppTask Microsoft.SharePoint.Lifecycle.MonitoredTaskExecution::task
0x214bed  callvirt instance class Microsoft.SharePoint.Lifecycle.Task Microsoft.SharePoint.Administration.SPAppTask::get_Task()
0x214bf2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Lifecycle.Task::get_JobId()
0x214bf7  box      [mscorlib]System.Guid
0x214bfc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x214c01  ldloc.s  0xB
0x214c03  ldstr    aRetries// "Retries"
  ... truncated ...
```
