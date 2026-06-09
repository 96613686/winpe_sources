# System.Windows.Xps.Packaging.XpsOMPackagingPolicy::CloseXpsOMPackageWriter

- ea: `0x1f160`
- end: `0x1f19f`
- name: `System.Windows.Xps.Packaging.XpsOMPackagingPolicy::CloseXpsOMPackageWriter`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x26f60`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x1f160`
- `0x1f950`

## string_xrefs

- `0x1f18e`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x1f160  ldarg.0
0x1f161  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPackageWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedDocumentSequenceWriter
0x1f166  brfalse.s loc_1F18E
0x1f168  ldarg.0
0x1f169  ldfld    int32 System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentDocumentSequenceWriterRef
0x1f16e  ldc.i4.0
0x1f16f  ble.s    loc_1F18E
0x1f171  ldarg.0
0x1f172  ldarg.0
0x1f173  ldfld    int32 System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentDocumentSequenceWriterRef
0x1f178  ldc.i4.1
0x1f179  sub
0x1f17a  stfld    int32 System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentDocumentSequenceWriterRef
0x1f17f  ldarg.0
0x1f180  ldfld    int32 System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentDocumentSequenceWriterRef
0x1f185  brtrue.s loc_1F19E
0x1f187  ldarg.0
0x1f188  call     instance void System.Windows.Xps.Packaging.XpsOMPackagingPolicy::Initialize()
0x1f18d  ret
0x1f18e  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x1f193  call     string System.Windows.Xps.SR::Get(string id)
0x1f198  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x1f19d  throw
0x1f19e  ret
```
