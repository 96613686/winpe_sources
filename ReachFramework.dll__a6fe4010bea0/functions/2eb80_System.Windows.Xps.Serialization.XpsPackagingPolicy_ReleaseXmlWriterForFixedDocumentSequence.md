# System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseXmlWriterForFixedDocumentSequence

- ea: `0x2eb80`
- end: `0x2ebd5`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseXmlWriterForFixedDocumentSequence`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x23f10`
- `0x2eb80`
- `0x2f520`

## string_xrefs

- `0x2ebc4`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2eb80  ldarg.0
0x2eb81  ldfld    class System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentSequenceWriter
0x2eb86  brfalse.s loc_2EBC4
0x2eb88  ldarg.0
0x2eb89  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentDocumentSequenceWriterRef
0x2eb8e  ldc.i4.0
0x2eb8f  ble.s    loc_2EBC4
0x2eb91  ldarg.0
0x2eb92  ldarg.0
0x2eb93  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentDocumentSequenceWriterRef
0x2eb98  ldc.i4.1
0x2eb99  sub
0x2eb9a  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentDocumentSequenceWriterRef
0x2eb9f  ldarg.0
0x2eba0  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentDocumentSequenceWriterRef
0x2eba5  brtrue.s loc_2EBD4
0x2eba7  ldarg.0
0x2eba8  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2ebad  ldarg.0
0x2ebae  ldfld    class System.Windows.Xps.Packaging.IXpsFixedDocumentSequenceWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentSequenceWriter
0x2ebb3  castclass System.Windows.Xps.Packaging.INode
0x2ebb8  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit(class System.Windows.Xps.Packaging.INode node)
0x2ebbd  ldarg.0
0x2ebbe  call     instance void System.Windows.Xps.Serialization.XpsPackagingPolicy::Initialize()
0x2ebc3  ret
0x2ebc4  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2ebc9  call     string System.Windows.Xps.SR::Get(string id)
0x2ebce  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2ebd3  throw
0x2ebd4  ret
```
