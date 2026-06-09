# System.Windows.Xps.Packaging.XpsOMPackagingPolicy::AcquireXmlWriterForResourceDictionary

- ea: `0x1f470`
- end: `0x1f48a`
- name: `System.Windows.Xps.Packaging.XpsOMPackagingPolicy::AcquireXmlWriterForResourceDictionary`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1f470`

## string_xrefs

- `0x1f478`: `CurrentFixedPageWriter uninitialized`

## pseudocode

```c

```

## disassembly

```asm
0x1f470  ldarg.0
0x1f471  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageXmlWriter
0x1f476  brtrue.s loc_1F483
0x1f478  ldstr    aCurrentfixedpa// "CurrentFixedPageWriter uninitialized"
0x1f47d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1f482  throw
0x1f483  ldarg.0
0x1f484  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentResourceXmlWriter
0x1f489  ret
```
