# System.Windows.Xps.Packaging.XpsOMPackagingPolicy::AddCurrentPageToPackageWriter

- ea: `0x1fb70`
- end: `0x1fc87`
- name: `System.Windows.Xps.Packaging.XpsOMPackagingPolicy::AddCurrentPageToPackageWriter`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1f370`

## callees

- `0xd660`
- `0x1bc20`
- `0x1d080`
- `0x1fa20`
- `0x1fa50`
- `0x1fac0`
- `0x1fb70`
- `0x1fc90`
- `0x20020`
- `0x3d490`
- `0x3d6e0`
- `0x3dad0`
- `0x3db00`

## pseudocode

```c

```

## disassembly

```asm
0x1fb70  ldarg.0
0x1fb71  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageXmlWriter
0x1fb76  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1fb7b  ldarg.0
0x1fb7c  ldfld    class [System.Printing]MS.Internal.PrintWin32Thunk.XpsPrintStream System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPagePrintStream
0x1fb81  callvirt instance class [mscorlib]System.Runtime.InteropServices.ComTypes.IStream [System.Printing]MS.Internal.PrintWin32Thunk.XpsPrintStream::GetManagedIStream()
0x1fb86  stloc.0
0x1fb87  ldarg.0
0x1fb88  ldarg.0
0x1fb89  ldfld    class [System]System.Uri System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageUri
0x1fb8e  call     instance class System.Windows.Xps.Serialization.RCW.IOpcPartUri System.Windows.Xps.Packaging.XpsOMPackagingPolicy::GenerateIOpcPartUri(class [System]System.Uri uri)
0x1fb93  stloc.1
0x1fb94  ldarg.0
0x1fb95  ldfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPagePrintTicket
0x1fb9a  brtrue.s loc_1FBA7
0x1fb9c  ldarg.0
0x1fb9d  newobj   instance void System.Printing.PrintTicket::.ctor()
0x1fba2  stfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPagePrintTicket
0x1fba7  ldarg.0
0x1fba8  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedPageContentType()
0x1fbad  ldarg.0
0x1fbae  ldfld    class System.Printing.PrintTicket System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPagePrintTicket
0x1fbb3  call     instance class System.Windows.Xps.Serialization.RCW.IXpsOMPrintTicketResource System.Windows.Xps.Packaging.XpsOMPackagingPolicy::GeneratePrintTicketResource(class [WindowsBase]MS.Internal.ContentType contentType, class System.Printing.PrintTicket printTicket)
0x1fbb8  stloc.2
0x1fbb9  ldarg.0
0x1fbba  ldfld    class [System.Printing]MS.Internal.PrintWin32Thunk.XpsPrintStream System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPagePrintStream
0x1fbbf  ldc.i4.0
0x1fbc0  conv.i8
0x1fbc1  ldc.i4.0
0x1fbc2  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x1fbc7  pop
0x1fbc8  ldarg.0
0x1fbc9  ldarg.0
0x1fbca  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMObjectFactory System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_xpsOMFactory
0x1fbcf  ldloc.0
0x1fbd0  ldloc.1
0x1fbd1  ldarg.0
0x1fbd2  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPartResources System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_xpsPartResources
0x1fbd7  ldc.i4.0
0x1fbd8  callvirt instance class System.Windows.Xps.Serialization.RCW.IXpsOMPage System.Windows.Xps.Serialization.RCW.IXpsOMObjectFactory::CreatePageFromStream([hasfieldmarshal] class [mscorlib]System.Runtime.InteropServices.ComTypes.IStream, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IOpcPartUri pageMarkupStream, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMPartResources partUri, [in] [hasfieldmarshal] int32 resources)
0x1fbdd  stfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPage System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageWriter
0x1fbe2  ldarg.0
0x1fbe3  call     instance void System.Windows.Xps.Packaging.XpsOMPackagingPolicy::SetHyperlinkTargetsForCurrentPage()
0x1fbe8  ldloca.s 4
0x1fbea  initobj  System.Windows.Xps.Serialization.RCW.XPS_SIZE
0x1fbf0  ldloca.s 4
0x1fbf2  ldarg.0
0x1fbf3  ldflda   valuetype [WindowsBase]System.Windows.Size System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPageSize
0x1fbf8  call     instance float64 [WindowsBase]System.Windows.Size::get_Width()
0x1fbfd  conv.r4
0x1fbfe  stfld    float32 System.Windows.Xps.Serialization.RCW.XPS_SIZE::width
0x1fc03  ldloca.s 4
0x1fc05  ldarg.0
0x1fc06  ldflda   valuetype [WindowsBase]System.Windows.Size System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentPageSize
0x1fc0b  call     instance float64 [WindowsBase]System.Windows.Size::get_Height()
0x1fc10  conv.r4
0x1fc11  stfld    float32 System.Windows.Xps.Serialization.RCW.XPS_SIZE::height
0x1fc16  ldloc.s  4
0x1fc18  stloc.3
0x1fc19  call     bool MS.Internal.ReachAppContextSwitches::get_ReleaseDiscardableFontResources()
0x1fc1e  brtrue.s loc_1FC3C
0x1fc20  ldarg.0
0x1fc21  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPackageWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedDocumentSequenceWriter
0x1fc26  ldarg.0
0x1fc27  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPage System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageWriter
0x1fc2c  ldloc.3
0x1fc2d  stloc.s  4
0x1fc2f  ldloca.s 4
0x1fc31  ldnull
0x1fc32  ldnull
0x1fc33  ldloc.2
0x1fc34  ldnull
0x1fc35  callvirt instance void System.Windows.Xps.Serialization.RCW.IXpsOMPackageWriter::AddPage([in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMPage page, [in] valuetype System.Windows.Xps.Serialization.RCW.XPS_SIZE& advisoryPageDimensions, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMPartUriCollection discardableResourceParts, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMStoryFragmentsResource storyFragments, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMPrintTicketResource pagePrintTicket, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMImageResource pageThumbnail)
0x1fc3a  br.s     loc_1FC77
0x1fc3c  ldarg.0
0x1fc3d  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPackageWriter System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedDocumentSequenceWriter
0x1fc42  ldarg.0
0x1fc43  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPage System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_currentFixedPageWriter
0x1fc48  ldloc.3
0x1fc49  stloc.s  4
0x1fc4b  ldloca.s 4
0x1fc4d  ldarg.0
0x1fc4e  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPartUriCollection System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_discardableResourceParts
0x1fc53  ldnull
0x1fc54  ldloc.2
0x1fc55  ldnull
0x1fc56  callvirt instance void System.Windows.Xps.Serialization.RCW.IXpsOMPackageWriter::AddPage([in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMPage page, [in] valuetype System.Windows.Xps.Serialization.RCW.XPS_SIZE& advisoryPageDimensions, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMPartUriCollection discardableResourceParts, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMStoryFragmentsResource storyFragments, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMPrintTicketResource pagePrintTicket, [in] [hasfieldmarshal] class System.Windows.Xps.Serialization.RCW.IXpsOMImageResource pageThumbnail)
0x1fc5b  br.s     loc_1FC69
0x1fc5d  ldarg.0
0x1fc5e  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPartUriCollection System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_discardableResourceParts
0x1fc63  ldc.i4.0
0x1fc64  callvirt instance void System.Windows.Xps.Serialization.RCW.IXpsOMPartUriCollection::RemoveAt([in] unsigned int32 index)
0x1fc69  ldarg.0
0x1fc6a  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMPartUriCollection System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_discardableResourceParts
0x1fc6f  callvirt instance unsigned int32 System.Windows.Xps.Serialization.RCW.IXpsOMPartUriCollection::GetCount()
0x1fc74  ldc.i4.0
0x1fc75  bgt.un.s loc_1FC5D
0x1fc77  leave.s  loc_1FC86
0x1fc79  pop
0x1fc7a  ldarg.0
0x1fc7b  call     instance void System.Windows.Xps.Packaging.XpsOMPackagingPolicy::Invalidate()
0x1fc80  newobj   instance void System.Printing.PrintingCanceledException::.ctor()
0x1fc85  throw
0x1fc86  ret
```
