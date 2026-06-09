# System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsFont

- ea: `0x2fa50`
- end: `0x2faa3`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseResourceStreamForXpsFont`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2e800`
- `0x2fa50`

## string_xrefs

- `0x2fa92`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2fa50  ldarg.0
0x2fa51  ldfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2fa56  ldc.i4.1
0x2fa57  bne.un.s loc_2FAA2
0x2fa59  ldarg.0
0x2fa5a  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsFontRef
0x2fa5f  ldc.i4.0
0x2fa60  ble.s    loc_2FA92
0x2fa62  ldarg.0
0x2fa63  ldarg.0
0x2fa64  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsFontRef
0x2fa69  ldc.i4.1
0x2fa6a  sub
0x2fa6b  stfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsFontRef
0x2fa70  ldarg.0
0x2fa71  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentXpsFontRef
0x2fa76  brtrue.s loc_2FAA2
0x2fa78  ldarg.0
0x2fa79  ldfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_fontResourceStream
0x2fa7e  callvirt instance void System.Windows.Xps.Serialization.XpsResourceStream::Initialize()
0x2fa83  ldarg.0
0x2fa84  ldnull
0x2fa85  stfld    class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.NullPackagingPolicy::_fontResourceStream
0x2fa8a  ldarg.0
0x2fa8b  ldc.i4.0
0x2fa8c  stfld    valuetype ResourceAcquireMode System.Windows.Xps.Serialization.NullPackagingPolicy::_fontAcquireMode
0x2fa91  ret
0x2fa92  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2fa97  call     string System.Windows.Xps.SR::Get(string id)
0x2fa9c  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2faa1  throw
0x2faa2  ret
```
