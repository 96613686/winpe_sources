# System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireXmlWriterForPage

- ea: `0x2f3f0`
- end: `0x2f414`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireXmlWriterForPage`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x23110`
- `0x2f3f0`

## string_xrefs

- `0x2f3f8`: `CurrentFixedPageWriter uninitialized`

## pseudocode

```c

```

## disassembly

```asm
0x2f3f0  ldarg.0
0x2f3f1  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f3f6  brtrue.s loc_2F403
0x2f3f8  ldstr    aCurrentfixedpa// "CurrentFixedPageWriter uninitialized"
0x2f3fd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2f402  throw
0x2f403  ldarg.0
0x2f404  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f409  castclass System.Windows.Xps.Packaging.XpsFixedPageReaderWriter
0x2f40e  callvirt instance class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::get_PageXmlWriter()
0x2f413  ret
```
