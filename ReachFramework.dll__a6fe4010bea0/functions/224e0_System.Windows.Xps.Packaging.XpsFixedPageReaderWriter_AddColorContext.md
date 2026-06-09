# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddColorContext

- ea: `0x224e0`
- end: `0x2250c`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddColorContext`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x200b0`
- `0x224e0`
- `0x22e80`
- `0x249a0`
- `0x25aa0`

## string_xrefs

- `0x224e8`: `FixedPageReader`

## pseudocode

```c

```

## disassembly

```asm
0x224e0  ldarg.0
0x224e1  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x224e6  brtrue.s loc_224F3
0x224e8  ldstr    aFixedpagereade// "FixedPageReader"
0x224ed  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x224f2  throw
0x224f3  ldarg.0
0x224f4  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x224f9  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_ColorContextContentType()
0x224fe  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart(class [WindowsBase]MS.Internal.ContentType contentType)
0x22503  stloc.0
0x22504  ldarg.0
0x22505  ldloc.0
0x22506  call     instance class System.Windows.Xps.Packaging.XpsColorContext System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddColorContext(class [WindowsBase]System.IO.Packaging.PackagePart packagePart)
0x2250b  ret
```
