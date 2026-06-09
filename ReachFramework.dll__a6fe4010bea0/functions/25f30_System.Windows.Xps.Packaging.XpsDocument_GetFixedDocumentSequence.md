# System.Windows.Xps.Packaging.XpsDocument::GetFixedDocumentSequence

- ea: `0x25f30`
- end: `0x2601f`
- name: `System.Windows.Xps.Packaging.XpsDocument::GetFixedDocumentSequence`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1b060`
- `0x1ee90`
- `0x1ef70`
- `0x20000`
- `0x247e0`
- `0x25a70`
- `0x25aa0`
- `0x25bb0`
- `0x25f30`
- `0x26330`

## string_xrefs

- `0x25f56`: `ReachPackaging_NotOpenForReading`
- `0x25f74`: `ReachPackaging_PackageUriNull`

## pseudocode

```c

```

## disassembly

```asm
0x25f30  ldarg.0
0x25f31  call     instance void System.Windows.Xps.Packaging.XpsDocument::CheckDisposed()
0x25f36  ldarg.0
0x25f37  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25f3c  brtrue.s loc_25F4E
0x25f3e  ldstr    aReachpackaging_29// "ReachPackaging_DocumentWasClosed"
0x25f43  call     string System.Windows.Xps.SR::Get(string id)
0x25f48  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x25f4d  throw
0x25f4e  ldarg.0
0x25f4f  call     instance bool System.Windows.Xps.Packaging.XpsDocument::get_IsReader()
0x25f54  brtrue.s loc_25F66
0x25f56  ldstr    aReachpackaging_31// "ReachPackaging_NotOpenForReading"
0x25f5b  call     string System.Windows.Xps.SR::Get(string id)
0x25f60  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x25f65  throw
0x25f66  ldnull
0x25f67  ldarg.0
0x25f68  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x25f6d  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x25f72  brfalse.s loc_25F84
0x25f74  ldstr    aReachpackaging_32// "ReachPackaging_PackageUriNull"
0x25f79  call     string System.Windows.Xps.SR::Get(string id)
0x25f7e  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x25f83  throw
0x25f84  ldarg.0
0x25f85  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25f8a  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::get_StartingPart()
0x25f8f  brtrue.s loc_25F93
0x25f91  ldnull
0x25f92  ret
0x25f93  ldarg.0
0x25f94  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25f99  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::get_StartingPart()
0x25f9e  callvirt instance class [WindowsBase]MS.Internal.ContentType [WindowsBase]System.IO.Packaging.PackagePart::get_ValidatedContentType()
0x25fa3  stloc.0
0x25fa4  ldloc.0
0x25fa5  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_DocumentSequenceContentType()
0x25faa  callvirt instance bool [WindowsBase]MS.Internal.ContentType::AreTypeAndSubTypeEqual(class [WindowsBase]MS.Internal.ContentType)
0x25faf  brtrue.s loc_25FC1
0x25fb1  ldstr    aReachpackaging_33// "ReachPackaging_InvalidStartingPart"
0x25fb6  call     string System.Windows.Xps.SR::Get(string id)
0x25fbb  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x25fc0  throw
0x25fc1  newobj   instance void [PresentationFramework]System.Windows.Markup.ParserContext::.ctor()
0x25fc6  stloc.1
0x25fc7  ldloc.1
0x25fc8  ldarg.0
0x25fc9  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x25fce  ldarg.0
0x25fcf  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25fd4  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::get_StartingPart()
0x25fd9  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x25fde  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::Create(class [System]System.Uri, class [System]System.Uri)
0x25fe3  callvirt instance void [PresentationFramework]System.Windows.Markup.ParserContext::set_BaseUri(class [System]System.Uri)
0x25fe8  ldarg.0
0x25fe9  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x25fee  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::get_StartingPart()
0x25ff3  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream()
0x25ff8  ldloc.1
0x25ff9  ldc.i4.1
0x25ffa  call     object MS.Internal.ReachFramework.Markup.XamlReaderProxy::Load(class [mscorlib]System.IO.Stream stream, class [PresentationFramework]System.Windows.Markup.ParserContext parserContext, bool useRestrictiveXamlReader)
0x25fff  stloc.2
0x26000  ldloc.2
0x26001  isinst   [PresentationFramework]System.Windows.Documents.FixedDocumentSequence
0x26006  brtrue.s loc_26018
0x26008  ldstr    aReachpackaging_34// "ReachPackaging_NotAFixedDocumentSequenc"...
0x2600d  call     string System.Windows.Xps.SR::Get(string id)
0x26012  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x26017  throw
0x26018  ldloc.2
0x26019  isinst   [PresentationFramework]System.Windows.Documents.FixedDocumentSequence
0x2601e  ret
```
