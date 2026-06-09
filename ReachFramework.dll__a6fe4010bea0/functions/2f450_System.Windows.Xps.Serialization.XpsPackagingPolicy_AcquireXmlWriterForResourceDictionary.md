# System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireXmlWriterForResourceDictionary

- ea: `0x2f450`
- end: `0x2f474`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireXmlWriterForResourceDictionary`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x220e0`
- `0x2f450`

## string_xrefs

- `0x2f458`: `CurrentFixedPageWriter uninitialized`

## pseudocode

```c

```

## disassembly

```asm
0x2f450  ldarg.0
0x2f451  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f456  brtrue.s loc_2F463
0x2f458  ldstr    aCurrentfixedpa// "CurrentFixedPageWriter uninitialized"
0x2f45d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2f462  throw
0x2f463  ldarg.0
0x2f464  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f469  castclass System.Windows.Xps.Packaging.XpsFixedPageReaderWriter
0x2f46e  callvirt instance class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::get_ResourceDictionaryXmlWriter()
0x2f473  ret
```
