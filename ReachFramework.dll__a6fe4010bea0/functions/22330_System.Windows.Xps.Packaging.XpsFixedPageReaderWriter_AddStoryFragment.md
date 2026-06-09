# System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddStoryFragment

- ea: `0x22330`
- end: `0x223b6`
- name: `System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::AddStoryFragment`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x1ee90`
- `0x1ef70`
- `0x20040`
- `0x201f0`
- `0x220d0`
- `0x22180`
- `0x22330`
- `0x248d0`
- `0x250b0`
- `0x25950`
- `0x25a70`
- `0x25aa0`
- `0x267b0`

## pseudocode

```c

```

## disassembly

```asm
0x22330  ldarg.0
0x22331  call     instance class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::get_StoryFragment()
0x22336  brfalse.s loc_22348
0x22338  ldstr    aReachpackaging_8// "ReachPackaging_MoreThanOneStoryFragment"
0x2233d  call     string System.Windows.Xps.SR::Get(string id)
0x22342  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x22347  throw
0x22348  ldarg.0
0x22349  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x2234e  ldarg.0
0x2234f  call     instance int32 System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::get_PageNumber()
0x22354  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsManager::CreateFragmentUri(int32 pageNumber)
0x22359  stloc.0
0x2235a  ldarg.0
0x2235b  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22360  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_StoryFragmentsContentType()
0x22365  ldloc.0
0x22366  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GeneratePart(class [WindowsBase]MS.Internal.ContentType contentType, class [System]System.Uri partUri)
0x2236b  stloc.1
0x2236c  ldarg.0
0x2236d  ldarg.0
0x2236e  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x22373  ldarg.0
0x22374  ldloc.1
0x22375  newobj   instance void System.Windows.Xps.Packaging.XpsStructure::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x2237a  stfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_storyFragment
0x2237f  ldarg.0
0x22380  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x22385  ldarg.0
0x22386  ldfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_storyFragment
0x2238b  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x22390  call     string System.Windows.Xps.Packaging.XpsManager::MakeRelativePath(class [System]System.Uri baseUri, class [System]System.Uri fileUri)
0x22395  stloc.2
0x22396  ldarg.0
0x22397  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_metroPart
0x2239c  ldloc.2
0x2239d  ldc.i4.2
0x2239e  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x223a3  ldc.i4.0
0x223a4  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_StoryFragmentsRelationshipName()
0x223a9  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string)
0x223ae  pop
0x223af  ldarg.0
0x223b0  ldfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::_storyFragment
0x223b5  ret
```
