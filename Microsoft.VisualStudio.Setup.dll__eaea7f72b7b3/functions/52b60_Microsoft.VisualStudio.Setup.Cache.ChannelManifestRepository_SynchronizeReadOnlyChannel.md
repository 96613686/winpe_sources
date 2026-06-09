# Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::SynchronizeReadOnlyChannel

- ea: `0x52b60`
- end: `0x52bf3`
- name: `Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::SynchronizeReadOnlyChannel`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x52b60`
- `0x53250`
- `0x535d0`
- `0x79630`

## string_xrefs

- `0x52b73`: `channelUri`
- `0x52bcc`: `Unable to synchronize read-only channel {0}, because there is no corresponding channel in the local cache.`

## pseudocode

```c

```

## disassembly

```asm
0x52b60  newobj   instance void <>c__DisplayClass20_0::.ctor()
0x52b65  stloc.0
0x52b66  ldloc.0
0x52b67  ldarg.1
0x52b68  stfld    class [System]System.Uri <>c__DisplayClass20_0::channelUri
0x52b6d  ldloc.0
0x52b6e  ldfld    class [System]System.Uri <>c__DisplayClass20_0::channelUri
0x52b73  ldstr    aChanneluri// "channelUri"
0x52b78  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x52b7d  ldsfld   object Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::SyncRoot
0x52b82  stloc.1
0x52b83  ldc.i4.0
0x52b84  stloc.2
0x52b85  ldloc.1
0x52b86  ldloca.s 2
0x52b88  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x52b8d  ldarg.0
0x52b8e  ldarg.0
0x52b8f  ldfld    string Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::root
0x52b94  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair> Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::GetChannels(string searchRoot)
0x52b99  ldloc.0
0x52b9a  ldftn    instance bool <>c__DisplayClass20_0::<SynchronizeReadOnlyChannel>b__0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair c)
0x52ba0  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair, bool>::.ctor(object, native int)
0x52ba5  call     T0x2B000023
0x52baa  dup
0x52bab  brtrue.s loc_52BB1
0x52bad  pop
0x52bae  ldnull
0x52baf  br.s     loc_52BB6
0x52bb1  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifestPair::get_ChannelManifest()
0x52bb6  stloc.3
0x52bb7  ldarg.0
0x52bb8  ldloc.3
0x52bb9  call     instance bool Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::SynchronizeReadOnlyChannel(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest channelManifest)
0x52bbe  brtrue.s loc_52BE6
0x52bc0  ldarg.0
0x52bc1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.ChannelManifestRepository::logger
0x52bc6  dup
0x52bc7  brtrue.s loc_52BCC
0x52bc9  pop
0x52bca  leave.s  loc_52BF2
0x52bcc  ldstr    aUnableToSynchr// "Unable to synchronize read-only channel"...
0x52bd1  ldloc.0
0x52bd2  ldfld    class [System]System.Uri <>c__DisplayClass20_0::channelUri
0x52bd7  call     string [mscorlib]System.String::Format(string, object)
0x52bdc  call     T0x2B000003
0x52be1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x52be6  leave.s  loc_52BF2
0x52be8  ldloc.2
0x52be9  brfalse.s loc_52BF1
0x52beb  ldloc.1
0x52bec  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x52bf1  endfinally
0x52bf2  ret
```
