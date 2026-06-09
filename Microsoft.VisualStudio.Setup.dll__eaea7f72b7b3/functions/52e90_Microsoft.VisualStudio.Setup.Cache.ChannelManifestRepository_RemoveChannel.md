# Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::RemoveChannel

- ea: `0x52e90`
- end: `0x52f46`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::RemoveChannel`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xe2b0`
- `0xffb0`
- `0x52e90`
- `0x52f50`
- `0x533e0`
- `0x534d0`

## string_xrefs

- `0x52ea1`: `channelManifestPair`
- `0x52f01`: `Cannot find channel manifest at `

## pseudocode

```c

```

## disassembly

```asm
0x52e90  ldsfld   object Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::SyncRoot
0x52e95  stloc.0
0x52e96  ldc.i4.0
0x52e97  stloc.1
0x52e98  ldloc.0
0x52e99  ldloca.s 1
0x52e9b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x52ea0  ldarg.1
0x52ea1  ldstr    aChannelmanifes// "channelManifestPair"
0x52ea6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x52eab  ldarg.0
0x52eac  ldarg.1
0x52ead  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52eb2  ldarg.1
0x52eb3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x52eb8  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ValidateChannelUris(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest installChannelManifest)
0x52ebd  ldarg.0
0x52ebe  ldarg.1
0x52ebf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52ec4  ldarg.1
0x52ec5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x52eca  ldc.i4.0
0x52ecb  call     instance string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::GetChannelManifestRoot(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest installChannelManifest, [opt] bool createRoot)
0x52ed0  stloc.2
0x52ed1  ldloc.2
0x52ed2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x52ed7  brtrue.s loc_52F01
0x52ed9  ldarg.0
0x52eda  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::fileSystem
0x52edf  ldloc.2
0x52ee0  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x52ee5  brfalse.s loc_52F01
0x52ee7  ldarg.0
0x52ee8  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::fileSystem
0x52eed  ldloc.2
0x52eee  ldloca.s 3
0x52ef0  ldc.i4.0
0x52ef1  ldc.i4.1
0x52ef2  ldc.i4.2
0x52ef3  ldc.i4   0x1F4
0x52ef8  ldnull
0x52ef9  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] bool recursive, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction)
0x52efe  pop
0x52eff  br.s     loc_52F32
0x52f01  ldstr    aCannotFindChan// "Cannot find channel manifest at "
0x52f06  ldloc.2
0x52f07  call     string [mscorlib]System.String::Concat(string, string)
0x52f0c  newobj   instance void Microsoft.VisualStudio.Setup.BadChannelManifestException::.ctor(string message)
0x52f11  stloc.s  4
0x52f13  ldarg.0
0x52f14  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x52f19  dup
0x52f1a  brtrue.s loc_52F1F
0x52f1c  pop
0x52f1d  br.s     loc_52F32
0x52f1f  ldloc.s  4
0x52f21  ldloc.s  4
0x52f23  callvirt instance string [mscorlib]System.Exception::get_Message()
0x52f28  call     T0x2B000003
0x52f2d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x52f32  ldarg.0
0x52f33  ldarg.1
0x52f34  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::RemoveReadOnlyChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair)
0x52f39  leave.s  loc_52F45
0x52f3b  ldloc.1
0x52f3c  brfalse.s loc_52F44
0x52f3e  ldloc.0
0x52f3f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x52f44  endfinally
0x52f45  ret
```
