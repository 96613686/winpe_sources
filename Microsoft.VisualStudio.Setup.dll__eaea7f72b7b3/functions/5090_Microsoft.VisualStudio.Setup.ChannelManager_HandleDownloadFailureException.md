# Microsoft.VisualStudio.Setup.ChannelManager::HandleDownloadFailureException

- ea: `0x5090`
- end: `0x512d`
- name: `Microsoft.VisualStudio.Setup.ChannelManager::HandleDownloadFailureException`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x63c70`
- `0x65d90`

## callees

- `0x5090`
- `0x5180`
- `0xe2f0`
- `0x199a0`

## string_xrefs

- `0x50c1`: `https://aka.ms/vspreinstall`
- `0x50df`: `https://aka.ms/vspreinstall`
- `0x50aa`: `ChannelManifestTestSignatureVerificationFailed_Args1`
- `0x50d2`: `ChannelManifestTestSignatureVerificationFailed_Args1`
- `0x50fe`: `The channel manifest failed signature validation. Verification result: '{0}.'`
- `0x511d`: `ChannelManifestSignatureVerificationFailed`

## pseudocode

```c

```

## disassembly

```asm
0x5090  ldarg.0
0x5091  ldarg.2
0x5092  call     instance bool Microsoft.VisualStudio.Setup.ChannelManager::IsVerificationResultInvalidTestCertificate(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.InvalidSignatureException ex)
0x5097  brfalse.s loc_50EB
0x5099  ldarg.0
0x509a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x509f  dup
0x50a0  brtrue.s loc_50A5
0x50a2  pop
0x50a3  br.s     loc_50CC
0x50a5  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x50aa  ldstr    aChannelmanifes_1// "ChannelManifestTestSignatureVerificatio"...
0x50af  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x50b4  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x50b9  ldc.i4.1
0x50ba  newarr   [mscorlib]System.Object
0x50bf  dup
0x50c0  ldc.i4.0
0x50c1  ldstr    aHttpsAkaMsVspr// "https://aka.ms/vspreinstall"
0x50c6  stelem.ref
0x50c7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x50cc  ldarg.1
0x50cd  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x50d2  ldstr    aChannelmanifes_1// "ChannelManifestTestSignatureVerificatio"...
0x50d7  ldc.i4.1
0x50d8  newarr   [mscorlib]System.Object
0x50dd  dup
0x50de  ldc.i4.0
0x50df  ldstr    aHttpsAkaMsVspr// "https://aka.ms/vspreinstall"
0x50e4  stelem.ref
0x50e5  newobj   instance void Microsoft.VisualStudio.Setup.ChannelManifestDownloadException::.ctor(class [mscorlib]System.Exception innerException, class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x50ea  throw
0x50eb  ldarg.2
0x50ec  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.InvalidSignatureException::get_Result()
0x50f1  stloc.0
0x50f2  ldarg.0
0x50f3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ChannelManager::logger
0x50f8  dup
0x50f9  brtrue.s loc_50FE
0x50fb  pop
0x50fc  br.s     loc_5117
0x50fe  ldstr    aTheChannelMani// "The channel manifest failed signature v"...
0x5103  ldc.i4.1
0x5104  newarr   [mscorlib]System.Object
0x5109  dup
0x510a  ldc.i4.0
0x510b  ldloc.0
0x510c  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x5111  stelem.ref
0x5112  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x5117  ldarg.1
0x5118  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x511d  ldstr    aChannelmanifes_2// "ChannelManifestSignatureVerificationFai"...
0x5122  call     T0x2B000003
0x5127  newobj   instance void Microsoft.VisualStudio.Setup.ChannelManifestDownloadException::.ctor(class [mscorlib]System.Exception innerException, class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x512c  throw
```
