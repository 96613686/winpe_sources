# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddFont_0

- ea: `0x22470`
- end: `0x224af`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddFont_0`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x22460`
- `0x224b0`

## callees

- `0x20090`
- `0x22470`
- `0x22dc0`
- `0x249a0`
- `0x24a30`
- `0x25aa0`

## string_xrefs

- `0x22478`: `FixedPageReader`

## pseudocode

```c

```

## disassembly

```asm
0x22470  ldarg.0
0x22471  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x22476  brtrue.s loc_22483
0x22478  ldstr    aFixedpagereade// "FixedPageReader"
0x2247d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x22482  throw
0x22483  ldnull
0x22484  stloc.0
0x22485  ldarg.1
0x22486  brfalse.s loc_22496
0x22488  ldarg.0
0x22489  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x2248e  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GenerateObfuscatedFontPart()
0x22493  stloc.0
0x22494  br.s     loc_224A7
0x22496  ldarg.0
0x22497  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x2249c  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FontContentType()
0x224a1  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart(class [WindowsBase]MS.Internal.ContentType contentType)
0x224a6  stloc.0
0x224a7  ldarg.0
0x224a8  ldloc.0
0x224a9  call     instance class System.Windows.Xps.Packaging.XpsFont System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddFont(class [WindowsBase]System.IO.Packaging.PackagePart packagePart)
0x224ae  ret
```
