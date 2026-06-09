# Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckPS1Authenticode

- ea: `0x25140`
- end: `0x254b2`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckPS1Authenticode`
- size: `882`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x241c0`
- `0x25140`

## callees

- `0x23900`
- `0x23930`
- `0x23950`
- `0x23c70`
- `0x23ca0`
- `0x241a0`
- `0x247b0`
- `0x24a90`
- `0x25140`
- `0x254c0`
- `0x25660`
- `0x256d0`
- `0x257c0`
- `0x257e0`
- `0x25800`
- `0x25810`
- `0x27100`
- `0x27160`
- `0x27180`
- `0x271c0`
- `0x27200`
- `0x27340`
- `0x27450`

## string_xrefs

- `0x25234`: `ManifestVerifier temporary ps1 file does not exist: `
- `0x2537a`: `ManifestVerifier ps1 cert chain Failed to build to valid root`
- `0x253b4`: `ManifestVerifier ps1 checking cert chain Failed `
- `0x25413`: `ManifestVerifier failed to clean up temp file: `
- `0x25494`: `ManifestVerifier failed to clean up temp file: `
- `0x25464`: `ManifestVerifier WinVerifyTrust Failed.`

## pseudocode

```c

```

## disassembly

```asm
0x25140  ldc.i4.0
0x25141  stloc.0
0x25142  ldarg.2
0x25143  callvirt instance class Microsoft.VisualStudio.Setup.Security.Signature Microsoft.VisualStudio.Setup.Security.SignObject::get_Signature()
0x25148  callvirt instance string Microsoft.VisualStudio.Setup.Security.Signature::TranformToPkcs()
0x2514d  stloc.1
0x2514e  ldloc.1
0x2514f  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x25154  brfalse.s loc_25158
0x25156  ldc.i4.6
0x25157  ret
0x25158  ldarg.2
0x25159  callvirt instance class Microsoft.VisualStudio.Setup.Security.Signature Microsoft.VisualStudio.Setup.Security.SignObject::get_Signature()
0x2515e  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x25163  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_Canonicalization()
0x25168  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x2516d  brtrue.s loc_25198
0x2516f  ldarg.2
0x25170  callvirt instance class Microsoft.VisualStudio.Setup.Security.Signature Microsoft.VisualStudio.Setup.Security.SignObject::get_Signature()
0x25175  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x2517a  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_Canonicalization()
0x2517f  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x25184  stloc.s  4
0x25186  ldarg.1
0x25187  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x2518c  ldloc.s  4
0x2518e  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x25193  callvirt instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentWhiteSpace(string value)
0x25198  ldarg.1
0x25199  ldloc.1
0x2519a  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::AppendPs1CertFooter(string ps1SignatureBlob)
0x2519f  stloc.2
0x251a0  ldarg.3
0x251a1  brfalse.s loc_251C2
0x251a3  ldarg.1
0x251a4  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_Bom()
0x251a9  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x251ae  brtrue.s loc_251C2
0x251b0  ldloc.2
0x251b1  ldarg.1
0x251b2  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_Bom()
0x251b7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x251bc  callvirt instance string [mscorlib]System.String::Substring(int32)
0x251c1  stloc.2
0x251c2  ldarg.1
0x251c3  callvirt instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::SetPs1TempFileName()
0x251c8  ldarg.0
0x251c9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x251ce  ldarg.1
0x251cf  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_TempFileName()
0x251d4  ldc.i4.2
0x251d5  ldc.i4.3
0x251d6  ldc.i4.0
0x251d7  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateFile(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileMode, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileAccess, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.FileShare)
0x251dc  stloc.s  5
0x251de  ldloc.s  5
0x251e0  ldc.i4.0
0x251e1  conv.i8
0x251e2  ldc.i4.0
0x251e3  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x251e8  pop
0x251e9  ldc.i4.0
0x251ea  newobj   instance void [mscorlib]System.Text.UTF8Encoding::.ctor(bool)
0x251ef  ldloc.2
0x251f0  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x251f5  stloc.s  6
0x251f7  ldloc.s  5
0x251f9  ldloc.s  6
0x251fb  ldc.i4.0
0x251fc  ldloc.s  6
0x251fe  ldlen
0x251ff  conv.i4
0x25200  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x25205  leave.s  loc_25213
0x25207  ldloc.s  5
0x25209  brfalse.s loc_25212
0x2520b  ldloc.s  5
0x2520d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25212  endfinally
0x25213  ldarg.0
0x25214  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x25219  ldarg.1
0x2521a  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_TempFileName()
0x2521f  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x25224  brtrue.s loc_25250
0x25226  ldc.i4.6
0x25227  stloc.0
0x25228  ldarg.0
0x25229  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x2522e  dup
0x2522f  brtrue.s loc_25234
0x25231  pop
0x25232  br.s     loc_2524E
0x25234  ldstr    aManifestverifi_27// "ManifestVerifier temporary ps1 file doe"...
0x25239  ldarg.1
0x2523a  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_TempFileName()
0x2523f  call     string [mscorlib]System.String::Concat(string, string)
0x25244  call     T0x2B000003
0x25249  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2524e  ldloc.0
0x2524f  ret
0x25250  ldc.i4   0x800B0100
0x25255  stloc.3
0x25256  ldarg.0
0x25257  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x2525c  ldarg.1
0x2525d  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_TempFileName()
0x25262  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string)
0x25267  stloc.s  7
0x25269  ldloc.s  7
0x2526b  ldc.i4.0
0x2526c  conv.i8
0x2526d  ldc.i4.0
0x2526e  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x25273  pop
0x25274  ldloc.s  7
0x25276  castclass [mscorlib]System.IO.FileStream
0x2527b  stloc.s  8
0x2527d  ldloc.s  8
0x2527f  callvirt instance class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle [mscorlib]System.IO.FileStream::get_SafeFileHandle()
0x25284  ldarg.1
0x25285  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_TempFileName()
0x2528a  newobj   instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::.ctor(class [mscorlib]System.Runtime.InteropServices.SafeHandle file, string path)
0x2528f  stloc.s  9
0x25291  ldloc.s  9
0x25293  ldc.i4.0
0x25294  callvirt instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::set_CheckHashOnly(bool value)
0x25299  ldloc.s  9
0x2529b  ldarg.0
0x2529c  call     instance bool Microsoft.VisualStudio.Setup.Security.ManifestVerifier::get_EnableRevocationChecks()
0x252a1  callvirt instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::set_EnableRevocationChecks(bool value)
0x252a6  ldsfld   native int Microsoft.VisualStudio.Setup.Security.NativeMethods::INVALID_HANDLE_VALUE
0x252ab  ldsfld   valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Security.NativeMethods::WINTRUST_ACTION_GENERIC_VERIFY_V2
0x252b0  ldloc.s  9
0x252b2  call     int32 Microsoft.VisualStudio.Setup.Security.NativeMethods::WinVerifyTrust(native int hWnd, [in] [hasfieldmarshal] valuetype [mscorlib]System.Guid pgActionID, [in] [out] [hasfieldmarshal] class Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA pWVTData)
0x252b7  stloc.3
0x252b8  ldloc.3
0x252b9  brfalse.s loc_252D5
0x252bb  ldloc.s  9
0x252bd  ldc.i4.1
0x252be  callvirt instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::set_CheckRevocationCache(bool value)
0x252c3  ldsfld   native int Microsoft.VisualStudio.Setup.Security.NativeMethods::INVALID_HANDLE_VALUE
0x252c8  ldsfld   valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Security.NativeMethods::WINTRUST_ACTION_GENERIC_VERIFY_V2
0x252cd  ldloc.s  9
0x252cf  call     int32 Microsoft.VisualStudio.Setup.Security.NativeMethods::WinVerifyTrust(native int hWnd, [in] [hasfieldmarshal] valuetype [mscorlib]System.Guid pgActionID, [in] [out] [hasfieldmarshal] class Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA pWVTData)
0x252d4  stloc.3
0x252d5  ldloc.s  9
0x252d7  callvirt instance void Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA::PrepareClose()
0x252dc  ldsfld   native int Microsoft.VisualStudio.Setup.Security.NativeMethods::INVALID_HANDLE_VALUE
0x252e1  ldsfld   valuetype [mscorlib]System.Guid Microsoft.VisualStudio.Setup.Security.NativeMethods::WINTRUST_ACTION_GENERIC_VERIFY_V2
0x252e6  ldloc.s  9
0x252e8  call     int32 Microsoft.VisualStudio.Setup.Security.NativeMethods::WinVerifyTrust(native int hWnd, [in] [hasfieldmarshal] valuetype [mscorlib]System.Guid pgActionID, [in] [out] [hasfieldmarshal] class Microsoft.VisualStudio.Setup.Security.WINTRUST_DATA pWVTData)
0x252ed  pop
0x252ee  leave.s  loc_25314
0x252f0  ldloc.s  9
0x252f2  brfalse.s loc_252FB
0x252f4  ldloc.s  9
0x252f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x252fb  endfinally
0x252fc  ldloc.s  8
0x252fe  brfalse.s loc_25307
0x25300  ldloc.s  8
0x25302  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25307  endfinally
0x25308  ldloc.s  7
0x2530a  brfalse.s loc_25313
0x2530c  ldloc.s  7
0x2530e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25313  endfinally
0x25314  ldloc.3
0x25315  brtrue   loc_253D4
0x2531a  newobj   instance void [System.Security]System.Security.Cryptography.Pkcs.SignedCms::.ctor()
0x2531f  stloc.s  0xA
0x25321  ldloc.s  0xA
0x25323  ldarg.2
0x25324  callvirt instance class Microsoft.VisualStudio.Setup.Security.Signature Microsoft.VisualStudio.Setup.Security.SignObject::get_Signature()
0x25329  callvirt instance string Microsoft.VisualStudio.Setup.Security.Signature::get_MessageValue()
0x2532e  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x25333  callvirt instance void [System.Security]System.Security.Cryptography.Pkcs.SignedCms::Decode(unsigned int8[])
0x25338  ldloc.s  0xA
0x2533a  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection [System.Security]System.Security.Cryptography.Pkcs.SignedCms::get_SignerInfos()
0x2533f  ldc.i4.0
0x25340  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.SignerInfo [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection::get_Item(int32)
0x25345  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.Security]System.Security.Cryptography.Pkcs.SignerInfo::get_Certificate()
0x2534a  stloc.s  0xB
0x2534c  ldarg.0
0x2534d  ldarg.0
0x2534e  ldarg.2
0x2534f  callvirt instance class Microsoft.VisualStudio.Setup.Security.Signature Microsoft.VisualStudio.Setup.Security.SignObject::get_Signature()
0x25354  callvirt instance class Microsoft.VisualStudio.Setup.Security.KeyInfo Microsoft.VisualStudio.Setup.Security.Signature::get_KeyInfo()
0x25359  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Security.KeyInfo::get_X509Data()
0x2535e  call     instance class [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection Microsoft.VisualStudio.Setup.Security.ManifestVerifier::GetCertListFromX509Data(class [mscorlib]System.Collections.Generic.IList`1<string> x509Data)
0x25363  ldloc.s  0xB
0x25365  call     instance bool Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckCertChain(class [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection x509Certs, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signValueCert)
0x2536a  brtrue.s loc_2538B
0x2536c  ldc.i4.3
0x2536d  stloc.0
0x2536e  ldarg.0
0x2536f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x25374  dup
0x25375  brtrue.s loc_2537A
0x25377  pop
0x25378  br.s     loc_2539F
0x2537a  ldstr    aManifestverifi_28// "ManifestVerifier ps1 cert chain Failed "...
0x2537f  call     T0x2B000003
0x25384  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x25389  br.s     loc_2539F
0x2538b  ldarg.s  4
0x2538d  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x25392  brtrue.s loc_2539F
0x25394  ldarg.0
0x25395  ldarg.s  4
0x25397  ldloc.s  0xB
0x25399  ldnull
0x2539a  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CopyCertsToLayoutFolder(string layoutCertPath, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signCertificate, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 csSignCertificate)
0x2539f  leave    loc_25473
0x253a4  stloc.s  0xC
0x253a6  ldc.i4.3
0x253a7  stloc.0
0x253a8  ldarg.0
0x253a9  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x253ae  dup
0x253af  brtrue.s loc_253B4
0x253b1  pop
0x253b2  br.s     loc_253CF
0x253b4  ldstr    aManifestverifi_29// "ManifestVerifier ps1 checking cert chai"...
0x253b9  ldloc.s  0xC
0x253bb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x253c0  call     string [mscorlib]System.String::Concat(string, string)
0x253c5  call     T0x2B000003
0x253ca  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x253cf  leave    loc_25473
0x253d4  ldarg.3
0x253d5  brtrue.s loc_25456
0x253d7  ldarg.1
0x253d8  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_Bom()
0x253dd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x253e2  brtrue.s loc_25456
0x253e4  ldloc.2
0x253e5  ldarg.1
0x253e6  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_Bom()
0x253eb  ldc.i4.5
0x253ec  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x253f1  brfalse.s loc_25456
0x253f3  ldarg.0
0x253f4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x253f9  ldarg.1
0x253fa  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_TempFileName()
0x253ff  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DeleteFile(string)
0x25404  leave.s  loc_2542F
0x25406  pop
0x25407  ldarg.0
0x25408  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x2540d  dup
0x2540e  brtrue.s loc_25413
0x25410  pop
0x25411  br.s     loc_2542D
0x25413  ldstr    aManifestverifi_30// "ManifestVerifier failed to clean up tem"...
0x25418  ldarg.1
0x25419  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_TempFileName()
0x2541e  call     string [mscorlib]System.String::Concat(string, string)
0x25423  call     T0x2B000003
0x25428  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2542d  leave.s  loc_2542F
0x2542f  ldarg.0
0x25430  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x25435  dup
0x25436  brtrue.s loc_2543B
0x25438  pop
0x25439  br.s     loc_2544A
0x2543b  ldstr    aRecheckingCata// "Rechecking catalog."
0x25440  call     T0x2B000003
0x25445  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2544a  ldarg.0
0x2544b  ldarg.1
0x2544c  ldarg.2
0x2544d  ldc.i4.1
0x2544e  ldarg.s  4
0x25450  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckPS1Authenticode(class Microsoft.VisualStudio.Setup.Security.ManifestDoc manifestDoc, class Microsoft.VisualStudio.Setup.Security.SignObject fileSignature, bool checkWithoutBom, string layoutCertPath)
0x25455  ret
0x25456  ldc.i4.2
0x25457  stloc.0
0x25458  ldarg.0
0x25459  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x2545e  dup
0x2545f  brtrue.s loc_25464
0x25461  pop
0x25462  br.s     loc_25473
0x25464  ldstr    aManifestverifi_31// "ManifestVerifier WinVerifyTrust Failed."
0x25469  call     T0x2B000003
0x2546e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x25473  nop
0x25474  ldarg.0
0x25475  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x2547a  ldarg.1
0x2547b  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_TempFileName()
0x25480  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DeleteFile(string)
0x25485  leave.s  loc_254B0
0x25487  pop
0x25488  ldarg.0
  ... truncated ...
```
