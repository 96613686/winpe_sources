# System.Deployment.Application.SubscriptionStore::CheckForDeploymentUpdate

- ea: `0x1f8f0`
- end: `0x1f9af`
- name: `System.Deployment.Application.SubscriptionStore::CheckForDeploymentUpdate`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x12e10`

## callees

- `0xda80`
- `0x13110`
- `0x13170`
- `0x17d50`
- `0x1ece0`
- `0x1ecf0`
- `0x1eda0`
- `0x1ede0`
- `0x1eea0`
- `0x1f770`
- `0x1f8f0`
- `0x1f9b0`
- `0x1fba0`
- `0x23020`
- `0x24970`

## string_xrefs

- `0x1f963`: `Upd_FoundUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x1f8f0  ldarg.0
0x1f8f1  ldarg.1
0x1f8f2  call     instance void System.Deployment.Application.SubscriptionStore::CheckInstalledAndShellVisible(class System.Deployment.Application.SubscriptionState subState)
0x1f8f7  ldarg.1
0x1f8f8  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_DeploymentProviderUri()
0x1f8fd  stloc.0
0x1f8fe  ldnull
0x1f8ff  stloc.1
0x1f900  ldarg.1
0x1f901  callvirt instance class System.Deployment.Application.SubscriptionStore System.Deployment.Application.SubscriptionState::get_SubscriptionStore()
0x1f906  ldloca.s 0
0x1f908  ldloca.s 1
0x1f90a  call     class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.DownloadManager::DownloadDeploymentManifest(class System.Deployment.Application.SubscriptionStore subStore, class [System]System.Uri& sourceUri, [out] class System.Deployment.Application.TempFile& tempFile)
0x1f90f  stloc.2
0x1f910  ldarg.0
0x1f911  ldarg.1
0x1f912  ldloc.0
0x1f913  ldloc.2
0x1f914  ldarg.1
0x1f915  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_CurrentDeployment()
0x1f91a  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0x1f91f  call     instance class [mscorlib]System.Version System.Deployment.Application.SubscriptionStore::CheckUpdateInManifest(class System.Deployment.Application.SubscriptionState subState, class [System]System.Uri updateCodebaseUri, class System.Deployment.Application.Manifest.AssemblyManifest deployment, class [mscorlib]System.Version currentVersion)
0x1f924  stloc.3
0x1f925  ldloc.3
0x1f926  ldnull
0x1f927  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1f92c  brtrue.s loc_1F931
0x1f92e  ldnull
0x1f92f  br.s     loc_1F937
0x1f931  ldloc.2
0x1f932  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1f937  stloc.s  4
0x1f939  ldarg.0
0x1f93a  ldarg.1
0x1f93b  ldloc.s  4
0x1f93d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1f942  call     instance void System.Deployment.Application.SubscriptionStore::SetPendingDeployment(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.DefinitionIdentity deployId, valuetype [mscorlib]System.DateTime checkTime)
0x1f947  ldloc.3
0x1f948  ldnull
0x1f949  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1f94e  brfalse.s loc_1F9A2
0x1f950  ldloc.2
0x1f951  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1f956  ldarg.1
0x1f957  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_PendingDeployment()
0x1f95c  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1f961  brfalse.s loc_1F9A2
0x1f963  ldstr    aUpdFoundupdate// "Upd_FoundUpdate"
0x1f968  call     string System.Deployment.Application.Resources::GetString(string s)
0x1f96d  ldc.i4.3
0x1f96e  newarr   [mscorlib]System.Object
0x1f973  dup
0x1f974  ldc.i4.0
0x1f975  ldarg.1
0x1f976  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_SubscriptionId()
0x1f97b  callvirt instance string [mscorlib]System.Object::ToString()
0x1f980  stelem.ref
0x1f981  dup
0x1f982  ldc.i4.1
0x1f983  ldloc.2
0x1f984  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1f989  callvirt instance class [mscorlib]System.Version System.Deployment.Application.DefinitionIdentity::get_Version()
0x1f98e  callvirt instance string [mscorlib]System.Object::ToString()
0x1f993  stelem.ref
0x1f994  dup
0x1f995  ldc.i4.2
0x1f996  ldloc.0
0x1f997  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1f99c  stelem.ref
0x1f99d  call     void System.Deployment.Application.Logger::AddPhaseInformation(string messageFormat, object[] args)
0x1f9a2  leave.s  loc_1F9AE
0x1f9a4  ldloc.1
0x1f9a5  brfalse.s loc_1F9AD
0x1f9a7  ldloc.1
0x1f9a8  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x1f9ad  endfinally
0x1f9ae  ret
```
