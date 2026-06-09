# System.Windows.Xps.Packaging.XpsOMPackagingPolicy::ReleaseXmlWriterForFixedPage

- ea: `0x1f370`
- end: `0x1f426`
- name: `System.Windows.Xps.Packaging.XpsOMPackagingPolicy::ReleaseXmlWriterForFixedPage`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x1f370`
- `0x1fb70`

## string_xrefs

- `0x1f415`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x1f370  ldarg.0
0x1f371  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageXmlWriter
0x1f376  brfalse  loc_1F415
0x1f37b  ldarg.0
0x1f37c  ldfld    int32 System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageWriterRef
0x1f381  ldc.i4.0
0x1f382  ble      loc_1F415
0x1f387  ldarg.0
0x1f388  ldarg.0
0x1f389  ldfld    int32 System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageWriterRef
0x1f38e  ldc.i4.1
0x1f38f  sub
0x1f390  stfld    int32 System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageWriterRef
0x1f395  ldarg.0
0x1f396  ldfld    int32 System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageWriterRef
0x1f39b  brtrue   loc_1F425
0x1f3a0  ldarg.0
0x1f3a1  call     instance void System.Windows.Xps.Packaging.XpsOMPackagingPolicy::AddCurrentPageToPackageWriter()
0x1f3a6  ldarg.0
0x1f3a7  ldnull
0x1f3a8  stfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPage System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageWriter
0x1f3ad  ldarg.0
0x1f3ae  ldnull
0x1f3af  stfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPagePrintTicket
0x1f3b4  ldarg.0
0x1f3b5  ldc.r8   0.0
0x1f3be  ldc.r8   0.0
0x1f3c7  newobj   instance void [WindowsBase]System.Windows.Size::.ctor(float64, float64)
0x1f3cc  stfld    valuetype [WindowsBase]System.Windows.Size System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPageSize
0x1f3d1  ldarg.0
0x1f3d2  ldfld    class [System.Printing]MS.Internal.PrintWin32Thunk.XpsPrintStream System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPagePrintStream
0x1f3d7  callvirt instance void [mscorlib]System.IO.Stream::Dispose()
0x1f3dc  ldarg.0
0x1f3dd  ldnull
0x1f3de  stfld    class [System.Printing]MS.Internal.PrintWin32Thunk.XpsPrintStream System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPagePrintStream
0x1f3e3  ldarg.0
0x1f3e4  ldnull
0x1f3e5  stfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageXmlWriter
0x1f3ea  ldarg.0
0x1f3eb  ldnull
0x1f3ec  stfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentResourceStream
0x1f3f1  ldarg.0
0x1f3f2  ldnull
0x1f3f3  stfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentResourceXmlWriter
0x1f3f8  ldarg.0
0x1f3f9  ldnull
0x1f3fa  stfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPageContentStream
0x1f3ff  ldarg.0
0x1f400  ldnull
0x1f401  stfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPageContentXmlWriter
0x1f406  ldarg.0
0x1f407  ldnull
0x1f408  stfld    class [System]System.Uri System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageUri
0x1f40d  ldarg.0
0x1f40e  ldnull
0x1f40f  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageLinkTargetStream
0x1f414  ret
0x1f415  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x1f41a  call     string System.Windows.Xps.SR::Get(string id)
0x1f41f  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x1f424  throw
0x1f425  ret
```
