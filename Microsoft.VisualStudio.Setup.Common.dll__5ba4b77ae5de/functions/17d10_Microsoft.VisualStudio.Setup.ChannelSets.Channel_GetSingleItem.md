# Microsoft.VisualStudio.Setup.ChannelSets.Channel::GetSingleItem

- ea: `0x17d10`
- end: `0x17d75`
- name: `Microsoft.VisualStudio.Setup.ChannelSets.Channel::GetSingleItem`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x17b20`
- `0x17d10`
- `0x17e30`
- `0x18ac0`

## string_xrefs

- `0x17d43`: `The ChannelManifest must contain excatly one item of type `

## pseudocode

```c

```

## disassembly

```asm
0x17d10  ldarg.1
0x17d11  brtrue.s loc_17D2A
0x17d13  ldarg.0
0x17d14  call     instance class Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest Microsoft.VisualStudio.Setup.ChannelSets.Channel::get_ChannelManifest()
0x17d19  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelItem> Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_ChannelItems()
0x17d1e  call     T0x2B0000A7
0x17d23  call     T0x2B0000A8
0x17d28  br.s     loc_17D3F
0x17d2a  ldarg.0
0x17d2b  call     instance class Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest Microsoft.VisualStudio.Setup.ChannelSets.Channel::get_ChannelManifest()
0x17d30  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelItem> Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_ChannelItems()
0x17d35  call     T0x2B0000A7
0x17d3a  call     T0x2B0000A9
0x17d3f  stloc.0
0x17d40  leave.s  loc_17D63
0x17d42  stloc.1
0x17d43  ldstr    aTheChannelmani_1// "The ChannelManifest must contain excatl"...
0x17d48  ldtoken  mvar<u1>
0x17d4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d52  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x17d57  call     string [mscorlib]System.String::Concat(string, string)
0x17d5c  ldloc.1
0x17d5d  newobj   instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelCompositionException::.ctor(string message, class [mscorlib]System.Exception inner)
0x17d62  throw
0x17d63  ldloc.0
0x17d64  box      mvar<u1>
0x17d69  brtrue.s loc_17D6D
0x17d6b  ldnull
0x17d6c  ret
0x17d6d  ldarg.0
0x17d6e  ldloc.0
0x17d6f  newobj   instance void class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<mvar<u1>>::.ctor(class Microsoft.VisualStudio.Setup.ChannelSets.IChannel, var<u1>)
0x17d74  ret
```
