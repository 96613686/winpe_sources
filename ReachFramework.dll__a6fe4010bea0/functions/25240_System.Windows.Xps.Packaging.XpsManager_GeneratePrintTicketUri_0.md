# System.Windows.Xps.Packaging.XpsManager::GeneratePrintTicketUri_0

- ea: `0x25240`
- end: `0x25339`
- name: `System.Windows.Xps.Packaging.XpsManager::GeneratePrintTicketUri_0`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1fac0`

## callees

- `0x20000`
- `0x20010`
- `0x20020`
- `0x25240`
- `0x255a0`

## string_xrefs

- `0x25261`: `/MetaData/Job_PT.xml`
- `0x252a0`: `/Document_PT.xml`
- `0x25320`: `_PT.xml`

## pseudocode

```c

```

## disassembly

```asm
0x25240  ldarg.1
0x25241  brtrue.s loc_2524E
0x25243  ldstr    aContenttype// "contentType"
0x25248  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2524d  throw
0x2524e  ldstr    asc_41B18// ""
0x25253  stloc.0
0x25254  ldarg.1
0x25255  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_DocumentSequenceContentType()
0x2525a  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x2525f  brfalse.s loc_2526C
0x25261  ldstr    aMetadataJobPtX// "/MetaData/Job_PT.xml"
0x25266  stloc.0
0x25267  br       loc_2532C
0x2526c  ldarg.1
0x2526d  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedDocumentContentType()
0x25272  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x25277  brfalse.s loc_252AD
0x25279  ldarg.0
0x2527a  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedDocumentContentType()
0x2527f  call     instance string System.Windows.Xps.Packaging.XpsManager::GetContentCounterKey(class [WindowsBase]MS.Internal.ContentType contentType)
0x25284  stloc.1
0x25285  ldarg.0
0x25286  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Windows.Xps.Packaging.XpsManager::_contentTypes
0x2528b  ldloc.1
0x2528c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x25291  ldc.i4.1
0x25292  sub
0x25293  stloc.2
0x25294  ldstr    aDocuments// "/Documents/"
0x25299  ldloca.s 2
0x2529b  call     instance string [mscorlib]System.Int32::ToString()
0x252a0  ldstr    aDocumentPtXml// "/Document_PT.xml"
0x252a5  call     string [mscorlib]System.String::Concat(string, string, string)
0x252aa  stloc.0
0x252ab  br.s     loc_2532C
0x252ad  ldarg.1
0x252ae  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedPageContentType()
0x252b3  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x252b8  brfalse.s loc_2532C
0x252ba  ldarg.0
0x252bb  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedDocumentContentType()
0x252c0  call     instance string System.Windows.Xps.Packaging.XpsManager::GetContentCounterKey(class [WindowsBase]MS.Internal.ContentType contentType)
0x252c5  stloc.3
0x252c6  ldarg.0
0x252c7  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FixedPageContentType()
0x252cc  call     instance string System.Windows.Xps.Packaging.XpsManager::GetContentCounterKey(class [WindowsBase]MS.Internal.ContentType contentType)
0x252d1  stloc.s  4
0x252d3  ldarg.0
0x252d4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Windows.Xps.Packaging.XpsManager::_contentTypes
0x252d9  ldloc.3
0x252da  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x252df  ldc.i4.1
0x252e0  sub
0x252e1  stloc.s  5
0x252e3  ldarg.0
0x252e4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> System.Windows.Xps.Packaging.XpsManager::_contentTypes
0x252e9  ldloc.s  4
0x252eb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x252f0  ldc.i4.1
0x252f1  sub
0x252f2  stloc.s  6
0x252f4  ldc.i4.5
0x252f5  newarr   [mscorlib]System.String
0x252fa  dup
0x252fb  ldc.i4.0
0x252fc  ldstr    aDocuments// "/Documents/"
0x25301  stelem.ref
0x25302  dup
0x25303  ldc.i4.1
0x25304  ldloca.s 5
0x25306  call     instance string [mscorlib]System.Int32::ToString()
0x2530b  stelem.ref
0x2530c  dup
0x2530d  ldc.i4.2
0x2530e  ldstr    aPage// "/Page"
0x25313  stelem.ref
0x25314  dup
0x25315  ldc.i4.3
0x25316  ldloca.s 6
0x25318  call     instance string [mscorlib]System.Int32::ToString()
0x2531d  stelem.ref
0x2531e  dup
0x2531f  ldc.i4.4
0x25320  ldstr    aPtXml// "_PT.xml"
0x25325  stelem.ref
0x25326  call     string [mscorlib]System.String::Concat(string[])
0x2532b  stloc.0
0x2532c  ldloc.0
0x2532d  ldc.i4.2
0x2532e  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x25333  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::CreatePartUri(class [System]System.Uri)
0x25338  ret
```
