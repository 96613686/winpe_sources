# System.Deployment.Application.ShellExposure::UpdateShellExtensions

- ea: `0x1ded0`
- end: `0x1df48`
- name: `System.Deployment.Application.ShellExposure::UpdateShellExtensions`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1d5b0`
- `0x1f1c0`

## callees

- `0xda60`
- `0x17d40`
- `0x1a620`
- `0x1d6f0`
- `0x1ded0`
- `0x1dfc0`
- `0x1ece0`
- `0x1ed60`
- `0x1ede0`
- `0x1ef20`
- `0x1ef60`
- `0x2c5a0`

## string_xrefs

- `0x1df11`: `Registering file associations if there is any in the manifest for the new version. `

## pseudocode

```c

```

## disassembly

```asm
0x1ded0  ldnull
0x1ded1  stloc.0
0x1ded2  ldarg.1
0x1ded3  ldind.ref
0x1ded4  brfalse.s loc_1DEDE
0x1ded6  ldarg.1
0x1ded7  ldind.ref
0x1ded8  callvirt instance string ShellExposureInformation::get_AppProduct()
0x1dedd  stloc.0
0x1dede  ldloc.0
0x1dedf  brtrue.s loc_1DEED
0x1dee1  ldarg.0
0x1dee2  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1dee7  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_Name()
0x1deec  stloc.0
0x1deed  ldarg.0
0x1deee  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_PreviousBind()
0x1def3  brfalse.s loc_1DF11
0x1def5  ldstr    aRemovingFileAs// "Removing file associations if existed f"...
0x1defa  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1deff  ldarg.0
0x1df00  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1df05  ldarg.0
0x1df06  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_PreviousApplicationManifest()
0x1df0b  ldloc.0
0x1df0c  call     void System.Deployment.Application.ShellExposure::RemoveShellExtensions(class System.Deployment.Application.DefinitionIdentity subId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string productName)
0x1df11  ldstr    aRegisteringFil// "Registering file associations if there "...
0x1df16  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1df1b  ldarg.0
0x1df1c  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1df21  ldarg.0
0x1df22  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x1df27  ldarg.0
0x1df28  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x1df2d  call     void System.Deployment.Application.ShellExposure::AddShellExtensions(class System.Deployment.Application.DefinitionIdentity subId, class [System]System.Uri deploymentProviderUri, class System.Deployment.Application.Manifest.AssemblyManifest appManifest)
0x1df32  ldc.i4   0x8000000
0x1df37  ldc.i4.0
0x1df38  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1df3d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1df42  call     void System.Deployment.Application.NativeMethods::SHChangeNotify(int32 eventID, unsigned int32 flags, native int item1, native int item2)
0x1df47  ret
```
