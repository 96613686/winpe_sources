# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddResourceDictionary

- ea: `0x22510`
- end: `0x2253c`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddResourceDictionary`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x20190`
- `0x22510`
- `0x22f00`
- `0x249a0`
- `0x25aa0`

## string_xrefs

- `0x22518`: `FixedPageReader`

## pseudocode

```c

```

## disassembly

```asm
0x22510  ldarg.0
0x22511  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x22516  brtrue.s loc_22523
0x22518  ldstr    aFixedpagereade// "FixedPageReader"
0x2251d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x22522  throw
0x22523  ldarg.0
0x22524  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22529  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceDictionaryContentType()
0x2252e  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart(class [WindowsBase]MS.Internal.ContentType contentType)
0x22533  stloc.0
0x22534  ldarg.0
0x22535  ldloc.0
0x22536  call     instance class System.Windows.Xps.Packaging.XpsResourceDictionary System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddResourceDictionary(class [WindowsBase]System.IO.Packaging.PackagePart packagePart)
0x2253b  ret
```
