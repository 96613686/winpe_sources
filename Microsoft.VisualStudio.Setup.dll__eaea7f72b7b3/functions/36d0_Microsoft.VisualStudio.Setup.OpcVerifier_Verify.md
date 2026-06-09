# Microsoft.VisualStudio.Setup.OpcVerifier::Verify

- ea: `0x36d0`
- end: `0x37f3`
- name: `Microsoft.VisualStudio.Setup.OpcVerifier::Verify`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3610`

## callees

- `0x36d0`
- `0x38c0`
- `0x3940`
- `0x3aa0`

## string_xrefs

- `0x3707`: `Vs_installer.vsix is test signed. Please run {0}.`
- `0x3714`: `https://aka.ms/vspreinstall`
- `0x374b`: `Unable to verify the integrity of the installation files: the certificate could not be verified`
- `0x37a1`: `The installation package is signed by: `
- `0x37c5`: `Unable to verify the integrity of the installation files: the subject name of the certificate does not match`

## pseudocode

```c

```

## disassembly

```asm
0x36d0  ldarg.0
0x36d1  ldarg.1
0x36d2  call     instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.VisualStudio.Setup.OpcVerifier::GetSigningCertificate(class [mscorlib]System.IO.Stream)
0x36d7  stloc.0
0x36d8  ldarg.0
0x36d9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager Microsoft.VisualStudio.Setup.OpcVerifier::verifier
0x36de  ldarg.1
0x36df  ldnull
0x36e0  ldnull
0x36e1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager::Verify(class [mscorlib]System.IO.Stream, string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext)
0x36e6  stloc.1
0x36e7  ldloc.1
0x36e8  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x36ed  brfalse.s loc_3756
0x36ef  ldloc.0
0x36f0  brfalse.s loc_371F
0x36f2  ldloc.0
0x36f3  call     bool Microsoft.VisualStudio.Setup.OpcVerifier::IsTestSigned(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signer)
0x36f8  brfalse.s loc_371F
0x36fa  ldarg.0
0x36fb  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.OpcVerifier::logger
0x3700  dup
0x3701  brtrue.s loc_3706
0x3703  pop
0x3704  br.s     loc_371F
0x3706  ldnull
0x3707  ldstr    aVsInstallerVsi// "Vs_installer.vsix is test signed. Pleas"...
0x370c  ldc.i4.1
0x370d  newarr   [mscorlib]System.Object
0x3712  dup
0x3713  ldc.i4.0
0x3714  ldstr    aHttpsAkaMsVspr// "https://aka.ms/vspreinstall"
0x3719  stelem.ref
0x371a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x371f  ldarg.0
0x3720  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.OpcVerifier::logger
0x3725  dup
0x3726  brtrue.s loc_372B
0x3728  pop
0x3729  br.s     loc_374B
0x372b  ldnull
0x372c  ldstr    aUnableToVerify// "Unable to verify the certificate: {0}"
0x3731  ldloc.1
0x3732  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x3737  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x373c  call     string [mscorlib]System.String::Format(string, object)
0x3741  call     T0x2B000003
0x3746  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x374b  ldstr    aUnableToVerify_0// "Unable to verify the integrity of the i"...
0x3750  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3755  throw
0x3756  ldloc.0
0x3757  brtrue.s loc_375C
0x3759  ldnull
0x375a  br.s     loc_3762
0x375c  ldloc.0
0x375d  call     instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x3762  brfalse.s loc_37D0
0x3764  ldloc.0
0x3765  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x376a  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x376f  ldsfld   string Microsoft.VisualStudio.Setup.OpcVerifier::MicrosoftSubject
0x3774  ldc.i4.5
0x3775  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::Contains(string, string, valuetype [mscorlib]System.StringComparison)
0x377a  brtrue.s loc_37D0
0x377c  ldloc.0
0x377d  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x3782  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x3787  ldsfld   string Microsoft.VisualStudio.Setup.OpcVerifier::TestSubject
0x378c  ldc.i4.5
0x378d  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::Contains(string, string, valuetype [mscorlib]System.StringComparison)
0x3792  brtrue.s loc_37D0
0x3794  ldarg.0
0x3795  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.OpcVerifier::logger
0x379a  dup
0x379b  brtrue.s loc_37A0
0x379d  pop
0x379e  br.s     loc_37C5
0x37a0  ldnull
0x37a1  ldstr    aTheInstallatio// "The installation package is signed by: "
0x37a6  ldloc.0
0x37a7  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x37ac  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x37b1  ldstr    aItMustBeSigned// ". It must be signed by Microsoft."
0x37b6  call     string [mscorlib]System.String::Concat(string, string, string)
0x37bb  call     T0x2B000003
0x37c0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x37c5  ldstr    aUnableToVerify_1// "Unable to verify the integrity of the i"...
0x37ca  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x37cf  throw
0x37d0  ldarg.2
0x37d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x37d6  brtrue.s loc_37F2
0x37d8  ldarg.3
0x37d9  brtrue.s loc_37F2
0x37db  ldarg.0
0x37dc  ldarg.2
0x37dd  ldloc.0
0x37de  call     instance void Microsoft.VisualStudio.Setup.OpcVerifier::CopyCertsToLayoutFolder(string layoutLocation, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signCertificate)
0x37e3  leave.s  loc_37F2
0x37e5  stloc.2
0x37e6  ldsfld   string Microsoft.VisualStudio.Setup.BootstrapperConstants::RootCertCreationFail
0x37eb  ldloc.2
0x37ec  newobj   instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x37f1  throw
0x37f2  ret
```
