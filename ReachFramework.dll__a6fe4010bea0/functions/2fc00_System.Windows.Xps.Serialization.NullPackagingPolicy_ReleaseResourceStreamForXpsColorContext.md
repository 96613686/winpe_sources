# System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsColorContext

- ea: `0x2fc00`
- end: `0x2fc43`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsColorContext`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2e800`
- `0x2fc00`

## string_xrefs

- `0x2fc32`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2fc00  ldarg.0
0x2fc01  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsColorContextRef
0x2fc06  ldc.i4.0
0x2fc07  ble.s    loc_2FC32
0x2fc09  ldarg.0
0x2fc0a  ldarg.0
0x2fc0b  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsColorContextRef
0x2fc10  ldc.i4.1
0x2fc11  sub
0x2fc12  stfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsColorContextRef
0x2fc17  ldarg.0
0x2fc18  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsColorContextRef
0x2fc1d  brtrue.s loc_2FC42
0x2fc1f  ldarg.0
0x2fc20  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_colorContextResourceStream
0x2fc25  callvirt instance void System.Windows.Xps.Serialization.XpsResourceStream::Initialize()
0x2fc2a  ldarg.0
0x2fc2b  ldnull
0x2fc2c  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_colorContextResourceStream
0x2fc31  ret
0x2fc32  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2fc37  call     string System.Windows.Xps.SR::Get(string id)
0x2fc3c  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2fc41  throw
0x2fc42  ret
```
