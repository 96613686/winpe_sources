# Microsoft.VisualStudio.Setup.ChannelSets.Channel::GetMultipleItems

- ea: `0x17d80`
- end: `0x17dd8`
- name: `Microsoft.VisualStudio.Setup.ChannelSets.Channel::GetMultipleItems`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x17b20`
- `0x17d80`
- `0x17e20`
- `0x18ac0`

## string_xrefs

- `0x17d9c`: `The ChannelManifest must contain one more items of type `

## pseudocode

```c

```

## disassembly

```asm
0x17d80  ldarg.0
0x17d81  call     instance class Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest Microsoft.VisualStudio.Setup.ChannelSets.Channel::get_ChannelManifest()
0x17d86  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.ChannelSets.IChannelItem> Microsoft.VisualStudio.Setup.ChannelSets.IChannelManifest::get_ChannelItems()
0x17d8b  call     T0x2B0000A7
0x17d90  stloc.0
0x17d91  ldarg.1
0x17d92  brfalse.s loc_17DBB
0x17d94  ldloc.0
0x17d95  call     T0x2B0000AA
0x17d9a  brtrue.s loc_17DBB
0x17d9c  ldstr    aTheChannelmani_2// "The ChannelManifest must contain one mo"...
0x17da1  ldtoken  mvar<u1>
0x17da6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17dab  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x17db0  call     string [mscorlib]System.String::Concat(string, string)
0x17db5  newobj   instance void Microsoft.VisualStudio.Setup.ChannelSets.ChannelCompositionException::.ctor(string message)
0x17dba  throw
0x17dbb  ldloc.0
0x17dbc  ldarg.0
0x17dbd  ldftn    T0x2B0000AB
0x17dc3  newobj   instance void class [mscorlib]System.Func`2<mvar<u1>, !!T0>::.ctor(object, native int)
0x17dc8  call     T0x2B0000AC
0x17dcd  call     T0x2B0000AD
0x17dd2  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.VisualStudio.Setup.ChannelSets.ChannelNode`1<mvar<u1>>>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x17dd7  ret
```
