# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddImage_0

- ea: `0x22650`
- end: `0x22696`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddImage_0`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1ef70`
- `0x22650`
- `0x226a0`

## string_xrefs

- `0x22658`: `FixedPageReader`

## pseudocode

```c

```

## disassembly

```asm
0x22650  ldarg.0
0x22651  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x22656  brtrue.s loc_22663
0x22658  ldstr    aFixedpagereade// "FixedPageReader"
0x2265d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x22662  throw
0x22663  ldarg.1
0x22664  brtrue.s loc_22671
0x22666  ldstr    aMimetype// "mimeType"
0x2266b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x22670  throw
0x22671  ldarg.1
0x22672  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22677  brtrue.s loc_22689
0x22679  ldstr    aReachpackaging_9// "ReachPackaging_InvalidType"
0x2267e  call     string System.Windows.Xps.SR::Get(string id)
0x22683  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x22688  throw
0x22689  ldarg.0
0x2268a  ldarg.1
0x2268b  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0x22690  call     instance class System.Windows.Xps.Packaging.XpsImage System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddImage(class [WindowsBase]MS.Internal.ContentType mimeType)
0x22695  ret
```
