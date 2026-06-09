# Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CopyCertsToLayoutFolder

- ea: `0x254c0`
- end: `0x255aa`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CopyCertsToLayoutFolder`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x24b00`
- `0x25140`

## callees

- `0x10270`
- `0x254c0`
- `0x255b0`

## string_xrefs

- `0x254dc`: `ManifestVerifier Exception creating directory for manifest root certificate.`
- `0x25527`: `ManifestVerifier Exception creating Manifest Signing certificate file: `
- `0x25591`: `ManifestVerifier Exception creating Manifest CounterSigning certificate file: `

## pseudocode

```c

```

## disassembly

```asm
0x254c0  ldarg.0
0x254c1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x254c6  ldarg.1
0x254c7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x254cc  leave.s  loc_254F0
0x254ce  stloc.2
0x254cf  ldarg.0
0x254d0  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x254d5  dup
0x254d6  brtrue.s loc_254DB
0x254d8  pop
0x254d9  br.s     loc_254EB
0x254db  ldloc.2
0x254dc  ldstr    aManifestverifi_32// "ManifestVerifier Exception creating dir"...
0x254e1  call     T0x2B000003
0x254e6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x254eb  leave    loc_255A9
0x254f0  ldarg.0
0x254f1  ldarg.2
0x254f2  call     instance unsigned int8[] Microsoft.VisualStudio.Setup.Security.ManifestVerifier::GetRootCertificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x254f7  stloc.0
0x254f8  ldnull
0x254f9  stloc.1
0x254fa  ldloc.0
0x254fb  brfalse.s loc_2553E
0x254fd  ldarg.1
0x254fe  ldarg.0
0x254ff  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestVerifier::manifestSignRootCert
0x25504  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x25509  stloc.1
0x2550a  ldarg.0
0x2550b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x25510  ldloc.1
0x25511  ldloc.0
0x25512  call     void Microsoft.VisualStudio.Setup.Extensions::WriteAllBytes(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, unsigned int8[] buffer)
0x25517  leave.s  loc_2553E
0x25519  stloc.3
0x2551a  ldarg.0
0x2551b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x25520  dup
0x25521  brtrue.s loc_25526
0x25523  pop
0x25524  br.s     loc_2553C
0x25526  ldloc.3
0x25527  ldstr    aManifestverifi_33// "ManifestVerifier Exception creating Man"...
0x2552c  ldloc.1
0x2552d  call     string [mscorlib]System.String::Concat(string, string)
0x25532  call     T0x2B000003
0x25537  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2553c  leave.s  loc_255A9
0x2553e  ldarg.3
0x2553f  brfalse.s loc_255A9
0x25541  ldarg.3
0x25542  callvirt instance native int [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::get_Handle()
0x25547  stloc.s  4
0x25549  ldloca.s 4
0x2554b  call     instance int64 [mscorlib]System.IntPtr::ToInt64()
0x25550  brfalse.s loc_255A9
0x25552  ldarg.0
0x25553  ldarg.3
0x25554  call     instance unsigned int8[] Microsoft.VisualStudio.Setup.Security.ManifestVerifier::GetRootCertificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x25559  stloc.s  5
0x2555b  ldnull
0x2555c  stloc.s  6
0x2555e  ldloc.s  5
0x25560  brfalse.s loc_255A9
0x25562  ldarg.1
0x25563  ldarg.0
0x25564  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestVerifier::manifestCounterSignRootCert
0x25569  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2556e  stloc.s  6
0x25570  ldarg.0
0x25571  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x25576  ldloc.s  6
0x25578  ldloc.s  5
0x2557a  call     void Microsoft.VisualStudio.Setup.Extensions::WriteAllBytes(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, unsigned int8[] buffer)
0x2557f  leave.s  loc_255A9
0x25581  stloc.s  7
0x25583  ldarg.0
0x25584  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x25589  dup
0x2558a  brtrue.s loc_2558F
0x2558c  pop
0x2558d  br.s     loc_255A7
0x2558f  ldloc.s  7
0x25591  ldstr    aManifestverifi_34// "ManifestVerifier Exception creating Man"...
0x25596  ldloc.s  6
0x25598  call     string [mscorlib]System.String::Concat(string, string)
0x2559d  call     T0x2B000003
0x255a2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x255a7  leave.s  loc_255A9
0x255a9  ret
```
