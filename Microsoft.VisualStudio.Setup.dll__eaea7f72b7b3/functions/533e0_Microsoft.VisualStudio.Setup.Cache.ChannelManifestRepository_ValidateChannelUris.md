# Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ValidateChannelUris

- ea: `0x533e0`
- end: `0x53436`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ValidateChannelUris`
- size: `86`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x52a60`
- `0x52c10`
- `0x52e90`
- `0x52f50`
- `0x52fd0`
- `0x53120`
- `0x53180`
- `0x531e0`
- `0x53250`

## callees

- `0x533e0`
- `0x53440`

## string_xrefs

- `0x533e6`: `Both channel manifest uri and install channel manifest uri are not set.`
- `0x533fc`: `UpdateUri must be set.`
- `0x5341e`: `UpdateUri must be set.`

## pseudocode

```c

```

## disassembly

```asm
0x533e0  ldarg.1
0x533e1  brtrue.s loc_533F1
0x533e3  ldarg.2
0x533e4  brtrue.s loc_533F1
0x533e6  ldstr    aBothChannelMan// "Both channel manifest uri and install c"...
0x533eb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x533f0  throw
0x533f1  ldarg.1
0x533f2  brfalse.s loc_53413
0x533f4  ldarg.1
0x533f5  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x533fa  brtrue.s loc_53407
0x533fc  ldstr    aUpdateuriMustB// "UpdateUri must be set."
0x53401  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x53406  throw
0x53407  ldarg.0
0x53408  ldarg.1
0x53409  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x5340e  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ValidateChannelUri(class [System]System.Uri channelUri)
0x53413  ldarg.2
0x53414  brfalse.s loc_53435
0x53416  ldarg.2
0x53417  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x5341c  brtrue.s loc_53429
0x5341e  ldstr    aUpdateuriMustB// "UpdateUri must be set."
0x53423  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x53428  throw
0x53429  ldarg.0
0x5342a  ldarg.2
0x5342b  callvirt instance class [System]System.Uri [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_UpdateUri()
0x53430  call     instance void Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::ValidateChannelUri(class [System]System.Uri channelUri)
0x53435  ret
```
