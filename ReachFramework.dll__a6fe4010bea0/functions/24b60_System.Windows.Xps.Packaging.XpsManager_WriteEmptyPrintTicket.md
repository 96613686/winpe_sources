# System.Windows.Xps.Packaging.XpsManager::WriteEmptyPrintTicket

- ea: `0x24b60`
- end: `0x24bdd`
- name: `System.Windows.Xps.Packaging.XpsManager::WriteEmptyPrintTicket`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x20d50`
- `0x21850`
- `0x22a00`

## callees

- `0x1d080`
- `0x1d0f0`
- `0x20070`
- `0x20220`
- `0x248c0`
- `0x248d0`
- `0x24b60`
- `0x25170`
- `0x25950`

## pseudocode

```c

```

## disassembly

```asm
0x24b60  ldarg.1
0x24b61  brtrue.s loc_24B6E
0x24b63  ldstr    aRelatedpart// "relatedPart"
0x24b68  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24b6d  throw
0x24b6e  ldarg.2
0x24b6f  brtrue.s loc_24B7C
0x24b71  ldstr    aMetropart// "metroPart"
0x24b76  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24b7b  throw
0x24b7c  ldarg.0
0x24b7d  call     instance bool System.Windows.Xps.Packaging.XpsManager::get_Streaming()
0x24b82  brfalse.s loc_24BDC
0x24b84  ldarg.0
0x24b85  ldarg.1
0x24b86  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsManager::GeneratePrintTicketUri(object relatedPart)
0x24b8b  stloc.0
0x24b8c  ldarg.0
0x24b8d  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_PrintTicketContentType()
0x24b92  ldloc.0
0x24b93  call     instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GeneratePart(class [WindowsBase]MS.Internal.ContentType contentType, class [System]System.Uri partUri)
0x24b98  stloc.1
0x24b99  ldarg.2
0x24b9a  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x24b9f  ldloc.1
0x24ba0  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x24ba5  call     string System.Windows.Xps.Packaging.XpsManager::MakeRelativePath(class [System]System.Uri baseUri, class [System]System.Uri fileUri)
0x24baa  stloc.2
0x24bab  ldarg.2
0x24bac  ldloc.2
0x24bad  ldc.i4.2
0x24bae  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x24bb3  ldc.i4.0
0x24bb4  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_PrintTicketRelationshipName()
0x24bb9  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string)
0x24bbe  pop
0x24bbf  ldloc.1
0x24bc0  ldc.i4.2
0x24bc1  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream(valuetype [mscorlib]System.IO.FileMode)
0x24bc6  stloc.3
0x24bc7  newobj   instance void System.Printing.PrintTicket::.ctor()
0x24bcc  stloc.s  4
0x24bce  ldloc.s  4
0x24bd0  ldloc.3
0x24bd1  callvirt instance void System.Printing.PrintTicket::SaveTo(class [mscorlib]System.IO.Stream outStream)
0x24bd6  ldloc.3
0x24bd7  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x24bdc  ret
```
