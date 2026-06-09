# Microsoft.VisualStudio.Setup.Security.ManifestVerifier::SignedCmsValidate

- ea: `0x24f30`
- end: `0x25024`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestVerifier::SignedCmsValidate`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x24b00`

## callees

- `0x24f30`

## string_xrefs

- `0x24f9f`: `ManifestVerifier Exception decoding signature value; `
- `0x24fde`: `ManifestVerifier signature message validation failed.`
- `0x2500e`: `ManifestVerifier Certificate thumbprint validation failed.`

## pseudocode

```c

```

## disassembly

```asm
0x24f30  ldarg.1
0x24f31  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x24f36  brfalse.s loc_24F3A
0x24f38  ldc.i4.0
0x24f39  ret
0x24f3a  ldarg.1
0x24f3b  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x24f40  stloc.0
0x24f41  newobj   instance void [System.Security]System.Security.Cryptography.Pkcs.SignedCms::.ctor()
0x24f46  stloc.1
0x24f47  ldloc.1
0x24f48  ldloc.0
0x24f49  callvirt instance void [System.Security]System.Security.Cryptography.Pkcs.SignedCms::Decode(unsigned int8[])
0x24f4e  ldloc.1
0x24f4f  ldc.i4.1
0x24f50  callvirt instance void [System.Security]System.Security.Cryptography.Pkcs.SignedCms::CheckSignature(bool)
0x24f55  ldloc.1
0x24f56  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.ContentInfo [System.Security]System.Security.Cryptography.Pkcs.SignedCms::get_ContentInfo()
0x24f5b  callvirt instance unsigned int8[] [System.Security]System.Security.Cryptography.Pkcs.ContentInfo::get_Content()
0x24f60  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x24f65  stloc.3
0x24f66  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0x24f6b  ldloc.1
0x24f6c  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.ContentInfo [System.Security]System.Security.Cryptography.Pkcs.SignedCms::get_ContentInfo()
0x24f71  callvirt instance unsigned int8[] [System.Security]System.Security.Cryptography.Pkcs.ContentInfo::get_Content()
0x24f76  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x24f7b  stloc.s  4
0x24f7d  ldloc.1
0x24f7e  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection [System.Security]System.Security.Cryptography.Pkcs.SignedCms::get_SignerInfos()
0x24f83  ldc.i4.0
0x24f84  callvirt instance class [System.Security]System.Security.Cryptography.Pkcs.SignerInfo [System.Security]System.Security.Cryptography.Pkcs.SignerInfoCollection::get_Item(int32)
0x24f89  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.Security]System.Security.Cryptography.Pkcs.SignerInfo::get_Certificate()
0x24f8e  stloc.2
0x24f8f  leave.s  loc_24FBF
0x24f91  stloc.s  5
0x24f93  ldarg.0
0x24f94  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24f99  dup
0x24f9a  brtrue.s loc_24F9F
0x24f9c  pop
0x24f9d  br.s     loc_24FBA
0x24f9f  ldstr    aManifestverifi_20// "ManifestVerifier Exception decoding sig"...
0x24fa4  ldloc.s  5
0x24fa6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24fab  call     string [mscorlib]System.String::Concat(string, string)
0x24fb0  call     T0x2B000003
0x24fb5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x24fba  ldc.i4.0
0x24fbb  stloc.s  6
0x24fbd  leave.s  loc_25021
0x24fbf  ldloc.3
0x24fc0  ldarg.2
0x24fc1  callvirt instance bool [mscorlib]System.String::Equals(string)
0x24fc6  brtrue.s loc_24FEF
0x24fc8  ldloc.s  4
0x24fca  ldarg.2
0x24fcb  callvirt instance bool [mscorlib]System.String::Contains(string)
0x24fd0  brtrue.s loc_24FEF
0x24fd2  ldarg.0
0x24fd3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x24fd8  dup
0x24fd9  brtrue.s loc_24FDE
0x24fdb  pop
0x24fdc  br.s     loc_24FED
0x24fde  ldstr    aManifestverifi_21// "ManifestVerifier signature message vali"...
0x24fe3  call     T0x2B000003
0x24fe8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x24fed  ldc.i4.0
0x24fee  ret
0x24fef  ldloc.2
0x24ff0  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x24ff5  ldarg.3
0x24ff6  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x24ffb  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x25000  brfalse.s loc_2501F
0x25002  ldarg.0
0x25003  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x25008  dup
0x25009  brtrue.s loc_2500E
0x2500b  pop
0x2500c  br.s     loc_2501D
0x2500e  ldstr    aManifestverifi_22// "ManifestVerifier Certificate thumbprint"...
0x25013  call     T0x2B000003
0x25018  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2501d  ldc.i4.0
0x2501e  ret
0x2501f  ldc.i4.1
0x25020  ret
0x25021  ldloc.s  6
0x25023  ret
```
