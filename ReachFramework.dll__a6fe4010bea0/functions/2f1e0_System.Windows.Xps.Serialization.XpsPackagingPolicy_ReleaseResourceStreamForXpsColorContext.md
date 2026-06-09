# System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsColorContext

- ea: `0x2f1e0`
- end: `0x2f243`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsColorContext`
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
- `0x2f1e0`

## string_xrefs

- `0x2f232`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f1e0  ldarg.0
0x2f1e1  ldfld    class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContext
0x2f1e6  brfalse.s loc_2F232
0x2f1e8  ldarg.0
0x2f1e9  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContextRef
0x2f1ee  ldc.i4.0
0x2f1ef  ble.s    loc_2F232
0x2f1f1  ldarg.0
0x2f1f2  ldarg.0
0x2f1f3  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContextRef
0x2f1f8  ldc.i4.1
0x2f1f9  sub
0x2f1fa  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContextRef
0x2f1ff  ldarg.0
0x2f200  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContextRef
0x2f205  brtrue.s loc_2F242
0x2f207  ldarg.0
0x2f208  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2f20d  ldarg.0
0x2f20e  ldfld    class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContext
0x2f213  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit(class System.Windows.Xps.Packaging.INode node)
0x2f218  ldarg.0
0x2f219  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_colorContextResourceStream
0x2f21e  callvirt instance void System.Windows.Xps.Serialization.XpsResourceStream::Initialize()
0x2f223  ldarg.0
0x2f224  ldnull
0x2f225  stfld    class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsColorContext
0x2f22a  ldarg.0
0x2f22b  ldnull
0x2f22c  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_colorContextResourceStream
0x2f231  ret
0x2f232  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2f237  call     string System.Windows.Xps.SR::Get(string id)
0x2f23c  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f241  throw
0x2f242  ret
```
