# System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::AddFixedPage

- ea: `0x212a0`
- end: `0x21327`
- name: `System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::AddFixedPage`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1ee90`
- `0x1ef70`
- `0x20020`
- `0x212a0`
- `0x21ef0`
- `0x248b0`
- `0x249a0`
- `0x25aa0`

## string_xrefs

- `0x212b5`: `XpsFixedDocumentReaderWriter`
- `0x212c8`: `ReachPackaging_PanelOrSequenceAlreadyOpen`

## pseudocode

```c

```

## disassembly

```asm
0x212a0  ldarg.0
0x212a1  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_metroPart
0x212a6  brfalse.s loc_212B5
0x212a8  ldarg.0
0x212a9  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x212ae  callvirt instance class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::get_MetroPackage()
0x212b3  brtrue.s loc_212C0
0x212b5  ldstr    aXpsfixeddocume// "XpsFixedDocumentReaderWriter"
0x212ba  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x212bf  throw
0x212c0  ldarg.0
0x212c1  ldfld    class System.Windows.Xps.Packaging.XpsFixedPageReaderWriter System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_currentPage
0x212c6  brfalse.s loc_212D8
0x212c8  ldstr    aReachpackaging_5// "ReachPackaging_PanelOrSequenceAlreadyOp"...
0x212cd  call     string System.Windows.Xps.SR::Get(string id)
0x212d2  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x212d7  throw
0x212d8  ldarg.0
0x212d9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x212de  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_linkTargetStream
0x212e3  ldarg.0
0x212e4  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x212e9  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedPageContentType()
0x212ee  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GenerateUniquePart(class [WindowsBase]MS.Internal.ContentType contentType)
0x212f3  stloc.0
0x212f4  ldarg.0
0x212f5  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x212fa  ldarg.0
0x212fb  ldloc.0
0x212fc  ldarg.0
0x212fd  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_linkTargetStream
0x21302  ldarg.0
0x21303  ldfld    int32 System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_pagesWritten
0x21308  ldc.i4.1
0x21309  add
0x2130a  newobj   instance void System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter parent, class [WindowsBase]System.IO.Packaging.PackagePart part, class [mscorlib]System.Collections.Generic.IList`1<string> linkTargetStream, int32 pageNumber)
0x2130f  stloc.1
0x21310  ldarg.0
0x21311  ldloc.1
0x21312  stfld    class System.Windows.Xps.Packaging.XpsFixedPageReaderWriter System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_currentPage
0x21317  ldarg.0
0x21318  ldarg.0
0x21319  ldfld    int32 System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_pagesWritten
0x2131e  ldc.i4.1
0x2131f  add
0x21320  stfld    int32 System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_pagesWritten
0x21325  ldloc.1
0x21326  ret
```
