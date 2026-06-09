# System.Deployment.Application.ApplicationDeployment::DetermineUpdateCheckResult

- ea: `0xd120`
- end: `0xd1f3`
- name: `System.Deployment.Application.ApplicationDeployment::DetermineUpdateCheckResult`
- size: `211`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0xc660`
- `0xc850`
- `0xcd50`
- `0xced0`

## callees

- `0xd120`
- `0xd2b0`
- `0x1ecd0`
- `0x1edc0`
- `0x1f9c0`
- `0x23fc0`
- `0x24970`
- `0x24b90`
- `0x252e0`

## pseudocode

```c

```

## disassembly

```asm
0xd120  ldc.i4.0
0xd121  stloc.0
0xd122  ldnull
0xd123  stloc.1
0xd124  ldc.i4.0
0xd125  stloc.2
0xd126  ldnull
0xd127  stloc.3
0xd128  ldc.i4.0
0xd129  conv.i8
0xd12a  stloc.s  4
0xd12c  ldc.i4.0
0xd12d  stloc.s  5
0xd12f  ldarg.1
0xd130  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xd135  stloc.s  6
0xd137  ldarg.0
0xd138  ldfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xd13d  callvirt instance void System.Deployment.Application.SubscriptionState::Invalidate()
0xd142  ldarg.0
0xd143  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.ApplicationDeployment::_subStore
0xd148  ldarg.0
0xd149  ldfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xd14e  ldarg.1
0xd14f  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::DeploySourceUri
0xd154  ldloc.s  6
0xd156  ldarg.0
0xd157  ldfld    class [mscorlib]System.Version System.Deployment.Application.ApplicationDeployment::_currentVersion
0xd15c  ldloca.s 5
0xd15e  callvirt instance class [mscorlib]System.Version System.Deployment.Application.SubscriptionStore::CheckUpdateInManifest(class System.Deployment.Application.SubscriptionState subState, class [System]System.Uri updateCodebaseUri, class System.Deployment.Application.Manifest.AssemblyManifest deployment, class [mscorlib]System.Version currentVersion, bool& bUpdateInPKTGroup)
0xd163  stloc.s  7
0xd165  ldloc.s  7
0xd167  ldnull
0xd168  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xd16d  brfalse.s loc_D1E7
0xd16f  ldloc.s  6
0xd171  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0xd176  ldarg.0
0xd177  ldfld    class System.Deployment.Application.SubscriptionState System.Deployment.Application.ApplicationDeployment::_subState
0xd17c  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_ExcludedDeployment()
0xd181  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xd186  brtrue.s loc_D1E7
0xd188  ldc.i4.1
0xd189  stloc.0
0xd18a  ldloc.s  7
0xd18c  stloc.1
0xd18d  ldloc.s  6
0xd18f  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xd194  callvirt instance class [mscorlib]System.Version System.Deployment.Application.Manifest.Deployment::get_MinimumRequiredVersion()
0xd199  stloc.3
0xd19a  ldloc.3
0xd19b  ldnull
0xd19c  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xd1a1  brfalse.s loc_D1B4
0xd1a3  ldloc.3
0xd1a4  ldarg.0
0xd1a5  ldfld    class [mscorlib]System.Version System.Deployment.Application.ApplicationDeployment::_currentVersion
0xd1aa  callvirt instance int32 [mscorlib]System.Version::CompareTo(class [mscorlib]System.Version)
0xd1af  ldc.i4.0
0xd1b0  ble.s    loc_D1B4
0xd1b2  ldc.i4.1
0xd1b3  stloc.2
0xd1b4  ldarg.1
0xd1b5  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0xd1ba  callvirt instance unsigned int64 System.Deployment.Application.Manifest.AssemblyManifest::CalculateDependenciesSize()
0xd1bf  stloc.s  8
0xd1c1  ldloc.s  8
0xd1c3  ldc.i8   0x7FFFFFFFFFFFFFFF
0xd1cc  ble.un.s loc_D1DB
0xd1ce  ldc.i8   0x7FFFFFFFFFFFFFFF
0xd1d7  stloc.s  4
0xd1d9  br.s     loc_D1DF
0xd1db  ldloc.s  8
0xd1dd  stloc.s  4
0xd1df  ldarg.1
0xd1e0  ldloc.s  5
0xd1e2  stfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdateInPKTGroup
0xd1e7  ldloc.0
0xd1e8  ldloc.1
0xd1e9  ldloc.2
0xd1ea  ldloc.3
0xd1eb  ldloc.s  4
0xd1ed  newobj   instance void System.Deployment.Application.UpdateCheckInfo::.ctor(bool updateAvailable, class [mscorlib]System.Version availableVersion, bool isUpdateRequired, class [mscorlib]System.Version minimumRequiredVersion, int64 updateSize)
0xd1f2  ret
```
