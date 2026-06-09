# System.Deployment.Application.DeploymentManager::SynchronizeCore

- ea: `0x11d60`
- end: `0x120ff`
- name: `System.Deployment.Application.DeploymentManager::SynchronizeCore`
- size: `927`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10de0`
- `0x11cf0`

## callees

- `0x11d60`
- `0x12100`
- `0x12190`
- `0x125f0`
- `0x12600`
- `0x13110`
- `0x13720`
- `0x146f0`
- `0x14d60`
- `0x17d30`
- `0x1f1c0`
- `0x1f8b0`
- `0x1fad0`
- `0x1faf0`
- `0x1fd20`
- `0x20a60`
- `0x23020`
- `0x23fe0`
- `0x249d0`
- `0x24b90`
- `0x24d10`

## string_xrefs

- `0x11e87`: `Ex_FileExtensionNotSupported`
- `0x11e08`: `Application is not cached.`
- `0x11ec1`: `Application is semi-trust and online. Size limits will be checked during download.`
- `0x11fbd`: `Application is cached.`
- `0x12000`: `Application is successfully committed to the store.`

## pseudocode

```c

```

## disassembly

```asm
0x11d60  ldarg.0
0x11d61  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11d66  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11d6b  stloc.0
0x11d6c  ldarg.0
0x11d6d  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11d72  ldloc.0
0x11d73  callvirt instance class System.Deployment.Application.SubscriptionState System.Deployment.Application.SubscriptionStore::GetSubscriptionState(class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x11d78  stloc.1
0x11d79  ldarg.0
0x11d7a  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11d7f  ldloc.1
0x11d80  ldloc.0
0x11d81  callvirt instance void System.Deployment.Application.SubscriptionStore::CheckDeploymentSubscriptionState(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest deployment)
0x11d86  ldarg.0
0x11d87  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11d8c  ldloc.1
0x11d8d  ldarg.0
0x11d8e  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11d93  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x11d98  callvirt instance void System.Deployment.Application.SubscriptionStore::CheckCustomUXFlag(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest application)
0x11d9d  ldarg.0
0x11d9e  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11da3  ldfld    string System.Deployment.Application.CommitApplicationParams::DeployManifestPath
0x11da8  brfalse.s loc_11DD9
0x11daa  ldarg.0
0x11dab  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11db0  ldc.i4.1
0x11db1  stfld    bool System.Deployment.Application.CommitApplicationParams::CommitDeploy
0x11db6  ldarg.0
0x11db7  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11dbc  ldarg.0
0x11dbd  ldfld    bool System.Deployment.Application.DeploymentManager::_isConfirmed
0x11dc2  stfld    bool System.Deployment.Application.CommitApplicationParams::IsConfirmed
0x11dc7  ldarg.0
0x11dc8  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11dcd  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x11dd2  stfld    valuetype [mscorlib]System.DateTime System.Deployment.Application.CommitApplicationParams::TimeStamp
0x11dd7  br.s     loc_11DE5
0x11dd9  ldarg.0
0x11dda  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11ddf  ldc.i4.0
0x11de0  stfld    bool System.Deployment.Application.CommitApplicationParams::CommitDeploy
0x11de5  ldarg.1
0x11de6  brtrue.s loc_11DF7
0x11de8  ldarg.0
0x11de9  ldfld    bool System.Deployment.Application.DeploymentManager::_cancellationPending
0x11dee  brfalse.s loc_11DF7
0x11df0  ldc.i4.1
0x11df1  stloc.3
0x11df2  leave    loc_120FD
0x11df7  ldarg.0
0x11df8  ldfld    bool System.Deployment.Application.DeploymentManager::_cached
0x11dfd  brtrue   loc_11FB7
0x11e02  ldarg.0
0x11e03  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11e08  ldstr    aApplicationIsN_0// "Application is not cached."
0x11e0d  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11e12  ldc.i4.0
0x11e13  stloc.s  4
0x11e15  ldarg.0
0x11e16  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11e1b  ldfld    valuetype System.Deployment.Application.AppType System.Deployment.Application.CommitApplicationParams::appType
0x11e20  ldc.i4.3
0x11e21  beq      loc_11F31
0x11e26  ldarg.0
0x11e27  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11e2c  ldfld    class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.CommitApplicationParams::Trust
0x11e31  brfalse  loc_11F2E
0x11e36  ldarg.0
0x11e37  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11e3c  ldfld    class [mscorlib]System.Security.Policy.ApplicationTrust System.Deployment.Application.CommitApplicationParams::Trust
0x11e41  callvirt instance class [mscorlib]System.Security.Policy.PolicyStatement [mscorlib]System.Security.Policy.ApplicationTrust::get_DefaultGrantSet()
0x11e46  callvirt instance class [mscorlib]System.Security.PermissionSet [mscorlib]System.Security.Policy.PolicyStatement::get_PermissionSet()
0x11e4b  callvirt instance bool [mscorlib]System.Security.PermissionSet::IsUnrestricted()
0x11e50  stloc.s  5
0x11e52  ldarg.0
0x11e53  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11e58  ldstr    aFulltrust_1// "fullTrust="
0x11e5d  ldloca.s 5
0x11e5f  call     instance string [mscorlib]System.Boolean::ToString()
0x11e64  call     string [mscorlib]System.String::Concat(string, string)
0x11e69  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11e6e  ldloc.s  5
0x11e70  brtrue.s loc_11E97
0x11e72  ldarg.0
0x11e73  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11e78  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x11e7d  callvirt instance class System.Deployment.Application.Manifest.FileAssociation[] System.Deployment.Application.Manifest.AssemblyManifest::get_FileAssociations()
0x11e82  ldlen
0x11e83  brfalse.s loc_11E97
0x11e85  ldc.i4.s 0x10
0x11e87  ldstr    aExFileextensio// "Ex_FileExtensionNotSupported"
0x11e8c  call     string System.Deployment.Application.Resources::GetString(string s)
0x11e91  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x11e96  throw
0x11e97  ldarg.0
0x11e98  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11e9d  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11ea2  callvirt instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x11ea7  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0x11eac  ldc.i4.0
0x11ead  ceq
0x11eaf  stloc.s  6
0x11eb1  ldloc.s  5
0x11eb3  ldc.i4.0
0x11eb4  ceq
0x11eb6  ldloc.s  6
0x11eb8  and
0x11eb9  brfalse.s loc_11F31
0x11ebb  ldarg.0
0x11ebc  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11ec1  ldstr    aApplicationIsS// "Application is semi-trust and online. S"...
0x11ec6  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11ecb  ldarg.0
0x11ecc  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x11ed1  brtrue.s loc_11EDE
0x11ed3  ldarg.0
0x11ed4  newobj   instance void System.Deployment.Application.DownloadOptions::.ctor()
0x11ed9  stfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x11ede  ldarg.0
0x11edf  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x11ee4  ldc.i4.1
0x11ee5  stfld    bool System.Deployment.Application.DownloadOptions::EnforceSizeLimit
0x11eea  ldarg.0
0x11eeb  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x11ef0  ldarg.0
0x11ef1  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11ef6  callvirt instance unsigned int64 System.Deployment.Application.SubscriptionStore::GetSizeLimitInBytesForSemiTrustApps()
0x11efb  stfld    unsigned int64 System.Deployment.Application.DownloadOptions::SizeLimit
0x11f00  ldarg.0
0x11f01  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x11f06  ldarg.0
0x11f07  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11f0c  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11f11  callvirt instance unsigned int64 System.Deployment.Application.Manifest.AssemblyManifest::get_SizeInBytes()
0x11f16  ldarg.0
0x11f17  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11f1c  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x11f21  callvirt instance unsigned int64 System.Deployment.Application.Manifest.AssemblyManifest::get_SizeInBytes()
0x11f26  add
0x11f27  stfld    unsigned int64 System.Deployment.Application.DownloadOptions::Size
0x11f2c  br.s     loc_11F31
0x11f2e  ldc.i4.1
0x11f2f  stloc.s  4
0x11f31  ldloc.1
0x11f32  ldarg.0
0x11f33  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11f38  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::DeployManifest
0x11f3d  ldarg.0
0x11f3e  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11f43  ldfld    class System.Deployment.Application.Manifest.AssemblyManifest System.Deployment.Application.CommitApplicationParams::AppManifest
0x11f48  ldarg.0
0x11f49  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11f4e  ldfld    class [System]System.Uri System.Deployment.Application.CommitApplicationParams::AppSourceUri
0x11f53  ldarg.0
0x11f54  ldfld    class System.Deployment.Application.TempDirectory System.Deployment.Application.DeploymentManager::_tempApplicationDirectory
0x11f59  callvirt instance string System.Deployment.Application.TempDirectory::get_Path()
0x11f5e  ldnull
0x11f5f  ldarg.1
0x11f60  brtrue.s loc_11F65
0x11f62  ldarg.0
0x11f63  br.s     loc_11F66
0x11f65  ldnull
0x11f66  ldarg.0
0x11f67  ldfld    class System.Deployment.Application.DownloadOptions System.Deployment.Application.DeploymentManager::_downloadOptions
0x11f6c  call     void System.Deployment.Application.DownloadManager::DownloadDependencies(class System.Deployment.Application.SubscriptionState subState, class System.Deployment.Application.Manifest.AssemblyManifest deployManifest, class System.Deployment.Application.Manifest.AssemblyManifest appManifest, class [System]System.Uri sourceUriBase, string targetDirectory, string group, class System.Deployment.Application.IDownloadNotification notification, class System.Deployment.Application.DownloadOptions options)
0x11f71  ldarg.1
0x11f72  brtrue.s loc_11F83
0x11f74  ldarg.0
0x11f75  ldfld    bool System.Deployment.Application.DeploymentManager::_cancellationPending
0x11f7a  brfalse.s loc_11F83
0x11f7c  ldc.i4.1
0x11f7d  stloc.3
0x11f7e  leave    loc_120FD
0x11f83  ldarg.0
0x11f84  call     instance void System.Deployment.Application.DeploymentManager::WaitForAssertApplicationRequirements()
0x11f89  ldloc.s  4
0x11f8b  brfalse.s loc_11F93
0x11f8d  ldarg.0
0x11f8e  call     instance void System.Deployment.Application.DeploymentManager::CheckSizeLimit()
0x11f93  ldarg.0
0x11f94  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11f99  ldc.i4.1
0x11f9a  stfld    bool System.Deployment.Application.CommitApplicationParams::CommitApp
0x11f9f  ldarg.0
0x11fa0  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11fa5  ldarg.0
0x11fa6  ldfld    class System.Deployment.Application.TempDirectory System.Deployment.Application.DeploymentManager::_tempApplicationDirectory
0x11fab  callvirt instance string System.Deployment.Application.TempDirectory::get_Path()
0x11fb0  stfld    string System.Deployment.Application.CommitApplicationParams::AppPayloadPath
0x11fb5  br.s     loc_11FCD
0x11fb7  ldarg.0
0x11fb8  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11fbd  ldstr    aApplicationIsC// "Application is cached."
0x11fc2  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11fc7  ldarg.0
0x11fc8  call     instance void System.Deployment.Application.DeploymentManager::WaitForAssertApplicationRequirements()
0x11fcd  ldarg.0
0x11fce  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11fd3  ldfld    bool System.Deployment.Application.CommitApplicationParams::CommitDeploy
0x11fd8  brtrue.s loc_11FE7
0x11fda  ldarg.0
0x11fdb  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11fe0  ldfld    bool System.Deployment.Application.CommitApplicationParams::CommitApp
0x11fe5  brfalse.s loc_1200A
0x11fe7  ldarg.0
0x11fe8  ldfld    class System.Deployment.Application.SubscriptionStore System.Deployment.Application.DeploymentManager::_subStore
0x11fed  ldloca.s 1
0x11fef  ldarg.0
0x11ff0  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x11ff5  callvirt instance void System.Deployment.Application.SubscriptionStore::CommitApplication(class System.Deployment.Application.SubscriptionState& subState, class System.Deployment.Application.CommitApplicationParams commitParams)
0x11ffa  ldarg.0
0x11ffb  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x12000  ldstr    aApplicationIsS_0// "Application is successfully committed t"...
0x12005  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1200a  ldarg.0
0x1200b  ldfld    class System.Deployment.Application.TempDirectory System.Deployment.Application.DeploymentManager::_tempApplicationDirectory
0x12010  brfalse.s loc_12024
0x12012  ldarg.0
0x12013  ldfld    class System.Deployment.Application.TempDirectory System.Deployment.Application.DeploymentManager::_tempApplicationDirectory
0x12018  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x1201d  ldarg.0
0x1201e  ldnull
0x1201f  stfld    class System.Deployment.Application.TempDirectory System.Deployment.Application.DeploymentManager::_tempApplicationDirectory
0x12024  ldarg.0
0x12025  ldfld    class System.Deployment.Application.TempFile System.Deployment.Application.DeploymentManager::_tempDeployment
0x1202a  brfalse.s loc_1203E
0x1202c  ldarg.0
0x1202d  ldfld    class System.Deployment.Application.TempFile System.Deployment.Application.DeploymentManager::_tempDeployment
0x12032  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x12037  ldarg.0
0x12038  ldnull
0x12039  stfld    class System.Deployment.Application.TempFile System.Deployment.Application.DeploymentManager::_tempDeployment
0x1203e  ldarg.0
0x1203f  ldfld    class [mscorlib]System.IO.FileStream System.Deployment.Application.DeploymentManager::_referenceTransaction
0x12044  brfalse.s loc_12058
0x12046  ldarg.0
0x12047  ldfld    class [mscorlib]System.IO.FileStream System.Deployment.Application.DeploymentManager::_referenceTransaction
0x1204c  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x12051  ldarg.0
0x12052  ldnull
0x12053  stfld    class [mscorlib]System.IO.FileStream System.Deployment.Application.DeploymentManager::_referenceTransaction
0x12058  ldarg.0
0x12059  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x1205e  ldstr    aRefreshingActi// "Refreshing ActivationContext from store"...
0x12063  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x12068  ldarg.0
0x12069  ldfld    class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::_actCtx
0x1206e  stloc.2
0x1206f  ldarg.0
0x12070  ldarg.0
0x12071  ldfld    class System.Deployment.Application.ActivationDescription System.Deployment.Application.DeploymentManager::_actDesc
0x12076  ldfld    class System.Deployment.Application.DefinitionAppId System.Deployment.Application.CommitApplicationParams::AppId
0x1207b  call     class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::ConstructActivationContextFromStore(class System.Deployment.Application.DefinitionAppId defAppId)
0x12080  stfld    class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::_actCtx
0x12085  ldloc.2
0x12086  callvirt instance void [mscorlib]System.ActivationContext::Dispose()
0x1208b  ldarg.0
0x1208c  ldc.i4.1
0x1208d  stfld    bool System.Deployment.Application.DeploymentManager::_cached
0x12092  leave.s  loc_120FB
0x12094  stloc.s  7
0x12096  ldarg.0
0x12097  ldstr    aExDownloadappl// "Ex_DownloadApplicationFailed"
0x1209c  call     string System.Deployment.Application.Resources::GetString(string s)
0x120a1  ldloc.s  7
0x120a3  call     instance void System.Deployment.Application.DeploymentManager::LogError(string message, class [mscorlib]System.Exception ex)
0x120a8  ldarg.0
0x120a9  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x120ae  ldc.i4.6
0x120af  newarr   [mscorlib]System.String
0x120b4  dup
0x120b5  ldc.i4.0
0x120b6  ldstr    aExceptionThrow_3// "Exception thrown in  SynchronizeCore():"...
0x120bb  stelem.ref
0x120bc  dup
0x120bd  ldc.i4.1
0x120be  ldloc.s  7
0x120c0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x120c5  callvirt instance string [mscorlib]System.Object::ToString()
0x120ca  stelem.ref
0x120cb  dup
0x120cc  ldc.i4.2
0x120cd  ldstr    asc_3345E// " : "
0x120d2  stelem.ref
0x120d3  dup
0x120d4  ldc.i4.3
0x120d5  ldloc.s  7
0x120d7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x120dc  stelem.ref
0x120dd  dup
0x120de  ldc.i4.4
0x120df  ldstr    asc_3279C// "\r\n"
0x120e4  stelem.ref
0x120e5  dup
0x120e6  ldc.i4.5
0x120e7  ldloc.s  7
0x120e9  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x120ee  stelem.ref
  ... truncated ...
```
