# Microsoft.VisualStudio.Setup.Security.SignatureManager::Verify_0

- ea: `0x26800`
- end: `0x26bc6`
- name: `Microsoft.VisualStudio.Setup.Security.SignatureManager::Verify_0`
- size: `966`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0xeff0`
- `0x10ea0`
- `0x199a0`
- `0x26800`
- `0x26c80`
- `0x26d40`

## string_xrefs

- `0x26b2c`: `CancelledDuringVerification`
- `0x2685f`: `Path is Null for package: {0}`
- `0x268f8`: `Checking SHA256 for path: `
- `0x26952`: `Falling back to multiple hashes check because verification returned {0} for path: {1}`
- `0x269cc`: `Falling back to signature and signer check because hash verification returned {0} for path: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x26800  ldarg.1
0x26801  ldstr    aFile// "file"
0x26806  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x2680b  ldarg.1
0x2680c  isinst   [mscorlib]System.IO.FileStream
0x26811  stloc.0
0x26812  ldloc.0
0x26813  brtrue.s loc_26825
0x26815  ldstr    aTheStreamDoesN// "The stream does not represent a file."
0x2681a  ldstr    aFile// "file"
0x2681f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x26824  throw
0x26825  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::.ctor()
0x2682a  dup
0x2682b  ldc.i4.2
0x2682c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x26831  stloc.1
0x26832  ldarg.2
0x26833  brtrue.s loc_2684D
0x26835  ldloc.0
0x26836  call     string Microsoft.VisualStudio.Setup.Extensions::GetFilePath(class [mscorlib]System.IO.FileStream fileStream)
0x2683b  stloc.2
0x2683c  ldarg.0
0x2683d  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.SignatureManager::fileSystem
0x26842  ldloc.2
0x26843  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x26848  brfalse.s loc_2684D
0x2684a  ldloc.2
0x2684b  starg.s  2
0x2684d  ldarg.2
0x2684e  brtrue.s loc_2689A
0x26850  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x26855  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VERIFYPACKAGEMESSAGE
0x2685a  stloc.s  4
0x2685c  dup
0x2685d  ldloc.s  4
0x2685f  ldstr    aPathIsNullForP// "Path is Null for package: {0}"
0x26864  ldarg.3
0x26865  brtrue.s loc_2686A
0x26867  ldnull
0x26868  br.s     loc_26870
0x2686a  ldarg.3
0x2686b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext::get_Package()
0x26870  call     string [mscorlib]System.String::Format(string, object)
0x26875  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2687a  stloc.3
0x2687b  ldarg.0
0x2687c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Security.SignatureManager::telemetry
0x26881  dup
0x26882  brtrue.s loc_26887
0x26884  pop
0x26885  br.s     loc_26894
0x26887  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VERIFYFAILUREEVENT
0x2688c  ldloc.3
0x2688d  ldnull
0x2688e  ldc.i4.0
0x2688f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x26894  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x26899  throw
0x2689a  nop
0x2689b  ldarg.3
0x2689c  brtrue.s loc_268A1
0x2689e  ldnull
0x2689f  br.s     loc_268A7
0x268a1  ldarg.3
0x268a2  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext::get_Package()
0x268a7  stloc.s  5
0x268a9  ldloc.s  5
0x268ab  call     valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PartialManifestType> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::GetManifestType(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage)
0x268b0  stloc.s  6
0x268b2  ldarg.3
0x268b3  brtrue.s loc_268B8
0x268b5  ldnull
0x268b6  br.s     loc_268BE
0x268b8  ldarg.3
0x268b9  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext::get_Sha256()
0x268be  stloc.s  7
0x268c0  ldarg.3
0x268c1  brtrue.s loc_268C6
0x268c3  ldnull
0x268c4  br.s     loc_268CC
0x268c6  ldarg.3
0x268c7  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext::get_Hashes()
0x268cc  stloc.s  8
0x268ce  ldloc.s  7
0x268d0  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x268d5  brfalse.s loc_268E3
0x268d7  ldloc.s  8
0x268d9  call     T0x2B0000B4
0x268de  brtrue   loc_269FB
0x268e3  ldloc.s  7
0x268e5  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x268ea  brtrue.s loc_26918
0x268ec  ldarg.0
0x268ed  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.SignatureManager::log
0x268f2  dup
0x268f3  brtrue.s loc_268F8
0x268f5  pop
0x268f6  br.s     loc_2690D
0x268f8  ldstr    aCheckingSha256// "Checking SHA256 for path: "
0x268fd  ldarg.2
0x268fe  call     string [mscorlib]System.String::Concat(string, string)
0x26903  call     T0x2B000003
0x26908  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2690d  ldarg.0
0x2690e  ldloc.0
0x2690f  ldloc.s  7
0x26911  ldarg.2
0x26912  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation Microsoft.VisualStudio.Setup.Security.SignatureManager::VerifySha256(class [mscorlib]System.IO.FileStream fileStream, string expected, string path)
0x26917  stloc.1
0x26918  ldloc.1
0x26919  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x2691e  brfalse.s loc_2699C
0x26920  ldloc.s  8
0x26922  call     T0x2B0000B4
0x26927  brtrue.s loc_2699C
0x26929  ldloc.s  8
0x2692b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x26930  stloc.s  9
0x26932  br.s     loc_26985
0x26934  ldloc.s  9
0x26936  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x2693b  stloc.s  0xA
0x2693d  ldloc.s  0xA
0x2693f  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x26944  brtrue.s loc_2697D
0x26946  ldarg.0
0x26947  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.SignatureManager::log
0x2694c  dup
0x2694d  brtrue.s loc_26952
0x2694f  pop
0x26950  br.s     loc_26972
0x26952  ldstr    aFallingBackToM// "Falling back to multiple hashes check b"...
0x26957  ldloc.1
0x26958  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x2695d  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x26962  ldarg.2
0x26963  call     string [mscorlib]System.String::Format(string, object, object)
0x26968  call     T0x2B000003
0x2696d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x26972  ldarg.0
0x26973  ldloc.0
0x26974  ldloc.s  0xA
0x26976  ldarg.2
0x26977  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation Microsoft.VisualStudio.Setup.Security.SignatureManager::VerifySha256(class [mscorlib]System.IO.FileStream fileStream, string expected, string path)
0x2697c  stloc.1
0x2697d  ldloc.1
0x2697e  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x26983  brfalse.s loc_2698E
0x26985  ldloc.s  9
0x26987  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2698c  brtrue.s loc_26934
0x2698e  leave.s  loc_2699C
0x26990  ldloc.s  9
0x26992  brfalse.s loc_2699B
0x26994  ldloc.s  9
0x26996  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2699b  endfinally
0x2699c  ldloc.1
0x2699d  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x269a2  brfalse  loc_26A94
0x269a7  ldarg.0
0x269a8  ldfld    bool Microsoft.VisualStudio.Setup.Security.SignatureManager::fallbackToSignature
0x269ad  brtrue.s loc_269C0
0x269af  ldarg.3
0x269b0  brfalse  loc_26A94
0x269b5  ldarg.3
0x269b6  call     instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext::get_IsDynamicEndpoint()
0x269bb  brfalse  loc_26A94
0x269c0  ldarg.0
0x269c1  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.SignatureManager::log
0x269c6  dup
0x269c7  brtrue.s loc_269CC
0x269c9  pop
0x269ca  br.s     loc_269EC
0x269cc  ldstr    aFallingBackToS// "Falling back to signature and signer ch"...
0x269d1  ldloc.1
0x269d2  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x269d7  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x269dc  ldarg.2
0x269dd  call     string [mscorlib]System.String::Format(string, object, object)
0x269e2  call     T0x2B000003
0x269e7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x269ec  ldarg.0
0x269ed  ldloc.0
0x269ee  ldarg.2
0x269ef  ldarg.3
0x269f0  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation Microsoft.VisualStudio.Setup.Security.SignatureManager::VerifySignatureAndSigner(class [mscorlib]System.IO.FileStream fileStream, string path, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext verificationContext)
0x269f5  stloc.1
0x269f6  br       loc_26A94
0x269fb  ldloca.s 6
0x269fd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PartialManifestType>::GetValueOrDefault()
0x26a02  ldc.i4.2
0x26a03  bne.un   loc_26A8A
0x26a08  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::.ctor()
0x26a0d  stloc.s  0xB
0x26a0f  ldloc.s  0xB
0x26a11  ldc.i4.5
0x26a12  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x26a17  ldloc.s  0xB
0x26a19  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x26a1e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceManager(class [mscorlib]System.Resources.ResourceManager)
0x26a23  ldloc.s  0xB
0x26a25  ldstr    aSignaturemanag_0// "SignatureManagerUnsupportedCatalogPaylo"...
0x26a2a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceId(string)
0x26a2f  ldloc.s  0xB
0x26a31  ldc.i4.2
0x26a32  newarr   [mscorlib]System.Object
0x26a37  dup
0x26a38  ldc.i4.0
0x26a39  ldloc.s  5
0x26a3b  brtrue.s loc_26A40
0x26a3d  ldnull
0x26a3e  br.s     loc_26A47
0x26a40  ldloc.s  5
0x26a42  callvirt instance string [mscorlib]System.Object::ToString()
0x26a47  dup
0x26a48  brtrue.s loc_26A50
0x26a4a  pop
0x26a4b  ldsfld   string [mscorlib]System.String::Empty
0x26a50  stelem.ref
0x26a51  dup
0x26a52  ldc.i4.1
0x26a53  ldarg.2
0x26a54  stelem.ref
0x26a55  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceArgs(object[])
0x26a5a  ldloc.s  0xB
0x26a5c  ldc.i4.2
0x26a5d  newarr   [mscorlib]System.Object
0x26a62  dup
0x26a63  ldc.i4.0
0x26a64  ldloc.s  5
0x26a66  brtrue.s loc_26A6B
0x26a68  ldnull
0x26a69  br.s     loc_26A72
0x26a6b  ldloc.s  5
0x26a6d  callvirt instance string [mscorlib]System.Object::ToString()
0x26a72  dup
0x26a73  brtrue.s loc_26A7B
0x26a75  pop
0x26a76  ldsfld   string [mscorlib]System.String::Empty
0x26a7b  stelem.ref
0x26a7c  dup
0x26a7d  ldc.i4.1
0x26a7e  ldarg.2
0x26a7f  stelem.ref
0x26a80  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_TelemetryResourceArgs(object[])
0x26a85  ldloc.s  0xB
0x26a87  stloc.1
0x26a88  br.s     loc_26A94
0x26a8a  ldarg.0
0x26a8b  ldloc.0
0x26a8c  ldarg.2
0x26a8d  ldarg.3
0x26a8e  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation Microsoft.VisualStudio.Setup.Security.SignatureManager::VerifySignatureAndSigner(class [mscorlib]System.IO.FileStream fileStream, string path, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext verificationContext)
0x26a93  stloc.1
0x26a94  ldloc.1
0x26a95  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x26a9a  brfalse.s loc_26B0E
0x26a9c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x26aa1  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VERIFYPACKAGERESULT
0x26aa6  stloc.s  4
0x26aa8  dup
0x26aa9  ldloc.s  4
0x26aab  ldloc.1
0x26aac  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x26ab1  box      [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult
0x26ab6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x26abb  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VERIFYPACKAGEMESSAGE
0x26ac0  stloc.s  0xE
0x26ac2  dup
0x26ac3  ldloc.s  0xE
0x26ac5  ldloc.1
0x26ac6  ldc.i4.1
0x26ac7  call     string Microsoft.VisualStudio.Setup.Extensions::GetNeutralMessage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation, bool information)
0x26acc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x26ad1  stloc.s  0xC
0x26ad3  ldarg.0
0x26ad4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Security.SignatureManager::telemetry
0x26ad9  dup
0x26ada  brtrue.s loc_26ADF
0x26adc  pop
0x26add  br.s     loc_26AED
0x26adf  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::VERIFYFAILUREEVENT
0x26ae4  ldloc.s  0xC
0x26ae6  ldnull
0x26ae7  ldc.i4.0
0x26ae8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x26aed  ldloc.1
0x26aee  ldc.i4.0
0x26aef  call     string Microsoft.VisualStudio.Setup.Extensions::GetNeutralMessage(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation, bool information)
0x26af4  stloc.s  0xD
0x26af6  ldarg.0
0x26af7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.SignatureManager::log
0x26afc  dup
0x26afd  brtrue.s loc_26B02
0x26aff  pop
0x26b00  br.s     loc_26B0E
0x26b02  ldloc.s  0xD
0x26b04  call     T0x2B000003
  ... truncated ...
```
