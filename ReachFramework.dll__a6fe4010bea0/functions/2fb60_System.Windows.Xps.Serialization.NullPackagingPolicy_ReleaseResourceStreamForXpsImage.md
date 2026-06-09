# System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsImage

- ea: `0x2fb60`
- end: `0x2fba3`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsImage`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2e800`
- `0x2fb60`

## string_xrefs

- `0x2fb92`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2fb60  ldarg.0
0x2fb61  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsImageRef
0x2fb66  ldc.i4.0
0x2fb67  ble.s    loc_2FB92
0x2fb69  ldarg.0
0x2fb6a  ldarg.0
0x2fb6b  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsImageRef
0x2fb70  ldc.i4.1
0x2fb71  sub
0x2fb72  stfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsImageRef
0x2fb77  ldarg.0
0x2fb78  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsImageRef
0x2fb7d  brtrue.s loc_2FBA2
0x2fb7f  ldarg.0
0x2fb80  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_imageResourceStream
0x2fb85  callvirt instance void System.Windows.Xps.Serialization.XpsResourceStream::Initialize()
0x2fb8a  ldarg.0
0x2fb8b  ldnull
0x2fb8c  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_imageResourceStream
0x2fb91  ret
0x2fb92  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2fb97  call     string System.Windows.Xps.SR::Get(string id)
0x2fb9c  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2fba1  throw
0x2fba2  ret
```
