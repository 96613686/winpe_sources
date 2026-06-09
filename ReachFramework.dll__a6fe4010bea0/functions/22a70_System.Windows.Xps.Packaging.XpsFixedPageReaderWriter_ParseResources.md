# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::ParseResources

- ea: `0x22a70`
- end: `0x22d00`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::ParseResources`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: ``

## callers

- `0x22a50`

## callees

- `0xd5b0`
- `0x1ef70`
- `0x20040`
- `0x20090`
- `0x200a0`
- `0x200b0`
- `0x20190`
- `0x201f0`
- `0x20210`
- `0x20240`
- `0x22a70`
- `0x23c60`
- `0x23cb0`
- `0x23ce0`
- `0x23d00`
- `0x23d20`
- `0x24570`
- `0x24be0`
- `0x259b0`
- `0x25a70`
- `0x25aa0`
- `0x26400`
- `0x267b0`

## pseudocode

```c

```

## disassembly

```asm
0x22a70  ldarg.0
0x22a71  ldfld    class System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_parentNode
0x22a76  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.INode::GetPart()
0x22a7b  stloc.0
0x22a7c  call     class MS.Internal.UriComparer MS.Internal.UriComparer::get_Default()
0x22a81  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [WindowsBase]System.IO.Packaging.PackageRelationship>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x22a86  stloc.1
0x22a87  ldloc.0
0x22a88  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_RestrictedFontRelationshipType()
0x22a8d  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.PackagePart::GetRelationshipsByType(string)
0x22a92  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0x22a97  stloc.2
0x22a98  br.s     loc_22ABD
0x22a9a  ldloc.2
0x22a9b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0x22aa0  stloc.3
0x22aa1  ldloc.0
0x22aa2  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x22aa7  ldloc.3
0x22aa8  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0x22aad  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0x22ab2  stloc.s  4
0x22ab4  ldloc.1
0x22ab5  ldloc.s  4
0x22ab7  ldloc.3
0x22ab8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [WindowsBase]System.IO.Packaging.PackageRelationship>::set_Item(var<u1>, !!T0)
0x22abd  ldloc.2
0x22abe  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22ac3  brtrue.s loc_22A9A
0x22ac5  leave.s  loc_22AD1
0x22ac7  ldloc.2
0x22ac8  brfalse.s loc_22AD0
0x22aca  ldloc.2
0x22acb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22ad0  endfinally
0x22ad1  ldarg.0
0x22ad2  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x22ad7  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.PackagePart::GetRelationships()
0x22adc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0x22ae1  stloc.s  5
0x22ae3  br       loc_22CE5
0x22ae8  ldloc.s  5
0x22aea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0x22aef  stloc.s  6
0x22af1  ldarg.0
0x22af2  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x22af7  ldloc.s  6
0x22af9  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0x22afe  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0x22b03  stloc.s  7
0x22b05  ldarg.0
0x22b06  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22b0b  ldloc.s  7
0x22b0d  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GetPart(class [System]System.Uri uri)
0x22b12  stloc.s  8
0x22b14  ldloc.s  8
0x22b16  callvirt instance class [WindowsBase]MS.Internal.ContentType [WindowsBase]System.IO.Packaging.PackagePart::get_ValidatedContentType()
0x22b1b  call     bool System.Windows.Xps.Packaging.XpsManager::SupportedImageType(class [WindowsBase]MS.Internal.ContentType imageContentType)
0x22b20  brfalse.s loc_22B59
0x22b22  ldloc.s  6
0x22b24  callvirt instance string [WindowsBase]System.IO.Packaging.PackageRelationship::get_RelationshipType()
0x22b29  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceRelationshipName()
0x22b2e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22b33  brfalse.s loc_22B59
0x22b35  ldarg.0
0x22b36  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22b3b  ldarg.0
0x22b3c  ldloc.s  8
0x22b3e  newobj   instance void System.Windows.Xps.Packaging.XpsImage::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x22b43  stloc.s  9
0x22b45  ldarg.0
0x22b46  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsImage> System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_imageCache
0x22b4b  ldloc.s  7
0x22b4d  ldloc.s  9
0x22b4f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsImage>::set_Item(var<u1>, !!T0)
0x22b54  br       loc_22CE5
0x22b59  ldloc.s  8
0x22b5b  callvirt instance class [WindowsBase]MS.Internal.ContentType [WindowsBase]System.IO.Packaging.PackagePart::get_ValidatedContentType()
0x22b60  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FontContentType()
0x22b65  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x22b6a  brtrue.s loc_22B7F
0x22b6c  ldloc.s  8
0x22b6e  callvirt instance class [WindowsBase]MS.Internal.ContentType [WindowsBase]System.IO.Packaging.PackagePart::get_ValidatedContentType()
0x22b73  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_FontObfuscatedContentType()
0x22b78  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x22b7d  brfalse.s loc_22BCB
0x22b7f  ldloc.s  6
0x22b81  callvirt instance string [WindowsBase]System.IO.Packaging.PackageRelationship::get_RelationshipType()
0x22b86  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceRelationshipName()
0x22b8b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22b90  brfalse.s loc_22BCB
0x22b92  ldarg.0
0x22b93  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22b98  ldarg.0
0x22b99  ldloc.s  8
0x22b9b  newobj   instance void System.Windows.Xps.Packaging.XpsFont::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x22ba0  stloc.s  0xA
0x22ba2  ldarg.0
0x22ba3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsFont> System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_fontCache
0x22ba8  ldloc.s  7
0x22baa  ldloc.s  0xA
0x22bac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsFont>::set_Item(var<u1>, !!T0)
0x22bb1  ldloc.1
0x22bb2  ldloc.s  7
0x22bb4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class [WindowsBase]System.IO.Packaging.PackageRelationship>::ContainsKey(var<u1>)
0x22bb9  brfalse  loc_22CE5
0x22bbe  ldloc.s  0xA
0x22bc0  ldc.i4.1
0x22bc1  callvirt instance void System.Windows.Xps.Packaging.XpsFont::set_IsRestricted(bool value)
0x22bc6  br       loc_22CE5
0x22bcb  ldloc.s  8
0x22bcd  callvirt instance class [WindowsBase]MS.Internal.ContentType [WindowsBase]System.IO.Packaging.PackagePart::get_ValidatedContentType()
0x22bd2  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_ColorContextContentType()
0x22bd7  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x22bdc  brfalse.s loc_22C15
0x22bde  ldloc.s  6
0x22be0  callvirt instance string [WindowsBase]System.IO.Packaging.PackageRelationship::get_RelationshipType()
0x22be5  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceRelationshipName()
0x22bea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22bef  brfalse.s loc_22C15
0x22bf1  ldarg.0
0x22bf2  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22bf7  ldarg.0
0x22bf8  ldloc.s  8
0x22bfa  newobj   instance void System.Windows.Xps.Packaging.XpsColorContext::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x22bff  stloc.s  0xB
0x22c01  ldarg.0
0x22c02  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsColorContext> System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_colorContextCache
0x22c07  ldloc.s  7
0x22c09  ldloc.s  0xB
0x22c0b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsColorContext>::set_Item(var<u1>, !!T0)
0x22c10  br       loc_22CE5
0x22c15  ldloc.s  8
0x22c17  callvirt instance class [WindowsBase]MS.Internal.ContentType [WindowsBase]System.IO.Packaging.PackagePart::get_ValidatedContentType()
0x22c1c  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceDictionaryContentType()
0x22c21  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x22c26  brfalse.s loc_22C5F
0x22c28  ldloc.s  6
0x22c2a  callvirt instance string [WindowsBase]System.IO.Packaging.PackageRelationship::get_RelationshipType()
0x22c2f  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceRelationshipName()
0x22c34  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22c39  brfalse.s loc_22C5F
0x22c3b  ldarg.0
0x22c3c  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22c41  ldarg.0
0x22c42  ldloc.s  8
0x22c44  newobj   instance void System.Windows.Xps.Packaging.XpsResourceDictionary::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x22c49  stloc.s  0xC
0x22c4b  ldarg.0
0x22c4c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsResourceDictionary> System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_resourceDictionaryCache
0x22c51  ldloc.s  7
0x22c53  ldloc.s  0xC
0x22c55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsResourceDictionary>::set_Item(var<u1>, !!T0)
0x22c5a  br       loc_22CE5
0x22c5f  ldloc.s  8
0x22c61  callvirt instance class [WindowsBase]MS.Internal.ContentType [WindowsBase]System.IO.Packaging.PackagePart::get_ValidatedContentType()
0x22c66  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_StoryFragmentsContentType()
0x22c6b  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x22c70  brfalse.s loc_22CB3
0x22c72  ldloc.s  6
0x22c74  callvirt instance string [WindowsBase]System.IO.Packaging.PackageRelationship::get_RelationshipType()
0x22c79  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_StoryFragmentsRelationshipName()
0x22c7e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22c83  brfalse.s loc_22CB3
0x22c85  ldarg.0
0x22c86  ldfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_storyFragment
0x22c8b  brfalse.s loc_22C9D
0x22c8d  ldstr    aReachpackaging_8// "ReachPackaging_MoreThanOneStoryFragment"
0x22c92  call     string System.Windows.Xps.SR::Get(string id)
0x22c97  newobj   instance void [System]System.IO.InvalidDataException::.ctor(string)
0x22c9c  throw
0x22c9d  ldarg.0
0x22c9e  ldarg.0
0x22c9f  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22ca4  ldarg.0
0x22ca5  ldloc.s  8
0x22ca7  newobj   instance void System.Windows.Xps.Packaging.XpsStructure::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x22cac  stfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_storyFragment
0x22cb1  br.s     loc_22CE5
0x22cb3  ldloc.s  6
0x22cb5  callvirt instance string [WindowsBase]System.IO.Packaging.PackageRelationship::get_RelationshipType()
0x22cba  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceRelationshipName()
0x22cbf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22cc4  brfalse.s loc_22CE5
0x22cc6  ldarg.0
0x22cc7  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22ccc  ldarg.0
0x22ccd  ldloc.s  8
0x22ccf  newobj   instance void System.Windows.Xps.Packaging.XpsResource::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x22cd4  stloc.s  0xD
0x22cd6  ldarg.0
0x22cd7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsResource> System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_resourceCache
0x22cdc  ldloc.s  7
0x22cde  ldloc.s  0xD
0x22ce0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class System.Windows.Xps.Packaging.XpsResource>::set_Item(var<u1>, !!T0)
0x22ce5  ldloc.s  5
0x22ce7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22cec  brtrue   loc_22AE8
0x22cf1  leave.s  loc_22CFF
0x22cf3  ldloc.s  5
0x22cf5  brfalse.s loc_22CFE
0x22cf7  ldloc.s  5
0x22cf9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22cfe  endfinally
0x22cff  ret
```
