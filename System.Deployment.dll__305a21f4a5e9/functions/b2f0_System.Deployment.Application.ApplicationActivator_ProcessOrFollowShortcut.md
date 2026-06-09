# System.Deployment.Application.ApplicationActivator::ProcessOrFollowShortcut

- ea: `0xb2f0`
- end: `0xb484`
- name: `System.Deployment.Application.ApplicationActivator::ProcessOrFollowShortcut`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xae50`

## callees

- `0xb2f0`
- `0xb490`
- `0xb4c0`
- `0xc200`
- `0xc2b0`
- `0xc2c0`
- `0x13170`
- `0x146f0`
- `0x17cd0`
- `0x17d40`
- `0x1d730`
- `0x1ed00`
- `0x1ed20`
- `0x1ed40`
- `0x1ef20`
- `0x1f8a0`
- `0x20b30`
- `0x23020`
- `0x23ca0`
- `0x23fe0`
- `0x24b30`
- `0x24b90`

## string_xrefs

- `0xb3fe`: `Start processing deployment manifest.`
- `0xb418`: `Processing of deployment manifest has successfully completed.`
- `0xb391`: `Application family is already installed and Shell Visible.`
- `0xb3e1`: `Application family is not installed or is not Shell-Visible.  Try to deploy it from the deployment provider specified in the shortcut : `

## pseudocode

```c

```

## disassembly

```asm
0xb2f0  ldarg.3
0xb2f1  ldnull
0xb2f2  stind.ref
0xb2f3  ldc.i4.5
0xb2f4  newarr   [mscorlib]System.String
0xb2f9  dup
0xb2fa  ldc.i4.0
0xb2fb  ldstr    aProcessorfollo_0// "ProcessOrFollowShortcut(shortcutFile="
0xb300  stelem.ref
0xb301  dup
0xb302  ldc.i4.1
0xb303  ldarg.1
0xb304  stelem.ref
0xb305  dup
0xb306  ldc.i4.2
0xb307  ldstr    aErrorpageurl// ",errorPageUrl="
0xb30c  stelem.ref
0xb30d  dup
0xb30e  ldc.i4.3
0xb30f  ldarg.2
0xb310  ldind.ref
0xb311  stelem.ref
0xb312  dup
0xb313  ldc.i4.4
0xb314  ldstr    aCalled// ") called."
0xb319  stelem.ref
0xb31a  call     string [mscorlib]System.String::Concat(string[])
0xb31f  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0xb324  ldarg.1
0xb325  stloc.0
0xb326  ldnull
0xb327  stloc.1
0xb328  ldarg.1
0xb329  ldc.i4.s 0x7C
0xb32b  ldc.i4.0
0xb32c  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0xb331  stloc.2
0xb332  ldloc.2
0xb333  ldc.i4.0
0xb334  ble.s    loc_B354
0xb336  ldarg.1
0xb337  ldc.i4.0
0xb338  ldloc.2
0xb339  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xb33e  stloc.0
0xb33f  ldloc.2
0xb340  ldc.i4.1
0xb341  add
0xb342  ldarg.1
0xb343  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb348  bge.s    loc_B354
0xb34a  ldarg.1
0xb34b  ldloc.2
0xb34c  ldc.i4.1
0xb34d  add
0xb34e  callvirt instance string [mscorlib]System.String::Substring(int32)
0xb353  stloc.1
0xb354  ldstr    aShortcutparame// "shortcutParameter="
0xb359  ldloc.1
0xb35a  call     string [mscorlib]System.String::Concat(string, string)
0xb35f  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb364  ldloc.0
0xb365  ldloca.s 3
0xb367  ldloca.s 4
0xb369  call     void System.Deployment.Application.ShellExposure::ParseAppShortcut(string shortcutFile, [out] class System.Deployment.Application.DefinitionIdentity& subId, [out] class [System]System.Uri& providerUri)
0xb36e  ldarg.0
0xb36f  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb374  ldloc.3
0xb375  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.DefinitionIdentity subId)
0xb37a  stloc.s  5
0xb37c  ldnull
0xb37d  stloc.s  6
0xb37f  ldloc.s  5
0xb381  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0xb386  brfalse.s loc_B3DD
0xb388  ldloc.s  5
0xb38a  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0xb38f  brfalse.s loc_B3DD
0xb391  ldstr    aApplicationFam// "Application family is already installed"...
0xb396  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb39b  ldarg.0
0xb39c  ldloca.s 5
0xb39e  ldarg.2
0xb39f  call     instance void System.Deployment.Application.ApplicationActivator::PerformDeploymentUpdate(class System.Deployment.Application.SubscriptionState& subState, string& errorPageUrl)
0xb3a4  ldloc.1
0xb3a5  brtrue.s loc_B3C2
0xb3a7  ldarg.0
0xb3a8  ldloc.s  5
0xb3aa  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xb3af  ldloc.s  5
0xb3b1  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0xb3b6  ldnull
0xb3b7  ldc.i4.0
0xb3b8  call     instance void System.Deployment.Application.ApplicationActivator::Activate(class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string activationParameter, bool useActivationParameter)
0xb3bd  br       loc_B481
0xb3c2  ldarg.0
0xb3c3  ldloc.s  5
0xb3c5  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xb3ca  ldloc.s  5
0xb3cc  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0xb3d1  ldloc.1
0xb3d2  ldc.i4.1
0xb3d3  call     instance void System.Deployment.Application.ApplicationActivator::Activate(class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string activationParameter, bool useActivationParameter)
0xb3d8  br       loc_B481
0xb3dd  ldloc.s  4
0xb3df  stloc.s  7
0xb3e1  ldstr    aApplicationFam_1// "Application family is not installed or "...
0xb3e6  ldloc.s  7
0xb3e8  dup
0xb3e9  brtrue.s loc_B3EF
0xb3eb  pop
0xb3ec  ldnull
0xb3ed  br.s     loc_B3F4
0xb3ef  callvirt instance string [mscorlib]System.Object::ToString()
0xb3f4  call     string [mscorlib]System.String::Concat(string, string)
0xb3f9  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb3fe  ldstr    aStartProcessin// "Start processing deployment manifest."
0xb403  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb408  ldarg.0
0xb409  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb40e  ldloca.s 7
0xb410  ldarg.3
0xb411  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifest(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile)
0xb416  stloc.s  8
0xb418  ldstr    aProcessingOfDe// "Processing of deployment manifest has s"...
0xb41d  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb422  ldloc.s  8
0xb424  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xb429  brfalse.s loc_B439
0xb42b  ldarg.2
0xb42c  ldloc.s  8
0xb42e  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xb433  callvirt instance string System.Deployment.Application.Manifest.Description::get_ErrorReportUrl()
0xb438  stind.ref
0xb439  ldloc.s  8
0xb43b  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xb440  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0xb445  brtrue.s loc_B458
0xb447  ldc.i4.1
0xb448  ldstr    aExShortcutrefo// "Ex_ShortcutRefOnlineOnly"
0xb44d  call     string System.Deployment.Application.Resources::GetString(string s)
0xb452  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xb457  throw
0xb458  newobj   instance void System.Deployment.Application.ActivationDescription::.ctor()
0xb45d  stloc.s  6
0xb45f  ldloc.s  6
0xb461  ldloc.s  8
0xb463  ldloc.s  7
0xb465  ldarg.3
0xb466  ldind.ref
0xb467  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0xb46c  callvirt instance void System.Deployment.Application.ActivationDescription::SetDeploymentManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0xb471  ldloc.s  6
0xb473  ldc.i4.0
0xb474  stfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0xb479  ldloc.s  6
0xb47b  ldc.i4.2
0xb47c  callvirt instance void System.Deployment.Application.ActivationDescription::set_ActType(valuetype System.Deployment.Application.ActivationType value)
0xb481  ldloc.s  6
0xb483  ret
```
