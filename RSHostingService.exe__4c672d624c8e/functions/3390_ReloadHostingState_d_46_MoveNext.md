# <ReloadHostingState>d__46::MoveNext

- ea: `0x3390`
- end: `0x35cb`
- name: `<ReloadHostingState>d__46::MoveNext`
- size: `571`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9d0`
- `0xb10`
- `0x10e0`
- `0x12b0`
- `0x1320`
- `0x1330`
- `0x1bf0`
- `0x1c00`
- `0x2190`
- `0x21a0`
- `0x2310`
- `0x2320`
- `0x2340`
- `0x2350`
- `0x3390`

## string_xrefs

- `0x33af`: `Can't load config from missing file at [{0}]`
- `0x358b`: `Exception occurred while configuring and starting processes`

## pseudocode

```c

```

## disassembly

```asm
0x3390  ldarg.0
0x3391  ldfld    int32 <ReloadHostingState>d__46::<>1__state
0x3396  stloc.0
0x3397  ldarg.0
0x3398  ldfld    class Microsoft.BIServer.BIService.BIService <ReloadHostingState>d__46::<>4__this
0x339d  stloc.1
0x339e  ldloc.0
0x339f  brfalse.s loc_33D2
0x33a1  ldloc.1
0x33a2  ldloc.1
0x33a3  ldfld    string Microsoft.BIServer.BIService.BIService::_serviceConfigFilePath
0x33a8  call     instance bool Microsoft.BIServer.BIService.BIService::SetNewConfigFilePathIfExists(string configFilePath)
0x33ad  brtrue.s loc_33D2
0x33af  ldstr    aCanTLoadConfig// "Can't load config from missing file at "...
0x33b4  ldc.i4.1
0x33b5  newarr   [mscorlib]System.Object
0x33ba  dup
0x33bb  ldc.i4.0
0x33bc  ldloc.1
0x33bd  ldfld    string Microsoft.BIServer.BIService.BIService::_serviceConfigFilePath
0x33c2  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x33c7  stelem.ref
0x33c8  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x33cd  leave    loc_35B7
0x33d2  nop
0x33d3  ldloc.0
0x33d4  brfalse  loc_34D0
0x33d9  ldloc.1
0x33da  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0x33df  callvirt instance class [System]System.Uri Microsoft.BIServer.BIService.ServiceConfig::get_ManagementUri()
0x33e4  newobj   instance void [System]System.UriBuilder::.ctor(class [System]System.Uri)
0x33e9  stloc.2
0x33ea  ldloc.2
0x33eb  ldstr    aApiV10Manageme// "/api/v1.0/ManagementState"
0x33f0  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x33f5  ldloc.1
0x33f6  ldstr    aManagementStat// "Management State"
0x33fb  ldloc.2
0x33fc  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x3401  newobj   instance void class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.TrustedWebApiProxy`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::.ctor(string, class [System]System.Uri)
0x3406  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.TrustedWebApiProxy`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.BIService.BIService::_managementStateAccessor
0x340b  ldloc.1
0x340c  ldloc.1
0x340d  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0x3412  callvirt instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ServiceConfig::get_ManagementProcessConfig()
0x3417  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x341c  call     instance void Microsoft.BIServer.BIService.BIService::AddLoggerConfigValuesToServiceProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> properties)
0x3421  ldloc.1
0x3422  ldloc.1
0x3423  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0x3428  callvirt instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ServiceConfig::get_ManagementProcessConfig()
0x342d  call     class Microsoft.BIServer.BIService.ManagedProcess Microsoft.BIServer.BIService.ManagedProcess::CreateManagementProcess(class Microsoft.BIServer.BIService.ProcessConfig processConfig)
0x3432  stfld    class Microsoft.BIServer.BIService.ManagedProcess Microsoft.BIServer.BIService.BIService::_managementProcess
0x3437  ldloc.1
0x3438  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0x343d  callvirt instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ServiceConfig::get_ManagementProcessConfig()
0x3442  ldc.i4.3
0x3443  newarr   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>
0x3448  dup
0x3449  ldc.i4.0
0x344a  ldloc.1
0x344b  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0x3450  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ServiceConfig::get_ServiceProperties()
0x3455  stelem.ref
0x3456  dup
0x3457  ldc.i4.1
0x3458  ldloc.1
0x3459  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0x345e  callvirt instance class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ServiceConfig::get_ManagementProcessConfig()
0x3463  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x3468  stelem.ref
0x3469  dup
0x346a  ldc.i4.2
0x346b  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x3470  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::ReadKeyValueSettings()
0x3475  stelem.ref
0x3476  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.RSHostingService.Configuration.ConfigurationMergeHelper::MergeRightMostWins(class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, string>[] sources)
0x347b  callvirt instance void Microsoft.BIServer.BIService.ProcessConfig::set_Config(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0x3480  ldloc.1
0x3481  ldloc.1
0x3482  ldfld    class Microsoft.BIServer.BIService.ManagedProcess Microsoft.BIServer.BIService.BIService::_managementProcess
0x3487  call     instance void Microsoft.BIServer.BIService.BIService::IntegrateProcess(class Microsoft.BIServer.BIService.ManagedProcess workerProcess)
0x348c  ldstr    aStartingManage// "Starting Management Process"
0x3491  call     void [mscorlib]System.Console::WriteLine(string)
0x3496  ldloc.1
0x3497  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.BIService.BIService::StartManagementProcess()
0x349c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetAwaiter()
0x34a1  stloc.s  4
0x34a3  ldloca.s 4
0x34a5  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_IsCompleted()
0x34aa  brtrue.s loc_34ED
0x34ac  ldarg.0
0x34ad  ldc.i4.0
0x34ae  dup
0x34af  stloc.0
0x34b0  stfld    int32 <ReloadHostingState>d__46::<>1__state
0x34b5  ldarg.0
0x34b6  ldloc.s  4
0x34b8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ReloadHostingState>d__46::<>u__1
0x34bd  ldarg.0
0x34be  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ReloadHostingState>d__46::<>t__builder
0x34c3  ldloca.s 4
0x34c5  ldarg.0
0x34c6  call     T0x2B000022
0x34cb  leave    loc_35CA
0x34d0  ldarg.0
0x34d1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ReloadHostingState>d__46::<>u__1
0x34d6  stloc.s  4
0x34d8  ldarg.0
0x34d9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ReloadHostingState>d__46::<>u__1
0x34de  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>
0x34e4  ldarg.0
0x34e5  ldc.i4.m1
0x34e6  dup
0x34e7  stloc.0
0x34e8  stfld    int32 <ReloadHostingState>d__46::<>1__state
0x34ed  ldloca.s 4
0x34ef  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetResult()
0x34f4  stloc.3
0x34f5  ldloc.1
0x34f6  ldloc.3
0x34f7  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState Microsoft.BIServer.BIService.BIService::_mgmtState
0x34fc  ldstr    aFetchedManagem// "Fetched ManagementState from Management"...
0x3501  ldc.i4.2
0x3502  newarr   [mscorlib]System.Object
0x3507  dup
0x3508  ldc.i4.0
0x3509  ldloc.1
0x350a  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState Microsoft.BIServer.BIService.BIService::_mgmtState
0x350f  callvirt instance valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::get_DatabaseValidationStatus()
0x3514  box      [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus
0x3519  stelem.ref
0x351a  dup
0x351b  ldc.i4.1
0x351c  ldloc.1
0x351d  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState Microsoft.BIServer.BIService.BIService::_mgmtState
0x3522  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::get_EncryptionKeyPresent()
0x3527  box      [mscorlib]System.Boolean
0x352c  stelem.ref
0x352d  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x3532  ldloc.1
0x3533  ldloc.1
0x3534  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0x3539  ldloc.1
0x353a  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState Microsoft.BIServer.BIService.BIService::_mgmtState
0x353f  call     instance void Microsoft.BIServer.BIService.BIService::UpdateManagedProcessConfigs(class Microsoft.BIServer.BIService.ServiceConfig serviceConfig, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState managementState)
0x3544  ldloc.1
0x3545  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0x354a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.BIServer.BIService.ProcessConfig> Microsoft.BIServer.BIService.ServiceConfig::get_ManagedProcesses()
0x354f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.BIService.ProcessConfig>::GetEnumerator()
0x3554  stloc.s  5
0x3556  br.s     loc_356E
0x3558  ldloc.s  5
0x355a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.BIServer.BIService.ProcessConfig>::get_Current()
0x355f  call     class Microsoft.BIServer.BIService.ManagedProcess Microsoft.BIServer.BIService.ManagedProcess::CreateWorkerProcess(class Microsoft.BIServer.BIService.ProcessConfig processConfig)
0x3564  stloc.s  6
0x3566  ldloc.1
0x3567  ldloc.s  6
0x3569  call     instance void Microsoft.BIServer.BIService.BIService::IntegrateProcess(class Microsoft.BIServer.BIService.ManagedProcess workerProcess)
0x356e  ldloc.s  5
0x3570  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3575  brtrue.s loc_3558
0x3577  leave.s  loc_3589
0x3579  ldloc.0
0x357a  ldc.i4.0
0x357b  bge.s    loc_3588
0x357d  ldloc.s  5
0x357f  brfalse.s loc_3588
0x3581  ldloc.s  5
0x3583  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3588  endfinally
0x3589  leave.s  loc_359C
0x358b  ldstr    aExceptionOccur_1// "Exception occurred while configuring an"...
0x3590  call     T0x2B000001
0x3595  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x359a  rethrow
0x359c  leave.s  loc_35B7
0x359e  stloc.s  7
0x35a0  ldarg.0
0x35a1  ldc.i4.s 0xFE
0x35a3  stfld    int32 <ReloadHostingState>d__46::<>1__state
0x35a8  ldarg.0
0x35a9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ReloadHostingState>d__46::<>t__builder
0x35ae  ldloc.s  7
0x35b0  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x35b5  leave.s  loc_35CA
0x35b7  ldarg.0
0x35b8  ldc.i4.s 0xFE
0x35ba  stfld    int32 <ReloadHostingState>d__46::<>1__state
0x35bf  ldarg.0
0x35c0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ReloadHostingState>d__46::<>t__builder
0x35c5  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x35ca  ret
```
