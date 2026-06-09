# System.Deployment.Application.SubscriptionStore::CommitApplication

- ea: `0x1f1c0`
- end: `0x1f544`
- name: `System.Deployment.Application.SubscriptionStore::CommitApplication`
- size: `900`
- prototype: ``
- caller_count: `3`
- callee_count: `31`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb960`
- `0x11d60`
- `0x122a0`

## callees

- `0x3560`
- `0x3c70`
- `0x3c80`
- `0xd5e0`
- `0xe080`
- `0xe360`
- `0x146f0`
- `0x17cd0`
- `0x17d40`
- `0x1ded0`
- `0x1ece0`
- `0x1ed00`
- `0x1ed20`
- `0x1ed40`
- `0x1ee80`
- `0x1f1c0`
- `0x1f5f0`
- `0x1f680`
- `0x1f720`
- `0x1f8b0`
- `0x1fad0`
- `0x1fb50`
- `0x1fbb0`
- `0x1fc60`
- `0x1fe20`
- `0x1ffb0`
- `0x20060`
- `0x218d0`
- `0x23020`
- `0x24970`
- `0x2c1e0`

## string_xrefs

- `0x1f1c0`: `CommitApplication called.`
- `0x1f1db`: `Commiting Deployment :  subscription metadata.`
- `0x1f226`: `Commiting Application:  application binaries.`
- `0x1f28e`: `This installation is a Cross Group: identityGroupFound=`
- `0x1f34a`: `Uninstalling all cross groups.`
- `0x1f38c`: `UninstallCustomHostSpecifiedSubscription : `
- `0x1f3e2`: `UninstallCustomUXSubscription : `
- `0x1f43a`: `UninstallSubscription : `
- `0x1f488`: `Not uninstalled :`

## pseudocode

```c

```

## disassembly

```asm
0x1f1c0  ldstr    aCommitapplicat// "CommitApplication called."
0x1f1c5  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1f1ca  ldarg.0
0x1f1cb  ldarg.1
0x1f1cc  ldind.ref
0x1f1cd  call     instance class [mscorlib]System.IDisposable System.Deployment.Application.SubscriptionStore::AcquireSubscriptionWriterLock(class System.Deployment.Application.SubscriptionState subState)
0x1f1d2  stloc.0
0x1f1d3  ldarg.2
0x1f1d4  ldfld    bool System.Deployment.Application.CommitApplicationParams::CommitDeploy
0x1f1d9  brfalse.s loc_1F21E
0x1f1db  ldstr    aCommitingDeplo// "Commiting Deployment :  subscription me"...
0x1f1e0  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f1e5  ldarg.2
0x1f1e6  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::DeploySourceUri
0x1f1eb  call     void System.Deployment.Application.UriHelper::ValidateSupportedScheme(class [System]System.Uri uri)
0x1f1f0  ldarg.0
0x1f1f1  ldarg.1
0x1f1f2  ldind.ref
0x1f1f3  ldarg.2
0x1f1f4  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x1f1f9  call     instance void System.Deployment.Application.SubscriptionStore::CheckDeploymentSubscriptionState(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x1f1fe  ldarg.0
0x1f1ff  ldarg.1
0x1f200  ldind.ref
0x1f201  ldarg.2
0x1f202  call     instance void System.Deployment.Application.SubscriptionStore::ValidateFileAssoctiation(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.CommitApplicationParams commitParams)
0x1f207  ldarg.2
0x1f208  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0x1f20d  brfalse.s loc_1F21E
0x1f20f  ldarg.2
0x1f210  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0x1f215  brtrue.s loc_1F21E
0x1f217  ldarg.1
0x1f218  ldind.ref
0x1f219  call     void System.Deployment.Application.SubscriptionStore::CheckInstalled(class System.Deployment.Application.SubscriptionState subState)
0x1f21e  ldarg.2
0x1f21f  ldfld    bool System.Deployment.Application.CommitApplicationParams::CommitApp
0x1f224  brfalse.s loc_1F251
0x1f226  ldstr    aCommitingAppli// "Commiting Application:  application bin"...
0x1f22b  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f230  ldarg.2
0x1f231  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::AppSourceUri
0x1f236  call     void System.Deployment.Application.UriHelper::ValidateSupportedScheme(class [System]System.Uri uri)
0x1f23b  ldarg.2
0x1f23c  ldfld    string System.Deployment.Application.CommitApplicationParams::AppGroup
0x1f241  brfalse.s loc_1F24A
0x1f243  ldarg.1
0x1f244  ldind.ref
0x1f245  call     void System.Deployment.Application.SubscriptionStore::CheckInstalled(class System.Deployment.Application.SubscriptionState subState)
0x1f24a  ldarg.0
0x1f24b  ldarg.2
0x1f24c  call     instance void System.Deployment.Application.SubscriptionStore::CheckApplicationPayload(class System.Deployment.Application.CommitApplicationParams commitParams)
0x1f251  ldc.i4.0
0x1f252  stloc.1
0x1f253  ldc.i4.0
0x1f254  stloc.2
0x1f255  ldc.i4.0
0x1f256  stloc.3
0x1f257  ldstr    asc_2F208// ""
0x1f25c  stloc.s  4
0x1f25e  ldarg.0
0x1f25f  ldfld    class System.Deployment.Application.ComponentStore System.Deployment.Application.SubscriptionStore::_compStore
0x1f264  ldarg.2
0x1f265  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::DeploySourceUri
0x1f26a  ldarg.2
0x1f26b  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x1f270  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1f275  ldloca.s 2
0x1f277  ldloca.s 3
0x1f279  ldloca.s 4
0x1f27b  callvirt instance class [mscorlib]System.Collections.ArrayList System.Deployment.Application.ComponentStore::CollectCrossGroupApplications(class [System]System.Uri codebaseUri, class System.Deployment.Application.DefinitionIdentity deploymentIdentity, bool& identityGroupFound, bool& locationGroupFound, string& identityGroupProductName)
0x1f280  stloc.s  5
0x1f282  ldloc.s  5
0x1f284  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1f289  ldc.i4.0
0x1f28a  ble.s    loc_1F2B0
0x1f28c  ldc.i4.1
0x1f28d  stloc.1
0x1f28e  ldstr    aThisInstallati// "This installation is a Cross Group: ide"...
0x1f293  ldloca.s 2
0x1f295  call     instance string [mscorlib]System.Boolean::ToString()
0x1f29a  ldstr    aLocationgroupf// ",locationGroupFound="
0x1f29f  ldloca.s 3
0x1f2a1  call     instance string [mscorlib]System.Boolean::ToString()
0x1f2a6  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1f2ab  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f2b0  ldarg.1
0x1f2b1  ldind.ref
0x1f2b2  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0x1f2b7  ldloc.2
0x1f2b8  and
0x1f2b9  ldloc.3
0x1f2ba  and
0x1f2bb  brfalse.s loc_1F2E4
0x1f2bd  ldc.i4.s 0xB
0x1f2bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1f2c4  ldstr    aExGroupmultipl// "Ex_GroupMultipleMatch"
0x1f2c9  call     string System.Deployment.Application.Resources::GetString(string s)
0x1f2ce  ldc.i4.1
0x1f2cf  newarr   [mscorlib]System.Object
0x1f2d4  dup
0x1f2d5  ldc.i4.0
0x1f2d6  ldloc.s  4
0x1f2d8  stelem.ref
0x1f2d9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1f2de  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1f2e3  throw
0x1f2e4  ldarg.1
0x1f2e5  ldarg.0
0x1f2e6  ldarg.2
0x1f2e7  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x1f2ec  call     instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x1f2f1  stind.ref
0x1f2f2  ldarg.0
0x1f2f3  ldfld    class System.Deployment.Application.ComponentStore System.Deployment.Application.SubscriptionStore::_compStore
0x1f2f8  ldarg.1
0x1f2f9  ldind.ref
0x1f2fa  ldarg.2
0x1f2fb  callvirt instance void System.Deployment.Application.ComponentStore::CommitApplication(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.CommitApplicationParams commitParams)
0x1f300  ldloc.1
0x1f301  brfalse  loc_1F4E5
0x1f306  ldstr    aPerformingCros// "Performing cross group migration."
0x1f30b  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f310  ldarg.1
0x1f311  ldind.ref
0x1f312  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0x1f317  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionAppId System.Deployment.Application.DefinitionAppId::get_ComPointer()
0x1f31c  call     class System.Deployment.Internal.Isolation.IActContext System.Deployment.Internal.Isolation.IsolationInterop::CreateActContext(class System.Deployment.Internal.Isolation.IDefinitionAppId AppId)
0x1f321  stloc.s  6
0x1f323  ldloc.s  6
0x1f325  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1f32a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1f32f  callvirt instance void System.Deployment.Internal.Isolation.IActContext::PrepareForExecution([in] [hasfieldmarshal] native int Inputs, [in] [hasfieldmarshal] native int Outputs)
0x1f334  ldloc.s  6
0x1f336  ldc.i4.0
0x1f337  ldc.i4.1
0x1f338  ldloca.s 7
0x1f33a  callvirt instance void System.Deployment.Internal.Isolation.IActContext::SetApplicationRunningState([in] unsigned int32 dwFlags, [in] unsigned int32 ulState, [out] unsigned int32& ulDisposition)
0x1f33f  ldloc.s  6
0x1f341  ldc.i4.0
0x1f342  ldc.i4.2
0x1f343  ldloca.s 7
0x1f345  callvirt instance void System.Deployment.Internal.Isolation.IActContext::SetApplicationRunningState([in] unsigned int32 dwFlags, [in] unsigned int32 ulState, [out] unsigned int32& ulDisposition)
0x1f34a  ldstr    aUninstallingAl// "Uninstalling all cross groups."
0x1f34f  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f354  ldloc.s  5
0x1f356  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x1f35b  stloc.s  8
0x1f35d  br       loc_1F4C2
0x1f362  ldloc.s  8
0x1f364  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1f369  castclass CrossGroupApplicationData
0x1f36e  stloc.s  9
0x1f370  ldloc.s  9
0x1f372  ldfld    valuetype GroupType CrossGroupApplicationData::CrossGroupType
0x1f377  ldc.i4.1
0x1f378  bne.un   loc_1F47E
0x1f37d  ldloc.s  9
0x1f37f  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f384  callvirt instance valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionState::get_appType()
0x1f389  ldc.i4.3
0x1f38a  bne.un.s loc_1F3D3
0x1f38c  ldstr    aUninstallcusto// "UninstallCustomHostSpecifiedSubscriptio"...
0x1f391  ldloc.s  9
0x1f393  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f398  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f39d  brtrue.s loc_1F3A6
0x1f39f  ldstr    aNull// "null"
0x1f3a4  br.s     loc_1F3B7
0x1f3a6  ldloc.s  9
0x1f3a8  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f3ad  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f3b2  callvirt instance string [mscorlib]System.Object::ToString()
0x1f3b7  call     string [mscorlib]System.String::Concat(string, string)
0x1f3bc  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f3c1  ldarg.0
0x1f3c2  ldloc.s  9
0x1f3c4  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f3c9  call     instance void System.Deployment.Application.SubscriptionStore::UninstallCustomHostSpecifiedSubscription(class System.Deployment.Application.SubscriptionState subState)
0x1f3ce  br       loc_1F4C2
0x1f3d3  ldloc.s  9
0x1f3d5  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f3da  callvirt instance valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionState::get_appType()
0x1f3df  ldc.i4.4
0x1f3e0  bne.un.s loc_1F429
0x1f3e2  ldstr    aUninstallcusto_0// "UninstallCustomUXSubscription : "
0x1f3e7  ldloc.s  9
0x1f3e9  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f3ee  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f3f3  brtrue.s loc_1F3FC
0x1f3f5  ldstr    aNull// "null"
0x1f3fa  br.s     loc_1F40D
0x1f3fc  ldloc.s  9
0x1f3fe  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f403  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f408  callvirt instance string [mscorlib]System.Object::ToString()
0x1f40d  call     string [mscorlib]System.String::Concat(string, string)
0x1f412  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f417  ldarg.0
0x1f418  ldloc.s  9
0x1f41a  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f41f  call     instance void System.Deployment.Application.SubscriptionStore::UninstallCustomUXSubscription(class System.Deployment.Application.SubscriptionState subState)
0x1f424  br       loc_1F4C2
0x1f429  ldloc.s  9
0x1f42b  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f430  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0x1f435  brfalse  loc_1F4C2
0x1f43a  ldstr    aUninstallsubsc// "UninstallSubscription : "
0x1f43f  ldloc.s  9
0x1f441  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f446  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f44b  brtrue.s loc_1F454
0x1f44d  ldstr    aNull// "null"
0x1f452  br.s     loc_1F465
0x1f454  ldloc.s  9
0x1f456  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f45b  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f460  callvirt instance string [mscorlib]System.Object::ToString()
0x1f465  call     string [mscorlib]System.String::Concat(string, string)
0x1f46a  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f46f  ldarg.0
0x1f470  ldloc.s  9
0x1f472  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f477  call     instance void System.Deployment.Application.SubscriptionStore::UninstallSubscription(class System.Deployment.Application.SubscriptionState subState)
0x1f47c  br.s     loc_1F4C2
0x1f47e  ldloc.s  9
0x1f480  ldfld    valuetype GroupType CrossGroupApplicationData::CrossGroupType
0x1f485  ldc.i4.2
0x1f486  bne.un.s loc_1F4C2
0x1f488  ldstr    aNotUninstalled// "Not uninstalled :"
0x1f48d  ldloc.s  9
0x1f48f  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f494  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f499  brtrue.s loc_1F4A2
0x1f49b  ldstr    aNull// "null"
0x1f4a0  br.s     loc_1F4B3
0x1f4a2  ldloc.s  9
0x1f4a4  ldfld    class System.Deployment.Application.SubscriptionState CrossGroupApplicationData::SubState
0x1f4a9  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f4ae  callvirt instance string [mscorlib]System.Object::ToString()
0x1f4b3  ldstr    aItIsInTheIdent// ". It is in the identity group."
0x1f4b8  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f4bd  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1f4c2  ldloc.s  8
0x1f4c4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f4c9  brtrue   loc_1F362
0x1f4ce  leave.s  loc_1F4E5
0x1f4d0  ldloc.s  8
0x1f4d2  isinst   [mscorlib]System.IDisposable
0x1f4d7  stloc.s  0xA
0x1f4d9  ldloc.s  0xA
0x1f4db  brfalse.s loc_1F4E4
0x1f4dd  ldloc.s  0xA
0x1f4df  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f4e4  endfinally
0x1f4e5  ldarg.2
0x1f4e6  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsConfirmed
0x1f4eb  brfalse.s loc_1F510
0x1f4ed  ldarg.1
0x1f4ee  ldind.ref
0x1f4ef  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0x1f4f4  brfalse.s loc_1F510
0x1f4f6  ldarg.1
0x1f4f7  ldind.ref
0x1f4f8  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0x1f4fd  brfalse.s loc_1F510
0x1f4ff  ldarg.2
0x1f500  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.CommitApplicationParams::appType
0x1f505  ldc.i4.4
0x1f506  beq.s    loc_1F510
0x1f508  ldarg.0
0x1f509  ldarg.1
0x1f50a  ldind.ref
0x1f50b  call     instance void System.Deployment.Application.SubscriptionStore::UpdateSubscriptionExposure(class System.Deployment.Application.SubscriptionState subState)
0x1f510  ldarg.2
0x1f511  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.CommitApplicationParams::appType
0x1f516  ldc.i4.4
0x1f517  bne.un.s loc_1F530
0x1f519  ldarg.1
0x1f51a  ldind.ref
0x1f51b  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f520  call     class ShellExposureInformation ShellExposureInformation::CreateShellExposureInformation(class System.Deployment.Application.DefinitionIdentity subscriptionIdentity)
0x1f525  stloc.s  0xB
0x1f527  ldarg.1
0x1f528  ldind.ref
0x1f529  ldloca.s 0xB
0x1f52b  call     void System.Deployment.Application.ShellExposure::UpdateShellExtensions(class System.Deployment.Application.SubscriptionState subState, class ShellExposureInformation& shellExposureInformation)
0x1f530  ldarg.1
0x1f531  ldind.ref
0x1f532  call     void System.Deployment.Application.SubscriptionStore::OnDeploymentAdded(class System.Deployment.Application.SubscriptionState subState)
0x1f537  leave.s  loc_1F543
0x1f539  ldloc.0
0x1f53a  brfalse.s loc_1F542
0x1f53c  ldloc.0
0x1f53d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f542  endfinally
0x1f543  ret
```
