# System.Deployment.Application.DeploymentManager::BindCoreWithAppId

- ea: `0x11860`
- end: `0x11a1a`
- name: `System.Deployment.Application.DeploymentManager::BindCoreWithAppId`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update`

## callers

- `0x113b0`

## callees

- `0xc1b0`
- `0xc200`
- `0xc220`
- `0xc2c0`
- `0xd530`
- `0xd600`
- `0xdbd0`
- `0x11860`
- `0x125f0`
- `0x14780`
- `0x17840`
- `0x17960`
- `0x17a00`
- `0x17d30`
- `0x1ed00`
- `0x1ed40`
- `0x1eee0`
- `0x1ef00`
- `0x1ef20`
- `0x1ef40`
- `0x1efa0`
- `0x1f800`
- `0x1f890`
- `0x1f8a0`
- `0x23020`
- `0x23c30`
- `0x24970`

## string_xrefs

- `0x119bc`: `_cached=`
- `0x119dc`: `_isupdate=`
- `0x11888`: `Ex_BindAppIdNotInstalled`

## pseudocode

```c

```

## disassembly

```asm
0x11860  ldc.i4.0
0x11861  stloc.0
0x11862  ldarg.0
0x11863  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.DeploymentManager::_bindAppId
0x11868  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionAppId::get_DeploymentIdentity()
0x1186d  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.DefinitionIdentity::ToSubscriptionId()
0x11872  stloc.1
0x11873  ldarg.0
0x11874  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11879  ldloc.1
0x1187a  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.DefinitionIdentity subId)
0x1187f  stloc.2
0x11880  ldloc.2
0x11881  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0x11886  brtrue.s loc_11898
0x11888  ldstr    aExBindappidnot// "Ex_BindAppIdNotInstalled"
0x1188d  call     string System.Deployment.Application.Resources::GetString(string s)
0x11892  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message)
0x11897  throw
0x11898  ldarg.0
0x11899  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.DeploymentManager::_bindAppId
0x1189e  ldloc.2
0x1189f  callvirt instance class System.Deployment.Application.DefinitionAppId System.Deployment.Application.SubscriptionState::get_CurrentBind()
0x118a4  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x118a9  brtrue.s loc_118BB
0x118ab  ldstr    aExBindappidnot_0// "Ex_BindAppIdNotCurrrent"
0x118b0  call     string System.Deployment.Application.Resources::GetString(string s)
0x118b5  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(string message)
0x118ba  throw
0x118bb  ldarg.1
0x118bc  brtrue.s loc_118C8
0x118be  ldarg.0
0x118bf  ldfld    bool System.Deployment.Application.DeploymentManager::_cancellationPending
0x118c4  brfalse.s loc_118C8
0x118c6  ldc.i4.1
0x118c7  ret
0x118c8  ldarg.2
0x118c9  ldarg.0
0x118ca  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x118cf  ldloca.s 3
0x118d1  callvirt instance class [mscorlib]System.IO.FileStream System.Deployment.Application.SubscriptionStore::AcquireReferenceTransaction([out] int64& transactionId)
0x118d6  stind.ref
0x118d7  ldarg.0
0x118d8  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x118dd  ldloc.2
0x118de  ldarg.0
0x118df  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.DeploymentManager::_bindAppId
0x118e4  ldloc.3
0x118e5  callvirt instance bool System.Deployment.Application.SubscriptionStore::CheckAndReferenceApplication(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.DefinitionAppId appId, int64 transactionId)
0x118ea  stloc.0
0x118eb  newobj   instance void System.Deployment.Application.ActivationDescription::.ctor()
0x118f0  stloc.s  4
0x118f2  ldloc.s  4
0x118f4  ldloc.2
0x118f5  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x118fa  ldloc.2
0x118fb  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_CurrentDeploymentSourceUri()
0x11900  ldnull
0x11901  callvirt instance void System.Deployment.Application.ActivationDescription::SetDeploymentManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0x11906  ldarg.0
0x11907  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x1190c  ldloc.2
0x1190d  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentDeploymentManifest()
0x11912  call     void System.Deployment.Application.Logger::SetDeploymentManifest(class LogIdentity log, class System.Deployment.Application.Manifest.AssemblyManifest deploymentManifest)
0x11917  ldloc.s  4
0x11919  ldarg.0
0x1191a  ldfld    bool System.Deployment.Application.DeploymentManager::_isupdate
0x1191f  stfld    bool System.Deployment.Application.CommitApplicationParams::IsUpdate
0x11924  ldloc.s  4
0x11926  ldloc.2
0x11927  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x1192c  ldloc.2
0x1192d  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_CurrentApplicationSourceUri()
0x11932  ldnull
0x11933  callvirt instance void System.Deployment.Application.ActivationDescription::SetApplicationManifest(class System.Deployment.Application.Manifest.AssemblyManifest manifest, class [System]System.Uri manifestUri, string manifestPath)
0x11938  ldarg.0
0x11939  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x1193e  ldloc.2
0x1193f  callvirt instance class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.SubscriptionState::get_CurrentApplicationManifest()
0x11944  call     void System.Deployment.Application.Logger::SetApplicationManifest(class LogIdentity log, class System.Deployment.Application.Manifest.AssemblyManifest applicationManifest)
0x11949  ldarg.0
0x1194a  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x1194f  ldloc.2
0x11950  callvirt instance class [System]System.Uri System.Deployment.Application.SubscriptionState::get_CurrentApplicationSourceUri()
0x11955  call     void System.Deployment.Application.Logger::SetApplicationUrl(class LogIdentity log, class [System]System.Uri applicationUri)
0x1195a  ldloc.s  4
0x1195c  ldloc.s  4
0x1195e  callvirt instance string System.Deployment.Application.ActivationDescription::ToAppCodebase()
0x11963  ldc.i4.2
0x11964  newarr   System.Deployment.Application.DefinitionIdentity
0x11969  dup
0x1196a  ldc.i4.0
0x1196b  ldloc.s  4
0x1196d  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11972  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x11977  stelem.ref
0x11978  dup
0x11979  ldc.i4.1
0x1197a  ldloc.s  4
0x1197c  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x11981  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x11986  stelem.ref
0x11987  newobj   instance void System.Deployment.Application.DefinitionAppId::.ctor(string codebase, class System.Deployment.Application.DefinitionIdentity[] idPath)
0x1198c  stfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0x11991  ldarg.1
0x11992  brtrue.s loc_1199E
0x11994  ldarg.0
0x11995  ldfld    bool System.Deployment.Application.DeploymentManager::_cancellationPending
0x1199a  brfalse.s loc_1199E
0x1199c  ldc.i4.1
0x1199d  ret
0x1199e  ldloc.2
0x1199f  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.SubscriptionState::get_EffectiveDescription()
0x119a4  stloc.s  5
0x119a6  ldarg.3
0x119a7  ldloc.s  5
0x119a9  callvirt instance string System.Deployment.Application.Manifest.Description::get_Product()
0x119ae  stind.ref
0x119af  ldarg.0
0x119b0  ldloc.0
0x119b1  stfld    bool System.Deployment.Application.DeploymentManager::_cached
0x119b6  ldarg.0
0x119b7  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x119bc  ldstr    aCached// "_cached="
0x119c1  ldarg.0
0x119c2  ldflda   bool System.Deployment.Application.DeploymentManager::_cached
0x119c7  call     instance string [mscorlib]System.Boolean::ToString()
0x119cc  call     string [mscorlib]System.String::Concat(string, string)
0x119d1  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x119d6  ldarg.0
0x119d7  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x119dc  ldstr    aIsupdate_0// "_isupdate="
0x119e1  ldarg.0
0x119e2  ldflda   bool System.Deployment.Application.DeploymentManager::_isupdate
0x119e7  call     instance string [mscorlib]System.Boolean::ToString()
0x119ec  call     string [mscorlib]System.String::Concat(string, string)
0x119f1  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x119f6  ldarg.0
0x119f7  ldarg.2
0x119f8  ldind.ref
0x119f9  stfld    class [mscorlib]System.IO.FileStream System.Deployment.Application.DeploymentManager::_referenceTransaction
0x119fe  ldarg.0
0x119ff  ldloc.s  4
0x11a01  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0x11a06  call     class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::ConstructActivationContextFromStore(class System.Deployment.Application.DefinitionAppId defAppId)
0x11a0b  stfld    class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::_actCtx
0x11a10  ldarg.0
0x11a11  ldloc.s  4
0x11a13  stfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11a18  ldc.i4.0
0x11a19  ret
```
