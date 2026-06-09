# System.IO.Packaging.PackageDigitalSignatureManager::RemoveAllSignatures

- ea: `0x4c590`
- end: `0x4c665`
- name: `System.IO.Packaging.PackageDigitalSignatureManager::RemoveAllSignatures`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x1f7c0`
- `0x2c100`
- `0x48cd0`
- `0x49a10`
- `0x49be0`
- `0x4a2f0`
- `0x4a310`
- `0x4a330`
- `0x4a450`
- `0x4a630`
- `0x4ba50`
- `0x4bc90`
- `0x4c590`
- `0x4cb20`
- `0x4cc30`
- `0x4ce10`

## string_xrefs

- `0x4c598`: `CannotRemoveSignatureFromReadOnlyFile`

## pseudocode

```c

```

## disassembly

```asm
0x4c590  ldarg.0
0x4c591  call     instance bool System.IO.Packaging.PackageDigitalSignatureManager::get_ReadOnly()
0x4c596  brfalse.s loc_4C5A8
0x4c598  ldstr    aCannotremovesi// "CannotRemoveSignatureFromReadOnlyFile"
0x4c59d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4c5a2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4c5a7  throw
0x4c5a8  ldarg.0
0x4c5a9  call     instance void System.IO.Packaging.PackageDigitalSignatureManager::EnsureSignatures()
0x4c5ae  ldc.i4.0
0x4c5af  stloc.0
0x4c5b0  br       loc_4C63F
0x4c5b5  ldarg.0
0x4c5b6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c5bb  ldloc.0
0x4c5bc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::get_Item(!!T0)
0x4c5c1  callvirt instance class System.IO.Packaging.PackagePart System.IO.Packaging.PackageDigitalSignature::get_SignaturePart()
0x4c5c6  stloc.1
0x4c5c7  ldloc.1
0x4c5c8  call     string MS.Internal.IO.Packaging.CertificatePart::get_RelationshipType()
0x4c5cd  callvirt instance class System.IO.Packaging.PackageRelationshipCollection System.IO.Packaging.PackagePart::GetRelationshipsByType(string relationshipType)
0x4c5d2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.IO.Packaging.PackageRelationship> System.IO.Packaging.PackageRelationshipCollection::GetEnumerator()
0x4c5d7  stloc.2
0x4c5d8  br.s     loc_4C605
0x4c5da  ldloc.2
0x4c5db  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.IO.Packaging.PackageRelationship>::get_Current()
0x4c5e0  stloc.3
0x4c5e1  ldloc.3
0x4c5e2  callvirt instance valuetype System.IO.Packaging.TargetMode System.IO.Packaging.PackageRelationship::get_TargetMode()
0x4c5e7  brtrue.s loc_4C605
0x4c5e9  ldarg.0
0x4c5ea  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c5ef  ldloc.3
0x4c5f0  callvirt instance class [System]System.Uri System.IO.Packaging.PackageRelationship::get_SourceUri()
0x4c5f5  ldloc.3
0x4c5f6  callvirt instance class [System]System.Uri System.IO.Packaging.PackageRelationship::get_TargetUri()
0x4c5fb  call     class [System]System.Uri System.IO.Packaging.PackUriHelper::ResolvePartUri(class [System]System.Uri sourcePartUri, class [System]System.Uri targetUri)
0x4c600  callvirt instance void System.IO.Packaging.Package::DeletePart(class [System]System.Uri partUri)
0x4c605  ldloc.2
0x4c606  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c60b  brtrue.s loc_4C5DA
0x4c60d  leave.s  loc_4C619
0x4c60f  ldloc.2
0x4c610  brfalse.s loc_4C618
0x4c612  ldloc.2
0x4c613  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c618  endfinally
0x4c619  ldarg.0
0x4c61a  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c61f  ldloc.1
0x4c620  callvirt instance class [System]System.Uri System.IO.Packaging.PackagePart::get_Uri()
0x4c625  callvirt instance void System.IO.Packaging.Package::DeletePart(class [System]System.Uri partUri)
0x4c62a  ldarg.0
0x4c62b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c630  ldloc.0
0x4c631  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::get_Item(!!T0)
0x4c636  callvirt instance void System.IO.Packaging.PackageDigitalSignature::Invalidate()
0x4c63b  ldloc.0
0x4c63c  ldc.i4.1
0x4c63d  add
0x4c63e  stloc.0
0x4c63f  ldloc.0
0x4c640  ldarg.0
0x4c641  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c646  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::get_Count()
0x4c64b  blt      loc_4C5B5
0x4c650  ldarg.0
0x4c651  call     instance void System.IO.Packaging.PackageDigitalSignatureManager::DeleteOriginPart()
0x4c656  leave.s  loc_4C664
0x4c658  ldarg.0
0x4c659  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c65e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::Clear()
0x4c663  endfinally
0x4c664  ret
```
