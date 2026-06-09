# System.Windows.Xps.Packaging.XpsOMPackagingPolicy::AcquireXmlWriterForPage

- ea: `0x1f450`
- end: `0x1f46a`
- name: `System.Windows.Xps.Packaging.XpsOMPackagingPolicy::AcquireXmlWriterForPage`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1f450`

## string_xrefs

- `0x1f458`: `CurrentFixedPageWriter uninitialized`

## pseudocode

```c

```

## disassembly

```asm
0x1f450  ldarg.0
0x1f451  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageXmlWriter
0x1f456  brtrue.s loc_1F463
0x1f458  ldstr    aCurrentfixedpa// "CurrentFixedPageWriter uninitialized"
0x1f45d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1f462  throw
0x1f463  ldarg.0
0x1f464  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPageContentXmlWriter
0x1f469  ret
```
