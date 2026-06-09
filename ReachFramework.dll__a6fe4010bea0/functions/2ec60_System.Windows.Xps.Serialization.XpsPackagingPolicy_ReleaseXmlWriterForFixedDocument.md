# System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseXmlWriterForFixedDocument

- ea: `0x2ec60`
- end: `0x2ecc4`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseXmlWriterForFixedDocument`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x23f10`
- `0x2ec60`

## string_xrefs

- `0x2ecb3`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2ec60  ldarg.0
0x2ec61  ldfld    class System.Windows.Xps.Packaging.IXpsFixedDocumentWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentWriter
0x2ec66  brfalse.s loc_2ECB3
0x2ec68  ldarg.0
0x2ec69  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentWriterRef
0x2ec6e  ldc.i4.0
0x2ec6f  ble.s    loc_2ECB3
0x2ec71  ldarg.0
0x2ec72  ldarg.0
0x2ec73  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentWriterRef
0x2ec78  ldc.i4.1
0x2ec79  sub
0x2ec7a  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentWriterRef
0x2ec7f  ldarg.0
0x2ec80  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentWriterRef
0x2ec85  brtrue.s loc_2ECC3
0x2ec87  ldarg.0
0x2ec88  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2ec8d  ldarg.0
0x2ec8e  ldfld    class System.Windows.Xps.Packaging.IXpsFixedDocumentWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentWriter
0x2ec93  castclass System.Windows.Xps.Packaging.INode
0x2ec98  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit(class System.Windows.Xps.Packaging.INode node)
0x2ec9d  ldarg.0
0x2ec9e  ldnull
0x2ec9f  stfld    class System.Windows.Xps.Packaging.IXpsFixedDocumentWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentWriter
0x2eca4  ldarg.0
0x2eca5  ldnull
0x2eca6  stfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2ecab  ldarg.0
0x2ecac  ldc.i4.0
0x2ecad  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriterRef
0x2ecb2  ret
0x2ecb3  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2ecb8  call     string System.Windows.Xps.SR::Get(string id)
0x2ecbd  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2ecc2  throw
0x2ecc3  ret
```
