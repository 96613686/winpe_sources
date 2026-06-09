# Microsoft.VisualStudio.Setup.Security.ManifestVerifier::Verify

- ea: `0x241c0`
- end: `0x24640`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestVerifier::Verify`
- size: `1152`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x10ea0`
- `0x199a0`
- `0x23880`
- `0x23910`
- `0x241b0`
- `0x241c0`
- `0x24b00`
- `0x25140`
- `0x27100`
- `0x27180`
- `0x27300`

## string_xrefs

- `0x243fa`: `CatalogFailedToDeserialize_Args1`
- `0x24455`: `CatalogFailedToDeserialize_Args1`
- `0x24609`: `ManifestFile_Args1`
- `0x2420e`: `ManifestVerifier`
- `0x2429d`: `ManifestVerifier`
- `0x24372`: `ManifestVerifier`
- `0x2451c`: `ManifestVerifier`
- `0x2423f`: `File doesn't exist in ManifestVerifier.`
- `0x24273`: `ManifestVerifier load Manifest: `
- `0x242b1`: `ManifestLoadFail`
- `0x24386`: `ManifestDeserializeFail`
- `0x243a3`: `ManifestVerifier deserialize failed.`
- `0x243c2`: `ManifestVerifier deserialize failed: `
- `0x244d7`: `ManifestVerifier verification: `
- `0x24530`: `ManifestFailedVerification`
- `0x2454d`: `ManifestVerifier failed verification.`
- `0x2456c`: `ManifestVerifier Result: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x241c0  ldarg.1
0x241c1  ldstr    aFilestream// "fileStream"
0x241c6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x241cb  ldarg.0
0x241cc  ldc.i4.0
0x241cd  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestVerifier::set_EnableRevocationChecks(bool value)
0x241d2  ldnull
0x241d3  stloc.1
0x241d4  ldarg.2
0x241d5  dup
0x241d6  brtrue.s loc_241EF
0x241d8  pop
0x241d9  ldarg.0
0x241da  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x241df  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_CurrentDirectory()
0x241e4  ldarg.1
0x241e5  call     string Microsoft.VisualStudio.Setup.Extensions::GetFilePath(class [mscorlib]System.IO.FileStream fileStream)
0x241ea  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x241ef  starg.s  2
0x241f1  ldarg.0
0x241f2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Security.ManifestVerifier::fileSystem
0x241f7  ldarg.2
0x241f8  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x241fd  brtrue.s loc_24258
0x241ff  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x24204  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x24209  stloc.s  5
0x2420b  dup
0x2420c  ldloc.s  5
0x2420e  ldstr    aManifestverifi// "ManifestVerifier"
0x24213  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x24218  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x2421d  stloc.s  6
0x2421f  dup
0x24220  ldloc.s  6
0x24222  ldstr    aFilenotfound// "FileNotFound"
0x24227  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2422c  stloc.s  4
0x2422e  ldarg.0
0x2422f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Security.ManifestVerifier::telemetry
0x24234  dup
0x24235  brtrue.s loc_2423A
0x24237  pop
0x24238  br.s     loc_24252
0x2423a  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x2423f  ldstr    aFileDoesnTExis// "File doesn't exist in ManifestVerifier."
0x24244  ldloc.s  4
0x24246  ldnull
0x24247  ldnull
0x24248  ldc.i4.0
0x24249  ldnull
0x2424a  ldc.i4.0
0x2424b  ldnull
0x2424c  ldc.i4.0
0x2424d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x24252  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor()
0x24257  throw
0x24258  nop
0x24259  ldarg.1
0x2425a  newobj   instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::.ctor(class [mscorlib]System.IO.FileStream fileStream)
0x2425f  stloc.2
0x24260  leave    loc_24338
0x24265  stloc.s  7
0x24267  ldarg.0
0x24268  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x2426d  dup
0x2426e  brtrue.s loc_24273
0x24270  pop
0x24271  br.s     loc_2428E
0x24273  ldstr    aManifestverifi_0// "ManifestVerifier load Manifest: "
0x24278  ldloc.s  7
0x2427a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2427f  call     string [mscorlib]System.String::Concat(string, string)
0x24284  call     T0x2B000003
0x24289  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2428e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x24293  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x24298  stloc.s  6
0x2429a  dup
0x2429b  ldloc.s  6
0x2429d  ldstr    aManifestverifi// "ManifestVerifier"
0x242a2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x242a7  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x242ac  stloc.s  5
0x242ae  dup
0x242af  ldloc.s  5
0x242b1  ldstr    aManifestloadfa// "ManifestLoadFail"
0x242b6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x242bb  stloc.s  8
0x242bd  ldarg.0
0x242be  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Security.ManifestVerifier::telemetry
0x242c3  dup
0x242c4  brtrue.s loc_242C9
0x242c6  pop
0x242c7  br.s     loc_242E1
0x242c9  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x242ce  ldstr    aCatalogFailedL// "Catalog failed load"
0x242d3  ldloc.s  8
0x242d5  ldnull
0x242d6  ldnull
0x242d7  ldc.i4.0
0x242d8  ldnull
0x242d9  ldc.i4.0
0x242da  ldnull
0x242db  ldc.i4.0
0x242dc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x242e1  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::.ctor()
0x242e6  stloc.s  9
0x242e8  ldloc.s  9
0x242ea  ldc.i4.5
0x242eb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x242f0  ldloc.s  9
0x242f2  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x242f7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceManager(class [mscorlib]System.Resources.ResourceManager)
0x242fc  ldloc.s  9
0x242fe  ldstr    aCatalogfailedt_0// "CatalogFailedToLoad_Args1"
0x24303  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceId(string)
0x24308  ldloc.s  9
0x2430a  ldc.i4.1
0x2430b  newarr   [mscorlib]System.Object
0x24310  dup
0x24311  ldc.i4.0
0x24312  ldarg.2
0x24313  stelem.ref
0x24314  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceArgs(object[])
0x24319  ldloc.s  9
0x2431b  ldc.i4.1
0x2431c  newarr   [mscorlib]System.Object
0x24321  dup
0x24322  ldc.i4.0
0x24323  ldarg.2
0x24324  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x24329  stelem.ref
0x2432a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_TelemetryResourceArgs(object[])
0x2432f  ldloc.s  9
0x24331  stloc.s  9
0x24333  leave    loc_2463D
0x24338  ldnull
0x24339  stloc.3
0x2433a  ldloc.2
0x2433b  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_SignatureBlob()
0x24340  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x24345  brfalse.s loc_2434E
0x24347  ldc.i4.1
0x24348  stloc.0
0x24349  br       loc_2450A
0x2434e  nop
0x2434f  ldloc.2
0x24350  callvirt instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_SignatureBlob()
0x24355  call     T0x2B000152
0x2435a  stloc.s  0xA
0x2435c  leave    loc_24434
0x24361  stloc.s  0xB
0x24363  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x24368  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x2436d  stloc.s  5
0x2436f  dup
0x24370  ldloc.s  5
0x24372  ldstr    aManifestverifi// "ManifestVerifier"
0x24377  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2437c  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x24381  stloc.s  6
0x24383  dup
0x24384  ldloc.s  6
0x24386  ldstr    aManifestdeseri// "ManifestDeserializeFail"
0x2438b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x24390  stloc.s  0xC
0x24392  ldarg.0
0x24393  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Security.ManifestVerifier::telemetry
0x24398  dup
0x24399  brtrue.s loc_2439E
0x2439b  pop
0x2439c  br.s     loc_243B6
0x2439e  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x243a3  ldstr    aManifestverifi_1// "ManifestVerifier deserialize failed."
0x243a8  ldloc.s  0xC
0x243aa  ldnull
0x243ab  ldnull
0x243ac  ldc.i4.0
0x243ad  ldnull
0x243ae  ldc.i4.0
0x243af  ldnull
0x243b0  ldc.i4.0
0x243b1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x243b6  ldarg.0
0x243b7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x243bc  dup
0x243bd  brtrue.s loc_243C2
0x243bf  pop
0x243c0  br.s     loc_243DD
0x243c2  ldstr    aManifestverifi_2// "ManifestVerifier deserialize failed: "
0x243c7  ldloc.s  0xB
0x243c9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x243ce  call     string [mscorlib]System.String::Concat(string, string)
0x243d3  call     T0x2B000003
0x243d8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x243dd  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::.ctor()
0x243e2  stloc.s  0xD
0x243e4  ldloc.s  0xD
0x243e6  ldc.i4.5
0x243e7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x243ec  ldloc.s  0xD
0x243ee  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x243f3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceManager(class [mscorlib]System.Resources.ResourceManager)
0x243f8  ldloc.s  0xD
0x243fa  ldstr    aCatalogfailedt// "CatalogFailedToDeserialize_Args1"
0x243ff  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceId(string)
0x24404  ldloc.s  0xD
0x24406  ldc.i4.1
0x24407  newarr   [mscorlib]System.Object
0x2440c  dup
0x2440d  ldc.i4.0
0x2440e  ldarg.2
0x2440f  stelem.ref
0x24410  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceArgs(object[])
0x24415  ldloc.s  0xD
0x24417  ldc.i4.1
0x24418  newarr   [mscorlib]System.Object
0x2441d  dup
0x2441e  ldc.i4.0
0x2441f  ldarg.2
0x24420  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x24425  stelem.ref
0x24426  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_TelemetryResourceArgs(object[])
0x2442b  ldloc.s  0xD
0x2442d  stloc.s  9
0x2442f  leave    loc_2463D
0x24434  ldloc.s  0xA
0x24436  brtrue.s loc_24489
0x24438  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::.ctor()
0x2443d  stloc.s  0xD
0x2443f  ldloc.s  0xD
0x24441  ldc.i4.5
0x24442  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_Result(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult)
0x24447  ldloc.s  0xD
0x24449  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x2444e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceManager(class [mscorlib]System.Resources.ResourceManager)
0x24453  ldloc.s  0xD
0x24455  ldstr    aCatalogfailedt// "CatalogFailedToDeserialize_Args1"
0x2445a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceId(string)
0x2445f  ldloc.s  0xD
0x24461  ldc.i4.1
0x24462  newarr   [mscorlib]System.Object
0x24467  dup
0x24468  ldc.i4.0
0x24469  ldarg.2
0x2446a  stelem.ref
0x2446b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_ResourceArgs(object[])
0x24470  ldloc.s  0xD
0x24472  ldc.i4.1
0x24473  newarr   [mscorlib]System.Object
0x24478  dup
0x24479  ldc.i4.0
0x2447a  ldarg.2
0x2447b  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x24480  stelem.ref
0x24481  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::set_TelemetryResourceArgs(object[])
0x24486  ldloc.s  0xD
0x24488  ret
0x24489  nop
0x2448a  ldloc.s  0xA
0x2448c  callvirt instance class Microsoft.VisualStudio.Setup.Security.Signature Microsoft.VisualStudio.Setup.Security.SignObject::get_Signature()
0x24491  callvirt instance class Microsoft.VisualStudio.Setup.Security.SignInfo Microsoft.VisualStudio.Setup.Security.Signature::get_SignInfo()
0x24496  callvirt instance string Microsoft.VisualStudio.Setup.Security.SignInfo::get_DigestMethod()
0x2449b  ldstr    aPkcs// "pkcs"
0x244a0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x244a5  brfalse.s loc_244B5
0x244a7  ldarg.0
0x244a8  ldloc.2
0x244a9  ldloc.s  0xA
0x244ab  ldc.i4.0
0x244ac  ldarg.3
0x244ad  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckPS1Authenticode(class Microsoft.VisualStudio.Setup.Security.ManifestDoc manifestDoc, class Microsoft.VisualStudio.Setup.Security.SignObject fileSignature, bool checkWithoutBom, string layoutCertPath)
0x244b2  stloc.0
0x244b3  br.s     loc_244C7
0x244b5  ldarg.0
0x244b6  ldloc.2
0x244b7  ldloc.s  0xA
0x244b9  callvirt instance class Microsoft.VisualStudio.Setup.Security.Signature Microsoft.VisualStudio.Setup.Security.SignObject::get_Signature()
0x244be  ldarg.3
0x244bf  ldloca.s 3
0x244c1  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult Microsoft.VisualStudio.Setup.Security.ManifestVerifier::CheckSign(class Microsoft.VisualStudio.Setup.Security.ManifestDoc manifestDoc, class Microsoft.VisualStudio.Setup.Security.Signature signature, string layoutCertPath, [out] class [mscorlib]System.Collections.Generic.IList`1<string>& signers)
0x244c6  stloc.0
0x244c7  leave.s  loc_2450A
0x244c9  stloc.s  0xE
0x244cb  ldarg.0
0x244cc  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Security.ManifestVerifier::log
0x244d1  dup
0x244d2  brtrue.s loc_244D7
0x244d4  pop
0x244d5  br.s     loc_244FE
0x244d7  ldstr    aManifestverifi_3// "ManifestVerifier verification: "
0x244dc  ldloc.s  0xE
0x244de  callvirt instance string [mscorlib]System.Exception::get_Message()
0x244e3  ldstr    aStack// " Stack: "
0x244e8  ldloc.s  0xE
0x244ea  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x244ef  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x244f4  call     T0x2B000003
0x244f9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
  ... truncated ...
```
