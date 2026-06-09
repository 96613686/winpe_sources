# System.Deployment.Application.ApplicationActivator::UninstallApplicationAndRedirectActivation

- ea: `0xabd0`
- end: `0xac93`
- name: `System.Deployment.Application.ApplicationActivator::UninstallApplicationAndRedirectActivation`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0xaca0`

## callees

- `0xabd0`
- `0xd930`
- `0x13480`
- `0x17c60`
- `0x1d730`
- `0x1ecf0`
- `0x1f0b0`
- `0x1f170`
- `0x1f5f0`
- `0x1f8a0`
- `0x23020`

## string_xrefs

- `0xac6f`: `Uninstall_FailedMsg`

## pseudocode

```c

```

## disassembly

```asm
0xabd0  ldnull
0xabd1  stloc.0
0xabd2  ldnull
0xabd3  stloc.1
0xabd4  ldnull
0xabd5  stloc.2
0xabd6  ldnull
0xabd7  stloc.3
0xabd8  call     class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionStore::get_CurrentUser()
0xabdd  stloc.s  4
0xabdf  ldloc.s  4
0xabe1  callvirt instance void System.Deployment.Application.SubscriptionStore::RefreshStorePointer()
0xabe6  ldarg.1
0xabe7  ldind.u1
0xabe8  brfalse.s loc_AC30
0xabea  ldarg.s  4
0xabec  callvirt instance string [System]System.Uri::get_LocalPath()
0xabf1  ldc.i4.s 0x7C
0xabf3  ldc.i4.0
0xabf4  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0xabf9  stloc.s  5
0xabfb  ldloc.s  5
0xabfd  ldc.i4.0
0xabfe  bgt.s    loc_AC09
0xac00  ldarg.s  4
0xac02  callvirt instance string [System]System.Uri::get_LocalPath()
0xac07  br.s     loc_AC18
0xac09  ldarg.s  4
0xac0b  callvirt instance string [System]System.Uri::get_LocalPath()
0xac10  ldc.i4.0
0xac11  ldloc.s  5
0xac13  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xac18  stloc.s  6
0xac1a  ldloc.s  6
0xac1c  ldloca.s 0
0xac1e  ldloca.s 3
0xac20  call     void System.Deployment.Application.ShellExposure::ParseAppShortcut(string shortcutFile, [out] class System.Deployment.Application.DefinitionIdentity& subId, [out] class [System]System.Uri& providerUri)
0xac25  ldloc.s  4
0xac27  ldloc.0
0xac28  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.DefinitionIdentity subId)
0xac2d  stloc.1
0xac2e  br.s     loc_AC55
0xac30  ldarg.3
0xac31  brfalse.s loc_AC45
0xac33  ldarg.3
0xac34  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(string text)
0xac39  stloc.0
0xac3a  ldloc.s  4
0xac3c  ldloc.0
0xac3d  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.DefinitionIdentity subId)
0xac42  stloc.1
0xac43  br.s     loc_AC55
0xac45  ldloc.s  4
0xac47  ldarg.2
0xac48  ldloca.s 2
0xac4a  ldloca.s 1
0xac4c  ldnull
0xac4d  ldnull
0xac4e  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifestBypass(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile, [out] class System.Deployment.Application.SubscriptionState& subState, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options)
0xac53  stloc.s  7
0xac55  ldloc.1
0xac56  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0xac5b  ldloc.1
0xac5c  callvirt instance void System.Deployment.Application.SubscriptionStore::UninstallSubscription(class System.Deployment.Application.SubscriptionState subState)
0xac61  ldarg.1
0xac62  ldind.u1
0xac63  brfalse.s loc_AC6B
0xac65  ldarg.2
0xac66  ldloc.3
0xac67  stind.ref
0xac68  ldarg.1
0xac69  ldc.i4.0
0xac6a  stind.i1
0xac6b  leave.s  loc_AC92
0xac6d  stloc.s  8
0xac6f  ldstr    aUninstallFaile// "Uninstall_FailedMsg"
0xac74  call     string System.Deployment.Application.Resources::GetString(string s)
0xac79  ldloc.s  8
0xac7b  call     void System.Deployment.Application.Logger::AddErrorInformation(string message, class [mscorlib]System.Exception exception)
0xac80  ldloc.s  8
0xac82  call     class [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo::Capture(class [mscorlib]System.Exception)
0xac87  stloc.s  9
0xac89  ldloc.s  9
0xac8b  callvirt instance void [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo::Throw()
0xac90  leave.s  loc_AC92
0xac92  ret
```
