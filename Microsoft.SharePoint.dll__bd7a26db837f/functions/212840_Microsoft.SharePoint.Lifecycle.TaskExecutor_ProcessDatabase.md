# Microsoft.SharePoint.Lifecycle.TaskExecutor::ProcessDatabase

- ea: `0x212840`
- end: `0x212d89`
- name: `Microsoft.SharePoint.Lifecycle.TaskExecutor::ProcessDatabase`
- size: `1353`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x2120e0`
- `0x2122a0`

## callees

- `0x1c8480`
- `0x2127a0`
- `0x212840`
- `0x212d90`
- `0x2134d0`
- `0x213620`
- `0x213650`
- `0x216980`
- `0x21ad60`
- `0x232440`
- `0x242050`
- `0x252a10`
- `0x254e00`
- `0x280060`
- `0x93dab0`
- `0x93dae0`
- `0x957770`

## string_xrefs

- `0x212845`: `TaskExecutor: ProcessDatabase - contentDatabase '{0}'`
- `0x21287e`: `TaskExecutor - ProcessDatabase: Will not process {0} because SPContentDatabaseLock.CanProcessContentDatabase returned false.`
- `0x2128c9`: `TaskExecutor checking for work in database {0}.`
- `0x2128f6`: `TaskExecutor found work in database {0}.`
- `0x21291d`: `TaskExecutor did not find work in database {0}.`
- `0x2129b8`: `TaskExecutor will work on content database with connection string {0}.`
- `0x212a29`: `TaskExecutor will assign thread {1} to content database with connection string {0}.`
- `0x212a74`: `TaskExecutor has started thread {1} on content database with connection string {0}.`
- `0x212ad9`: `TaskExecutor will assign thread {1} to content database with connection string {0} as an async worker.`
- `0x212b1d`: `TaskExecutor has started thread {1} on content database with connection string {0} as an async worker.`
- `0x212b6d`: `TaskExecutor waiting on a need to check for halt order.`
- `0x212bb3`: `TaskExecutor was signalled to check for halt order.`
- `0x212bd4`: `TaskExecutor encountered an exception while running worker threads:`
- `0x212c0d`: `TaskExecutor has issued a haltOrder. Threads {1} should wrap up on content database with connection string {0}.`
- `0x212c5b`: `TaskExecutor is joining thread {1} on content database with connection string {0}.`
- `0x212c9b`: `TaskExecutor has joined thread {1} on content database with connection string {0}.`
- `0x212ce1`: `TaskExecutor is joining async thread {1} on content database with connection string {0}.`
- `0x212d21`: `TaskExecutor has joined joining async thread {1} on content database with connection string {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x212840  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x212845  ldstr    aTaskexecutorPr_4// "TaskExecutor: ProcessDatabase - content"...
0x21284a  ldc.i4.1
0x21284b  newarr   [mscorlib]System.Object
0x212850  stloc.s  0xC
0x212852  ldloc.s  0xC
0x212854  ldc.i4.0
0x212855  ldarg.1
0x212856  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x21285b  stelem.ref
0x21285c  ldloc.s  0xC
0x21285e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x212863  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x212868  stloc.s  0xD
0x21286a  ldarg.1
0x21286b  call     bool Microsoft.SharePoint.Administration.SPContentDatabaseLockManager::CanProcessContentDatabase(class Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase)
0x212870  brtrue.s loc_2128A4
0x212872  ldc.i4   0x2437CC
0x212877  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x21287c  ldc.i4.s 0x14
0x21287e  ldstr    aTaskexecutorPr_5// "TaskExecutor - ProcessDatabase: Will no"...
0x212883  ldc.i4.1
0x212884  newarr   [mscorlib]System.Object
0x212889  stloc.s  0xE
0x21288b  ldloc.s  0xE
0x21288d  ldc.i4.0
0x21288e  ldarg.1
0x21288f  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x212894  stelem.ref
0x212895  ldloc.s  0xE
0x212897  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x21289c  ldc.i4.0
0x21289d  stloc.s  0xB
0x21289f  leave    loc_212D86
0x2128a4  ldarg.1
0x2128a5  callvirt instance class Microsoft.SharePoint.Utilities.SqlSession Microsoft.SharePoint.Administration.SPDatabase::get_SqlSession()
0x2128aa  stloc.0
0x2128ab  ldloc.0
0x2128ac  callvirt instance string Microsoft.SharePoint.Utilities.SqlSession::get_ConnectionString()
0x2128b1  call     string Microsoft.SharePoint.Utilities.SqlSession::GetConnectionStringForLogging(string connectionString)
0x2128b6  stloc.1
0x2128b7  ldloc.0
0x2128b8  call     void Microsoft.SharePoint.Lifecycle.SprocWrappers::CheckForExpiredDownloads(class Microsoft.SharePoint.Utilities.SqlSession dbSessionWrapper)
0x2128bd  ldc.i4   0x1C671B
0x2128c2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x2128c7  ldc.i4.s 0x64
0x2128c9  ldstr    aTaskexecutorCh// "TaskExecutor checking for work in datab"...
0x2128ce  ldc.i4.1
0x2128cf  newarr   [mscorlib]System.Object
0x2128d4  stloc.s  0xF
0x2128d6  ldloc.s  0xF
0x2128d8  ldc.i4.0
0x2128d9  ldloc.1
0x2128da  stelem.ref
0x2128db  ldloc.s  0xF
0x2128dd  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2128e2  ldloc.0
0x2128e3  call     bool Microsoft.SharePoint.Lifecycle.SprocWrappers::PeekIfWorkExists(class Microsoft.SharePoint.Utilities.SqlSession dbSessionWrapper)
0x2128e8  brfalse.s loc_212911
0x2128ea  ldc.i4   0x1C671C
0x2128ef  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x2128f4  ldc.i4.s 0x64
0x2128f6  ldstr    aTaskexecutorFo_0// "TaskExecutor found work in database {0}"...
0x2128fb  ldc.i4.1
0x2128fc  newarr   [mscorlib]System.Object
0x212901  stloc.s  0x10
0x212903  ldloc.s  0x10
0x212905  ldc.i4.0
0x212906  ldloc.1
0x212907  stelem.ref
0x212908  ldloc.s  0x10
0x21290a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x21290f  br.s     loc_21293E
0x212911  ldc.i4   0x1C671D
0x212916  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x21291b  ldc.i4.s 0x64
0x21291d  ldstr    aTaskexecutorDi// "TaskExecutor did not find work in datab"...
0x212922  ldc.i4.1
0x212923  newarr   [mscorlib]System.Object
0x212928  stloc.s  0x11
0x21292a  ldloc.s  0x11
0x21292c  ldc.i4.0
0x21292d  ldloc.1
0x21292e  stelem.ref
0x21292f  ldloc.s  0x11
0x212931  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x212936  ldc.i4.0
0x212937  stloc.s  0xB
0x212939  leave    loc_212D86
0x21293e  ldc.i4.0
0x21293f  stloc.2
0x212940  ldc.i4.5
0x212941  newarr   [mscorlib]System.Boolean
0x212946  stsfld   bool[] Microsoft.SharePoint.Lifecycle.TaskExecutor::haltSuggestions
0x21294b  ldc.i4.5
0x21294c  newarr   [mscorlib]System.Object
0x212951  stsfld   object[] Microsoft.SharePoint.Lifecycle.TaskExecutor::threadTaskPullLocks
0x212956  ldc.i4.0
0x212957  stloc.3
0x212958  br.s     loc_21296A
0x21295a  ldsfld   object[] Microsoft.SharePoint.Lifecycle.TaskExecutor::threadTaskPullLocks
0x21295f  ldloc.3
0x212960  newobj   instance void [mscorlib]System.Object::.ctor()
0x212965  stelem.ref
0x212966  ldloc.3
0x212967  ldc.i4.1
0x212968  add
0x212969  stloc.3
0x21296a  ldloc.3
0x21296b  ldsfld   object[] Microsoft.SharePoint.Lifecycle.TaskExecutor::threadTaskPullLocks
0x212970  ldlen
0x212971  conv.i4
0x212972  blt.s    loc_21295A
0x212974  ldarg.0
0x212975  ldc.i4.0
0x212976  stfld    bool Microsoft.SharePoint.Lifecycle.TaskExecutor::haltOrderIssued
0x21297b  ldarg.0
0x21297c  ldc.i4.0
0x21297d  newobj   instance void [mscorlib]System.Threading.AutoResetEvent::.ctor(bool)
0x212982  dup
0x212983  stloc.s  0x12
0x212985  stfld    class [mscorlib]System.Threading.AutoResetEvent Microsoft.SharePoint.Lifecycle.TaskExecutor::checkIfShouldIssueHaltOrderEvent
0x21298a  ldloc.s  0x12
0x21298c  stloc.s  0x13
0x21298e  ldarg.0
0x21298f  ldc.i4.5
0x212990  newobj   instance void WakeWorkerThreadEventSet::.ctor(int32 numberOfEvents)
0x212995  dup
0x212996  stloc.s  0x14
0x212998  stfld    class WakeWorkerThreadEventSet Microsoft.SharePoint.Lifecycle.TaskExecutor::wakeupWorkerEvents
0x21299d  ldloc.s  0x14
0x21299f  stloc.s  0x15
0x2129a1  ldc.i4.4
0x2129a2  newarr   [mscorlib]System.Threading.Thread
0x2129a7  stloc.s  4
0x2129a9  ldnull
0x2129aa  stloc.s  5
0x2129ac  ldc.i4   0x621C4
0x2129b1  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x2129b6  ldc.i4.s 0x64
0x2129b8  ldstr    aTaskexecutorWi// "TaskExecutor will work on content datab"...
0x2129bd  ldc.i4.1
0x2129be  newarr   [mscorlib]System.Object
0x2129c3  stloc.s  0x16
0x2129c5  ldloc.s  0x16
0x2129c7  ldc.i4.0
0x2129c8  ldloc.1
0x2129c9  stelem.ref
0x2129ca  ldloc.s  0x16
0x2129cc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2129d1  ldc.i4.0
0x2129d2  stloc.s  6
0x2129d4  br       loc_212AA6
0x2129d9  ldloc.s  4
0x2129db  ldloc.s  6
0x2129dd  ldarg.0
0x2129de  ldftn    instance void Microsoft.SharePoint.Lifecycle.TaskExecutor::ExecuteTaskCycle(object parameterObject)
0x2129e4  newobj   instance void [mscorlib]System.Threading.ParameterizedThreadStart::.ctor(object, native int)
0x2129e9  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ParameterizedThreadStart)
0x2129ee  stelem.ref
0x2129ef  ldloc.s  4
0x2129f1  ldloc.s  6
0x2129f3  ldelem.ref
0x2129f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2129f9  ldstr    aSyncworker0// "SyncWorker {0}"
0x2129fe  ldc.i4.1
0x2129ff  newarr   [mscorlib]System.Object
0x212a04  stloc.s  0x17
0x212a06  ldloc.s  0x17
0x212a08  ldc.i4.0
0x212a09  ldloc.s  6
0x212a0b  box      [mscorlib]System.Int32
0x212a10  stelem.ref
0x212a11  ldloc.s  0x17
0x212a13  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x212a18  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0x212a1d  ldc.i4   0x621C5
0x212a22  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x212a27  ldc.i4.s 0x64
0x212a29  ldstr    aTaskexecutorWi_0// "TaskExecutor will assign thread {1} to "...
0x212a2e  ldc.i4.2
0x212a2f  newarr   [mscorlib]System.Object
0x212a34  stloc.s  0x18
0x212a36  ldloc.s  0x18
0x212a38  ldc.i4.0
0x212a39  ldloc.1
0x212a3a  stelem.ref
0x212a3b  ldloc.s  0x18
0x212a3d  ldc.i4.1
0x212a3e  ldloc.s  4
0x212a40  ldloc.s  6
0x212a42  ldelem.ref
0x212a43  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x212a48  box      [mscorlib]System.Int32
0x212a4d  stelem.ref
0x212a4e  ldloc.s  0x18
0x212a50  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x212a55  ldloc.s  4
0x212a57  ldloc.s  6
0x212a59  ldelem.ref
0x212a5a  ldloc.0
0x212a5b  ldarg.1
0x212a5c  ldloc.s  6
0x212a5e  newobj   instance void DatabaseSessionThreadStartParameter::.ctor(class Microsoft.SharePoint.Utilities.SqlSession session, class Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase, int32 haltSuggestionIndex)
0x212a63  callvirt instance void [mscorlib]System.Threading.Thread::Start(object)
0x212a68  ldc.i4   0x621C6
0x212a6d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x212a72  ldc.i4.s 0x64
0x212a74  ldstr    aTaskexecutorHa// "TaskExecutor has started thread {1} on "...
0x212a79  ldc.i4.2
0x212a7a  newarr   [mscorlib]System.Object
0x212a7f  stloc.s  0x19
0x212a81  ldloc.s  0x19
0x212a83  ldc.i4.0
0x212a84  ldloc.1
0x212a85  stelem.ref
0x212a86  ldloc.s  0x19
0x212a88  ldc.i4.1
0x212a89  ldloc.s  4
0x212a8b  ldloc.s  6
0x212a8d  ldelem.ref
0x212a8e  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x212a93  box      [mscorlib]System.Int32
0x212a98  stelem.ref
0x212a99  ldloc.s  0x19
0x212a9b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x212aa0  ldloc.s  6
0x212aa2  ldc.i4.1
0x212aa3  add
0x212aa4  stloc.s  6
0x212aa6  ldloc.s  6
0x212aa8  ldc.i4.4
0x212aa9  blt      loc_2129D9
0x212aae  ldarg.0
0x212aaf  ldftn    instance void Microsoft.SharePoint.Lifecycle.TaskExecutor::ExecuteAsyncDelegatePool(object sessionAsObject)
0x212ab5  newobj   instance void [mscorlib]System.Threading.ParameterizedThreadStart::.ctor(object, native int)
0x212aba  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ParameterizedThreadStart)
0x212abf  stloc.s  5
0x212ac1  ldloc.s  5
0x212ac3  ldstr    aAsyncworker// "AsyncWorker"
0x212ac8  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0x212acd  ldc.i4   0xC1454
0x212ad2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x212ad7  ldc.i4.s 0x64
0x212ad9  ldstr    aTaskexecutorWi_1// "TaskExecutor will assign thread {1} to "...
0x212ade  ldc.i4.2
0x212adf  newarr   [mscorlib]System.Object
0x212ae4  stloc.s  0x1A
0x212ae6  ldloc.s  0x1A
0x212ae8  ldc.i4.0
0x212ae9  ldloc.1
0x212aea  stelem.ref
0x212aeb  ldloc.s  0x1A
0x212aed  ldc.i4.1
0x212aee  ldloc.s  5
0x212af0  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x212af5  box      [mscorlib]System.Int32
0x212afa  stelem.ref
0x212afb  ldloc.s  0x1A
0x212afd  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x212b02  ldloc.s  5
0x212b04  ldloc.0
0x212b05  ldarg.1
0x212b06  ldc.i4.4
0x212b07  newobj   instance void DatabaseSessionThreadStartParameter::.ctor(class Microsoft.SharePoint.Utilities.SqlSession session, class Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase, int32 haltSuggestionIndex)
0x212b0c  callvirt instance void [mscorlib]System.Threading.Thread::Start(object)
0x212b11  ldc.i4   0xC1455
0x212b16  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x212b1b  ldc.i4.s 0x64
0x212b1d  ldstr    aTaskexecutorHa_0// "TaskExecutor has started thread {1} on "...
0x212b22  ldc.i4.2
0x212b23  newarr   [mscorlib]System.Object
0x212b28  stloc.s  0x1B
0x212b2a  ldloc.s  0x1B
0x212b2c  ldc.i4.0
0x212b2d  ldloc.1
0x212b2e  stelem.ref
0x212b2f  ldloc.s  0x1B
0x212b31  ldc.i4.1
0x212b32  ldloc.s  5
0x212b34  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x212b39  box      [mscorlib]System.Int32
0x212b3e  stelem.ref
0x212b3f  ldloc.s  0x1B
0x212b41  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x212b46  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x212b4b  stloc.s  0x1C
0x212b4d  ldloca.s 0x1C
0x212b4f  ldc.r8   10.0
0x212b58  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x212b5d  stloc.s  7
0x212b5f  br.s     loc_212BBD
0x212b61  ldc.i4   0x24C31D
0x212b66  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppDeployment()
0x212b6b  ldc.i4.s 0x32
0x212b6d  ldstr    aTaskexecutorWa// "TaskExecutor waiting on a need to check"...
0x212b72  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x212b77  ldloca.s 7
0x212b79  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x212b7e  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
  ... truncated ...
```
