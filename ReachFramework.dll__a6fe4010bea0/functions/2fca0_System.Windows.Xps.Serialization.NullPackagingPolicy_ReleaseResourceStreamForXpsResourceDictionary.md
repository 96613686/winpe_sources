# System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsResourceDictionary

- ea: `0x2fca0`
- end: `0x2fce3`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsResourceDictionary`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2e800`
- `0x2fca0`

## string_xrefs

- `0x2fcd2`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2fca0  ldarg.0
0x2fca1  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsResourceDictionaryRef
0x2fca6  ldc.i4.0
0x2fca7  ble.s    loc_2FCD2
0x2fca9  ldarg.0
0x2fcaa  ldarg.0
0x2fcab  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsResourceDictionaryRef
0x2fcb0  ldc.i4.1
0x2fcb1  sub
0x2fcb2  stfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsResourceDictionaryRef
0x2fcb7  ldarg.0
0x2fcb8  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsResourceDictionaryRef
0x2fcbd  brtrue.s loc_2FCE2
0x2fcbf  ldarg.0
0x2fcc0  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_resourceDictionaryResourceStream
0x2fcc5  callvirt instance void System.Windows.Xps.Serialization.XpsResourceStream::Initialize()
0x2fcca  ldarg.0
0x2fccb  ldnull
0x2fccc  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_resourceDictionaryResourceStream
0x2fcd1  ret
0x2fcd2  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2fcd7  call     string System.Windows.Xps.SR::Get(string id)
0x2fcdc  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2fce1  throw
0x2fce2  ret
```
