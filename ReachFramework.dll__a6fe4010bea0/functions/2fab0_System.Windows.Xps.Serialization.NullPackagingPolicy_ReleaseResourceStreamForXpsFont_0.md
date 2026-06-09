# System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsFont_0

- ea: `0x2fab0`
- end: `0x2fb08`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsFont_0`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2e880`
- `0x2fab0`

## string_xrefs

- `0x2faf7`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2fab0  ldarg.0
0x2fab1  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2fab6  ldc.i4.2
0x2fab7  bne.un.s loc_2FB07
0x2fab9  ldarg.0
0x2faba  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.NullPackagingPolicy::_fontsCache
0x2fabf  ldarg.1
0x2fac0  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x2fac5  castclass System.Windows.Xps.Serialization.ResourceStreamCacheItem
0x2faca  stloc.0
0x2facb  ldloc.0
0x2facc  brfalse.s loc_2FAF7
0x2face  ldloc.0
0x2facf  callvirt instance int32 System.Windows.Xps.Serialization.ResourceStreamCacheItem::Release()
0x2fad4  brtrue.s loc_2FB07
0x2fad6  ldarg.0
0x2fad7  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.NullPackagingPolicy::_fontsCache
0x2fadc  ldarg.1
0x2fadd  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0x2fae2  ldarg.0
0x2fae3  ldfld    class [mscorlib]System.Collections.Hashtable System.Windows.Xps.Serialization.NullPackagingPolicy::_fontsCache
0x2fae8  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x2faed  brtrue.s loc_2FB07
0x2faef  ldarg.0
0x2faf0  ldc.i4.0
0x2faf1  stfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2faf6  ret
0x2faf7  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2fafc  call     string System.Windows.Xps.SR::Get(string id)
0x2fb01  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2fb06  throw
0x2fb07  ret
```
