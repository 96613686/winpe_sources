# System.Windows.Xps.Serialization.ReachTreeWalker::SerializeHyperlink

- ea: `0x355e0`
- end: `0x35723`
- name: `System.Windows.Xps.Serialization.ReachTreeWalker::SerializeHyperlink`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x35440`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x26840`
- `0x2ea30`
- `0x2ea40`
- `0x30630`
- `0x355c0`
- `0x355e0`
- `0x35730`
- `0x35750`
- `0x35780`
- `0x357a0`
- `0x39670`

## string_xrefs

- `0x356ac`: `FixedPage.NavigateUri`
- `0x356bc`: `FixedPage.NavigateUri`

## pseudocode

```c

```

## disassembly

```asm
0x355e0  ldstr    aPath_0// "Path"
0x355e5  stloc.0
0x355e6  ldarg.0
0x355e7  call     instance class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.ReachTreeWalker::get_LinkXmlWriter()
0x355ec  stloc.1
0x355ed  ldc.i4.0
0x355ee  stloc.2
0x355ef  ldarg.2
0x355f0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x355f5  brtrue.s loc_355FF
0x355f7  ldarg.0
0x355f8  ldarg.2
0x355f9  call     instance bool System.Windows.Xps.Serialization.ReachTreeWalker::AddLinkTarget(string name)
0x355fe  stloc.2
0x355ff  ldloc.2
0x35600  brtrue.s loc_3560C
0x35602  ldarg.3
0x35603  ldnull
0x35604  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x35609  brfalse.s loc_3560C
0x3560b  ret
0x3560c  ldloc.1
0x3560d  ldloc.0
0x3560e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x35613  ldarg.3
0x35614  ldnull
0x35615  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x3561a  brfalse  loc_356DA
0x3561f  ldarg.0
0x35620  ldarg.3
0x35621  call     instance bool System.Windows.Xps.Serialization.ReachTreeWalker::IsFragment(class [System]System.Uri uri)
0x35626  brfalse  loc_356BA
0x3562b  ldarg.0
0x3562c  call     instance class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.ReachTreeWalker::get_SerializationManager()
0x35631  callvirt instance class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.PackageSerializationManager::get_PackagingPolicy()
0x35636  isinst   System.Windows.Xps.Serialization.XpsPackagingPolicy
0x3563b  stloc.s  4
0x3563d  ldarg.0
0x3563e  call     instance class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.ReachTreeWalker::get_SerializationManager()
0x35643  callvirt instance class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.PackageSerializationManager::get_PackagingPolicy()
0x35648  isinst   System.Windows.Xps.Packaging.XpsOMPackagingPolicy
0x3564d  stloc.s  5
0x3564f  ldloc.s  4
0x35651  brtrue.s loc_35667
0x35653  ldloc.s  5
0x35655  brtrue.s loc_35667
0x35657  ldstr    aReachserializa_19// "ReachSerialization_WrongPackagingPolicy"
0x3565c  call     string System.Windows.Xps.SR::Get(string id)
0x35661  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x35666  throw
0x35667  ldarg.0
0x35668  call     instance class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.ReachTreeWalker::get_SerializationManager()
0x3566d  callvirt instance class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.PackageSerializationManager::get_PackagingPolicy()
0x35672  callvirt instance class [System]System.Uri System.Windows.Xps.Serialization.BasePackagingPolicy::get_CurrentFixedDocumentUri()
0x35677  stloc.s  6
0x35679  ldarg.0
0x3567a  call     instance class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.ReachTreeWalker::get_SerializationManager()
0x3567f  callvirt instance class System.Windows.Xps.Serialization.BasePackagingPolicy System.Windows.Xps.Serialization.PackageSerializationManager::get_PackagingPolicy()
0x35684  callvirt instance class [System]System.Uri System.Windows.Xps.Serialization.BasePackagingPolicy::get_CurrentFixedPageUri()
0x35689  stloc.s  7
0x3568b  ldloc.s  7
0x3568d  ldloc.s  6
0x3568f  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::GetRelativeUri(class [System]System.Uri, class [System]System.Uri)
0x35694  stloc.s  8
0x35696  ldloc.s  8
0x35698  callvirt instance string [System]System.Uri::get_OriginalString()
0x3569d  ldarg.3
0x3569e  callvirt instance string [System]System.Uri::get_OriginalString()
0x356a3  call     string [mscorlib]System.String::Concat(string, string)
0x356a8  stloc.s  9
0x356aa  ldarg.0
0x356ab  ldloc.1
0x356ac  ldstr    aFixedpageNavig// "FixedPage.NavigateUri"
0x356b1  ldloc.s  9
0x356b3  call     instance void System.Windows.Xps.Serialization.ReachTreeWalker::WriteAttribute(class [System.Xml]System.Xml.XmlWriter writer, string name, object value)
0x356b8  br.s     loc_356C7
0x356ba  ldarg.0
0x356bb  ldloc.1
0x356bc  ldstr    aFixedpageNavig// "FixedPage.NavigateUri"
0x356c1  ldarg.3
0x356c2  call     instance void System.Windows.Xps.Serialization.ReachTreeWalker::WriteAttribute(class [System.Xml]System.Xml.XmlWriter writer, string name, object value)
0x356c7  ldarg.0
0x356c8  ldloc.1
0x356c9  ldstr    aFill// "Fill"
0x356ce  ldstr    a00000000// "#00000000"
0x356d3  call     instance void System.Windows.Xps.Serialization.ReachTreeWalker::WriteAttribute(class [System.Xml]System.Xml.XmlWriter writer, string name, object value)
0x356d8  br.s     loc_356EB
0x356da  ldarg.0
0x356db  ldloc.1
0x356dc  ldstr    aOpacity// "Opacity"
0x356e1  ldstr    a0_0// "0"
0x356e6  call     instance void System.Windows.Xps.Serialization.ReachTreeWalker::WriteAttribute(class [System.Xml]System.Xml.XmlWriter writer, string name, object value)
0x356eb  ldloc.2
0x356ec  brfalse.s loc_356FB
0x356ee  ldarg.0
0x356ef  ldloc.1
0x356f0  ldstr    aName_0// "Name"
0x356f5  ldarg.2
0x356f6  call     instance void System.Windows.Xps.Serialization.ReachTreeWalker::WriteAttribute(class [System.Xml]System.Xml.XmlWriter writer, string name, object value)
0x356fb  ldarg.1
0x356fc  ldc.i4.1
0x356fd  callvirt instance void [PresentationCore]System.Windows.Media.PathGeometry::set_FillRule(valuetype [PresentationCore]System.Windows.Media.FillRule)
0x35702  ldarg.0
0x35703  ldfld    class System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.Serialization.ReachTreeWalker::_serializationManager
0x35708  castclass System.Windows.Xps.Serialization.IXpsSerializationManager
0x3570d  callvirt instance valuetype [WindowsBase]System.Windows.Size System.Windows.Xps.Serialization.IXpsSerializationManager::get_FixedPageSize()
0x35712  stloc.3
0x35713  ldloc.1
0x35714  ldarg.1
0x35715  ldloc.3
0x35716  call     bool System.Windows.Xps.Serialization.VisualTreeFlattener::WritePath(class [System.Xml]System.Xml.XmlWriter bodyWriter, class [PresentationCore]System.Windows.Media.Geometry geometry, valuetype [WindowsBase]System.Windows.Size pageSize)
0x3571b  pop
0x3571c  ldloc.1
0x3571d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x35722  ret
```
