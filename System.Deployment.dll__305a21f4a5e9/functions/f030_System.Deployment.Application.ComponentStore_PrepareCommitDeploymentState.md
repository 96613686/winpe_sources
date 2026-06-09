# System.Deployment.Application.ComponentStore::PrepareCommitDeploymentState

- ea: `0xf030`
- end: `0xf155`
- name: `System.Deployment.Application.ComponentStore::PrepareCommitDeploymentState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0xef90`

## callees

- `0xd600`
- `0xf030`
- `0xf520`
- `0xf5f0`
- `0xfc00`
- `0x1ed20`
- `0x1ed40`
- `0x1ee40`
- `0x23fa0`
- `0x23fc0`
- `0x23fe0`
- `0x24b90`

## pseudocode

```c

```

## disassembly

```asm
0xf030  ldarg.3
0xf031  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xf036  stloc.0
0xf037  ldarg.3
0xf038  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xf03d  stloc.1
0xf03e  ldarg.2
0xf03f  newobj   instance void System.Deployment.Application.SubscriptionStateInternal::.ctor(class System.Deployment.Application.SubscriptionState subState)
0xf044  stloc.2
0xf045  ldarg.3
0xf046  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsConfirmed
0xf04b  brfalse  loc_F115
0xf050  ldloc.2
0xf051  ldc.i4.1
0xf052  stfld    bool System.Deployment.Application.SubscriptionStateInternal::IsInstalled
0xf057  ldloc.2
0xf058  ldloc.1
0xf059  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xf05e  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0xf063  stfld    bool System.Deployment.Application.SubscriptionStateInternal::IsShellVisible
0xf068  ldloc.2
0xf069  ldloc.1
0xf06a  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xf06f  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Deployment::get_ProviderCodebaseUri()
0xf074  ldnull
0xf075  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xf07a  brtrue.s loc_F084
0xf07c  ldarg.3
0xf07d  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::DeploySourceUri
0xf082  br.s     loc_F08F
0xf084  ldloc.1
0xf085  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xf08a  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Deployment::get_ProviderCodebaseUri()
0xf08f  stfld    class [System]System.Uri System.Deployment.Application.SubscriptionStateInternal::DeploymentProviderUri
0xf094  ldloc.1
0xf095  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xf09a  callvirt instance class [mscorlib]System.Version System.Deployment.Application.Manifest.Deployment::get_MinimumRequiredVersion()
0xf09f  ldnull
0xf0a0  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xf0a5  brfalse.s loc_F0B8
0xf0a7  ldloc.2
0xf0a8  ldloc.1
0xf0a9  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xf0ae  callvirt instance class [mscorlib]System.Version System.Deployment.Application.Manifest.Deployment::get_MinimumRequiredVersion()
0xf0b3  stfld    class [mscorlib]System.Version System.Deployment.Application.SubscriptionStateInternal::MinimumRequiredVersion
0xf0b8  ldloc.0
0xf0b9  ldarg.2
0xf0ba  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xf0bf  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xf0c4  brtrue.s loc_F0EC
0xf0c6  ldloc.2
0xf0c7  ldloc.0
0xf0c8  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xf0cd  ldloc.2
0xf0ce  ldloc.2
0xf0cf  ldfld    bool System.Deployment.Application.SubscriptionStateInternal::IsShellVisible
0xf0d4  brfalse.s loc_F0DE
0xf0d6  ldarg.2
0xf0d7  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsShellVisible()
0xf0dc  brfalse.s loc_F0E6
0xf0de  ldarg.2
0xf0df  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0xf0e4  br.s     loc_F0E7
0xf0e6  ldnull
0xf0e7  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PreviousBind
0xf0ec  ldloc.2
0xf0ed  ldnull
0xf0ee  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PendingBind
0xf0f3  ldloc.2
0xf0f4  ldnull
0xf0f5  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::PendingDeployment
0xf0fa  ldloc.2
0xf0fb  ldnull
0xf0fc  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::ExcludedDeployment
0xf101  ldloc.2
0xf102  ldarg.3
0xf103  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.CommitApplicationParams::appType
0xf108  stfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionStateInternal::appType
0xf10d  ldloc.2
0xf10e  call     void System.Deployment.Application.ComponentStore::ResetUpdateSkippedState(class System.Deployment.Application.SubscriptionStateInternal newState)
0xf113  br.s     loc_F141
0xf115  ldloc.2
0xf116  ldloc.0
0xf117  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PendingBind
0xf11c  ldloc.2
0xf11d  ldloc.0
0xf11e  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_DeploymentIdentity()
0xf123  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::PendingDeployment
0xf128  ldloc.2
0xf129  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionStateInternal::PendingDeployment
0xf12e  ldarg.2
0xf12f  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.SubscriptionState::get_UpdateSkippedDeployment()
0xf134  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xf139  brtrue.s loc_F141
0xf13b  ldloc.2
0xf13c  call     void System.Deployment.Application.ComponentStore::ResetUpdateSkippedState(class System.Deployment.Application.SubscriptionStateInternal newState)
0xf141  ldloc.2
0xf142  ldarg.3
0xf143  ldfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.CommitApplicationParams::TimeStamp
0xf148  stfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.SubscriptionStateInternal::LastCheckTime
0xf14d  ldloc.2
0xf14e  call     void System.Deployment.Application.ComponentStore::FinalizeSubscriptionState(class System.Deployment.Application.SubscriptionStateInternal newState)
0xf153  ldloc.2
0xf154  ret
```
