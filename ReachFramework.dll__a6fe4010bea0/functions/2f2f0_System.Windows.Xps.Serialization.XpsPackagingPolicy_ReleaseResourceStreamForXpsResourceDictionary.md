# System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsResourceDictionary

- ea: `0x2f2f0`
- end: `0x2f353`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsResourceDictionary`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x23f10`
- `0x2e800`
- `0x2f2f0`

## string_xrefs

- `0x2f342`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f2f0  ldarg.0
0x2f2f1  ldfld    class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionary
0x2f2f6  brfalse.s loc_2F342
0x2f2f8  ldarg.0
0x2f2f9  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionaryRef
0x2f2fe  ldc.i4.0
0x2f2ff  ble.s    loc_2F342
0x2f301  ldarg.0
0x2f302  ldarg.0
0x2f303  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionaryRef
0x2f308  ldc.i4.1
0x2f309  sub
0x2f30a  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionaryRef
0x2f30f  ldarg.0
0x2f310  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionaryRef
0x2f315  brtrue.s loc_2F352
0x2f317  ldarg.0
0x2f318  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2f31d  ldarg.0
0x2f31e  ldfld    class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionary
0x2f323  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit(class System.Windows.Xps.Packaging.INode node)
0x2f328  ldarg.0
0x2f329  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_resourceDictionaryResourceStream
0x2f32e  callvirt instance void System.Windows.Xps.Serialization.XpsResourceStream::Initialize()
0x2f333  ldarg.0
0x2f334  ldnull
0x2f335  stfld    class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsResourceDictionary
0x2f33a  ldarg.0
0x2f33b  ldnull
0x2f33c  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_resourceDictionaryResourceStream
0x2f341  ret
0x2f342  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2f347  call     string System.Windows.Xps.SR::Get(string id)
0x2f34c  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f351  throw
0x2f352  ret
```
