# <ChangeChannelAsync>d__7::MoveNext

- ea: `0x77b60`
- end: `0x77e67`
- name: `<ChangeChannelAsync>d__7::MoveNext`
- size: `775`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update`

## callees

- `0x11460`
- `0x114f0`
- `0x11530`
- `0x199a0`
- `0x22610`
- `0x22750`
- `0x22770`
- `0x228b0`
- `0x3ed60`
- `0x3f170`
- `0x4b780`
- `0x4c730`
- `0x4ca60`
- `0x4ebc0`
- `0x4ec00`
- `0x4ec20`
- `0x4ec40`
- `0x563e0`
- `0x77b60`

## string_xrefs

- `0x77bec`: `Changing the channel for the update to {0}`
- `0x77e26`: `Successfully changed the channel for the update`

## pseudocode

```c

```

## disassembly

```asm
0x77b60  ldarg.0
0x77b61  ldfld    int32 <ChangeChannelAsync>d__7::<>1__state
0x77b66  stloc.0
0x77b67  ldarg.0
0x77b68  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater <ChangeChannelAsync>d__7::<>4__this
0x77b6d  stloc.1
0x77b6e  ldloc.0
0x77b6f  brfalse  loc_77D38
0x77b74  ldloc.1
0x77b75  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77b7a  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_ChannelUri()
0x77b7f  brtrue.s loc_77B88
0x77b81  ldc.i4.0
0x77b82  stloc.2
0x77b83  leave    loc_77E52
0x77b88  ldloc.1
0x77b89  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.ProductUpdaterServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::serviceOptions
0x77b8e  callvirt instance class Microsoft.VisualStudio.Setup.Services.IQueryFactory Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_QueryFactory()
0x77b93  callvirt instance class Microsoft.VisualStudio.Setup.Cache.IQuery Microsoft.VisualStudio.Setup.Services.IQueryFactory::Create()
0x77b98  stloc.s  5
0x77b9a  ldloc.s  5
0x77b9c  ldloc.1
0x77b9d  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77ba2  callvirt instance string Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::get_InstanceId()
0x77ba7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance Microsoft.VisualStudio.Setup.Cache.IQuery::GetInstanceForId(string instanceId)
0x77bac  stloc.s  6
0x77bae  ldloc.1
0x77baf  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77bb4  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_ChannelUri()
0x77bb9  ldloc.s  6
0x77bbb  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance::get_ChannelUri()
0x77bc0  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x77bc5  brfalse.s loc_77BCE
0x77bc7  ldc.i4.0
0x77bc8  stloc.2
0x77bc9  leave    loc_77E52
0x77bce  leave.s  loc_77BE0
0x77bd0  ldloc.0
0x77bd1  ldc.i4.0
0x77bd2  bge.s    loc_77BDF
0x77bd4  ldloc.s  5
0x77bd6  brfalse.s loc_77BDF
0x77bd8  ldloc.s  5
0x77bda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x77bdf  endfinally
0x77be0  ldloc.1
0x77be1  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x77be6  dup
0x77be7  brtrue.s loc_77BEC
0x77be9  pop
0x77bea  br.s     loc_77C0A
0x77bec  ldstr    aChangingTheCha// "Changing the channel for the update to "...
0x77bf1  ldc.i4.1
0x77bf2  newarr   [mscorlib]System.Object
0x77bf7  dup
0x77bf8  ldc.i4.0
0x77bf9  ldloc.1
0x77bfa  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77bff  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_ChannelUri()
0x77c04  stelem.ref
0x77c05  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x77c0a  ldloc.1
0x77c0b  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77c10  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_InstallChannelUri()
0x77c15  brfalse.s loc_77C4F
0x77c17  ldloc.1
0x77c18  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x77c1d  dup
0x77c1e  brtrue.s loc_77C23
0x77c20  pop
0x77c21  br.s     loc_77C4F
0x77c23  ldstr    aUsingFixedChan// "Using fixed channel {0} and catalog {1}"
0x77c28  ldc.i4.2
0x77c29  newarr   [mscorlib]System.Object
0x77c2e  dup
0x77c2f  ldc.i4.0
0x77c30  ldloc.1
0x77c31  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77c36  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_InstallChannelUri()
0x77c3b  stelem.ref
0x77c3c  dup
0x77c3d  ldc.i4.1
0x77c3e  ldloc.1
0x77c3f  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77c44  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_InstallCatalogUri()
0x77c49  stelem.ref
0x77c4a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x77c4f  ldloc.1
0x77c50  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.ProductUpdaterServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::serviceOptions
0x77c55  callvirt instance class Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_ChannelManager()
0x77c5a  ldloc.1
0x77c5b  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77c60  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_ChannelUri()
0x77c65  ldc.i4.0
0x77c66  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair Microsoft.VisualStudio.Setup.IChannelManager::GetChannel(class [System]System.Uri channelUri, [opt] bool localChannelOnly)
0x77c6b  stloc.3
0x77c6c  ldloc.3
0x77c6d  brtrue.s loc_77C72
0x77c6f  ldnull
0x77c70  br.s     loc_77C78
0x77c72  ldloc.3
0x77c73  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x77c78  dup
0x77c79  brtrue.s loc_77C88
0x77c7b  pop
0x77c7c  ldloc.3
0x77c7d  brtrue.s loc_77C82
0x77c7f  ldnull
0x77c80  br.s     loc_77C88
0x77c82  ldloc.3
0x77c83  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x77c88  stloc.s  4
0x77c8a  ldloc.s  4
0x77c8c  brfalse.s loc_77CAA
0x77c8e  ldloc.s  4
0x77c90  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x77c95  ldloc.1
0x77c96  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77c9b  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_UpdateVersion()
0x77ca0  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x77ca5  brfalse  loc_77DF3
0x77caa  ldloc.1
0x77cab  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.ProductUpdaterServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::serviceOptions
0x77cb0  callvirt instance class Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_ChannelManager()
0x77cb5  ldloc.1
0x77cb6  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77cbb  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_ChannelUri()
0x77cc0  callvirt instance void Microsoft.VisualStudio.Setup.IChannelManager::RemoveInstallChannel(class [System]System.Uri channelUri)
0x77cc5  ldloc.1
0x77cc6  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.ProductUpdaterServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::serviceOptions
0x77ccb  callvirt instance class Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_ChannelManager()
0x77cd0  ldloc.1
0x77cd1  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77cd6  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_ChannelUri()
0x77cdb  ldloc.1
0x77cdc  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77ce1  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_InstallChannelUri()
0x77ce6  ldloc.1
0x77ce7  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77cec  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_InstallCatalogUri()
0x77cf1  stloc.s  8
0x77cf3  ldloca.s 9
0x77cf5  initobj  [mscorlib]System.Threading.CancellationToken
0x77cfb  ldloc.s  9
0x77cfd  ldloc.s  8
0x77cff  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> Microsoft.VisualStudio.Setup.IChannelManager::AddAsync(class [System]System.Uri channelUri, class [System]System.Uri installChannelUri, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken, [opt] class [System]System.Uri installCatalogUri)
0x77d04  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::GetAwaiter()
0x77d09  stloc.s  7
0x77d0b  ldloca.s 7
0x77d0d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::get_IsCompleted()
0x77d12  brtrue.s loc_77D55
0x77d14  ldarg.0
0x77d15  ldc.i4.0
0x77d16  dup
0x77d17  stloc.0
0x77d18  stfld    int32 <ChangeChannelAsync>d__7::<>1__state
0x77d1d  ldarg.0
0x77d1e  ldloc.s  7
0x77d20  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <ChangeChannelAsync>d__7::<>u__1
0x77d25  ldarg.0
0x77d26  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ChangeChannelAsync>d__7::<>t__builder
0x77d2b  ldloca.s 7
0x77d2d  ldarg.0
0x77d2e  call     T0x2B000377
0x77d33  leave    loc_77E66
0x77d38  ldarg.0
0x77d39  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <ChangeChannelAsync>d__7::<>u__1
0x77d3e  stloc.s  7
0x77d40  ldarg.0
0x77d41  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> <ChangeChannelAsync>d__7::<>u__1
0x77d46  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>
0x77d4c  ldarg.0
0x77d4d  ldc.i4.m1
0x77d4e  dup
0x77d4f  stloc.0
0x77d50  stfld    int32 <ChangeChannelAsync>d__7::<>1__state
0x77d55  ldloca.s 7
0x77d57  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair>::GetResult()
0x77d5c  stloc.3
0x77d5d  ldloc.3
0x77d5e  brtrue.s loc_77D63
0x77d60  ldnull
0x77d61  br.s     loc_77D69
0x77d63  ldloc.3
0x77d64  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x77d69  dup
0x77d6a  brtrue.s loc_77D79
0x77d6c  pop
0x77d6d  ldloc.3
0x77d6e  brtrue.s loc_77D73
0x77d70  ldnull
0x77d71  br.s     loc_77D79
0x77d73  ldloc.3
0x77d74  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x77d79  stloc.s  4
0x77d7b  ldloc.s  4
0x77d7d  brfalse.s loc_77D98
0x77d7f  ldloc.s  4
0x77d81  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x77d86  ldloc.1
0x77d87  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77d8c  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_UpdateVersion()
0x77d91  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x77d96  brfalse.s loc_77DF3
0x77d98  ldloc.1
0x77d99  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.ProductUpdaterServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::serviceOptions
0x77d9e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_Logger()
0x77da3  dup
0x77da4  brtrue.s loc_77DA9
0x77da6  pop
0x77da7  br.s     loc_77DDE
0x77da9  ldstr    aDidNotFindChan_0// "Did not find channel product with versi"...
0x77dae  ldloc.1
0x77daf  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77db4  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions::get_UpdateVersion()
0x77db9  call     string [mscorlib]System.String::Format(string, object)
0x77dbe  ldstr    aInsteadFoundVe_0// "Instead found version: {0}."
0x77dc3  ldloc.s  4
0x77dc5  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x77dca  call     string [mscorlib]System.String::Format(string, object)
0x77dcf  call     string [mscorlib]System.String::Concat(string, string)
0x77dd4  call     T0x2B000003
0x77dd9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x77dde  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x77de3  ldstr    aChannelproduct_0// "ChannelProductMismatch"
0x77de8  call     T0x2B000003
0x77ded  newobj   instance void Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationBlockedException::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId, object[] args)
0x77df2  throw
0x77df3  ldloc.1
0x77df4  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.ProductUpdaterServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::serviceOptions
0x77df9  callvirt instance class Microsoft.VisualStudio.Setup.Services.IUpdateSettingsService Microsoft.VisualStudio.Setup.ServiceOptions.ProductUpdaterServiceOptions::get_UpdateSettingsService()
0x77dfe  ldloc.1
0x77dff  ldfld    class Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdaterOptions Microsoft.VisualStudio.Setup.Services.Installer.ProductUpdater::options
0x77e04  callvirt instance string Microsoft.VisualStudio.Setup.Services.Installer.InstallerBaseOptions::get_InstanceId()
0x77e09  ldloc.3
0x77e0a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x77e0f  ldc.i4.1
0x77e10  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannel [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::GetChannel(bool)
0x77e15  callvirt instance void Microsoft.VisualStudio.Setup.Services.IUpdateSettingsService::ChangeChannel(string instanceId, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannel newChannel)
0x77e1a  ldloc.1
0x77e1b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x77e20  dup
0x77e21  brtrue.s loc_77E26
0x77e23  pop
0x77e24  br.s     loc_77E35
0x77e26  ldstr    aSuccessfullyCh// "Successfully changed the channel for th"...
0x77e2b  call     T0x2B000003
0x77e30  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x77e35  ldc.i4.1
0x77e36  stloc.2
0x77e37  leave.s  loc_77E52
0x77e39  stloc.s  0xA
0x77e3b  ldarg.0
0x77e3c  ldc.i4.s 0xFE
0x77e3e  stfld    int32 <ChangeChannelAsync>d__7::<>1__state
0x77e43  ldarg.0
0x77e44  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ChangeChannelAsync>d__7::<>t__builder
0x77e49  ldloc.s  0xA
0x77e4b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x77e50  leave.s  loc_77E66
0x77e52  ldarg.0
0x77e53  ldc.i4.s 0xFE
0x77e55  stfld    int32 <ChangeChannelAsync>d__7::<>1__state
0x77e5a  ldarg.0
0x77e5b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ChangeChannelAsync>d__7::<>t__builder
0x77e60  ldloc.2
0x77e61  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetResult(var<u1>)
0x77e66  ret
```
