# System.Windows.Xps.Packaging.XpsOMPackagingPolicy::ReleaseResourceStreamForXpsFont_0

- ea: `0x1f640`
- end: `0x1f6ae`
- name: `System.Windows.Xps.Packaging.XpsOMPackagingPolicy::ReleaseResourceStreamForXpsFont_0`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0xd660`
- `0x1eee0`
- `0x1ef70`
- `0x1f640`
- `0x1f6b0`
- `0x2e7e0`
- `0x2e7f0`
- `0x2e800`
- `0x2e830`
- `0x2e880`

## string_xrefs

- `0x1f69d`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x1f640  ldarg.0
0x1f641  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_fontsCache
0x1f646  ldarg.1
0x1f647  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x1f64c  castclass System.Windows.Xps.Serialization.ResourceStreamCacheItem
0x1f651  stloc.0
0x1f652  ldloc.0
0x1f653  brfalse.s loc_1F69D
0x1f655  ldloc.0
0x1f656  callvirt instance int32 System.Windows.Xps.Serialization.ResourceStreamCacheItem::Release()
0x1f65b  brtrue.s loc_1F6AD
0x1f65d  call     bool MS.Internal.ReachAppContextSwitches::get_ReleaseDiscardableFontResources()
0x1f662  brfalse.s loc_1F675
0x1f664  ldarg.0
0x1f665  ldloc.0
0x1f666  callvirt instance class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.ResourceStreamCacheItem::get_XpsResourceStream()
0x1f66b  callvirt instance class [System]System.Uri System.Windows.Xps.Serialization.XpsResourceStream::get_Uri()
0x1f670  call     instance void System.Windows.Xps.Packaging.XpsOMPackagingPolicy::ReleaseFontResource(class [System]System.Uri uri)
0x1f675  ldloc.0
0x1f676  callvirt instance class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.ResourceStreamCacheItem::get_XpsResourceStream()
0x1f67b  callvirt instance class [mscorlib]System.IO.Stream System.Windows.Xps.Serialization.XpsResourceStream::get_Stream()
0x1f680  callvirt instance void [mscorlib]System.IO.Stream::Dispose()
0x1f685  ldloc.0
0x1f686  callvirt instance class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.ResourceStreamCacheItem::get_XpsResourceStream()
0x1f68b  callvirt instance void System.Windows.Xps.Serialization.XpsResourceStream::Initialize()
0x1f690  ldarg.0
0x1f691  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_fontsCache
0x1f696  ldarg.1
0x1f697  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x1f69c  ret
0x1f69d  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x1f6a2  call     string System.Windows.Xps.SR::Get(string id)
0x1f6a7  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x1f6ac  throw
0x1f6ad  ret
```
