# System.Deployment.Application.DeploymentManager::SynchronizeGroupCore

- ea: `0x122a0`
- end: `0x12460`
- name: `System.Deployment.Application.DeploymentManager::SynchronizeGroupCore`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting`

## callers

- `0x10ec0`
- `0x12230`

## callees

- `0x122a0`
- `0x124d0`
- `0x12920`
- `0x12990`
- `0x13110`
- `0x13720`
- `0x146f0`
- `0x14d60`
- `0x1f1c0`
- `0x1f8b0`
- `0x1fc20`
- `0x1fc90`
- `0x1fcb0`
- `0x1fd20`
- `0x200e0`
- `0x20a60`
- `0x23020`
- `0x23fe0`
- `0x24b90`
- `0x24d10`

## string_xrefs

- `0x1231f`: `Ex_FileExtensionNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x122a0  ldnull
0x122a1  stloc.0
0x122a2  ldarg.2
0x122a3  callvirt instance string System.Deployment.Application.SyncGroupHelper::get_Group()
0x122a8  stloc.1
0x122a9  ldarg.0
0x122aa  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x122af  ldarg.0
0x122b0  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x122b5  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x122ba  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x122bf  stloc.2
0x122c0  ldarg.0
0x122c1  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x122c6  ldloc.2
0x122c7  ldarg.0
0x122c8  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x122cd  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0x122d2  ldarg.0
0x122d3  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x122d8  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x122dd  ldloc.1
0x122de  callvirt instance bool System.Deployment.Application.SubscriptionStore::CheckGroupInstalled(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.DefinitionAppId appId, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, string groupName)
0x122e3  brfalse.s loc_122ED
0x122e5  ldc.i4.0
0x122e6  stloc.s  6
0x122e8  leave    loc_1245D
0x122ed  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x122f2  callvirt instance class [mscorlib]System.Security.Policy.ApplicationTrust [mscorlib]System.AppDomain::get_ApplicationTrust()
0x122f7  callvirt instance class [mscorlib]System.Security.Policy.PolicyStatement [mscorlib]System.Security.Policy.ApplicationTrust::get_DefaultGrantSet()
0x122fc  callvirt instance class [mscorlib]System.Security.PermissionSet [mscorlib]System.Security.Policy.PolicyStatement::get_PermissionSet()
0x12301  callvirt instance bool [mscorlib]System.Security.PermissionSet::IsUnrestricted()
0x12306  stloc.3
0x12307  ldloc.3
0x12308  brtrue.s loc_1232F
0x1230a  ldarg.0
0x1230b  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x12310  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x12315  callvirt instance class System.Deployment.Application.Manifest.FileAssociation[] System.Deployment.Application.Manifest.AssemblyManifest::get_FileAssociations()
0x1231a  ldlen
0x1231b  brfalse.s loc_1232F
0x1231d  ldc.i4.s 0x10
0x1231f  ldstr    aExFileextensio// "Ex_FileExtensionNotSupported"
0x12324  call     string System.Deployment.Application.Resources::GetString(string s)
0x12329  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1232e  throw
0x1232f  ldarg.0
0x12330  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x12335  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x1233a  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x1233f  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0x12344  ldc.i4.0
0x12345  ceq
0x12347  stloc.s  4
0x12349  ldloc.3
0x1234a  ldc.i4.0
0x1234b  ceq
0x1234d  ldloc.s  4
0x1234f  and
0x12350  brfalse.s loc_123A8
0x12352  ldarg.0
0x12353  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x12358  brtrue.s loc_12365
0x1235a  ldarg.0
0x1235b  newobj   instance void System.Deployment.Application.DownloadOptions::.ctor()
0x12360  stfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x12365  ldarg.0
0x12366  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x1236b  ldc.i4.1
0x1236c  stfld    bool System.Deployment.Application.DownloadOptions::EnforceSizeLimit
0x12371  ldarg.0
0x12372  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x12377  ldarg.0
0x12378  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x1237d  callvirt instance unsigned int64 System.Deployment.Application.SubscriptionStore::GetSizeLimitInBytesForSemiTrustApps()
0x12382  stfld    unsigned int64 System.Deployment.Application.DownloadOptions::SizeLimit
0x12387  ldarg.0
0x12388  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x1238d  ldarg.0
0x1238e  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x12393  ldarg.0
0x12394  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x12399  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0x1239e  callvirt instance unsigned int64 System.Deployment.Application.SubscriptionStore::GetPrivateSize(class System.Deployment.Application.DefinitionAppId appId)
0x123a3  stfld    unsigned int64 System.Deployment.Application.DownloadOptions::Size
0x123a8  ldarg.0
0x123a9  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x123ae  callvirt instance class System.Deployment.Application.TempDirectory System.Deployment.Application.SubscriptionStore::AcquireTempDirectory()
0x123b3  stloc.0
0x123b4  ldloc.2
0x123b5  ldarg.0
0x123b6  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x123bb  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x123c0  ldarg.0
0x123c1  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x123c6  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x123cb  ldarg.0
0x123cc  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x123d1  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::AppSourceUri
0x123d6  ldloc.0
0x123d7  callvirt instance string System.Deployment.Application.TempDirectory::get_Path()
0x123dc  ldloc.1
0x123dd  ldarg.1
0x123de  brtrue.s loc_123E3
0x123e0  ldarg.2
0x123e1  br.s     loc_123E4
0x123e3  ldnull
0x123e4  ldarg.0
0x123e5  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x123ea  call     void System.Deployment.Application.DownloadManager::DownloadDependencies(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest deployManifest, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, class [System]System.Uri sourceUriBase, string targetDirectory, string group, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options)
0x123ef  ldarg.1
0x123f0  brtrue.s loc_123FF
0x123f2  ldarg.2
0x123f3  callvirt instance bool System.Deployment.Application.SyncGroupHelper::get_CancellationPending()
0x123f8  brfalse.s loc_123FF
0x123fa  ldc.i4.1
0x123fb  stloc.s  6
0x123fd  leave.s  loc_1245D
0x123ff  ldarg.0
0x12400  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x12405  newobj   instance void System.Deployment.Application.CommitApplicationParams::.ctor(class System.Deployment.Application.CommitApplicationParams src)
0x1240a  stloc.s  5
0x1240c  ldloc.s  5
0x1240e  ldc.i4.1
0x1240f  stfld    bool System.Deployment.Application.CommitApplicationParams::CommitApp
0x12414  ldloc.s  5
0x12416  ldloc.0
0x12417  callvirt instance string System.Deployment.Application.TempDirectory::get_Path()
0x1241c  stfld    string System.Deployment.Application.CommitApplicationParams::AppPayloadPath
0x12421  ldloc.s  5
0x12423  ldnull
0x12424  stfld    string System.Deployment.Application.CommitApplicationParams::AppManifestPath
0x12429  ldloc.s  5
0x1242b  ldloc.1
0x1242c  stfld    string System.Deployment.Application.CommitApplicationParams::AppGroup
0x12431  ldloc.s  5
0x12433  ldc.i4.0
0x12434  stfld    bool System.Deployment.Application.CommitApplicationParams::CommitDeploy
0x12439  ldarg.0
0x1243a  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x1243f  ldloca.s 2
0x12441  ldloc.s  5
0x12443  callvirt instance void System.Deployment.Application.SubscriptionStore::CommitApplication(class System.Deployment.Application.SubscriptionState& subState, class System.Deployment.Application.CommitApplicationParams commitParams)
0x12448  leave.s  loc_1245B
0x1244a  ldarg.0
0x1244b  ldarg.2
0x1244c  call     instance void System.Deployment.Application.DeploymentManager::DetachFromGroup(class System.Deployment.Application.SyncGroupHelper sgh)
0x12451  ldloc.0
0x12452  brfalse.s loc_1245A
0x12454  ldloc.0
0x12455  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x1245a  endfinally
0x1245b  ldc.i4.0
0x1245c  ret
0x1245d  ldloc.s  6
0x1245f  ret
```
