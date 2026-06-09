# System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::EnsureDoucmentStructure

- ea: `0x21a40`
- end: `0x21ae6`
- name: `System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::EnsureDoucmentStructure`
- size: `166`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x21290`
- `0x216a0`
- `0x21730`

## callees

- `0x1ef70`
- `0x201e0`
- `0x21a40`
- `0x248b0`
- `0x25aa0`
- `0x267b0`

## pseudocode

```c

```

## disassembly

```asm
0x21a40  ldarg.0
0x21a41  ldfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_documentStructure
0x21a46  brfalse.s loc_21A49
0x21a48  ret
0x21a49  ldnull
0x21a4a  stloc.0
0x21a4b  ldnull
0x21a4c  stloc.1
0x21a4d  ldarg.0
0x21a4e  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_metroPart
0x21a53  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_StructureRelationshipName()
0x21a58  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.PackagePart::GetRelationshipsByType(string)
0x21a5d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0x21a62  stloc.2
0x21a63  br.s     loc_21A81
0x21a65  ldloc.2
0x21a66  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0x21a6b  stloc.3
0x21a6c  ldloc.0
0x21a6d  brfalse.s loc_21A7F
0x21a6f  ldstr    aReachpackaging_6// "ReachPackaging_MoreThanOneDocStructure"
0x21a74  call     string System.Windows.Xps.SR::Get(string id)
0x21a79  newobj   instance void [System]System.IO.InvalidDataException::.ctor(string)
0x21a7e  throw
0x21a7f  ldloc.3
0x21a80  stloc.0
0x21a81  ldloc.2
0x21a82  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x21a87  brtrue.s loc_21A65
0x21a89  leave.s  loc_21A95
0x21a8b  ldloc.2
0x21a8c  brfalse.s loc_21A94
0x21a8e  ldloc.2
0x21a8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21a94  endfinally
0x21a95  ldloc.0
0x21a96  brfalse.s loc_21AE5
0x21a98  ldloc.0
0x21a99  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_SourceUri()
0x21a9e  ldloc.0
0x21a9f  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0x21aa4  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0x21aa9  stloc.s  4
0x21aab  ldarg.0
0x21aac  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x21ab1  callvirt instance class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::get_MetroPackage()
0x21ab6  ldloc.s  4
0x21ab8  callvirt instance bool [WindowsBase]System.IO.Packaging.Package::PartExists(class [System]System.Uri)
0x21abd  brfalse.s loc_21AE5
0x21abf  ldarg.0
0x21ac0  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x21ac5  callvirt instance class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::get_MetroPackage()
0x21aca  ldloc.s  4
0x21acc  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0x21ad1  stloc.1
0x21ad2  ldarg.0
0x21ad3  ldarg.0
0x21ad4  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x21ad9  ldarg.0
0x21ada  ldloc.1
0x21adb  newobj   instance void System.Windows.Xps.Packaging.XpsStructure::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x21ae0  stfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_documentStructure
0x21ae5  ret
```
