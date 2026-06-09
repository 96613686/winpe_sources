# System.Deployment.Application.ComponentStore::PrepareCommitApplication

- ea: `0xef90`
- end: `0xf02a`
- name: `System.Deployment.Application.ComponentStore::PrepareCommitApplication`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xe360`

## callees

- `0xef90`
- `0xf030`
- `0xf160`
- `0xf280`
- `0xf500`
- `0x23fe0`
- `0x24b90`
- `0x284a0`
- `0x285e0`

## pseudocode

```c

```

## disassembly

```asm
0xef90  ldarg.3
0xef91  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0xef96  stloc.0
0xef97  ldnull
0xef98  stloc.1
0xef99  ldarg.3
0xef9a  ldfld    bool System.Deployment.Application.CommitApplicationParams::CommitDeploy
0xef9f  brfalse.s loc_EFE0
0xefa1  ldarg.0
0xefa2  ldarg.1
0xefa3  ldarg.2
0xefa4  ldarg.3
0xefa5  call     instance class System.Deployment.Application.SubscriptionStateInternal System.Deployment.Application.ComponentStore::PrepareCommitDeploymentState(class StoreTransactionContext storeTxn, class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.CommitApplicationParams commitParams)
0xefaa  stloc.1
0xefab  ldarg.3
0xefac  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsConfirmed
0xefb1  brfalse.s loc_EFC1
0xefb3  ldloc.0
0xefb4  ldloc.1
0xefb5  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::CurrentBind
0xefba  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xefbf  brtrue.s loc_EFD7
0xefc1  ldarg.3
0xefc2  ldfld    bool System.Deployment.Application.CommitApplicationParams::IsConfirmed
0xefc7  brtrue.s loc_EFE0
0xefc9  ldloc.0
0xefca  ldloc.1
0xefcb  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionStateInternal::PendingBind
0xefd0  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xefd5  brfalse.s loc_EFE0
0xefd7  ldarg.0
0xefd8  ldarg.1
0xefd9  ldarg.2
0xefda  ldarg.3
0xefdb  call     instance void System.Deployment.Application.ComponentStore::PrepareStageDeploymentComponent(class StoreTransactionContext storeTxn, class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.CommitApplicationParams commitParams)
0xefe0  ldarg.3
0xefe1  ldfld    bool System.Deployment.Application.CommitApplicationParams::CommitApp
0xefe6  brfalse.s loc_F018
0xefe8  ldarg.0
0xefe9  ldarg.1
0xefea  ldarg.3
0xefeb  call     instance void System.Deployment.Application.ComponentStore::PrepareStageAppComponent(class StoreTransactionContext storeTxn, class System.Deployment.Application.CommitApplicationParams commitParams)
0xeff0  ldarg.3
0xeff1  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0xeff6  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0xeffb  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0xf000  brtrue.s loc_F018
0xf002  ldarg.3
0xf003  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.CommitApplicationParams::appType
0xf008  ldc.i4.3
0xf009  beq.s    loc_F018
0xf00b  ldarg.1
0xf00c  callvirt instance class ScavengeContext StoreTransactionContext::get_ScavengeContext()
0xf011  ldloc.0
0xf012  ldarg.2
0xf013  callvirt instance void ScavengeContext::AddOnlineAppToCommit(class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.SubscriptionState subState)
0xf018  ldarg.3
0xf019  ldfld    bool System.Deployment.Application.CommitApplicationParams::CommitDeploy
0xf01e  brfalse.s loc_F029
0xf020  ldarg.0
0xf021  ldarg.1
0xf022  ldarg.2
0xf023  ldloc.1
0xf024  call     instance void System.Deployment.Application.ComponentStore::PrepareSetSubscriptionState(class StoreTransactionContext storeTxn, class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.SubscriptionStateInternal newState)
0xf029  ret
```
