# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddThumbnail

- ea: `0x22540`
- end: `0x225a1`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddThumbnail`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x20260`
- `0x22170`
- `0x22540`
- `0x24ec0`
- `0x25a70`
- `0x25aa0`

## string_xrefs

- `0x22548`: `FixedPageReader`

## pseudocode

```c

```

## disassembly

```asm
0x22540  ldarg.0
0x22541  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x22546  brtrue.s loc_22553
0x22548  ldstr    aFixedpagereade// "FixedPageReader"
0x2254d  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x22552  throw
0x22553  ldarg.0
0x22554  ldarg.0
0x22555  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x2255a  ldarg.1
0x2255b  ldarg.0
0x2255c  ldarg.0
0x2255d  call     instance class System.Windows.Xps.Packaging.XpsThumbnail System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::get_Thumbnail()
0x22562  callvirt instance class System.Windows.Xps.Packaging.XpsThumbnail System.Windows.Xps.Packaging.XpsManager::AddThumbnail(valuetype System.Windows.Xps.Packaging.XpsImageType imageType, class System.Windows.Xps.Packaging.INode parent, class System.Windows.Xps.Packaging.XpsThumbnail oldThumbnail)
0x22567  stfld    class System.Windows.Xps.Packaging.XpsThumbnail System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_thumbnail
0x2256c  ldarg.0
0x2256d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Xps.Packaging.INode> System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_currentChildren
0x22572  ldarg.0
0x22573  ldfld    class System.Windows.Xps.Packaging.XpsThumbnail System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_thumbnail
0x22578  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Xps.Packaging.INode>::Add(var<u1>)
0x2257d  ldarg.0
0x2257e  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x22583  ldarg.0
0x22584  ldfld    class System.Windows.Xps.Packaging.XpsThumbnail System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_thumbnail
0x22589  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x2258e  ldc.i4.0
0x2258f  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ThumbnailRelationshipName()
0x22594  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string)
0x22599  pop
0x2259a  ldarg.0
0x2259b  ldfld    class System.Windows.Xps.Packaging.XpsThumbnail System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_thumbnail
0x225a0  ret
```
