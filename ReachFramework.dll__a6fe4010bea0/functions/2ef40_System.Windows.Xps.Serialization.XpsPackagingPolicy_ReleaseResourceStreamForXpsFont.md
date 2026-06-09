# System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsFont

- ea: `0x2ef40`
- end: `0x2efb3`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseResourceStreamForXpsFont`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x23f10`
- `0x2e800`
- `0x2ef40`

## string_xrefs

- `0x2efa2`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2ef40  ldarg.0
0x2ef41  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2ef46  ldc.i4.1
0x2ef47  bne.un.s loc_2EFB2
0x2ef49  ldarg.0
0x2ef4a  ldfld    class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFont
0x2ef4f  brfalse.s loc_2EFA2
0x2ef51  ldarg.0
0x2ef52  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFontRef
0x2ef57  ldc.i4.0
0x2ef58  ble.s    loc_2EFA2
0x2ef5a  ldarg.0
0x2ef5b  ldarg.0
0x2ef5c  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFontRef
0x2ef61  ldc.i4.1
0x2ef62  sub
0x2ef63  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFontRef
0x2ef68  ldarg.0
0x2ef69  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFontRef
0x2ef6e  brtrue.s loc_2EFB2
0x2ef70  ldarg.0
0x2ef71  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2ef76  ldarg.0
0x2ef77  ldfld    class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFont
0x2ef7c  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit(class System.Windows.Xps.Packaging.INode node)
0x2ef81  ldarg.0
0x2ef82  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontResourceStream
0x2ef87  callvirt instance void System.Windows.Xps.Serialization.XpsResourceStream::Initialize()
0x2ef8c  ldarg.0
0x2ef8d  ldnull
0x2ef8e  stfld    class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentXpsFont
0x2ef93  ldarg.0
0x2ef94  ldnull
0x2ef95  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontResourceStream
0x2ef9a  ldarg.0
0x2ef9b  ldc.i4.0
0x2ef9c  stfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.XpsPackagingPolicy::_fontAcquireMode
0x2efa1  ret
0x2efa2  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2efa7  call     string System.Windows.Xps.SR::Get(string id)
0x2efac  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2efb1  throw
0x2efb2  ret
```
