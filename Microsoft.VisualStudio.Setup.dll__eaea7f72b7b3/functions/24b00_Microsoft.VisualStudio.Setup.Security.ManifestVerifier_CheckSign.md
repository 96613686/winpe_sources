# Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckSign

- ea: `0x24b00`
- end: `0x24f24`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckSign`
- size: `1060`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x241c0`

## callees

- `0x238d0`
- `0x23950`
- `0x23d30`
- `0x23d80`
- `0x247b0`
- `0x24a40`
- `0x24a90`
- `0x24b00`
- `0x24f30`
- `0x25030`
- `0x254c0`
- `0x27180`
- `0x271a0`
- `0x271c0`
- `0x271e0`
- `0x272e0`
- `0x27300`
- `0x27320`
- `0x273f0`
- `0x27450`
- `0x274d0`
- `0x27640`
- `0x27660`
- `0x27680`
- `0x276a0`

## string_xrefs

- `0x24c20`: `ManifestVerifier Rechecking digest.`
- `0x24c7a`: `ManifestVerifier digest did not match. Actual: `
- `0x24cad`: `ManifestVerifier digest did not match. Actual: `
- `0x24e92`: `ManifestVerifier countersign cert chain does not go to a valid root.`
- `0x24ec4`: `ManifestVerifier Timestamp check failed.`

## pseudocode

```c

```

## disassembly

```asm
0x24b00  ldarg.s  4
0x24b02  ldnull
0x24b03  stind.ref
0x24b04  ldarg.2
0x24b05  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24b0a  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_SignatureMethod()
0x24b0f  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x24b14  brtrue.s loc_24B54
0x24b16  ldarg.1
0x24b17  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x24b1c  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x24b21  brtrue.s loc_24B54
0x24b23  ldarg.2
0x24b24  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24b29  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestMethod()
0x24b2e  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x24b33  brtrue.s loc_24B54
0x24b35  ldarg.2
0x24b36  callvirt instance class Microsoft.VisualStudio.Setup.Security.KeyInfo Microsoft.VisualStudio.Setup.Security.Signature::get_KeyInfo()
0x24b3b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Security.KeyInfo::get_X509Data()
0x24b40  call     T0x2B0000B4
0x24b45  brtrue.s loc_24B54
0x24b47  ldarg.2
0x24b48  callvirt instance string Microsoft.VisualStudio.Setup.Security.Signature::get_SignatureValue()
0x24b4d  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x24b52  brfalse.s loc_24B56
0x24b54  ldc.i4.2
0x24b55  ret
0x24b56  ldnull
0x24b57  stloc.0
0x24b58  ldc.i4.0
0x24b59  stloc.1
0x24b5a  ldarg.2
0x24b5b  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24b60  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_SignatureMethod()
0x24b65  ldstr    aCng// "_cng"
0x24b6a  callvirt instance bool [mscorlib]System.String::Contains(string)
0x24b6f  brfalse.s loc_24B91
0x24b71  ldarg.2
0x24b72  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24b77  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::GetSignInfoBlob()
0x24b7c  ldarg.2
0x24b7d  callvirt instance class Microsoft.VisualStudio.Setup.Security.KeyInfo Microsoft.VisualStudio.Setup.Security.Signature::get_KeyInfo()
0x24b82  callvirt instance string Microsoft.VisualStudio.Setup.Security.KeyInfo::GetKeyInfoBlob()
0x24b87  call     string [mscorlib]System.String::Concat(string, string)
0x24b8c  stloc.0
0x24b8d  ldc.i4.1
0x24b8e  stloc.1
0x24b8f  br.s     loc_24BBB
0x24b91  ldarg.2
0x24b92  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24b97  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_SignatureMethod()
0x24b9c  call     string Microsoft.VisualStudio.Setup.Security.ManifestMethods::GetAlgorithmName(string algorithm)
0x24ba1  stloc.s  7
0x24ba3  ldarg.2
0x24ba4  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24ba9  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::GetSignInfoBlob()
0x24bae  ldloc.s  7
0x24bb0  call     unsigned int8[] Microsoft.VisualStudio.Setup.Security.ManifestMethods::CalculateHashValue(string dataBlob, string hashMethod)
0x24bb5  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x24bba  stloc.0
0x24bbb  ldarg.1
0x24bbc  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x24bc1  ldarg.2
0x24bc2  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24bc7  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestMethod()
0x24bcc  call     unsigned int8[] Microsoft.VisualStudio.Setup.Security.ManifestMethods::CalculateHashValue(string dataBlob, string hashMethod)
0x24bd1  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x24bd6  stloc.2
0x24bd7  ldloc.2
0x24bd8  ldarg.2
0x24bd9  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24bde  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestValue()
0x24be3  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x24be8  brfalse  loc_24CD4
0x24bed  ldarg.1
0x24bee  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_Bom()
0x24bf3  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x24bf8  brtrue   loc_24CA1
0x24bfd  ldarg.1
0x24bfe  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x24c03  ldarg.1
0x24c04  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_Bom()
0x24c09  ldc.i4.5
0x24c0a  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x24c0f  brfalse  loc_24CA1
0x24c14  ldarg.0
0x24c15  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24c1a  dup
0x24c1b  brtrue.s loc_24C20
0x24c1d  pop
0x24c1e  br.s     loc_24C2F
0x24c20  ldstr    aManifestverifi_16// "ManifestVerifier Rechecking digest."
0x24c25  call     T0x2B000003
0x24c2a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x24c2f  ldarg.1
0x24c30  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x24c35  ldarg.1
0x24c36  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_Bom()
0x24c3b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x24c40  callvirt instance string [mscorlib]System.String::Substring(int32)
0x24c45  ldarg.2
0x24c46  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24c4b  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestMethod()
0x24c50  call     unsigned int8[] Microsoft.VisualStudio.Setup.Security.ManifestMethods::CalculateHashValue(string dataBlob, string hashMethod)
0x24c55  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x24c5a  stloc.2
0x24c5b  ldloc.2
0x24c5c  ldarg.2
0x24c5d  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24c62  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestValue()
0x24c67  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x24c6c  brfalse.s loc_24CD4
0x24c6e  ldarg.0
0x24c6f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24c74  dup
0x24c75  brtrue.s loc_24C7A
0x24c77  pop
0x24c78  br.s     loc_24C9F
0x24c7a  ldstr    aManifestverifi_17// "ManifestVerifier digest did not match. "...
0x24c7f  ldloc.2
0x24c80  ldstr    aExpected// " Expected: "
0x24c85  ldarg.2
0x24c86  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24c8b  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestValue()
0x24c90  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x24c95  call     T0x2B000003
0x24c9a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x24c9f  ldc.i4.2
0x24ca0  ret
0x24ca1  ldarg.0
0x24ca2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24ca7  dup
0x24ca8  brtrue.s loc_24CAD
0x24caa  pop
0x24cab  br.s     loc_24CD2
0x24cad  ldstr    aManifestverifi_17// "ManifestVerifier digest did not match. "...
0x24cb2  ldloc.2
0x24cb3  ldstr    aExpected// " Expected: "
0x24cb8  ldarg.2
0x24cb9  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24cbe  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestValue()
0x24cc3  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x24cc8  call     T0x2B000003
0x24ccd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x24cd2  ldc.i4.2
0x24cd3  ret
0x24cd4  ldarg.2
0x24cd5  callvirt instance string Microsoft.VisualStudio.Setup.Security.Signature::get_SignatureValue()
0x24cda  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x24cdf  pop
0x24ce0  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x24ce5  ldloc.0
0x24ce6  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x24ceb  stloc.3
0x24cec  ldarg.2
0x24ced  callvirt instance class Microsoft.VisualStudio.Setup.Security.KeyInfo Microsoft.VisualStudio.Setup.Security.Signature::get_KeyInfo()
0x24cf2  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Security.KeyInfo::get_X509Data()
0x24cf7  ldc.i4.0
0x24cf8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x24cfd  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x24d02  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor(unsigned int8[])
0x24d07  stloc.s  4
0x24d09  ldloc.1
0x24d0a  brfalse.s loc_24D2A
0x24d0c  ldarg.0
0x24d0d  ldarg.2
0x24d0e  callvirt instance string Microsoft.VisualStudio.Setup.Security.Signature::get_SignatureValue()
0x24d13  ldloc.3
0x24d14  ldloc.s  4
0x24d16  ldarg.2
0x24d17  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24d1c  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestMethod()
0x24d21  call     instance bool Microsoft.VisualStudio.Setup.Security.ManifestVerifier::AsymmetricValidate(string signatureValue, unsigned int8[] referenceRawData, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signCertificate, string digestMethod)
0x24d26  brtrue.s loc_24D3D
0x24d28  ldc.i4.2
0x24d29  ret
0x24d2a  ldarg.0
0x24d2b  ldarg.2
0x24d2c  callvirt instance string Microsoft.VisualStudio.Setup.Security.Signature::get_SignatureValue()
0x24d31  ldloc.0
0x24d32  ldloc.s  4
0x24d34  call     instance bool Microsoft.VisualStudio.Setup.Security.ManifestVerifier::SignedCmsValidate(string signatureValue, string reference, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signCertificate)
0x24d39  brtrue.s loc_24D3D
0x24d3b  ldc.i4.2
0x24d3c  ret
0x24d3d  ldarg.0
0x24d3e  ldarg.2
0x24d3f  callvirt instance class Microsoft.VisualStudio.Setup.Security.KeyInfo Microsoft.VisualStudio.Setup.Security.Signature::get_KeyInfo()
0x24d44  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Security.KeyInfo::get_X509Data()
0x24d49  call     instance class [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection Microsoft.VisualStudio.Setup.Security.ManifestVerifier::GetCertListFromX509Data(class [mscorlib]System.Collections.Generic.IList`1<string> x509Data)
0x24d4e  stloc.s  5
0x24d50  ldarg.0
0x24d51  ldloc.s  5
0x24d53  ldloc.s  4
0x24d55  call     instance bool Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckCertChain(class [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection x509Certs, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signValueCert)
0x24d5a  brtrue.s loc_24D79
0x24d5c  ldloc.s  4
0x24d5e  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x24d63  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x24d68  ldsfld   string Microsoft.VisualStudio.Setup.Security.SignatureManager::VSBuildLabSubject
0x24d6d  ldc.i4.5
0x24d6e  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x24d73  brfalse.s loc_24D77
0x24d75  ldc.i4.4
0x24d76  ret
0x24d77  ldc.i4.3
0x24d78  ret
0x24d79  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor()
0x24d7e  stloc.s  6
0x24d80  ldarg.2
0x24d81  callvirt instance class Microsoft.VisualStudio.Setup.Security.CounterSign Microsoft.VisualStudio.Setup.Security.Signature::get_CounterSign()
0x24d86  callvirt instance string Microsoft.VisualStudio.Setup.Security.CounterSign::get_CounterSignature()
0x24d8b  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x24d90  brtrue   loc_24ED5
0x24d95  ldarg.2
0x24d96  callvirt instance class Microsoft.VisualStudio.Setup.Security.CounterSign Microsoft.VisualStudio.Setup.Security.Signature::get_CounterSign()
0x24d9b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Security.CounterSign::get_X509Data()
0x24da0  call     T0x2B0000B4
0x24da5  brtrue   loc_24ED5
0x24daa  ldloc.s  4
0x24dac  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x24db1  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x24db6  ldsfld   string Microsoft.VisualStudio.Setup.Security.SignatureManager::VSBuildLabSubject
0x24dbb  ldc.i4.5
0x24dbc  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x24dc1  brtrue   loc_24ED5
0x24dc6  ldarg.2
0x24dc7  callvirt instance class Microsoft.VisualStudio.Setup.Security.CounterSign Microsoft.VisualStudio.Setup.Security.Signature::get_CounterSign()
0x24dcc  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Security.CounterSign::get_X509Data()
0x24dd1  ldc.i4.0
0x24dd2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x24dd7  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x24ddc  stloc.s  8
0x24dde  ldloc.s  6
0x24de0  ldloc.s  8
0x24de2  callvirt instance void [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::Import(unsigned int8[])
0x24de7  ldnull
0x24de8  stloc.s  9
0x24dea  ldarg.2
0x24deb  callvirt instance class Microsoft.VisualStudio.Setup.Security.CounterSign Microsoft.VisualStudio.Setup.Security.Signature::get_CounterSign()
0x24df0  callvirt instance string Microsoft.VisualStudio.Setup.Security.CounterSign::get_CounterSignatureMethod()
0x24df5  ldstr    aTimestamp// "timeStamp"
0x24dfa  call     bool [mscorlib]System.String::Equals(string, string)
0x24dff  brfalse.s loc_24E2B
0x24e01  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0x24e06  ldarg.2
0x24e07  callvirt instance string Microsoft.VisualStudio.Setup.Security.Signature::get_SignatureValue()
0x24e0c  ldloc.s  6
0x24e0e  callvirt instance class [System]System.Security.Cryptography.Oid [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SignatureAlgorithm()
0x24e13  callvirt instance string [System]System.Security.Cryptography.Oid::get_FriendlyName()
0x24e18  call     string Microsoft.VisualStudio.Setup.Security.ManifestMethods::GetAlgorithmName(string algorithm)
0x24e1d  call     unsigned int8[] Microsoft.VisualStudio.Setup.Security.ManifestMethods::CalculateHashValue(string dataBlob, string hashMethod)
0x24e22  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x24e27  stloc.s  9
0x24e29  br.s     loc_24E52
0x24e2b  ldarg.2
0x24e2c  callvirt instance string Microsoft.VisualStudio.Setup.Security.Signature::get_SignatureValue()
0x24e31  ldarg.2
0x24e32  callvirt instance class Microsoft.VisualStudio.Setup.Security.CounterSign Microsoft.VisualStudio.Setup.Security.Signature::get_CounterSign()
0x24e37  callvirt instance string Microsoft.VisualStudio.Setup.Security.CounterSign::get_Timestamp()
0x24e3c  call     string [mscorlib]System.String::Concat(string, string)
0x24e41  ldstr    aSha1_0// "sha1"
0x24e46  call     unsigned int8[] Microsoft.VisualStudio.Setup.Security.ManifestMethods::CalculateHashValue(string dataBlob, string hashMethod)
0x24e4b  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x24e50  stloc.s  9
0x24e52  ldarg.0
0x24e53  ldarg.2
0x24e54  callvirt instance class Microsoft.VisualStudio.Setup.Security.CounterSign Microsoft.VisualStudio.Setup.Security.Signature::get_CounterSign()
0x24e59  callvirt instance string Microsoft.VisualStudio.Setup.Security.CounterSign::get_CounterSignature()
0x24e5e  ldloc.s  9
0x24e60  ldloc.s  6
0x24e62  call     instance bool Microsoft.VisualStudio.Setup.Security.ManifestVerifier::SignedCmsValidate(string signatureValue, string reference, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signCertificate)
0x24e67  brtrue.s loc_24E6B
0x24e69  ldc.i4.2
0x24e6a  ret
0x24e6b  ldarg.0
0x24e6c  ldarg.0
0x24e6d  ldarg.2
0x24e6e  callvirt instance class Microsoft.VisualStudio.Setup.Security.CounterSign Microsoft.VisualStudio.Setup.Security.Signature::get_CounterSign()
0x24e73  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Security.CounterSign::get_X509Data()
0x24e78  call     instance class [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection Microsoft.VisualStudio.Setup.Security.ManifestVerifier::GetCertListFromX509Data(class [mscorlib]System.Collections.Generic.IList`1<string> x509Data)
0x24e7d  ldloc.s  6
0x24e7f  call     instance bool Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckCertChain(class [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection x509Certs, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signValueCert)
0x24e84  brtrue.s loc_24EA3
0x24e86  ldarg.0
0x24e87  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24e8c  dup
0x24e8d  brtrue.s loc_24E92
0x24e8f  pop
0x24e90  br.s     loc_24EA1
0x24e92  ldstr    aManifestverifi_18// "ManifestVerifier countersign cert chain"...
0x24e97  call     T0x2B000003
0x24e9c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x24ea1  ldc.i4.3
0x24ea2  ret
0x24ea3  ldarg.0
0x24ea4  ldloc.s  4
0x24ea6  ldarg.2
0x24ea7  callvirt instance class Microsoft.VisualStudio.Setup.Security.CounterSign Microsoft.VisualStudio.Setup.Security.Signature::get_CounterSign()
  ... truncated ...
```
