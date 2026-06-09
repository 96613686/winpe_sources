# System.Deployment.Application.Manifest.AssemblyManifest::AnalyzeManifestCertificate

- ea: `0x26960`
- end: `0x26a85`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::AnalyzeManifestCertificate`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0xba10`
- `0x28360`

## callees

- `0x75c0`
- `0x7720`
- `0x7c60`
- `0x7c70`
- `0x14ba0`
- `0x17cd0`
- `0x17d40`
- `0x26960`
- `0x26a90`
- `0x26ac0`

## string_xrefs

- `0x26960`: `AnalyzeManifestCertificate called.`

## pseudocode

```c

```

## disassembly

```asm
0x26960  ldstr    aAnalyzemanifes// "AnalyzeManifestCertificate called."
0x26965  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x2696a  ldc.i4.5
0x2696b  stloc.0
0x2696c  ldnull
0x2696d  stloc.1
0x2696e  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x26973  stloc.2
0x26974  ldloc.2
0x26975  ldc.i4.1
0x26976  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_PreserveWhitespace(bool)
0x2697b  ldloc.2
0x2697c  ldarg.0
0x2697d  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(string)
0x26982  ldloc.2
0x26983  ldloca.s 1
0x26985  ldloca.s 0
0x26987  ldc.i4.1
0x26988  call     void System.Deployment.Application.Manifest.AssemblyManifest::VerifyManifestCertificate(class [System.Xml]System.Xml.XmlDocument deploymentManifestXmlDom, [out] class System.Deployment.Internal.CodeSigning.SignedCmiManifest2& signedManifest, [out] valuetype CertificateStatus& certificateStatus, bool useSha256OrHigher)
0x2698d  leave    loc_26A67
0x26992  stloc.3
0x26993  ldloc.3
0x26994  call     bool System.Deployment.Application.ExceptionUtility::IsHardException(class [mscorlib]System.Exception exception)
0x26999  brfalse.s loc_2699D
0x2699b  rethrow
0x2699d  ldloc.3
0x2699e  isinst   [mscorlib]System.Security.Cryptography.CryptographicException
0x269a3  brfalse  loc_26A40
0x269a8  ldloc.1
0x269a9  callvirt instance class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::get_StrongNameSignerInfo()
0x269ae  brfalse.s loc_26A27
0x269b0  ldloc.1
0x269b1  callvirt instance class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::get_StrongNameSignerInfo()
0x269b6  callvirt instance int32 System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo::get_ErrorCode()
0x269bb  ldc.i4   0x80096010
0x269c0  bne.un.s loc_26A27
0x269c2  ldloc.2
0x269c3  ldloca.s 1
0x269c5  ldloca.s 0
0x269c7  ldc.i4.0
0x269c8  call     void System.Deployment.Application.Manifest.AssemblyManifest::VerifyManifestCertificate(class [System.Xml]System.Xml.XmlDocument deploymentManifestXmlDom, [out] class System.Deployment.Internal.CodeSigning.SignedCmiManifest2& signedManifest, [out] valuetype CertificateStatus& certificateStatus, bool useSha256OrHigher)
0x269cd  leave.s  loc_26A40
0x269cf  stloc.s  4
0x269d1  ldloc.s  4
0x269d3  call     bool System.Deployment.Application.ExceptionUtility::IsHardException(class [mscorlib]System.Exception exception)
0x269d8  brfalse.s loc_269DC
0x269da  rethrow
0x269dc  ldloc.s  4
0x269de  isinst   [mscorlib]System.Security.Cryptography.CryptographicException
0x269e3  brfalse.s loc_269FE
0x269e5  ldloc.1
0x269e6  callvirt instance class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::get_AuthenticodeSignerInfo()
0x269eb  brfalse.s loc_269FE
0x269ed  ldloc.1
0x269ee  callvirt instance class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::get_AuthenticodeSignerInfo()
0x269f3  callvirt instance int32 System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::get_ErrorCode()
0x269f8  call     valuetype CertificateStatus System.Deployment.Application.Manifest.AssemblyManifest::GetCertificateStatus(int32 error)
0x269fd  stloc.0
0x269fe  ldstr    aExceptionThrow_4// "Exception thrown : "
0x26a03  ldloc.s  4
0x26a05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x26a0a  callvirt instance string [mscorlib]System.Object::ToString()
0x26a0f  ldstr    asc_32300// ":"
0x26a14  ldloc.s  4
0x26a16  callvirt instance string [mscorlib]System.Exception::get_Message()
0x26a1b  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x26a20  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x26a25  leave.s  loc_26A40
0x26a27  ldloc.1
0x26a28  callvirt instance class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::get_AuthenticodeSignerInfo()
0x26a2d  brfalse.s loc_26A40
0x26a2f  ldloc.1
0x26a30  callvirt instance class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::get_AuthenticodeSignerInfo()
0x26a35  callvirt instance int32 System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::get_ErrorCode()
0x26a3a  call     valuetype CertificateStatus System.Deployment.Application.Manifest.AssemblyManifest::GetCertificateStatus(int32 error)
0x26a3f  stloc.0
0x26a40  ldstr    aExceptionThrow_4// "Exception thrown : "
0x26a45  ldloc.3
0x26a46  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x26a4b  callvirt instance string [mscorlib]System.Object::ToString()
0x26a50  ldstr    asc_32300// ":"
0x26a55  ldloc.3
0x26a56  callvirt instance string [mscorlib]System.Exception::get_Message()
0x26a5b  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x26a60  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x26a65  leave.s  loc_26A67
0x26a67  ldstr    aCertificateSta// "Certificate Status="
0x26a6c  ldloca.s 0
0x26a6e  constrained. CertificateStatus
0x26a74  callvirt instance string [mscorlib]System.Object::ToString()
0x26a79  call     string [mscorlib]System.String::Concat(string, string)
0x26a7e  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x26a83  ldloc.0
0x26a84  ret
```
