# System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseXmlWriterForFixedDocument

- ea: `0x2f780`
- end: `0x2f7d4`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseXmlWriterForFixedDocument`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2f780`
- `0x2fe90`

## string_xrefs

- `0x2f7c3`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f780  ldarg.0
0x2f781  ldfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedDocumentWriter
0x2f786  brfalse.s loc_2F7C3
0x2f788  ldarg.0
0x2f789  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedDocumentWriterRef
0x2f78e  ldc.i4.0
0x2f78f  ble.s    loc_2F7C3
0x2f791  ldarg.0
0x2f792  ldarg.0
0x2f793  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedDocumentWriterRef
0x2f798  ldc.i4.1
0x2f799  sub
0x2f79a  stfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedDocumentWriterRef
0x2f79f  ldarg.0
0x2f7a0  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedDocumentWriterRef
0x2f7a5  brtrue.s loc_2F7D3
0x2f7a7  ldarg.0
0x2f7a8  ldnull
0x2f7a9  stfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedDocumentWriter
0x2f7ae  ldarg.0
0x2f7af  ldnull
0x2f7b0  stfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriter
0x2f7b5  ldarg.0
0x2f7b6  ldc.i4.0
0x2f7b7  stfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriterRef
0x2f7bc  ldarg.0
0x2f7bd  call     instance void System.Windows.Xps.Serialization.NullPackagingPolicy::InitializeResourceReferences()
0x2f7c2  ret
0x2f7c3  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2f7c8  call     string System.Windows.Xps.SR::Get(string id)
0x2f7cd  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f7d2  throw
0x2f7d3  ret
```
