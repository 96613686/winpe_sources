# Microsoft.VisualStudio.Setup.Security.ManifestVerifier::GetSigner

- ea: `0x24640`
- end: `0x247a3`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestVerifier::GetSigner`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x23880`
- `0x23910`
- `0x24640`
- `0x24a90`
- `0x27100`
- `0x27180`
- `0x271c0`
- `0x27300`
- `0x27450`

## string_xrefs

- `0x2466e`: `ManifestVerifier cannot load Manifest: {0}`
- `0x246a7`: `Manifest '{0}' not signed.`
- `0x246dd`: `ManifestVerifier deserialize failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x24640  ldarg.1
0x24641  ldstr    aFile// "file"
0x24646  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x2464b  ldarg.2
0x2464c  ldstr    aPath// "path"
0x24651  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x24656  ldnull
0x24657  stloc.0
0x24658  ldarg.1
0x24659  newobj   instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::.ctor(class [mscorlib]System.IO.FileStream fileStream)
0x2465e  stloc.1
0x2465f  leave.s  loc_2468E
0x24661  stloc.2
0x24662  ldarg.0
0x24663  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24668  dup
0x24669  brtrue.s loc_2466E
0x2466b  pop
0x2466c  br.s     loc_24687
0x2466e  ldstr    aManifestverifi_6// "ManifestVerifier cannot load Manifest: "...
0x24673  ldc.i4.1
0x24674  newarr   [mscorlib]System.Object
0x24679  dup
0x2467a  ldc.i4.0
0x2467b  ldloc.2
0x2467c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24681  stelem.ref
0x24682  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x24687  ldloc.0
0x24688  stloc.3
0x24689  leave    loc_247A1
0x2468e  ldloc.1
0x2468f  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_SignatureBlob()
0x24694  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x24699  brfalse.s loc_246BD
0x2469b  ldarg.0
0x2469c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x246a1  dup
0x246a2  brtrue.s loc_246A7
0x246a4  pop
0x246a5  br.s     loc_246BB
0x246a7  ldstr    aManifest0NotSi// "Manifest '{0}' not signed."
0x246ac  ldc.i4.1
0x246ad  newarr   [mscorlib]System.Object
0x246b2  dup
0x246b3  ldc.i4.0
0x246b4  ldarg.2
0x246b5  stelem.ref
0x246b6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x246bb  ldloc.0
0x246bc  ret
0x246bd  nop
0x246be  ldloc.1
0x246bf  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_SignatureBlob()
0x246c4  call     T0x2B000152
0x246c9  stloc.s  4
0x246cb  leave.s  loc_246FE
0x246cd  stloc.s  5
0x246cf  ldarg.0
0x246d0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x246d5  dup
0x246d6  brtrue.s loc_246DB
0x246d8  pop
0x246d9  br.s     loc_246F7
0x246db  ldloc.s  5
0x246dd  ldstr    aManifestverifi_7// "ManifestVerifier deserialize failed: {0"...
0x246e2  ldc.i4.1
0x246e3  newarr   [mscorlib]System.Object
0x246e8  dup
0x246e9  ldc.i4.0
0x246ea  ldloc.s  5
0x246ec  callvirt instance string [mscorlib]System.Exception::get_Message()
0x246f1  stelem.ref
0x246f2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x246f7  ldloc.0
0x246f8  stloc.3
0x246f9  leave    loc_247A1
0x246fe  ldloc.s  4
0x24700  brtrue.s loc_24704
0x24702  ldloc.0
0x24703  ret
0x24704  nop
0x24705  ldloc.s  4
0x24707  callvirt instance class Microsoft.VisualStudio.Setup.Security.Signature Microsoft.VisualStudio.Setup.Security.SignObject::get_Signature()
0x2470c  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24711  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestMethod()
0x24716  ldstr    aPkcs// "pkcs"
0x2471b  ldc.i4.5
0x2471c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x24721  brtrue.s loc_2476D
0x24723  ldloc.s  4
0x24725  callvirt instance class Microsoft.VisualStudio.Setup.Security.Signature Microsoft.VisualStudio.Setup.Security.SignObject::get_Signature()
0x2472a  stloc.s  6
0x2472c  ldarg.0
0x2472d  ldloc.s  6
0x2472f  callvirt instance class Microsoft.VisualStudio.Setup.Security.KeyInfo Microsoft.VisualStudio.Setup.Security.Signature::get_KeyInfo()
0x24734  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.VisualStudio.Setup.Security.KeyInfo::get_X509Data()
0x24739  call     instance class [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection Microsoft.VisualStudio.Setup.Security.ManifestVerifier::GetCertListFromX509Data(class [mscorlib]System.Collections.Generic.IList`1<string> x509Data)
0x2473e  dup
0x2473f  brtrue.s loc_24745
0x24741  pop
0x24742  ldnull
0x24743  br.s     loc_24754
0x24745  call     T0x2B000153
0x2474a  call     T0x2B000154
0x2474f  callvirt instance string [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::get_Subject()
0x24754  stloc.s  7
0x24756  ldloc.s  7
0x24758  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2475d  brtrue.s loc_2476D
0x2475f  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Signer::.ctor()
0x24764  dup
0x24765  ldloc.s  7
0x24767  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Signer::set_SubjectName(string)
0x2476c  stloc.0
0x2476d  leave.s  loc_2479F
0x2476f  stloc.s  8
0x24771  ldarg.0
0x24772  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24777  dup
0x24778  brtrue.s loc_2477D
0x2477a  pop
0x2477b  br.s     loc_2479B
0x2477d  ldstr    aFailedToGetSig_0// "Failed to get signer for '{0}': {1}"
0x24782  ldc.i4.2
0x24783  newarr   [mscorlib]System.Object
0x24788  dup
0x24789  ldc.i4.0
0x2478a  ldarg.2
0x2478b  stelem.ref
0x2478c  dup
0x2478d  ldc.i4.1
0x2478e  ldloc.s  8
0x24790  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24795  stelem.ref
0x24796  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2479b  ldloc.0
0x2479c  stloc.3
0x2479d  leave.s  loc_247A1
0x2479f  ldloc.0
0x247a0  ret
0x247a1  ldloc.3
0x247a2  ret
```
