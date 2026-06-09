# Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::SynchronizeReadOnlyChannels

- ea: `0x4c0a0`
- end: `0x4c0f7`
- name: `Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::SynchronizeReadOnlyChannels`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x74c00`

## callees

- `0x115b0`
- `0x22610`
- `0x4b780`
- `0x4c0a0`

## string_xrefs

- `0x4c0ac`: `Synchronizing read only channels after operation completion.`
- `0x4c0db`: `Failed to synchronize read only channels: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4c0a0  ldarg.0
0x4c0a1  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x4c0a6  dup
0x4c0a7  brtrue.s loc_4C0AC
0x4c0a9  pop
0x4c0aa  br.s     loc_4C0BB
0x4c0ac  ldstr    aSynchronizingR_0// "Synchronizing read only channels after "...
0x4c0b1  call     T0x2B000003
0x4c0b6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x4c0bb  ldarg.0
0x4c0bc  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::serviceOptions
0x4c0c1  callvirt instance class Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.ServiceOptions.InstallerBaseServiceOptions::get_ChannelManager()
0x4c0c6  callvirt instance void Microsoft.VisualStudio.Setup.IChannelManager::SynchronizeReadOnlyChannels()
0x4c0cb  leave.s  loc_4C0F6
0x4c0cd  stloc.0
0x4c0ce  ldarg.0
0x4c0cf  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.Installer.InstallerBase::get_Logger()
0x4c0d4  dup
0x4c0d5  brtrue.s loc_4C0DA
0x4c0d7  pop
0x4c0d8  br.s     loc_4C0F4
0x4c0da  ldloc.0
0x4c0db  ldstr    aFailedToSynchr// "Failed to synchronize read only channel"...
0x4c0e0  ldc.i4.1
0x4c0e1  newarr   [mscorlib]System.Object
0x4c0e6  dup
0x4c0e7  ldc.i4.0
0x4c0e8  ldloc.0
0x4c0e9  callvirt instance string [mscorlib]System.Object::ToString()
0x4c0ee  stelem.ref
0x4c0ef  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x4c0f4  leave.s  loc_4C0F6
0x4c0f6  ret
```
