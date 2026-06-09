# Microsoft.VisualStudio.Setup.ChannelManager::TryRemoveInstallChannel

- ea: `0x4ef0`
- end: `0x4f51`
- name: `Microsoft.VisualStudio.Setup.ChannelManager::TryRemoveInstallChannel`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x40a0`
- `0x40d0`

## callees

- `0x4ef0`
- `0x55260`
- `0x63860`

## string_xrefs

- `0x4f38`: `Failed to remove install channel for a null {0}`
- `0x4f45`: `ChannelManifestPair`

## pseudocode

```c

```

## disassembly

```asm
0x4ef0  ldarg.1
0x4ef1  brfalse.s loc_4F2D
0x4ef3  ldarg.0
0x4ef4  ldfld    class Microsoft.VisualStudio.Setup.Cache.IChannelRepository Microsoft.VisualStudio.Setup.ChannelManager::channelRepository
0x4ef9  ldarg.1
0x4efa  callvirt instance void Microsoft.VisualStudio.Setup.Cache.IChannelRepository::RemoveInstallChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair)
0x4eff  ldarg.0
0x4f00  ldfld    class ChannelStatusTracker Microsoft.VisualStudio.Setup.ChannelManager::channelStatusTracker
0x4f05  ldarg.1
0x4f06  callvirt instance void ChannelStatusTracker::Remove(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair channelManifestPair)
0x4f0b  leave.s  loc_4F50
0x4f0d  stloc.0
0x4f0e  ldarg.0
0x4f0f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x4f14  dup
0x4f15  brtrue.s loc_4F1A
0x4f17  pop
0x4f18  br.s     loc_4F2B
0x4f1a  ldloc.0
0x4f1b  ldloc.0
0x4f1c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4f21  call     T0x2B000003
0x4f26  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x4f2b  leave.s  loc_4F50
0x4f2d  ldarg.0
0x4f2e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x4f33  dup
0x4f34  brtrue.s loc_4F38
0x4f36  pop
0x4f37  ret
0x4f38  ldstr    aFailedToRemove// "Failed to remove install channel for a "...
0x4f3d  ldc.i4.1
0x4f3e  newarr   [mscorlib]System.Object
0x4f43  dup
0x4f44  ldc.i4.0
0x4f45  ldstr    aChannelmanifes_0// "ChannelManifestPair"
0x4f4a  stelem.ref
0x4f4b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x4f50  ret
```
