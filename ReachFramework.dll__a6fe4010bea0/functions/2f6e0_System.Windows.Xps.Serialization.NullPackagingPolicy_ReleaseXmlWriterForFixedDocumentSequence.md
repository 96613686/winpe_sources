# System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseXmlWriterForFixedDocumentSequence

- ea: `0x2f6e0`
- end: `0x2f725`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseXmlWriterForFixedDocumentSequence`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2f6e0`
- `0x2fe60`
- `0x2fe90`

## string_xrefs

- `0x2f714`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f6e0  ldarg.0
0x2f6e1  ldfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedDocumentSequenceWriter
0x2f6e6  brfalse.s loc_2F714
0x2f6e8  ldarg.0
0x2f6e9  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentDocumentSequenceWriterRef
0x2f6ee  ldc.i4.0
0x2f6ef  ble.s    loc_2F714
0x2f6f1  ldarg.0
0x2f6f2  ldarg.0
0x2f6f3  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentDocumentSequenceWriterRef
0x2f6f8  ldc.i4.1
0x2f6f9  sub
0x2f6fa  stfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentDocumentSequenceWriterRef
0x2f6ff  ldarg.0
0x2f700  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentDocumentSequenceWriterRef
0x2f705  brtrue.s loc_2F724
0x2f707  ldarg.0
0x2f708  call     instance void System.Windows.Xps.Serialization.NullPackagingPolicy::Initialize()
0x2f70d  ldarg.0
0x2f70e  call     instance void System.Windows.Xps.Serialization.NullPackagingPolicy::InitializeResourceReferences()
0x2f713  ret
0x2f714  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2f719  call     string System.Windows.Xps.SR::Get(string id)
0x2f71e  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f723  throw
0x2f724  ret
```
