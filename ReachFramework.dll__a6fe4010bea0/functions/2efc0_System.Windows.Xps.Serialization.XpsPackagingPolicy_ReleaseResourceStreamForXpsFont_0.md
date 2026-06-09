# System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsFont_0

- ea: `0x2efc0`
- end: `0x2f029`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsFont_0`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x23f10`
- `0x2e850`
- `0x2e880`
- `0x2efc0`

## string_xrefs

- `0x2f018`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2efc0  ldarg.0
0x2efc1  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2efc6  ldc.i4.2
0x2efc7  bne.un.s loc_2F028
0x2efc9  ldarg.0
0x2efca  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontsCache
0x2efcf  ldarg.1
0x2efd0  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x2efd5  castclass System.Windows.Xps.Serialization.ResourceStreamCacheItem
0x2efda  stloc.0
0x2efdb  ldloc.0
0x2efdc  brfalse.s loc_2F018
0x2efde  ldloc.0
0x2efdf  callvirt instance int32 System.Windows.Xps.Serialization.ResourceStreamCacheItem::Release()
0x2efe4  brtrue.s loc_2F028
0x2efe6  ldarg.0
0x2efe7  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2efec  ldloc.0
0x2efed  callvirt instance class System.Windows.Xps.Packaging.XpsResource System.Windows.Xps.Serialization.ResourceStreamCacheItem::get_XpsResource()
0x2eff2  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit(class System.Windows.Xps.Packaging.INode node)
0x2eff7  ldarg.0
0x2eff8  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontsCache
0x2effd  ldarg.1
0x2effe  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x2f003  ldarg.0
0x2f004  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontsCache
0x2f009  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x2f00e  brtrue.s loc_2F028
0x2f010  ldarg.0
0x2f011  ldc.i4.0
0x2f012  stfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2f017  ret
0x2f018  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2f01d  call     string System.Windows.Xps.SR::Get(string id)
0x2f022  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f027  throw
0x2f028  ret
```
