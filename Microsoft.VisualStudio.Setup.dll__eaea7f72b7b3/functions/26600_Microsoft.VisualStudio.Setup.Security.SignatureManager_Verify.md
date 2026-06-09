# Microsoft.VisualStudio.Setup.Security.SignatureManager::Verify

- ea: `0x26600`
- end: `0x267fa`
- name: `Microsoft.VisualStudio.Setup.Security.SignatureManager::Verify`
- size: `506`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xeff0`
- `0x199a0`
- `0x26600`

## string_xrefs

- `0x26623`: `verify-manifest`
- `0x26719`: `ManifestVerifier Exception`
- `0x26720`: `ManifestVerifier Exception`

## pseudocode

```c

```

## disassembly

```asm
0x26600  ldarg.1
0x26601  ldstr    aPath// "path"
0x26606  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x2660b  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::.ctor()
0x26610  dup
0x26611  ldc.i4.0
0x26612  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x26617  stloc.0
0x26618  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2661d  dup
0x2661e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::ENGINEOPERATIONTYPE
0x26623  ldstr    aVerifyManifest// "verify-manifest"
0x26628  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x2662d  stloc.1
0x2662e  ldarg.0
0x2662f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Security.SignatureManager::telemetry
0x26634  dup
0x26635  brtrue.s loc_2663B
0x26637  pop
0x26638  ldnull
0x26639  br.s     loc_26648
0x2663b  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::PACKAGEOPERATIONEVENT
0x26640  ldloc.1
0x26641  ldc.i4.0
0x26642  ldc.i4.0
0x26643  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x26648  stloc.2
0x26649  ldarg.0
0x2664a  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.SignatureManager::fileSystem
0x2664f  ldarg.1
0x26650  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x26655  brfalse  loc_26760
0x2665a  ldarg.0
0x2665b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.SignatureManager::fileSystem
0x26660  ldarg.1
0x26661  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string)
0x26666  stloc.3
0x26667  ldnull
0x26668  stloc.s  4
0x2666a  ldarg.3
0x2666b  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x26670  brtrue.s loc_26680
0x26672  ldarg.3
0x26673  ldarg.0
0x26674  ldfld    string Microsoft.VisualStudio.Setup.Security.SignatureManager::certificateSubPath
0x26679  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2667e  stloc.s  4
0x26680  ldarg.0
0x26681  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifier> Microsoft.VisualStudio.Setup.Security.SignatureManager::verifiers
0x26686  ldstr    aVsman// "vsman"
0x2668b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifier>::get_Item(void)
0x26690  ldloc.3
0x26691  castclass [mscorlib]System.IO.FileStream
0x26696  ldarg.1
0x26697  ldloc.s  4
0x26699  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifier::Verify(class [mscorlib]System.IO.FileStream, string, string)
0x2669e  stloc.0
0x2669f  ldloc.0
0x266a0  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x266a5  brfalse.s loc_266F5
0x266a7  ldloc.2
0x266a8  brfalse.s loc_266D2
0x266aa  ldloc.2
0x266ab  ldstr    a0Result1Messag// "{0} - Result: {1}; Message: {2}"
0x266b0  ldc.i4.2
0x266b1  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryEnums/OperationResult
0x266b6  ldloc.0
0x266b7  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x266bc  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x266c1  ldloc.0
0x266c2  ldc.i4.1
0x266c3  call     string Microsoft.VisualStudio.Setup.Extensions::GetNeutralMessage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation, bool information)
0x266c8  call     string [mscorlib]System.String::Format(string, object, object, object)
0x266cd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x266d2  ldloc.0
0x266d3  ldc.i4.0
0x266d4  call     string Microsoft.VisualStudio.Setup.Extensions::GetNeutralMessage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation, bool information)
0x266d9  stloc.s  5
0x266db  ldarg.0
0x266dc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.SignatureManager::log
0x266e1  dup
0x266e2  brtrue.s loc_266E7
0x266e4  pop
0x266e5  br.s     loc_2670E
0x266e7  ldloc.s  5
0x266e9  call     T0x2B000003
0x266ee  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x266f3  br.s     loc_2670E
0x266f5  ldloc.2
0x266f6  brfalse.s loc_2670E
0x266f8  ldloc.2
0x266f9  ldc.i4.1
0x266fa  stloc.s  6
0x266fc  ldloca.s 6
0x266fe  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryEnums/OperationResult
0x26704  callvirt instance string [mscorlib]System.Object::ToString()
0x26709  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x2670e  leave    loc_267F5
0x26713  stloc.s  7
0x26715  ldloc.2
0x26716  brfalse.s loc_2672B
0x26718  ldloc.2
0x26719  ldstr    aManifestverifi_36// "ManifestVerifier Exception"
0x2671e  ldloc.s  7
0x26720  ldstr    aManifestverifi_36// "ManifestVerifier Exception"
0x26725  ldc.i4.1
0x26726  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x2672b  ldarg.0
0x2672c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.SignatureManager::log
0x26731  dup
0x26732  brtrue.s loc_26737
0x26734  pop
0x26735  br.s     loc_2674A
0x26737  ldloc.s  7
0x26739  ldloc.s  7
0x2673b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x26740  call     T0x2B000003
0x26745  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2674a  ldloc.0
0x2674b  ldc.i4.6
0x2674c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x26751  leave    loc_267F5
0x26756  ldloc.3
0x26757  brfalse.s loc_2675F
0x26759  ldloc.3
0x2675a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2675f  endfinally
0x26760  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::.ctor()
0x26765  stloc.s  0xA
0x26767  ldloc.s  0xA
0x26769  ldc.i4.6
0x2676a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x2676f  ldloc.s  0xA
0x26771  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x26776  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceManager(class [mscorlib]System.Resources.ResourceManager)
0x2677b  ldloc.s  0xA
0x2677d  ldstr    aCatalogverific_0// "CatalogVerificationMissingFile_Args1"
0x26782  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceId(string)
0x26787  ldloc.s  0xA
0x26789  ldc.i4.1
0x2678a  newarr   [mscorlib]System.Object
0x2678f  dup
0x26790  ldc.i4.0
0x26791  ldarg.1
0x26792  stelem.ref
0x26793  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceArgs(object[])
0x26798  ldloc.s  0xA
0x2679a  ldc.i4.1
0x2679b  newarr   [mscorlib]System.Object
0x267a0  dup
0x267a1  ldc.i4.0
0x267a2  ldarg.1
0x267a3  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x267a8  stelem.ref
0x267a9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_TelemetryResourceArgs(object[])
0x267ae  ldloc.s  0xA
0x267b0  stloc.0
0x267b1  ldloc.0
0x267b2  ldc.i4.1
0x267b3  call     string Microsoft.VisualStudio.Setup.Extensions::GetNeutralMessage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation, bool information)
0x267b8  stloc.s  8
0x267ba  ldloc.2
0x267bb  brfalse.s loc_267C5
0x267bd  ldloc.2
0x267be  ldloc.s  8
0x267c0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x267c5  ldloc.0
0x267c6  ldc.i4.0
0x267c7  call     string Microsoft.VisualStudio.Setup.Extensions::GetNeutralMessage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation, bool information)
0x267cc  stloc.s  9
0x267ce  ldarg.0
0x267cf  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.SignatureManager::log
0x267d4  dup
0x267d5  brtrue.s loc_267DA
0x267d7  pop
0x267d8  br.s     loc_267E6
0x267da  ldloc.s  9
0x267dc  call     T0x2B000003
0x267e1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x267e6  ldloc.0
0x267e7  stloc.s  0xA
0x267e9  leave.s  loc_267F7
0x267eb  ldloc.2
0x267ec  brfalse.s loc_267F4
0x267ee  ldloc.2
0x267ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x267f4  endfinally
0x267f5  ldloc.0
0x267f6  ret
0x267f7  ldloc.s  0xA
0x267f9  ret
```
