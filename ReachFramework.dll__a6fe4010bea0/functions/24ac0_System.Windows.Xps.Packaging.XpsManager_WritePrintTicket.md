# System.Windows.Xps.Packaging.XpsManager::WritePrintTicket

- ea: `0x24ac0`
- end: `0x24b53`
- name: `System.Windows.Xps.Packaging.XpsManager::WritePrintTicket`
- size: `147`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x20d50`
- `0x21850`
- `0x22a00`

## callees

- `0x1d0f0`
- `0x20070`
- `0x20220`
- `0x248d0`
- `0x24ac0`
- `0x25170`
- `0x25950`

## pseudocode

```c

```

## disassembly

```asm
0x24ac0  ldarg.1
0x24ac1  brtrue.s loc_24ACE
0x24ac3  ldstr    aRelatedpart// "relatedPart"
0x24ac8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24acd  throw
0x24ace  ldarg.2
0x24acf  brtrue.s loc_24ADC
0x24ad1  ldstr    aMetropart// "metroPart"
0x24ad6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24adb  throw
0x24adc  ldarg.3
0x24add  brtrue.s loc_24AEA
0x24adf  ldstr    aPrintticket_0// "printTicket"
0x24ae4  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24ae9  throw
0x24aea  ldarg.0
0x24aeb  ldarg.1
0x24aec  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsManager::GeneratePrintTicketUri(object relatedPart)
0x24af1  stloc.0
0x24af2  ldarg.0
0x24af3  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_PrintTicketContentType()
0x24af8  ldloc.0
0x24af9  call     instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GeneratePart(class [WindowsBase]MS.Internal.ContentType contentType, class [System]System.Uri partUri)
0x24afe  stloc.1
0x24aff  ldarg.2
0x24b00  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x24b05  ldloc.1
0x24b06  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x24b0b  call     string System.Windows.Xps.Packaging.XpsManager::MakeRelativePath(class [System]System.Uri baseUri, class [System]System.Uri fileUri)
0x24b10  stloc.2
0x24b11  ldarg.2
0x24b12  ldloc.2
0x24b13  ldc.i4.2
0x24b14  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x24b19  ldc.i4.0
0x24b1a  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_PrintTicketRelationshipName()
0x24b1f  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string)
0x24b24  pop
0x24b25  ldarg.0
0x24b26  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24b2b  callvirt instance valuetype [mscorlib]System.IO.FileAccess [WindowsBase]System.IO.Packaging.Package::get_FileOpenAccess()
0x24b30  ldc.i4.2
0x24b31  bne.un.s loc_24B3D
0x24b33  ldloc.1
0x24b34  ldc.i4.2
0x24b35  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream(valuetype [mscorlib]System.IO.FileMode)
0x24b3a  stloc.3
0x24b3b  br.s     loc_24B45
0x24b3d  ldloc.1
0x24b3e  ldc.i4.4
0x24b3f  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream(valuetype [mscorlib]System.IO.FileMode)
0x24b44  stloc.3
0x24b45  ldarg.3
0x24b46  ldloc.3
0x24b47  callvirt instance void System.Printing.PrintTicket::SaveTo(class [mscorlib]System.IO.Stream outStream)
0x24b4c  ldloc.3
0x24b4d  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x24b52  ret
```
