# <ManagementStateInternal>d__3::MoveNext

- ea: `0xd60`
- end: `0xfa6`
- name: `<ManagementStateInternal>d__3::MoveNext`
- size: `582`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x2f0`
- `0x800`
- `0x880`
- `0x8c0`
- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0xd60  ldarg.0
0xd61  ldfld    int32 <ManagementStateInternal>d__3::<>1__state
0xd66  stloc.0
0xd67  ldarg.0
0xd68  ldfld    class Microsoft.BIServer.Management.WebApi.Controllers.StateController <ManagementStateInternal>d__3::<>4__this
0xd6d  stloc.1
0xd6e  ldloc.0
0xd6f  ldc.i4.1
0xd70  pop
0xd71  pop
0xd72  nop
0xd73  ldloc.0
0xd74  ldc.i4.1
0xd75  ble.un.s loc_D82
0xd77  ldarg.0
0xd78  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewConnection()
0xd7d  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ManagementStateInternal>d__3::<sqlAccess>5__2
0xd82  nop
0xd83  ldloc.0
0xd84  brfalse  loc_E23
0xd89  ldloc.0
0xd8a  ldc.i4.1
0xd8b  beq      loc_E90
0xd90  ldarg.0
0xd91  ldc.i4.0
0xd92  newarr   [mscorlib]System.Byte
0xd97  stfld    unsigned int8[] <ManagementStateInternal>d__3::<encryptedSymmetricKey>5__3
0xd9c  ldarg.0
0xd9d  ldarg.0
0xd9e  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ManagementStateInternal>d__3::<sqlAccess>5__2
0xda3  call     valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetStatusAndUpdateIfRequired(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess sqlAccess)
0xda8  stfld    valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus <ManagementStateInternal>d__3::<databaseValidationStatus>5__4
0xdad  newobj   instance void [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::.ctor()
0xdb2  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0xdb7  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_InstanceId()
0xdbc  call     instance class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::Load(string)
0xdc1  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_SkuType()
0xdc6  pop
0xdc7  ldarg.0
0xdc8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0xdcd  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> <ManagementStateInternal>d__3::<configSwitches>5__5
0xdd2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xdd7  stloc.3
0xdd8  ldarg.0
0xdd9  ldfld    valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus <ManagementStateInternal>d__3::<databaseValidationStatus>5__4
0xdde  ldc.i4.2
0xddf  bne.un   loc_EF8
0xde4  ldarg.0
0xde5  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ManagementStateInternal>d__3::<sqlAccess>5__2
0xdea  call     class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> Microsoft.BIServer.Management.WebApi.Controllers.StateController::LoadConfigSwitches(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess sqlAccess)
0xdef  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>>::GetAwaiter()
0xdf4  stloc.s  5
0xdf6  ldloca.s 5
0xdf8  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>>::get_IsCompleted()
0xdfd  brtrue.s loc_E40
0xdff  ldarg.0
0xe00  ldc.i4.0
0xe01  dup
0xe02  stloc.0
0xe03  stfld    int32 <ManagementStateInternal>d__3::<>1__state
0xe08  ldarg.0
0xe09  ldloc.s  5
0xe0b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <ManagementStateInternal>d__3::<>u__1
0xe10  ldarg.0
0xe11  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ManagementStateInternal>d__3::<>t__builder
0xe16  ldloca.s 5
0xe18  ldarg.0
0xe19  call     T0x2B00000E
0xe1e  leave    loc_FA5
0xe23  ldarg.0
0xe24  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <ManagementStateInternal>d__3::<>u__1
0xe29  stloc.s  5
0xe2b  ldarg.0
0xe2c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>> <ManagementStateInternal>d__3::<>u__1
0xe31  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>>
0xe37  ldarg.0
0xe38  ldc.i4.m1
0xe39  dup
0xe3a  stloc.0
0xe3b  stfld    int32 <ManagementStateInternal>d__3::<>1__state
0xe40  ldloca.s 5
0xe42  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>>::GetResult()
0xe47  stloc.s  4
0xe49  ldarg.0
0xe4a  ldloc.s  4
0xe4c  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> <ManagementStateInternal>d__3::<configSwitches>5__5
0xe51  ldarg.0
0xe52  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ManagementStateInternal>d__3::<sqlAccess>5__2
0xe57  call     class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> Microsoft.BIServer.Management.WebApi.Controllers.StateController::LoadConfigInfo(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess sqlAccess)
0xe5c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::GetAwaiter()
0xe61  stloc.s  6
0xe63  ldloca.s 6
0xe65  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::get_IsCompleted()
0xe6a  brtrue.s loc_EAD
0xe6c  ldarg.0
0xe6d  ldc.i4.1
0xe6e  dup
0xe6f  stloc.0
0xe70  stfld    int32 <ManagementStateInternal>d__3::<>1__state
0xe75  ldarg.0
0xe76  ldloc.s  6
0xe78  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <ManagementStateInternal>d__3::<>u__2
0xe7d  ldarg.0
0xe7e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ManagementStateInternal>d__3::<>t__builder
0xe83  ldloca.s 6
0xe85  ldarg.0
0xe86  call     T0x2B00000F
0xe8b  leave    loc_FA5
0xe90  ldarg.0
0xe91  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <ManagementStateInternal>d__3::<>u__2
0xe96  stloc.s  6
0xe98  ldarg.0
0xe99  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <ManagementStateInternal>d__3::<>u__2
0xe9e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>
0xea4  ldarg.0
0xea5  ldc.i4.m1
0xea6  dup
0xea7  stloc.0
0xea8  stfld    int32 <ManagementStateInternal>d__3::<>1__state
0xead  ldloca.s 6
0xeaf  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::GetResult()
0xeb4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0xeb9  stloc.3
0xeba  ldarg.0
0xebb  ldloc.1
0xebc  ldarg.0
0xebd  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ManagementStateInternal>d__3::<sqlAccess>5__2
0xec2  ldarg.0
0xec3  ldflda   unsigned int8[] <ManagementStateInternal>d__3::<encryptedSymmetricKey>5__3
0xec8  ldarg.0
0xec9  ldfld    valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus <ManagementStateInternal>d__3::<databaseValidationStatus>5__4
0xece  call     instance valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.Management.WebApi.Controllers.StateController::ReloadEncryptedSymmetricKey(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess sqlAccess, unsigned int8[]& encryptedSymmetricKey, valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus databaseValidationStatus)
0xed3  stfld    valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus <ManagementStateInternal>d__3::<databaseValidationStatus>5__4
0xed8  ldstr    aEncryptionInfl// "Encryption-influenced database validati"...
0xedd  ldc.i4.1
0xede  newarr   [mscorlib]System.Object
0xee3  dup
0xee4  ldc.i4.0
0xee5  ldarg.0
0xee6  ldfld    valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus <ManagementStateInternal>d__3::<databaseValidationStatus>5__4
0xeeb  box      [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus
0xef0  stelem.ref
0xef1  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(string, object[])
0xef6  br.s     loc_F16
0xef8  ldstr    aHostingstateDa// "HostingState database validation status"...
0xefd  ldc.i4.1
0xefe  newarr   [mscorlib]System.Object
0xf03  dup
0xf04  ldc.i4.0
0xf05  ldarg.0
0xf06  ldfld    valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus <ManagementStateInternal>d__3::<databaseValidationStatus>5__4
0xf0b  box      [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus
0xf10  stelem.ref
0xf11  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(string, object[])
0xf16  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::.ctor()
0xf1b  dup
0xf1c  ldarg.0
0xf1d  ldfld    unsigned int8[] <ManagementStateInternal>d__3::<encryptedSymmetricKey>5__3
0xf22  stfld    unsigned int8[] [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::EncryptionKey
0xf27  dup
0xf28  ldarg.0
0xf29  ldfld    valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus <ManagementStateInternal>d__3::<databaseValidationStatus>5__4
0xf2e  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::set_DatabaseValidationStatus(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus)
0xf33  dup
0xf34  ldarg.0
0xf35  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> <ManagementStateInternal>d__3::<configSwitches>5__5
0xf3a  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::RsConfigSwitches
0xf3f  dup
0xf40  ldloc.3
0xf41  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::ConfigurationInfo
0xf46  stloc.2
0xf47  leave.s  loc_F91
0xf49  ldloc.0
0xf4a  ldc.i4.0
0xf4b  bge.s    loc_F60
0xf4d  ldarg.0
0xf4e  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ManagementStateInternal>d__3::<sqlAccess>5__2
0xf53  brfalse.s loc_F60
0xf55  ldarg.0
0xf56  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ManagementStateInternal>d__3::<sqlAccess>5__2
0xf5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf60  endfinally
0xf61  callvirt instance string [mscorlib]System.Exception::get_Message()
0xf66  call     T0x2B000002
0xf6b  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0xf70  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState::get_Unavailable()
0xf75  stloc.2
0xf76  leave.s  loc_F91
0xf78  stloc.s  7
0xf7a  ldarg.0
0xf7b  ldc.i4.s 0xFE
0xf7d  stfld    int32 <ManagementStateInternal>d__3::<>1__state
0xf82  ldarg.0
0xf83  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ManagementStateInternal>d__3::<>t__builder
0xf88  ldloc.s  7
0xf8a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::SetException(class [mscorlib]System.Exception)
0xf8f  leave.s  loc_FA5
0xf91  ldarg.0
0xf92  ldc.i4.s 0xFE
0xf94  stfld    int32 <ManagementStateInternal>d__3::<>1__state
0xf99  ldarg.0
0xf9a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <ManagementStateInternal>d__3::<>t__builder
0xf9f  ldloc.2
0xfa0  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::SetResult(var<u1>)
0xfa5  ret
```
