# Microsoft.VisualStudio.Setup.Validation.ExperimentValidator::CheckSignature

- ea: `0x1fac0`
- end: `0x1fb90`
- name: `Microsoft.VisualStudio.Setup.Validation.ExperimentValidator::CheckSignature`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1fa80`

## callees

- `0x199a0`
- `0x1fac0`
- `0x21b80`
- `0x21c90`

## string_xrefs

- `0x1fb0d`: `https://aka.ms/vspreinstall`
- `0x1fb00`: `ManifestTestSignFail_Args1`
- `0x1fb32`: `ManifestSignatureVerificationFailed`

## pseudocode

```c

```

## disassembly

```asm
0x1fac0  ldarg.0
0x1fac1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Validation.ExperimentValidator::logger
0x1fac6  dup
0x1fac7  brtrue.s loc_1FACC
0x1fac9  pop
0x1faca  br.s     loc_1FADB
0x1facc  ldstr    aCheckingThatTh// "Checking that the catalog is signed by "...
0x1fad1  call     T0x2B000003
0x1fad6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1fadb  ldarg.0
0x1fadc  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Validation.ExperimentValidator::services
0x1fae1  ldc.i4.1
0x1fae2  call     T0x2B000011
0x1fae7  stloc.0
0x1fae8  ldloc.0
0x1fae9  ldarg.1
0x1faea  ldarg.2
0x1faeb  ldnull
0x1faec  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager::Verify(class [mscorlib]System.IO.Stream, string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext)
0x1faf1  stloc.1
0x1faf2  ldloc.1
0x1faf3  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x1faf8  ldc.i4.4
0x1faf9  bne.un.s loc_1FB25
0x1fafb  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x1fb00  ldstr    aManifesttestsi// "ManifestTestSignFail_Args1"
0x1fb05  ldc.i4.1
0x1fb06  newarr   [mscorlib]System.Object
0x1fb0b  dup
0x1fb0c  ldc.i4.0
0x1fb0d  ldstr    aHttpsAkaMsVspr// "https://aka.ms/vspreinstall"
0x1fb12  stelem.ref
0x1fb13  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x1fb18  dup
0x1fb19  ldarg.0
0x1fb1a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog Microsoft.VisualStudio.Setup.Validation.ExperimentValidator::catalog
0x1fb1f  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_Manifest(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest value)
0x1fb24  ret
0x1fb25  ldloc.1
0x1fb26  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x1fb2b  brfalse.s loc_1FB4E
0x1fb2d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x1fb32  ldstr    aManifestsignat// "ManifestSignatureVerificationFailed"
0x1fb37  call     T0x2B000003
0x1fb3c  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x1fb41  dup
0x1fb42  ldarg.0
0x1fb43  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog Microsoft.VisualStudio.Setup.Validation.ExperimentValidator::catalog
0x1fb48  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_Manifest(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest value)
0x1fb4d  ret
0x1fb4e  ldloc.1
0x1fb4f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Signers()
0x1fb54  dup
0x1fb55  brtrue.s loc_1FB5B
0x1fb57  pop
0x1fb58  ldnull
0x1fb59  br.s     loc_1FB60
0x1fb5b  call     T0x2B0000BE
0x1fb60  stloc.2
0x1fb61  ldloc.2
0x1fb62  brfalse.s loc_1FB6D
0x1fb64  ldloc.0
0x1fb65  ldloc.2
0x1fb66  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager::IsMicrosoftSubjectName(string)
0x1fb6b  brtrue.s loc_1FB8E
0x1fb6d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x1fb72  ldstr    aCatalognotfrom// "CatalogNotFromMicrosoft"
0x1fb77  call     T0x2B000003
0x1fb7c  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x1fb81  dup
0x1fb82  ldarg.0
0x1fb83  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog Microsoft.VisualStudio.Setup.Validation.ExperimentValidator::catalog
0x1fb88  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_Manifest(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IManifest value)
0x1fb8d  ret
0x1fb8e  ldnull
0x1fb8f  ret
```
