# System.Deployment.Application.ApplicationActivator::PerformDeploymentUpdate

- ea: `0xb4c0`
- end: `0xb6c4`
- name: `System.Deployment.Application.ApplicationActivator::PerformDeploymentUpdate`
- size: `516`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config, installer_update`

## callers

- `0xb170`
- `0xb2f0`

## callees

- `0xb4c0`
- `0xb6d0`
- `0xb830`
- `0xbfe0`
- `0xc200`
- `0xc2b0`
- `0xc2c0`
- `0xda80`
- `0x13110`
- `0x13170`
- `0x14b40`
- `0x17c80`
- `0x17cc0`
- `0x17cd0`
- `0x17d40`
- `0x1ece0`
- `0x1eda0`
- `0x1edc0`
- `0x1ede0`
- `0x1eea0`
- `0x1eee0`
- `0x1f9b0`
- `0x20b30`
- `0x21e00`
- `0x23020`
- `0x23ca0`
- `0x23fb0`
- `0x23fc0`
- `0x240c0`
- `0x24970`
- `0x24b30`
- `0x24b90`

## string_xrefs

- `0xb4df`: `PhaseLog_DeploymentUpdateCheck`
- `0xb4ee`: `PerformDeploymentUpdate called.`
- `0xb4f8`: `UpdateOnStart=`
- `0xb553`: `Start processing deployment manifest for update check : `
- `0xb580`: `End processing deployment manifest.`
- `0xb5a5`: `Upd_UpdateCheckDownloadFailed`
- `0xb631`: `Update available in the deployment server.`

## pseudocode

```c

```

## disassembly

```asm
0xb4c0  ldarg.1
0xb4c1  ldind.ref
0xb4c2  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0xb4c7  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xb4cc  callvirt instance class System.Deployment.Application.Manifest.DeploymentUpdate System.Deployment.Application.Manifest.Deployment::get_DeploymentUpdate()
0xb4d1  stloc.0
0xb4d2  ldloc.0
0xb4d3  brfalse.s loc_B4DD
0xb4d5  ldloc.0
0xb4d6  callvirt instance bool System.Deployment.Application.Manifest.DeploymentUpdate::get_BeforeApplicationStartup()
0xb4db  br.s     loc_B4DE
0xb4dd  ldc.i4.0
0xb4de  stloc.1
0xb4df  ldstr    aPhaselogDeploy// "PhaseLog_DeploymentUpdateCheck"
0xb4e4  call     string System.Deployment.Application.Resources::GetString(string s)
0xb4e9  call     void System.Deployment.Application.Logger::AddPhaseInformation(string message)
0xb4ee  ldstr    aPerformdeploym_0// "PerformDeploymentUpdate called."
0xb4f3  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0xb4f8  ldstr    aUpdateonstart// "UpdateOnStart="
0xb4fd  ldloca.s 1
0xb4ff  call     instance string [mscorlib]System.Boolean::ToString()
0xb504  ldstr    aPendingdeploym// ",PendingDeployment="
0xb509  ldarg.1
0xb50a  ldind.ref
0xb50b  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_PendingDeployment()
0xb510  dup
0xb511  brtrue.s loc_B517
0xb513  pop
0xb514  ldnull
0xb515  br.s     loc_B51C
0xb517  callvirt instance string [mscorlib]System.Object::ToString()
0xb51c  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xb521  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb526  ldloc.1
0xb527  brtrue.s loc_B548
0xb529  ldarg.1
0xb52a  ldind.ref
0xb52b  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_PendingDeployment()
0xb530  brfalse  loc_B6C3
0xb535  ldarg.1
0xb536  ldind.ref
0xb537  ldarg.1
0xb538  ldind.ref
0xb539  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_PendingDeployment()
0xb53e  call     bool System.Deployment.Application.ApplicationActivator::SkipUpdate(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.DefinitionIdentity targetIdentity)
0xb543  brtrue   loc_B6C3
0xb548  ldnull
0xb549  stloc.2
0xb54a  ldarg.1
0xb54b  ldind.ref
0xb54c  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0xb551  stloc.s  4
0xb553  ldstr    aStartProcessin_0// "Start processing deployment manifest fo"...
0xb558  ldloc.s  4
0xb55a  dup
0xb55b  brtrue.s loc_B561
0xb55d  pop
0xb55e  ldnull
0xb55f  br.s     loc_B566
0xb561  callvirt instance string [mscorlib]System.Object::ToString()
0xb566  call     string [mscorlib]System.String::Concat(string, string)
0xb56b  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb570  ldarg.0
0xb571  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb576  ldloca.s 4
0xb578  ldloca.s 2
0xb57a  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifest(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile)
0xb57f  stloc.3
0xb580  ldstr    aEndProcessingD// "End processing deployment manifest."
0xb585  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb58a  ldloc.3
0xb58b  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xb590  brfalse.s loc_B59F
0xb592  ldarg.2
0xb593  ldloc.3
0xb594  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xb599  callvirt instance string System.Deployment.Application.Manifest.Description::get_ErrorReportUrl()
0xb59e  stind.ref
0xb59f  leave.s  loc_B5CE
0xb5a1  stloc.s  5
0xb5a3  ldloc.s  5
0xb5a5  ldstr    aUpdUpdatecheck// "Upd_UpdateCheckDownloadFailed"
0xb5aa  call     string System.Deployment.Application.Resources::GetString(string s)
0xb5af  ldc.i4.1
0xb5b0  newarr   [mscorlib]System.Object
0xb5b5  dup
0xb5b6  ldc.i4.0
0xb5b7  ldarg.1
0xb5b8  ldind.ref
0xb5b9  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0xb5be  callvirt instance string [mscorlib]System.Object::ToString()
0xb5c3  stelem.ref
0xb5c4  call     void System.Deployment.Application.Logger::AddErrorInformation(class [mscorlib]System.Exception exception, string messageFormat, object[] args)
0xb5c9  leave    loc_B6C3
0xb5ce  ldarg.0
0xb5cf  ldfld    class System.Deployment.Application.UserInterface System.Deployment.Application.ApplicationActivator::_ui
0xb5d4  callvirt instance bool System.Deployment.Application.UserInterface::SplashCancelled()
0xb5d9  brfalse.s loc_B5E1
0xb5db  newobj   instance void System.Deployment.Application.DownloadCancelledException::.ctor()
0xb5e0  throw
0xb5e1  ldarg.1
0xb5e2  ldind.ref
0xb5e3  ldloc.3
0xb5e4  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0xb5e9  call     bool System.Deployment.Application.ApplicationActivator::SkipUpdate(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.DefinitionIdentity targetIdentity)
0xb5ee  brtrue   loc_B6B7
0xb5f3  ldarg.0
0xb5f4  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb5f9  ldarg.1
0xb5fa  ldind.ref
0xb5fb  ldloc.s  4
0xb5fd  ldloc.3
0xb5fe  ldarg.1
0xb5ff  ldind.ref
0xb600  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_CurrentDeployment()
0xb605  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0xb60a  callvirt instance class [mscorlib]System.Version System.Deployment.Application.SubscriptionStore::CheckUpdateInManifest(class System.Deployment.Application.SubscriptionState subState, class [System]System.Uri updateCodebaseUri, class System.Deployment.Application.Manifest.AssemblyManifest deployment, class [mscorlib]System.Version currentVersion)
0xb60f  ldnull
0xb610  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xb615  brfalse  loc_B6B7
0xb61a  ldloc.3
0xb61b  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0xb620  ldarg.1
0xb621  ldind.ref
0xb622  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_ExcludedDeployment()
0xb627  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xb62c  brtrue   loc_B6B7
0xb631  ldstr    aUpdateAvailabl// "Update available in the deployment serv"...
0xb636  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb63b  newobj   instance void System.Deployment.Application.ActivationDescription::.ctor()
0xb640  stloc.s  6
0xb642  ldloc.s  6
0xb644  ldloc.3
0xb645  ldloc.s  4
0xb647  ldloc.2
0xb648  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0xb64d  callvirt instance void System.Deployment.Application.ActivationDescription::SetDeploymentManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0xb652  ldloc.s  6
0xb654  ldc.i4.1
0xb655  stfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0xb65a  ldloc.s  6
0xb65c  ldc.i4.0
0xb65d  stfld    bool System.Deployment.Application.CommitApplicationParams::IsRequiredUpdate
0xb662  ldloc.s  6
0xb664  ldc.i4.4
0xb665  callvirt instance void System.Deployment.Application.ActivationDescription::set_ActType(valuetype System.Deployment.Application.ActivationType value)
0xb66a  ldloc.3
0xb66b  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xb670  callvirt instance class [mscorlib]System.Version System.Deployment.Application.Manifest.Deployment::get_MinimumRequiredVersion()
0xb675  ldnull
0xb676  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xb67b  brfalse.s loc_B6A4
0xb67d  ldloc.3
0xb67e  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xb683  callvirt instance class [mscorlib]System.Version System.Deployment.Application.Manifest.Deployment::get_MinimumRequiredVersion()
0xb688  ldarg.1
0xb689  ldind.ref
0xb68a  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_CurrentDeployment()
0xb68f  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0xb694  callvirt instance int32 [mscorlib]System.Version::CompareTo(class [mscorlib]System.Version)
0xb699  ldc.i4.0
0xb69a  ble.s    loc_B6A4
0xb69c  ldloc.s  6
0xb69e  ldc.i4.1
0xb69f  stfld    bool System.Deployment.Application.CommitApplicationParams::IsRequiredUpdate
0xb6a4  ldarg.0
0xb6a5  ldloc.s  6
0xb6a7  ldarg.1
0xb6a8  ldind.ref
0xb6a9  call     instance void System.Deployment.Application.ApplicationActivator::CheckDeploymentProviderValidity(class System.Deployment.Application.ActivationDescription actDesc, class System.Deployment.Application.SubscriptionState subState)
0xb6ae  ldarg.0
0xb6af  ldarg.1
0xb6b0  ldloc.s  6
0xb6b2  call     instance void System.Deployment.Application.ApplicationActivator::ConsumeUpdatedDeployment(class System.Deployment.Application.SubscriptionState& subState, class System.Deployment.Application.ActivationDescription actDesc)
0xb6b7  leave.s  loc_B6C3
0xb6b9  ldloc.2
0xb6ba  brfalse.s loc_B6C2
0xb6bc  ldloc.2
0xb6bd  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0xb6c2  endfinally
0xb6c3  ret
```
