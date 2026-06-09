# System.Windows.Xps.Serialization.XpsPackagingPolicy::PreCommitCurrentPage

- ea: `0x2f420`
- end: `0x2f444`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::PreCommitCurrentPage`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x23120`
- `0x2f420`

## string_xrefs

- `0x2f428`: `CurrentFixedPageWriter uninitialized`

## pseudocode

```c

```

## disassembly

```asm
0x2f420  ldarg.0
0x2f421  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f426  brtrue.s loc_2F433
0x2f428  ldstr    aCurrentfixedpa// "CurrentFixedPageWriter uninitialized"
0x2f42d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2f432  throw
0x2f433  ldarg.0
0x2f434  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f439  castclass System.Windows.Xps.Packaging.XpsFixedPageReaderWriter
0x2f43e  callvirt instance void System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::PrepareCommit()
0x2f443  ret
```
