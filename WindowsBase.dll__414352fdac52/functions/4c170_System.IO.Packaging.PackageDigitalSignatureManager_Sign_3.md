# System.IO.Packaging.PackageDigitalSignatureManager::Sign_3

- ea: `0x4c170`
- end: `0x4c329`
- name: `System.IO.Packaging.PackageDigitalSignatureManager::Sign_3`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x4c140`

## callees

- `0x1f7c0`
- `0x1f7d0`
- `0x1f7e0`
- `0x1f890`
- `0x1f8e0`
- `0x23c30`
- `0x23e40`
- `0x2c100`
- `0x48c10`
- `0x48cc0`
- `0x49010`
- `0x49b40`
- `0x4a5c0`
- `0x4bd60`
- `0x4c170`
- `0x4c7b0`
- `0x4c810`
- `0x4c980`
- `0x4cc00`
- `0x4cc30`
- `0x4ce10`
- `0x4ce20`

## string_xrefs

- `0x4c178`: `CannotSignReadOnlyFile`

## pseudocode

```c

```

## disassembly

```asm
0x4c170  ldarg.0
0x4c171  call     instance bool System.IO.Packaging.PackageDigitalSignatureManager::get_ReadOnly()
0x4c176  brfalse.s loc_4C188
0x4c178  ldstr    aCannotsignread// "CannotSignReadOnlyFile"
0x4c17d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4c182  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4c187  throw
0x4c188  ldarg.0
0x4c189  ldarg.1
0x4c18a  ldarg.2
0x4c18b  ldarg.3
0x4c18c  ldarg.s  4
0x4c18e  ldarg.s  5
0x4c190  ldarg.s  6
0x4c192  call     instance void System.IO.Packaging.PackageDigitalSignatureManager::VerifySignArguments(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri> parts, class [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate certificate, class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.IO.Packaging.PackageRelationshipSelector> relationshipSelectors, string signatureId, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Security]System.Security.Cryptography.Xml.DataObject> signatureObjects, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Security]System.Security.Cryptography.Xml.Reference> objectReferences)
0x4c197  ldarg.s  4
0x4c199  brfalse.s loc_4C1A9
0x4c19b  ldarg.s  4
0x4c19d  ldsfld   string [mscorlib]System.String::Empty
0x4c1a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4c1a7  brfalse.s loc_4C1B0
0x4c1a9  ldstr    aPackagesignatu_2// "packageSignature"
0x4c1ae  starg.s  4
0x4c1b0  ldarg.0
0x4c1b1  call     instance void System.IO.Packaging.PackageDigitalSignatureManager::EnsureSignatures()
0x4c1b6  ldarg.0
0x4c1b7  call     instance class [System]System.Uri System.IO.Packaging.PackageDigitalSignatureManager::GenerateSignaturePartName()
0x4c1bc  stloc.0
0x4c1bd  ldarg.0
0x4c1be  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c1c3  ldloc.0
0x4c1c4  callvirt instance bool System.IO.Packaging.Package::PartExists(class [System]System.Uri partUri)
0x4c1c9  brfalse.s loc_4C1DB
0x4c1cb  ldstr    aDuplicatesigna// "DuplicateSignature"
0x4c1d0  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4c1d5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4c1da  throw
0x4c1db  ldarg.0
0x4c1dc  call     instance class System.IO.Packaging.PackagePart System.IO.Packaging.PackageDigitalSignatureManager::get_OriginPart()
0x4c1e1  ldloc.0
0x4c1e2  ldc.i4.0
0x4c1e3  ldsfld   string System.IO.Packaging.PackageDigitalSignatureManager::_originToSignatureRelationshipType
0x4c1e8  callvirt instance class System.IO.Packaging.PackageRelationship System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri targetUri, valuetype System.IO.Packaging.TargetMode targetMode, string relationshipType)
0x4c1ed  stloc.1
0x4c1ee  ldarg.0
0x4c1ef  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c1f4  callvirt instance void System.IO.Packaging.Package::Flush()
0x4c1f9  ldarg.0
0x4c1fa  ldarg.1
0x4c1fb  call     instance void System.IO.Packaging.PackageDigitalSignatureManager::VerifyPartsExist(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri> parts)
0x4c200  ldarg.0
0x4c201  ldfld    valuetype System.IO.Packaging.CertificateEmbeddingOption System.IO.Packaging.PackageDigitalSignatureManager::_certificateEmbeddingOption
0x4c206  ldc.i4.1
0x4c207  ceq
0x4c209  stloc.2
0x4c20a  ldarg.2
0x4c20b  isinst   [System]System.Security.Cryptography.X509Certificates.X509Certificate2
0x4c210  stloc.3
0x4c211  ldloc.3
0x4c212  brtrue.s loc_4C220
0x4c214  ldarg.2
0x4c215  callvirt instance native int [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::get_Handle()
0x4c21a  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor(native int)
0x4c21f  stloc.3
0x4c220  ldnull
0x4c221  stloc.s  4
0x4c223  ldnull
0x4c224  stloc.s  5
0x4c226  ldarg.0
0x4c227  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c22c  ldloc.0
0x4c22d  call     class MS.Internal.ContentType MS.Internal.IO.Packaging.XmlDigitalSignatureProcessor::get_ContentType()
0x4c232  callvirt instance string [mscorlib]System.Object::ToString()
0x4c237  callvirt instance class System.IO.Packaging.PackagePart System.IO.Packaging.Package::CreatePart(class [System]System.Uri partUri, string contentType)
0x4c23c  stloc.s  5
0x4c23e  ldarg.0
0x4c23f  ldloc.s  5
0x4c241  ldarg.1
0x4c242  ldarg.3
0x4c243  ldloc.3
0x4c244  ldarg.s  4
0x4c246  ldloc.2
0x4c247  ldarg.s  5
0x4c249  ldarg.s  6
0x4c24b  call     class System.IO.Packaging.PackageDigitalSignature MS.Internal.IO.Packaging.XmlDigitalSignatureProcessor::Sign(class System.IO.Packaging.PackageDigitalSignatureManager manager, class System.IO.Packaging.PackagePart signaturePart, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri> parts, class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.IO.Packaging.PackageRelationshipSelector> relationshipSelectors, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signer, string signatureId, bool embedCertificate, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Security]System.Security.Cryptography.Xml.DataObject> signatureObjects, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Security]System.Security.Cryptography.Xml.Reference> objectReferences)
0x4c250  stloc.s  4
0x4c252  leave.s  loc_4C2B4
0x4c254  pop
0x4c255  ldarg.0
0x4c256  ldloc.0
0x4c257  ldarg.0
0x4c258  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c25d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::get_Count()
0x4c262  call     instance void System.IO.Packaging.PackageDigitalSignatureManager::InternalRemoveSignature(class [System]System.Uri signatureUri, int32 countOfSignaturesRemaining)
0x4c267  ldarg.0
0x4c268  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c26d  callvirt instance void System.IO.Packaging.Package::Flush()
0x4c272  rethrow
0x4c274  pop
0x4c275  ldarg.0
0x4c276  ldloc.0
0x4c277  ldarg.0
0x4c278  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c27d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::get_Count()
0x4c282  call     instance void System.IO.Packaging.PackageDigitalSignatureManager::InternalRemoveSignature(class [System]System.Uri signatureUri, int32 countOfSignaturesRemaining)
0x4c287  ldarg.0
0x4c288  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c28d  callvirt instance void System.IO.Packaging.Package::Flush()
0x4c292  rethrow
0x4c294  pop
0x4c295  ldarg.0
0x4c296  ldloc.0
0x4c297  ldarg.0
0x4c298  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c29d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::get_Count()
0x4c2a2  call     instance void System.IO.Packaging.PackageDigitalSignatureManager::InternalRemoveSignature(class [System]System.Uri signatureUri, int32 countOfSignaturesRemaining)
0x4c2a7  ldarg.0
0x4c2a8  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c2ad  callvirt instance void System.IO.Packaging.Package::Flush()
0x4c2b2  rethrow
0x4c2b4  ldarg.0
0x4c2b5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c2ba  ldloc.s  4
0x4c2bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::Add(var<u1>)
0x4c2c1  ldarg.0
0x4c2c2  ldfld    valuetype System.IO.Packaging.CertificateEmbeddingOption System.IO.Packaging.PackageDigitalSignatureManager::_certificateEmbeddingOption
0x4c2c7  brtrue.s loc_4C31B
0x4c2c9  call     string MS.Internal.IO.Packaging.CertificatePart::get_PartNamePrefix()
0x4c2ce  ldloc.3
0x4c2cf  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SerialNumber()
0x4c2d4  call     string MS.Internal.IO.Packaging.CertificatePart::get_PartNameExtension()
0x4c2d9  call     string [mscorlib]System.String::Concat(string, string, string)
0x4c2de  ldc.i4.2
0x4c2df  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x4c2e4  call     class [System]System.Uri System.IO.Packaging.PackUriHelper::CreatePartUri(class [System]System.Uri partUri)
0x4c2e9  stloc.s  6
0x4c2eb  ldarg.0
0x4c2ec  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c2f1  ldloc.s  6
0x4c2f3  newobj   instance void MS.Internal.IO.Packaging.CertificatePart::.ctor(class System.IO.Packaging.Package container, class [System]System.Uri partName)
0x4c2f8  stloc.s  7
0x4c2fa  ldloc.s  7
0x4c2fc  ldloc.3
0x4c2fd  callvirt instance void MS.Internal.IO.Packaging.CertificatePart::SetCertificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 certificate)
0x4c302  ldloc.s  5
0x4c304  ldloc.s  6
0x4c306  ldc.i4.0
0x4c307  call     string MS.Internal.IO.Packaging.CertificatePart::get_RelationshipType()
0x4c30c  callvirt instance class System.IO.Packaging.PackageRelationship System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri targetUri, valuetype System.IO.Packaging.TargetMode targetMode, string relationshipType)
0x4c311  pop
0x4c312  ldloc.s  4
0x4c314  ldloc.s  7
0x4c316  callvirt instance void System.IO.Packaging.PackageDigitalSignature::SetCertificatePart(class MS.Internal.IO.Packaging.CertificatePart certificatePart)
0x4c31b  ldarg.0
0x4c31c  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackageDigitalSignatureManager::_container
0x4c321  callvirt instance void System.IO.Packaging.Package::Flush()
0x4c326  ldloc.s  4
0x4c328  ret
```
