# System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsFont_0

- ea: `0x2ee70`
- end: `0x2ef39`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireResourceStreamForXpsFont_0`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x21de0`
- `0x23f60`
- `0x25a70`
- `0x26480`
- `0x2e7c0`
- `0x2e820`
- `0x2e830`
- `0x2e840`
- `0x2e860`
- `0x2e870`
- `0x2ee70`

## string_xrefs

- `0x2ef1a`: `ReachSerialization_NoFixedPageWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2ee70  ldnull
0x2ee71  stloc.0
0x2ee72  ldarg.0
0x2ee73  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2ee78  ldc.i4.1
0x2ee79  beq      loc_2EF37
0x2ee7e  ldarg.0
0x2ee7f  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2ee84  brtrue.s loc_2EE8D
0x2ee86  ldarg.0
0x2ee87  ldc.i4.2
0x2ee88  stfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2ee8d  ldarg.0
0x2ee8e  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontsCache
0x2ee93  ldarg.1
0x2ee94  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x2ee99  castclass System.Windows.Xps.Serialization.ResourceStreamCacheItem
0x2ee9e  stloc.1
0x2ee9f  ldloc.1
0x2eea0  brtrue   loc_2EF2A
0x2eea5  newobj   instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::.ctor()
0x2eeaa  stloc.1
0x2eeab  ldarg.0
0x2eeac  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2eeb1  brfalse.s loc_2EF1A
0x2eeb3  ldarg.0
0x2eeb4  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2eeb9  callvirt instance class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Packaging.IXpsFixedPageWriter::AddFont()
0x2eebe  stloc.2
0x2eebf  ldloc.2
0x2eec0  brfalse.s loc_2EF37
0x2eec2  ldarg.0
0x2eec3  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2eec8  ldloc.2
0x2eec9  ldc.i4.0
0x2eeca  ldarg.0
0x2eecb  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2eed0  castclass System.Windows.Xps.Packaging.INode
0x2eed5  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::AddItem(class System.Windows.Xps.Packaging.INode n, int32 number, class System.Windows.Xps.Packaging.INode parent)
0x2eeda  ldloc.1
0x2eedb  ldloc.2
0x2eedc  callvirt instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::set_XpsResource(class System.Windows.Xps.Packaging.XpsResource value)
0x2eee1  ldarg.0
0x2eee2  ldloc.2
0x2eee3  callvirt instance class [mscorlib]System.IO.Stream System.Windows.Xps.Packaging.XpsResource::GetStream()
0x2eee8  ldloc.2
0x2eee9  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2eeee  newobj   instance void System.Windows.Xps.Serialization.XpsResourceStream::.ctor(class [mscorlib]System.IO.Stream stream, class [System]System.Uri uri)
0x2eef3  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontResourceStream
0x2eef8  ldloc.1
0x2eef9  ldarg.0
0x2eefa  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontResourceStream
0x2eeff  callvirt instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::set_XpsResourceStream(class System.Windows.Xps.Serialization.XpsResourceStream value)
0x2ef04  ldarg.0
0x2ef05  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontsCache
0x2ef0a  ldarg.1
0x2ef0b  ldloc.1
0x2ef0c  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x2ef11  ldarg.0
0x2ef12  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontResourceStream
0x2ef17  stloc.0
0x2ef18  br.s     loc_2EF37
0x2ef1a  ldstr    aReachserializa_0// "ReachSerialization_NoFixedPageWriter"
0x2ef1f  call     string System.Windows.Xps.SR::Get(string id)
0x2ef24  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2ef29  throw
0x2ef2a  ldloc.1
0x2ef2b  callvirt instance class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.ResourceStreamCacheItem::get_XpsResourceStream()
0x2ef30  stloc.0
0x2ef31  ldloc.1
0x2ef32  callvirt instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::IncRef()
0x2ef37  ldloc.0
0x2ef38  ret
```
