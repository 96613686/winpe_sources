# Microsoft.VisualStudio.Setup.Activities.VerifyPackageAndDeleteCorruptFiles::VerifyAndDeleteCorruptFile

- ea: `0x61a30`
- end: `0x61b2f`
- name: `Microsoft.VisualStudio.Setup.Activities.VerifyPackageAndDeleteCorruptFiles::VerifyAndDeleteCorruptFile`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x61890`

## callees

- `0xed30`
- `0xfed0`
- `0x596d0`
- `0x596f0`
- `0x59710`
- `0x617c0`
- `0x61a30`

## string_xrefs

- `0x61a9d`: `DeleteCorruptCachedFile`
- `0x61ac7`: `Existing corrupt file in cache '{0}'`
- `0x61aea`: `Corrupt cached payload file found: '`

## pseudocode

```c

```

## disassembly

```asm
0x61a30  ldarg.0
0x61a31  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x61a36  ldarg.1
0x61a37  ldc.i4.s 0x10
0x61a39  ldc.i4   0x200
0x61a3e  call     bool Microsoft.VisualStudio.Setup.Activities.VerifyPackageAndDeleteCorruptFiles::IsFilePotentiallyCorrupt(class [mscorlib]System.IServiceProvider serviceProvider, string file, [opt] int32 headBuffer, [opt] int32 tailBuffer)
0x61a43  brfalse  loc_61B2E
0x61a48  ldarg.0
0x61a49  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.VerifyPackageAndDeleteCorruptFiles::fileSystem
0x61a4e  ldarg.1
0x61a4f  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string)
0x61a54  stloc.1
0x61a55  ldarg.0
0x61a56  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager Microsoft.VisualStudio.Setup.Activities.VerifyPackageAndDeleteCorruptFiles::verifier
0x61a5b  ldloc.1
0x61a5c  ldarg.1
0x61a5d  ldarg.2
0x61a5e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager::Verify(class [mscorlib]System.IO.Stream, string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext)
0x61a63  stloc.0
0x61a64  leave.s  loc_61A70
0x61a66  ldloc.1
0x61a67  brfalse.s loc_61A6F
0x61a69  ldloc.1
0x61a6a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61a6f  endfinally
0x61a70  ldloc.0
0x61a71  brtrue.s loc_61A76
0x61a73  ldc.i4.1
0x61a74  br.s     loc_61A7F
0x61a76  ldloc.0
0x61a77  call     instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x61a7c  ldc.i4.0
0x61a7d  cgt.un
0x61a7f  brfalse  loc_61B2E
0x61a84  ldarg.0
0x61a85  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x61a8a  ldc.i4.0
0x61a8b  call     T0x2B000039
0x61a90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x61a95  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTLOCATIONPROPERTY
0x61a9a  stloc.3
0x61a9b  dup
0x61a9c  ldloc.3
0x61a9d  ldstr    aDeletecorruptc// "DeleteCorruptCachedFile"
0x61aa2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x61aa7  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTTYPEPROPERTY
0x61aac  stloc.s  4
0x61aae  dup
0x61aaf  ldloc.s  4
0x61ab1  ldstr    aVerifyexisting// "VerifyExistingPackage"
0x61ab6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x61abb  stloc.2
0x61abc  dup
0x61abd  brtrue.s loc_61AC2
0x61abf  pop
0x61ac0  br.s     loc_61AE4
0x61ac2  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x61ac7  ldstr    aExistingCorrup// "Existing corrupt file in cache '{0}'"
0x61acc  ldarg.0
0x61acd  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x61ad2  call     string [mscorlib]System.String::Format(string, object)
0x61ad7  ldloc.2
0x61ad8  ldnull
0x61ad9  ldnull
0x61ada  ldc.i4.0
0x61adb  ldnull
0x61adc  ldc.i4.0
0x61add  ldnull
0x61ade  ldc.i4.0
0x61adf  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x61ae4  ldarg.0
0x61ae5  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x61aea  ldstr    aCorruptCachedP// "Corrupt cached payload file found: '"
0x61aef  ldarg.1
0x61af0  ldstr    asc_7FEB6// "'"
0x61af5  call     string [mscorlib]System.String::Concat(string, string, string)
0x61afa  call     T0x2B000003
0x61aff  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.Extensions::TryWriteVerbose(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, string, object[])
0x61b04  ldarg.0
0x61b05  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.VerifyPackageAndDeleteCorruptFiles::fileSystem
0x61b0a  ldarg.0
0x61b0b  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x61b10  ldarg.1
0x61b11  call     void Microsoft.VisualStudio.Setup.Extensions::TryQuarantinePayloadFile(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem filesystem, class [mscorlib]System.IServiceProvider serviceProvider, string payloadFile)
0x61b16  ldarg.0
0x61b17  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Activities.VerifyPackageAndDeleteCorruptFiles::fileSystem
0x61b1c  ldarg.1
0x61b1d  ldloca.s 5
0x61b1f  ldc.i4.0
0x61b20  ldc.i4.2
0x61b21  ldc.i4   0x1F4
0x61b26  ldnull
0x61b27  ldnull
0x61b28  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteFileWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x61b2d  pop
0x61b2e  ret
```
