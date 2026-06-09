# Microsoft.VisualStudio.Setup.Cache.Query::GetCatalogPath

- ea: `0x57a50`
- end: `0x57ac6`
- name: `Microsoft.VisualStudio.Setup.Cache.Query::GetCatalogPath`
- size: `118`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x57420`
- `0x575d0`
- `0x57900`

## callees

- `0x52970`
- `0x55210`
- `0x57a50`
- `0x57ea0`

## string_xrefs

- `0x57a66`: `Channel information not found in installed instance '`
- `0x57a92`: `' is not found in channel manifest`

## pseudocode

```c

```

## disassembly

```asm
0x57a50  ldarg.1
0x57a51  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetInstance()
0x57a56  stloc.0
0x57a57  ldloc.0
0x57a58  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_ChannelId()
0x57a5d  stloc.1
0x57a5e  ldloc.1
0x57a5f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x57a64  brfalse.s loc_57A81
0x57a66  ldstr    aChannelInforma// "Channel information not found in instal"...
0x57a6b  ldloc.0
0x57a6c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance::get_InstanceId()
0x57a71  ldstr    asc_7FEB6// "'"
0x57a76  call     string [mscorlib]System.String::Concat(string, string, string)
0x57a7b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x57a80  throw
0x57a81  ldarg.0
0x57a82  ldloc.0
0x57a83  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair Microsoft.VisualStudio.Setup.Cache.Query::GetChannelManifestPair(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance instance)
0x57a88  dup
0x57a89  brtrue.s loc_57AA2
0x57a8b  pop
0x57a8c  ldstr    aInstanceChanne// "Instance channel id '"
0x57a91  ldloc.1
0x57a92  ldstr    aIsNotFoundInCh// "' is not found in channel manifest"
0x57a97  call     string [mscorlib]System.String::Concat(string, string, string)
0x57a9c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x57aa1  throw
0x57aa2  stloc.2
0x57aa3  ldarg.0
0x57aa4  ldfld    class Microsoft.VisualStudio.Setup.Services.ServiceProvider Microsoft.VisualStudio.Setup.Cache.Query::services
0x57aa9  ldnull
0x57aaa  call     class Microsoft.VisualStudio.Setup.Cache.IChannelRepository Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::Create(class [mscorlib]System.IServiceProvider services, [opt] string customSubDirectoryName)
0x57aaf  ldloc.2
0x57ab0  ldloca.s 3
0x57ab2  ldloca.s 4
0x57ab4  callvirt instance void Microsoft.VisualStudio.Setup.Cache.IChannelRepository::GetCatalogPathsForChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair, [out] string& channelCatalogFileName, [out] string& installChannelCatalogFileName)
0x57ab9  ldloc.2
0x57aba  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x57abf  brfalse.s loc_57AC4
0x57ac1  ldloc.s  4
0x57ac3  ret
0x57ac4  ldloc.3
0x57ac5  ret
```
