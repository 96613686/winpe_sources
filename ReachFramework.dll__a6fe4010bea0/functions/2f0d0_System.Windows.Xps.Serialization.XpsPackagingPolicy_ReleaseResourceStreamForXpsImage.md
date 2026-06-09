# System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsImage

- ea: `0x2f0d0`
- end: `0x2f133`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsImage`
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
- `0x2f0d0`

## string_xrefs

- `0x2f122`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f0d0  ldarg.0
0x2f0d1  ldfld    class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImage
0x2f0d6  brfalse.s loc_2F122
0x2f0d8  ldarg.0
0x2f0d9  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImageRef
0x2f0de  ldc.i4.0
0x2f0df  ble.s    loc_2F122
0x2f0e1  ldarg.0
0x2f0e2  ldarg.0
0x2f0e3  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImageRef
0x2f0e8  ldc.i4.1
0x2f0e9  sub
0x2f0ea  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImageRef
0x2f0ef  ldarg.0
0x2f0f0  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImageRef
0x2f0f5  brtrue.s loc_2F132
0x2f0f7  ldarg.0
0x2f0f8  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2f0fd  ldarg.0
0x2f0fe  ldfld    class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImage
0x2f103  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit(class System.Windows.Xps.Packaging.INode node)
0x2f108  ldarg.0
0x2f109  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_imageResourceStream
0x2f10e  callvirt instance void System.Windows.Xps.Serialization.XpsResourceStream::Initialize()
0x2f113  ldarg.0
0x2f114  ldnull
0x2f115  stfld    class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsImage
0x2f11a  ldarg.0
0x2f11b  ldnull
0x2f11c  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_imageResourceStream
0x2f121  ret
0x2f122  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2f127  call     string System.Windows.Xps.SR::Get(string id)
0x2f12c  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f131  throw
0x2f132  ret
```
