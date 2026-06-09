# System.Windows.Xps.Packaging.XpsManager::GetPrintTicketPart

- ea: `0x24df0`
- end: `0x24e81`
- name: `System.Windows.Xps.Packaging.XpsManager::GetPrintTicketPart`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x24a10`

## callees

- `0x1ef70`
- `0x20220`
- `0x24df0`

## string_xrefs

- `0x24e02`: `ReachPackaging_InvalidDocUri`

## pseudocode

```c

```

## disassembly

```asm
0x24df0  ldarg.0
0x24df1  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24df6  ldarg.1
0x24df7  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0x24dfc  stloc.0
0x24dfd  ldnull
0x24dfe  stloc.1
0x24dff  ldloc.0
0x24e00  brtrue.s loc_24E12
0x24e02  ldstr    aReachpackaging_19// "ReachPackaging_InvalidDocUri"
0x24e07  call     string System.Windows.Xps.SR::Get(string id)
0x24e0c  newobj   instance void [System]System.IO.InvalidDataException::.ctor(string)
0x24e11  throw
0x24e12  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_PrintTicketRelationshipName()
0x24e17  stloc.2
0x24e18  ldnull
0x24e19  stloc.3
0x24e1a  ldloc.0
0x24e1b  ldloc.2
0x24e1c  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.PackagePart::GetRelationshipsByType(string)
0x24e21  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0x24e26  stloc.s  4
0x24e28  br.s     loc_24E49
0x24e2a  ldloc.s  4
0x24e2c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0x24e31  stloc.s  5
0x24e33  ldloc.3
0x24e34  brfalse.s loc_24E46
0x24e36  ldstr    aReachpackaging_22// "ReachPackaging_MoreThanOnePrintTicketPa"...
0x24e3b  call     string System.Windows.Xps.SR::Get(string id)
0x24e40  newobj   instance void [System]System.IO.InvalidDataException::.ctor(string)
0x24e45  throw
0x24e46  ldloc.s  5
0x24e48  stloc.3
0x24e49  ldloc.s  4
0x24e4b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24e50  brtrue.s loc_24E2A
0x24e52  leave.s  loc_24E60
0x24e54  ldloc.s  4
0x24e56  brfalse.s loc_24E5F
0x24e58  ldloc.s  4
0x24e5a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24e5f  endfinally
0x24e60  ldloc.3
0x24e61  brfalse.s loc_24E7F
0x24e63  ldarg.1
0x24e64  ldloc.3
0x24e65  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0x24e6a  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0x24e6f  stloc.s  6
0x24e71  ldarg.0
0x24e72  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24e77  ldloc.s  6
0x24e79  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0x24e7e  stloc.1
0x24e7f  ldloc.1
0x24e80  ret
```
