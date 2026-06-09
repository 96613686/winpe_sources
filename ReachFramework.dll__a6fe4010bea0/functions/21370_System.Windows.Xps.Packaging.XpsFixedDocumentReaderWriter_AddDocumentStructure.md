# System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::AddDocumentStructure

- ea: `0x21370`
- end: `0x213f0`
- name: `System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::AddDocumentStructure`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1ee90`
- `0x1ef70`
- `0x20030`
- `0x201e0`
- `0x21290`
- `0x21370`
- `0x248d0`
- `0x25060`
- `0x25950`
- `0x25a70`
- `0x25aa0`
- `0x267b0`

## pseudocode

```c

```

## disassembly

```asm
0x21370  ldarg.0
0x21371  call     instance class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::get_DocumentStructure()
0x21376  brfalse.s loc_21388
0x21378  ldstr    aReachpackaging_6// "ReachPackaging_MoreThanOneDocStructure"
0x2137d  call     string System.Windows.Xps.SR::Get(string id)
0x21382  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x21387  throw
0x21388  ldarg.0
0x21389  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x2138e  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsManager::CreateStructureUri()
0x21393  stloc.0
0x21394  ldarg.0
0x21395  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x2139a  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_DocumentStructureContentType()
0x2139f  ldloc.0
0x213a0  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GeneratePart(class [WindowsBase]MS.Internal.ContentType contentType, class [System]System.Uri partUri)
0x213a5  stloc.1
0x213a6  ldarg.0
0x213a7  ldarg.0
0x213a8  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x213ad  ldarg.0
0x213ae  ldloc.1
0x213af  newobj   instance void System.Windows.Xps.Packaging.XpsStructure::.ctor(class System.Windows.Xps.Packaging.XpsManager xpsManager, class System.Windows.Xps.Packaging.INode parent, class [WindowsBase]System.IO.Packaging.PackagePart part)
0x213b4  stfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_documentStructure
0x213b9  ldarg.0
0x213ba  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x213bf  ldarg.0
0x213c0  ldfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_documentStructure
0x213c5  callvirt instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x213ca  call     string System.Windows.Xps.Packaging.XpsManager::MakeRelativePath(class [System]System.Uri baseUri, class [System]System.Uri fileUri)
0x213cf  stloc.2
0x213d0  ldarg.0
0x213d1  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_metroPart
0x213d6  ldloc.2
0x213d7  ldc.i4.2
0x213d8  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x213dd  ldc.i4.0
0x213de  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_StructureRelationshipName()
0x213e3  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string)
0x213e8  pop
0x213e9  ldarg.0
0x213ea  ldfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_documentStructure
0x213ef  ret
```
