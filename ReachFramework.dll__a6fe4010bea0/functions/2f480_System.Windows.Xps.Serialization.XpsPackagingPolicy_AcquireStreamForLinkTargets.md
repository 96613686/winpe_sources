# System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireStreamForLinkTargets

- ea: `0x2f480`
- end: `0x2f4a4`
- name: `System.Windows.Xps.Serialization.XpsPackagingPolicy::AcquireStreamForLinkTargets`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x220c0`
- `0x2f480`

## string_xrefs

- `0x2f488`: `CurrentFixedPageWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f480  ldarg.0
0x2f481  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f486  brtrue.s loc_2F493
0x2f488  ldstr    aCurrentfixedpa_0// "CurrentFixedPageWriter"
0x2f48d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2f492  throw
0x2f493  ldarg.0
0x2f494  ldfld    class System.Windows.Xps.Packaging.IXpsFixedPageWriter System.Windows.Xps.Serialization.XpsPackagingPolicy::_currentFixedPageWriter
0x2f499  castclass System.Windows.Xps.Packaging.XpsFixedPageReaderWriter
0x2f49e  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::get_LinkTargetStream()
0x2f4a3  ret
```
