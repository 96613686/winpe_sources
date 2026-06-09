# Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::GetChannelsManifestInfo_0

- ea: `0x537f0`
- end: `0x5390e`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::GetChannelsManifestInfo_0`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x52e40`

## callees

- `0x537f0`

## string_xrefs

- `0x53822`: `Setup expects one or more channel manifest in the repository.`
- `0x5386d`: `Channel manifest file `
- `0x538b8`: `Failed to extract channel manifest info from `

## pseudocode

```c

```

## disassembly

```asm
0x537f0  ldarg.0
0x537f1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::fileSystem
0x537f6  ldarg.1
0x537f7  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x537fc  brfalse  loc_5390D
0x53801  ldarg.0
0x53802  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::fileSystem
0x53807  ldarg.1
0x53808  ldc.i4.0
0x53809  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetDirectories(string, bool)
0x5380e  dup
0x5380f  call     T0x2B000015
0x53814  brtrue.s loc_53831
0x53816  ldarg.0
0x53817  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x5381c  dup
0x5381d  brtrue.s loc_53822
0x5381f  pop
0x53820  br.s     loc_53831
0x53822  ldstr    aSetupExpectsOn// "Setup expects one or more channel manif"...
0x53827  call     T0x2B000003
0x5382c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x53831  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x53836  stloc.0
0x53837  br       loc_538F6
0x5383c  ldloc.0
0x5383d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x53842  stloc.1
0x53843  ldarg.1
0x53844  ldloc.1
0x53845  ldsfld   string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ChannelManifestFileName
0x5384a  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x5384f  stloc.2
0x53850  ldarg.0
0x53851  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::fileSystem
0x53856  ldloc.2
0x53857  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x5385c  brtrue.s loc_53889
0x5385e  ldarg.0
0x5385f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x53864  dup
0x53865  brtrue.s loc_5386D
0x53867  pop
0x53868  br       loc_538F6
0x5386d  ldstr    aChannelManifes_0// "Channel manifest file "
0x53872  ldloc.2
0x53873  ldstr    aDoesNotExist_0// " does not exist."
0x53878  call     string [mscorlib]System.String::Concat(string, string, string)
0x5387d  call     T0x2B000003
0x53882  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x53887  br.s     loc_538F6
0x53889  nop
0x5388a  ldarg.0
0x5388b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::channelManifestInfoExtractor
0x53890  ldloc.2
0x53891  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Serialization.ChannelManifestInfoExtractor::ExtractFromManifest(string)
0x53896  stloc.3
0x53897  ldloc.3
0x53898  brfalse.s loc_538A8
0x5389a  ldarg.2
0x5389b  ldloc.3
0x5389c  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestInfo::get_UpdateUri()
0x538a1  ldloc.3
0x538a2  call     T0x2B000266
0x538a7  pop
0x538a8  leave.s  loc_538F6
0x538aa  stloc.s  4
0x538ac  ldarg.0
0x538ad  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x538b2  dup
0x538b3  brtrue.s loc_538B8
0x538b5  pop
0x538b6  br.s     loc_538D2
0x538b8  ldstr    aFailedToExtrac_0// "Failed to extract channel manifest info"...
0x538bd  ldloc.2
0x538be  ldstr    aItMayBeCorrupt// ". It may be corrupted."
0x538c3  call     string [mscorlib]System.String::Concat(string, string, string)
0x538c8  call     T0x2B000003
0x538cd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x538d2  ldarg.0
0x538d3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x538d8  dup
0x538d9  brtrue.s loc_538DE
0x538db  pop
0x538dc  br.s     loc_538F4
0x538de  ldstr    aException0// "Exception: {0}"
0x538e3  ldloc.s  4
0x538e5  call     string [mscorlib]System.String::Format(string, object)
0x538ea  call     T0x2B000003
0x538ef  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x538f4  leave.s  loc_538F6
0x538f6  ldloc.0
0x538f7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x538fc  brtrue   loc_5383C
0x53901  leave.s  loc_5390D
0x53903  ldloc.0
0x53904  brfalse.s loc_5390C
0x53906  ldloc.0
0x53907  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5390c  endfinally
0x5390d  ret
```
