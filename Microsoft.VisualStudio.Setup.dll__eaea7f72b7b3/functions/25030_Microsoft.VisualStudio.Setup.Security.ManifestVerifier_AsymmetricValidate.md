# Microsoft.VisualStudio.Setup.Security.ManifestVerifier::AsymmetricValidate

- ea: `0x25030`
- end: `0x2513d`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestVerifier::AsymmetricValidate`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x24b00`

## callees

- `0x23e60`
- `0x25030`

## string_xrefs

- `0x25078`: `ManifestVerifier Failed to create SignatureDescription.`
- `0x2509f`: `ManifestVerifier Failed to create digest hash algorithm.`
- `0x250f4`: `ManifestVerifier Failed to verify asymmetric signature.`
- `0x25118`: `ManifestVerifier Exception verifying asymmetric signature `

## pseudocode

```c

```

## disassembly

```asm
0x25030  ldarg.1
0x25031  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x25036  brfalse.s loc_2503A
0x25038  ldc.i4.0
0x25039  ret
0x2503a  ldarg.3
0x2503b  callvirt instance class [System]System.Security.Cryptography.X509Certificates.PublicKey [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_PublicKey()
0x25040  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm [System]System.Security.Cryptography.X509Certificates.PublicKey::get_Key()
0x25045  castclass [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider
0x2504a  stloc.0
0x2504b  ldarg.3
0x2504c  callvirt instance class [System]System.Security.Cryptography.Oid [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SignatureAlgorithm()
0x25051  callvirt instance string [System]System.Security.Cryptography.Oid::get_FriendlyName()
0x25056  dup
0x25057  ldarg.s  4
0x25059  call     void Microsoft.VisualStudio.Setup.Security.ManifestMethods::EnableSha256RSA(string signatureMethod, string digestMethod)
0x2505e  call     object [mscorlib]System.Security.Cryptography.CryptoConfig::CreateFromName(string)
0x25063  isinst   [mscorlib]System.Security.Cryptography.SignatureDescription
0x25068  stloc.1
0x25069  ldloc.1
0x2506a  brtrue.s loc_25089
0x2506c  ldarg.0
0x2506d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x25072  dup
0x25073  brtrue.s loc_25078
0x25075  pop
0x25076  br.s     loc_25087
0x25078  ldstr    aManifestverifi_23// "ManifestVerifier Failed to create Signa"...
0x2507d  call     T0x2B000003
0x25082  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x25087  ldc.i4.0
0x25088  ret
0x25089  ldloc.1
0x2508a  callvirt instance class [mscorlib]System.Security.Cryptography.HashAlgorithm [mscorlib]System.Security.Cryptography.SignatureDescription::CreateDigest()
0x2508f  stloc.2
0x25090  ldloc.2
0x25091  brtrue.s loc_250B0
0x25093  ldarg.0
0x25094  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x25099  dup
0x2509a  brtrue.s loc_2509F
0x2509c  pop
0x2509d  br.s     loc_250AE
0x2509f  ldstr    aManifestverifi_24// "ManifestVerifier Failed to create diges"...
0x250a4  call     T0x2B000003
0x250a9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x250ae  ldc.i4.0
0x250af  ret
0x250b0  ldloc.2
0x250b1  ldarg.2
0x250b2  ldc.i4.0
0x250b3  ldarg.2
0x250b4  ldlen
0x250b5  conv.i4
0x250b6  ldarg.2
0x250b7  ldc.i4.0
0x250b8  callvirt instance int32 [mscorlib]System.Security.Cryptography.HashAlgorithm::TransformBlock(unsigned int8[], int32, int32, unsigned int8[], int32)
0x250bd  pop
0x250be  ldloc.2
0x250bf  ldc.i4.0
0x250c0  newarr   [mscorlib]System.Byte
0x250c5  ldc.i4.0
0x250c6  ldc.i4.0
0x250c7  callvirt instance unsigned int8[] [mscorlib]System.Security.Cryptography.HashAlgorithm::TransformFinalBlock(unsigned int8[], int32, int32)
0x250cc  pop
0x250cd  ldloc.1
0x250ce  ldloc.0
0x250cf  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricSignatureDeformatter [mscorlib]System.Security.Cryptography.SignatureDescription::CreateDeformatter(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm)
0x250d4  stloc.3
0x250d5  ldarg.1
0x250d6  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x250db  stloc.s  4
0x250dd  ldloc.3
0x250de  ldloc.2
0x250df  ldloc.s  4
0x250e1  callvirt instance bool [mscorlib]System.Security.Cryptography.AsymmetricSignatureDeformatter::VerifySignature(class [mscorlib]System.Security.Cryptography.HashAlgorithm, unsigned int8[])
0x250e6  brtrue.s loc_25108
0x250e8  ldarg.0
0x250e9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x250ee  dup
0x250ef  brtrue.s loc_250F4
0x250f1  pop
0x250f2  br.s     loc_25103
0x250f4  ldstr    aManifestverifi_25// "ManifestVerifier Failed to verify asymm"...
0x250f9  call     T0x2B000003
0x250fe  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x25103  ldc.i4.0
0x25104  stloc.s  5
0x25106  leave.s  loc_2513A
0x25108  leave.s  loc_25138
0x2510a  stloc.s  6
0x2510c  ldarg.0
0x2510d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x25112  dup
0x25113  brtrue.s loc_25118
0x25115  pop
0x25116  br.s     loc_25133
0x25118  ldstr    aManifestverifi_26// "ManifestVerifier Exception verifying as"...
0x2511d  ldloc.s  6
0x2511f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x25124  call     string [mscorlib]System.String::Concat(string, string)
0x25129  call     T0x2B000003
0x2512e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x25133  ldc.i4.0
0x25134  stloc.s  5
0x25136  leave.s  loc_2513A
0x25138  ldc.i4.1
0x25139  ret
0x2513a  ldloc.s  5
0x2513c  ret
```
