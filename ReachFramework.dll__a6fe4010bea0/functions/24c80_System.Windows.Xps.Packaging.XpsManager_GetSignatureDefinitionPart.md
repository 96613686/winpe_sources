# System.Windows.Xps.Packaging.XpsManager::GetSignatureDefinitionPart

- ea: `0x24c80`
- end: `0x24d16`
- name: `System.Windows.Xps.Packaging.XpsManager::GetSignatureDefinitionPart`
- size: `150`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x21610`
- `0x216a0`
- `0x21a00`
- `0x21b90`
- `0x24c40`

## callees

- `0x1ef70`
- `0x20050`
- `0x20230`
- `0x24c80`

## string_xrefs

- `0x24c92`: `ReachPackaging_InvalidDocUri`

## pseudocode

```c

```

## disassembly

```asm
0x24c80  ldarg.0
0x24c81  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24c86  ldarg.1
0x24c87  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0x24c8c  stloc.0
0x24c8d  ldnull
0x24c8e  stloc.1
0x24c8f  ldloc.0
0x24c90  brtrue.s loc_24CA2
0x24c92  ldstr    aReachpackaging_19// "ReachPackaging_InvalidDocUri"
0x24c97  call     string System.Windows.Xps.SR::Get(string id)
0x24c9c  newobj   instance void [System]System.IO.InvalidDataException::.ctor(string)
0x24ca1  throw
0x24ca2  call     class [WindowsBase]MS.Internal.ContentType System.Windows.Xps.Packaging.XpsS0Markup::get_SignatureDefintionType()
0x24ca7  stloc.2
0x24ca8  ldnull
0x24ca9  stloc.3
0x24caa  ldloc.0
0x24cab  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SignatureDefinitionRelationshipName()
0x24cb0  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationshipCollection [WindowsBase]System.IO.Packaging.PackagePart::GetRelationshipsByType(string)
0x24cb5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship> [WindowsBase]System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0x24cba  stloc.s  4
0x24cbc  br.s     loc_24CDD
0x24cbe  ldloc.s  4
0x24cc0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.IO.Packaging.PackageRelationship>::get_Current()
0x24cc5  stloc.s  5
0x24cc7  ldloc.3
0x24cc8  brfalse.s loc_24CDA
0x24cca  ldstr    aReachpackaging_20// "ReachPackaging_MoreThanOneSigDefParts"
0x24ccf  call     string System.Windows.Xps.SR::Get(string id)
0x24cd4  newobj   instance void [System]System.IO.InvalidDataException::.ctor(string)
0x24cd9  throw
0x24cda  ldloc.s  5
0x24cdc  stloc.3
0x24cdd  ldloc.s  4
0x24cdf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24ce4  brtrue.s loc_24CBE
0x24ce6  leave.s  loc_24CF4
0x24ce8  ldloc.s  4
0x24cea  brfalse.s loc_24CF3
0x24cec  ldloc.s  4
0x24cee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24cf3  endfinally
0x24cf4  ldloc.3
0x24cf5  brfalse.s loc_24D14
0x24cf7  ldarg.0
0x24cf8  ldfld    class [WindowsBase]System.IO.Packaging.Package System.Windows.Xps.Packaging.XpsManager::_metroPackage
0x24cfd  ldloc.3
0x24cfe  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_SourceUri()
0x24d03  ldloc.3
0x24d04  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackageRelationship::get_TargetUri()
0x24d09  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri, class [System]System.Uri)
0x24d0e  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart [WindowsBase]System.IO.Packaging.Package::GetPart(class [System]System.Uri)
0x24d13  stloc.1
0x24d14  ldloc.1
0x24d15  ret
```
