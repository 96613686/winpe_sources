# Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::AddChannel_0

- ea: `0x52c10`
- end: `0x52d9c`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::AddChannel_0`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x52c00`

## callees

- `0xfe50`
- `0x52c10`
- `0x53380`
- `0x533e0`
- `0x53490`
- `0x534f0`
- `0x53660`

## string_xrefs

- `0x52c11`: `channelManifestPair`
- `0x52d2b`: `Channel manifest: `
- `0x52d32`: ` was being deleted because it is outdated.`
- `0x52d65`: `Install channel manifest cannot update and CanUpdate flag should be set to false`

## pseudocode

```c

```

## disassembly

```asm
0x52c10  ldarg.1
0x52c11  ldstr    aChannelmanifes// "channelManifestPair"
0x52c16  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x52c1b  ldarg.0
0x52c1c  ldarg.1
0x52c1d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52c22  ldarg.1
0x52c23  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x52c28  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ValidateChannelUris(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest installChannelManifest)
0x52c2d  ldc.i4.0
0x52c2e  stloc.0
0x52c2f  ldsfld   object Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::SyncRoot
0x52c34  stloc.1
0x52c35  ldc.i4.0
0x52c36  stloc.2
0x52c37  ldloc.1
0x52c38  ldloca.s 2
0x52c3a  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x52c3f  ldarg.0
0x52c40  ldarg.1
0x52c41  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52c46  ldarg.1
0x52c47  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x52c4c  ldarg.2
0x52c4d  ldc.i4.1
0x52c4e  call     instance string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::GetChannelManifestRoot(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, string installChannelManifest, bool targetRoot)
0x52c53  stloc.3
0x52c54  ldarg.1
0x52c55  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52c5a  brfalse  loc_52D48
0x52c5f  ldloc.3
0x52c60  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x52c65  brtrue   loc_52D48
0x52c6a  ldloc.3
0x52c6b  ldsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ChannelManifestFileName
0x52c70  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x52c75  stloc.s  4
0x52c77  ldarg.0
0x52c78  ldloc.s  4
0x52c7a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::GetExistingChannelManifest(string)
0x52c7f  stloc.s  5
0x52c81  ldc.i4.1
0x52c82  stloc.s  6
0x52c84  ldloc.s  5
0x52c86  brfalse.s loc_52CDF
0x52c88  ldloc.s  5
0x52c8a  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x52c8f  stloc.s  7
0x52c91  ldarg.1
0x52c92  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52c97  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestBuildVersion(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest)
0x52c9c  ldloc.s  7
0x52c9e  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x52ca3  brfalse.s loc_52CBE
0x52ca5  ldloc.s  5
0x52ca7  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_IsRetired()
0x52cac  ldarg.1
0x52cad  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52cb2  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_IsRetired()
0x52cb7  bne.un.s loc_52CBE
0x52cb9  ldc.i4.0
0x52cba  stloc.s  6
0x52cbc  br.s     loc_52CDF
0x52cbe  ldarg.0
0x52cbf  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x52cc4  dup
0x52cc5  brtrue.s loc_52CCA
0x52cc7  pop
0x52cc8  br.s     loc_52CDF
0x52cca  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CommonResources::get_DownloadedChannelIsOlderThanExistingOne_Args1()
0x52ccf  ldc.i4.1
0x52cd0  newarr   [mscorlib]System.Object
0x52cd5  dup
0x52cd6  ldc.i4.0
0x52cd7  ldloc.s  4
0x52cd9  stelem.ref
0x52cda  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x52cdf  ldloc.s  6
0x52ce1  brfalse.s loc_52D48
0x52ce3  ldarg.0
0x52ce4  ldarg.1
0x52ce5  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52cea  ldloc.3
0x52ceb  ldloc.s  4
0x52ced  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::WriteChannelManifest(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, string channelManifestRoot, string channelManifestFileName)
0x52cf2  ldarg.0
0x52cf3  ldloc.3
0x52cf4  ldarg.s  4
0x52cf6  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::WriteLastUpdateDate(string channelRoot, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTimeOffset> lastUpdateDate)
0x52cfb  ldarg.3
0x52cfc  brfalse.s loc_52D46
0x52cfe  ldloc.3
0x52cff  ldsfld   string Microsoft.VisualStudio.Setup.Cache.InstanceRepository::CatalogFileName
0x52d04  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x52d09  stloc.s  8
0x52d0b  ldarg.0
0x52d0c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::fileSystem
0x52d11  ldloc.s  8
0x52d13  ldc.i4.2
0x52d14  ldc.i4   0x1F4
0x52d19  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileIfExists(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [opt] int32 retryCount, [opt] int32 retryDelay)
0x52d1e  pop
0x52d1f  ldarg.0
0x52d20  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x52d25  dup
0x52d26  brtrue.s loc_52D2B
0x52d28  pop
0x52d29  br.s     loc_52D46
0x52d2b  ldstr    aChannelManifes// "Channel manifest: "
0x52d30  ldloc.s  8
0x52d32  ldstr    aWasBeingDelete// " was being deleted because it is outdat"...
0x52d37  call     string [mscorlib]System.String::Concat(string, string, string)
0x52d3c  call     T0x2B000003
0x52d41  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x52d46  ldc.i4.1
0x52d47  stloc.0
0x52d48  ldarg.1
0x52d49  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x52d4e  brfalse.s loc_52D8E
0x52d50  ldloc.3
0x52d51  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x52d56  brtrue.s loc_52D8E
0x52d58  ldarg.1
0x52d59  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x52d5e  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_CanUpdate()
0x52d63  brfalse.s loc_52D70
0x52d65  ldstr    aInstallChannel// "Install channel manifest cannot update "...
0x52d6a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x52d6f  throw
0x52d70  ldloc.3
0x52d71  ldsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::InstallChannelManifestFileName
0x52d76  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x52d7b  stloc.s  9
0x52d7d  ldarg.0
0x52d7e  ldarg.1
0x52d7f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_InstallChannelManifest()
0x52d84  ldloc.3
0x52d85  ldloc.s  9
0x52d87  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::WriteChannelManifest(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest, string channelManifestRoot, string channelManifestFileName)
0x52d8c  ldc.i4.1
0x52d8d  stloc.0
0x52d8e  leave.s  loc_52D9A
0x52d90  ldloc.2
0x52d91  brfalse.s loc_52D99
0x52d93  ldloc.1
0x52d94  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x52d99  endfinally
0x52d9a  ldloc.0
0x52d9b  ret
```
