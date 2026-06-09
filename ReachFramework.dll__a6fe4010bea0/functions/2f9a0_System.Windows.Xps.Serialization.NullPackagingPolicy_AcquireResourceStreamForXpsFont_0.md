# System.Windows.Xps.Serialization.NullPackagingPolicy::AcquireResourceStreamForXpsFont_0

- ea: `0x2f9a0`
- end: `0x2fa4a`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::AcquireResourceStreamForXpsFont_0`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2e7c0`
- `0x2e820`
- `0x2e830`
- `0x2e840`
- `0x2e860`
- `0x2e870`
- `0x2f9a0`

## string_xrefs

- `0x2fa2b`: `ReachSerialization_NoFixedPageWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f9a0  ldnull
0x2f9a1  stloc.0
0x2f9a2  ldarg.0
0x2f9a3  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2f9a8  ldc.i4.1
0x2f9a9  beq      loc_2FA48
0x2f9ae  ldarg.0
0x2f9af  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2f9b4  brtrue.s loc_2F9BD
0x2f9b6  ldarg.0
0x2f9b7  ldc.i4.2
0x2f9b8  stfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2f9bd  ldarg.0
0x2f9be  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.NullPackagingPolicy::_fontsCache
0x2f9c3  ldarg.1
0x2f9c4  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x2f9c9  castclass System.Windows.Xps.Serialization.ResourceStreamCacheItem
0x2f9ce  stloc.1
0x2f9cf  ldloc.1
0x2f9d0  brtrue.s loc_2FA3B
0x2f9d2  newobj   instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::.ctor()
0x2f9d7  stloc.1
0x2f9d8  ldarg.0
0x2f9d9  ldfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriter
0x2f9de  brfalse.s loc_2FA2B
0x2f9e0  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x2f9e5  stloc.2
0x2f9e6  ldloc.2
0x2f9e7  brfalse.s loc_2FA48
0x2f9e9  ldloc.1
0x2f9ea  ldnull
0x2f9eb  callvirt instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::set_XpsResource(class System.Windows.Xps.Packaging.XpsResource value)
0x2f9f0  ldarg.0
0x2f9f1  ldloc.2
0x2f9f2  ldstr    aPackageFont// "package/font"
0x2f9f7  ldc.i4.2
0x2f9f8  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x2f9fd  newobj   instance void System.Windows.Xps.Serialization.XpsResourceStream::.ctor(class [mscorlib]System.IO.Stream stream, class [System]System.Uri uri)
0x2fa02  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_fontResourceStream
0x2fa07  ldloc.1
0x2fa08  ldarg.0
0x2fa09  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_fontResourceStream
0x2fa0e  callvirt instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::set_XpsResourceStream(class System.Windows.Xps.Serialization.XpsResourceStream value)
0x2fa13  ldarg.0
0x2fa14  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.NullPackagingPolicy::_fontsCache
0x2fa19  ldarg.1
0x2fa1a  ldloc.1
0x2fa1b  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x2fa20  ldarg.0
0x2fa21  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_fontResourceStream
0x2fa26  stloc.0
0x2fa27  ldnull
0x2fa28  stloc.2
0x2fa29  br.s     loc_2FA48
0x2fa2b  ldstr    aReachserializa_0// "ReachSerialization_NoFixedPageWriter"
0x2fa30  call     string System.Windows.Xps.SR::Get(string id)
0x2fa35  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2fa3a  throw
0x2fa3b  ldloc.1
0x2fa3c  callvirt instance class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.ResourceStreamCacheItem::get_XpsResourceStream()
0x2fa41  stloc.0
0x2fa42  ldloc.1
0x2fa43  callvirt instance void System.Windows.Xps.Serialization.ResourceStreamCacheItem::IncRef()
0x2fa48  ldloc.0
0x2fa49  ret
```
