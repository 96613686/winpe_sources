# Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::RemoveInstallChannel

- ea: `0x52fd0`
- end: `0x530ac`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::RemoveInstallChannel`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0xfe50`
- `0x52fd0`
- `0x533e0`
- `0x534d0`

## string_xrefs

- `0x52fd1`: `channelManifestPair`
- `0x53041`: `Trying to remove channel manifest: `
- `0x53075`: `Trying to remove product manifest: `

## pseudocode

```c

```

## disassembly

```asm
0x52fd0  ldarg.1
0x52fd1  ldstr    aChannelmanifes// "channelManifestPair"
0x52fd6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x52fdb  ldarg.0
0x52fdc  ldarg.1
0x52fdd  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52fe2  ldarg.1
0x52fe3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x52fe8  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ValidateChannelUris(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest installChannelManifest)
0x52fed  ldarg.0
0x52fee  ldarg.1
0x52fef  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52ff4  ldarg.1
0x52ff5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x52ffa  ldc.i4.0
0x52ffb  call     instance string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::GetChannelManifestRoot(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest installChannelManifest, [opt] bool createRoot)
0x53000  stloc.0
0x53001  ldloc.0
0x53002  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x53007  brtrue   loc_530AB
0x5300c  ldsfld   object Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::SyncRoot
0x53011  stloc.1
0x53012  ldc.i4.0
0x53013  stloc.2
0x53014  ldloc.1
0x53015  ldloca.s 2
0x53017  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5301c  ldloc.0
0x5301d  ldsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::InstallChannelManifestFileName
0x53022  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x53027  stloc.3
0x53028  ldloc.0
0x53029  ldsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::InstallProductManifestFileName
0x5302e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x53033  stloc.s  4
0x53035  ldarg.0
0x53036  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x5303b  dup
0x5303c  brtrue.s loc_53041
0x5303e  pop
0x5303f  br.s     loc_53056
0x53041  ldstr    aTryingToRemove// "Trying to remove channel manifest: "
0x53046  ldloc.3
0x53047  call     string [mscorlib]System.String::Concat(string, string)
0x5304c  call     T0x2B000003
0x53051  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x53056  ldarg.0
0x53057  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::fileSystem
0x5305c  ldloc.3
0x5305d  ldc.i4.2
0x5305e  ldc.i4   0x1F4
0x53063  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileIfExists(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] int32 retryCount, [opt] int32 retryDelay)
0x53068  pop
0x53069  ldarg.0
0x5306a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x5306f  dup
0x53070  brtrue.s loc_53075
0x53072  pop
0x53073  br.s     loc_5308B
0x53075  ldstr    aTryingToRemove_0// "Trying to remove product manifest: "
0x5307a  ldloc.s  4
0x5307c  call     string [mscorlib]System.String::Concat(string, string)
0x53081  call     T0x2B000003
0x53086  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5308b  ldarg.0
0x5308c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::fileSystem
0x53091  ldloc.s  4
0x53093  ldc.i4.2
0x53094  ldc.i4   0x1F4
0x53099  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileIfExists(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] int32 retryCount, [opt] int32 retryDelay)
0x5309e  pop
0x5309f  leave.s  loc_530AB
0x530a1  ldloc.2
0x530a2  brfalse.s loc_530AA
0x530a4  ldloc.1
0x530a5  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x530aa  endfinally
0x530ab  ret
```
