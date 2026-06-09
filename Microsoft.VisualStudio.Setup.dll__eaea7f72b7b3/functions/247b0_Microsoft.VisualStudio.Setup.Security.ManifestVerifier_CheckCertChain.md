# Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckCertChain

- ea: `0x247b0`
- end: `0x248c2`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckCertChain`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x24b00`
- `0x25140`

## callees

- `0x247b0`
- `0x248d0`
- `0x249b0`

## string_xrefs

- `0x247c8`: `ManifestVerifier x509Data certificate data is missing.`
- `0x247fe`: `ManifestVerifier signing certificate does not match x509Data certificate.`
- `0x2486c`: `ManifestVerifier failed. Falling back to checking machine store.`
- `0x248ac`: `ManifestVerifier exception building chain.`

## pseudocode

```c

```

## disassembly

```asm
0x247b0  ldarg.1
0x247b1  brfalse.s loc_247BC
0x247b3  ldarg.1
0x247b4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x247b9  ldc.i4.1
0x247ba  bge.s    loc_247D9
0x247bc  ldarg.0
0x247bd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x247c2  dup
0x247c3  brtrue.s loc_247C8
0x247c5  pop
0x247c6  br.s     loc_247D7
0x247c8  ldstr    aManifestverifi_8// "ManifestVerifier x509Data certificate d"...
0x247cd  call     T0x2B000003
0x247d2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x247d7  ldc.i4.0
0x247d8  ret
0x247d9  ldarg.1
0x247da  ldc.i4.0
0x247db  callvirt instance class [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection::get_Item(int32)
0x247e0  isinst   [System]System.Security.Cryptography.X509Certificates.X509Certificate2
0x247e5  stloc.0
0x247e6  ldarg.2
0x247e7  brfalse.s loc_2480F
0x247e9  ldarg.2
0x247ea  ldloc.0
0x247eb  callvirt instance bool [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::Equals(class [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate)
0x247f0  brtrue.s loc_2480F
0x247f2  ldarg.0
0x247f3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x247f8  dup
0x247f9  brtrue.s loc_247FE
0x247fb  pop
0x247fc  br.s     loc_2480D
0x247fe  ldstr    aManifestverifi_9// "ManifestVerifier signing certificate do"...
0x24803  call     T0x2B000003
0x24808  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2480d  ldc.i4.0
0x2480e  ret
0x2480f  ldarg.0
0x24810  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService Microsoft.VisualStudio.Setup.Security.ManifestVerifier::settings
0x24815  brfalse.s loc_24824
0x24817  ldarg.0
0x24818  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService Microsoft.VisualStudio.Setup.Security.ManifestVerifier::settings
0x2481d  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ISettingsService::get_NoWeb()
0x24822  br.s     loc_24825
0x24824  ldc.i4.0
0x24825  stloc.1
0x24826  ldc.i4.0
0x24827  stloc.2
0x24828  ldarg.0
0x24829  ldarg.1
0x2482a  ldloc.2
0x2482b  ldloc.1
0x2482c  call     instance class [System]System.Security.Cryptography.X509Certificates.X509Chain Microsoft.VisualStudio.Setup.Security.ManifestVerifier::ConfigureChainForBuilding(class [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection x509Certs, bool checkMachineCerts, bool isOfflineRevocation)
0x24831  stloc.3
0x24832  ldloc.3
0x24833  ldloc.0
0x24834  callvirt instance bool [System]System.Security.Cryptography.X509Certificates.X509Chain::Build(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x24839  brfalse.s loc_24840
0x2483b  ldc.i4.1
0x2483c  stloc.s  4
0x2483e  leave.s  loc_248BF
0x24840  ldarg.0
0x24841  ldloc.3
0x24842  callvirt instance valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatus[] [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainStatus()
0x24847  call     instance valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatusFlags Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckChainStatusFlags(valuetype [System]System.Security.Cryptography.X509Certificates.X509ChainStatus[] certChainStatus)
0x2484c  stloc.s  5
0x2484e  ldloc.s  5
0x24850  brtrue.s loc_24857
0x24852  ldc.i4.1
0x24853  stloc.s  4
0x24855  leave.s  loc_248BF
0x24857  ldloc.s  5
0x24859  ldc.i4   0x10000
0x2485e  bne.un.s loc_2489A
0x24860  ldarg.0
0x24861  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24866  dup
0x24867  brtrue.s loc_2486C
0x24869  pop
0x2486a  br.s     loc_2487B
0x2486c  ldstr    aManifestverifi_10// "ManifestVerifier failed. Falling back t"...
0x24871  call     T0x2B000003
0x24876  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2487b  ldc.i4.1
0x2487c  stloc.2
0x2487d  ldarg.0
0x2487e  ldarg.1
0x2487f  ldloc.2
0x24880  ldloc.1
0x24881  call     instance class [System]System.Security.Cryptography.X509Certificates.X509Chain Microsoft.VisualStudio.Setup.Security.ManifestVerifier::ConfigureChainForBuilding(class [System]System.Security.Cryptography.X509Certificates.X509CertificateCollection x509Certs, bool checkMachineCerts, bool isOfflineRevocation)
0x24886  stloc.3
0x24887  ldloc.3
0x24888  ldloc.0
0x24889  callvirt instance bool [System]System.Security.Cryptography.X509Certificates.X509Chain::Build(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x2488e  brfalse.s loc_24895
0x24890  ldc.i4.1
0x24891  stloc.s  4
0x24893  leave.s  loc_248BF
0x24895  ldc.i4.0
0x24896  stloc.s  4
0x24898  leave.s  loc_248BF
0x2489a  leave.s  loc_248BD
0x2489c  stloc.s  6
0x2489e  ldarg.0
0x2489f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x248a4  dup
0x248a5  brtrue.s loc_248AA
0x248a7  pop
0x248a8  br.s     loc_248BB
0x248aa  ldloc.s  6
0x248ac  ldstr    aManifestverifi_11// "ManifestVerifier exception building cha"...
0x248b1  call     T0x2B000003
0x248b6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x248bb  leave.s  loc_248BD
0x248bd  ldc.i4.0
0x248be  ret
0x248bf  ldloc.s  4
0x248c1  ret
```
