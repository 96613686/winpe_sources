# System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseXmlWriterForFixedPage

- ea: `0x2ed50`
- end: `0x2edb6`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::ReleaseXmlWriterForFixedPage`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x218a0`
- `0x23f10`
- `0x2ed50`

## string_xrefs

- `0x2eda5`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2ed50  ldarg.0
0x2ed51  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2ed56  brfalse.s loc_2EDA5
0x2ed58  ldarg.0
0x2ed59  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriterRef
0x2ed5e  ldc.i4.0
0x2ed5f  ble.s    loc_2EDA5
0x2ed61  ldarg.0
0x2ed62  ldarg.0
0x2ed63  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriterRef
0x2ed68  ldc.i4.1
0x2ed69  sub
0x2ed6a  stfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriterRef
0x2ed6f  ldarg.0
0x2ed70  ldfld    int32 System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriterRef
0x2ed75  brtrue.s loc_2EDB5
0x2ed77  ldarg.0
0x2ed78  ldfld    class System.Windows.Xps.Packaging.XpsInterleavingPolicy System.Windows.Xps.Serialization.XpsPackagingPolicy::_interleavingPolicy
0x2ed7d  ldarg.0
0x2ed7e  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2ed83  castclass System.Windows.Xps.Packaging.INode
0x2ed88  callvirt instance void System.Windows.Xps.Packaging.XpsInterleavingPolicy::Commit(class System.Windows.Xps.Packaging.INode node)
0x2ed8d  ldarg.0
0x2ed8e  ldnull
0x2ed8f  stfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2ed94  ldarg.0
0x2ed95  ldfld    class System.Windows.Xps.Packaging.IXpsFixedDocumentWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedDocumentWriter
0x2ed9a  isinst   System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter
0x2ed9f  callvirt instance void System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::CurrentPageCommitted()
0x2eda4  ret
0x2eda5  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2edaa  call     string System.Windows.Xps.SR::Get(string id)
0x2edaf  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2edb4  throw
0x2edb5  ret
```
