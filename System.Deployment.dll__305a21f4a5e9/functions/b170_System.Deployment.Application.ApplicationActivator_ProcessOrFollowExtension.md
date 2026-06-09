# System.Deployment.Application.ApplicationActivator::ProcessOrFollowExtension

- ea: `0xb170`
- end: `0xb2ea`
- name: `System.Deployment.Application.ApplicationActivator::ProcessOrFollowExtension`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0xae50`

## callees

- `0xb170`
- `0xb490`
- `0xb4c0`
- `0xc200`
- `0xc2b0`
- `0xc2c0`
- `0xd930`
- `0x13170`
- `0x146f0`
- `0x17cd0`
- `0x17d40`
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

- `0xb267`: `Start processing deployment manifest.`
- `0xb29a`: `Processing of deployment manifest has successfully completed.`
- `0xb17d`: `ProcessOrFollowExtension(`
- `0xb1f1`: `Application family is already installed and Shell Visible.`
- `0xb223`: `Application family is not installed or is not Shell-Visible.  Try to deploy it from the deployment provider specified in the extension : `

## pseudocode

```c

```

## disassembly

```asm
0xb170  ldarg.s  5
0xb172  ldnull
0xb173  stind.ref
0xb174  ldc.i4.s 9
0xb176  newarr   [mscorlib]System.String
0xb17b  dup
0xb17c  ldc.i4.0
0xb17d  ldstr    aProcessorfollo// "ProcessOrFollowExtension("
0xb182  stelem.ref
0xb183  dup
0xb184  ldc.i4.1
0xb185  ldarg.1
0xb186  dup
0xb187  brtrue.s loc_B18D
0xb189  pop
0xb18a  ldnull
0xb18b  br.s     loc_B192
0xb18d  callvirt instance string [mscorlib]System.Object::ToString()
0xb192  stelem.ref
0xb193  dup
0xb194  ldc.i4.2
0xb195  ldstr    asc_308B8// ","
0xb19a  stelem.ref
0xb19b  dup
0xb19c  ldc.i4.3
0xb19d  ldarg.2
0xb19e  stelem.ref
0xb19f  dup
0xb1a0  ldc.i4.4
0xb1a1  ldstr    asc_308B8// ","
0xb1a6  stelem.ref
0xb1a7  dup
0xb1a8  ldc.i4.5
0xb1a9  ldarg.3
0xb1aa  stelem.ref
0xb1ab  dup
0xb1ac  ldc.i4.6
0xb1ad  ldstr    asc_308B8// ","
0xb1b2  stelem.ref
0xb1b3  dup
0xb1b4  ldc.i4.7
0xb1b5  ldarg.s  4
0xb1b7  ldind.ref
0xb1b8  stelem.ref
0xb1b9  dup
0xb1ba  ldc.i4.8
0xb1bb  ldstr    aCalled// ") called."
0xb1c0  stelem.ref
0xb1c1  call     string [mscorlib]System.String::Concat(string[])
0xb1c6  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0xb1cb  ldarg.2
0xb1cc  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(string text)
0xb1d1  stloc.0
0xb1d2  ldarg.0
0xb1d3  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb1d8  ldloc.0
0xb1d9  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.DefinitionIdentity subId)
0xb1de  stloc.1
0xb1df  ldnull
0xb1e0  stloc.2
0xb1e1  ldloc.1
0xb1e2  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0xb1e7  brfalse.s loc_B223
0xb1e9  ldloc.1
0xb1ea  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0xb1ef  brfalse.s loc_B223
0xb1f1  ldstr    aApplicationFam// "Application family is already installed"...
0xb1f6  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb1fb  ldarg.0
0xb1fc  ldloca.s 1
0xb1fe  ldarg.s  4
0xb200  call     instance void System.Deployment.Application.ApplicationActivator::PerformDeploymentUpdate(class System.Deployment.Application.SubscriptionState& subState, string& errorPageUrl)
0xb205  ldarg.0
0xb206  ldloc.1
0xb207  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xb20c  ldloc.1
0xb20d  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0xb212  ldarg.1
0xb213  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb218  ldc.i4.1
0xb219  call     instance void System.Deployment.Application.ApplicationActivator::Activate(class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string activationParameter, bool useActivationParameter)
0xb21e  br       loc_B2E8
0xb223  ldstr    aApplicationFam_0// "Application family is not installed or "...
0xb228  ldarg.3
0xb229  call     string [mscorlib]System.String::Concat(string, string)
0xb22e  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb233  ldarg.3
0xb234  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb239  brfalse.s loc_B260
0xb23b  ldc.i4.1
0xb23c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xb241  ldstr    aExFileassociat// "Ex_FileAssociationNoDpUrl"
0xb246  call     string System.Deployment.Application.Resources::GetString(string s)
0xb24b  ldc.i4.1
0xb24c  newarr   [mscorlib]System.Object
0xb251  dup
0xb252  ldc.i4.0
0xb253  ldarg.2
0xb254  stelem.ref
0xb255  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb25a  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xb25f  throw
0xb260  ldarg.3
0xb261  newobj   instance void [System]System.Uri::.ctor(string)
0xb266  stloc.3
0xb267  ldstr    aStartProcessin// "Start processing deployment manifest."
0xb26c  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb271  ldarg.0
0xb272  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationActivator::_subStore
0xb277  ldloca.s 3
0xb279  ldarg.s  5
0xb27b  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifest(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile)
0xb280  stloc.s  4
0xb282  ldloc.s  4
0xb284  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xb289  brfalse.s loc_B29A
0xb28b  ldarg.s  4
0xb28d  ldloc.s  4
0xb28f  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0xb294  callvirt instance string System.Deployment.Application.Manifest.Description::get_ErrorReportUrl()
0xb299  stind.ref
0xb29a  ldstr    aProcessingOfDe// "Processing of deployment manifest has s"...
0xb29f  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0xb2a4  ldloc.s  4
0xb2a6  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xb2ab  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0xb2b0  brtrue.s loc_B2C3
0xb2b2  ldc.i4.1
0xb2b3  ldstr    aExFileassociat_0// "Ex_FileAssociationRefOnline"
0xb2b8  call     string System.Deployment.Application.Resources::GetString(string s)
0xb2bd  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0xb2c2  throw
0xb2c3  newobj   instance void System.Deployment.Application.ActivationDescription::.ctor()
0xb2c8  stloc.2
0xb2c9  ldloc.2
0xb2ca  ldloc.s  4
0xb2cc  ldloc.3
0xb2cd  ldarg.s  5
0xb2cf  ldind.ref
0xb2d0  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0xb2d5  callvirt instance void System.Deployment.Application.ActivationDescription::SetDeploymentManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0xb2da  ldloc.2
0xb2db  ldc.i4.0
0xb2dc  stfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0xb2e1  ldloc.2
0xb2e2  ldc.i4.3
0xb2e3  callvirt instance void System.Deployment.Application.ActivationDescription::set_ActType(valuetype System.Deployment.Application.ActivationType value)
0xb2e8  ldloc.2
0xb2e9  ret
```
