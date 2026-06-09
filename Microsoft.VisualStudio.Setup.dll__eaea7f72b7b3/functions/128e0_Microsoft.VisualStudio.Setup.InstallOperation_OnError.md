# Microsoft.VisualStudio.Setup.InstallOperation::OnError

- ea: `0x128e0`
- end: `0x12c78`
- name: `Microsoft.VisualStudio.Setup.InstallOperation::OnError`
- size: `920`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callees

- `0xd460`
- `0xd6b0`
- `0xd870`
- `0xd8b0`
- `0x12010`
- `0x12020`
- `0x12040`
- `0x12050`
- `0x12060`
- `0x128e0`
- `0x12c80`
- `0x14880`
- `0x3f1d0`
- `0x59710`
- `0x59b70`
- `0x59b80`
- `0x5df20`
- `0x5e1c0`
- `0x5e570`
- `0x5e590`
- `0x60080`
- `0x600a0`
- `0x60100`

## string_xrefs

- `0x12b33`: `Install`
- `0x12917`: `OnErrorTokenCancel`
- `0x12aad`: `Install activity failed without return code for package '`
- `0x12b92`: `CachePackage`

## pseudocode

```c

```

## disassembly

```asm
0x128e0  ldarg.0
0x128e1  ldarg.0
0x128e2  call     instance bool Microsoft.VisualStudio.Setup.InstallOperation::get_IsCancelled()
0x128e7  ldarg.2
0x128e8  callvirt instance bool Microsoft.VisualStudio.Setup.Activities.ActivityEventArgs::get_Cancel()
0x128ed  or
0x128ee  call     instance void Microsoft.VisualStudio.Setup.InstallOperation::set_IsCancelled(bool value)
0x128f3  ldarg.2
0x128f4  callvirt instance bool Microsoft.VisualStudio.Setup.Activities.ActivityEventArgs::get_Cancel()
0x128f9  brfalse.s loc_1292D
0x128fb  ldarg.0
0x128fc  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.InstallOperation::linkedCancellationTokenSource
0x12901  brfalse.s loc_1292D
0x12903  ldarg.0
0x12904  ldfld    class Microsoft.VisualStudio.Setup.ITester Microsoft.VisualStudio.Setup.InstallOperation::tester
0x12909  dup
0x1290a  brtrue.s loc_1290F
0x1290c  pop
0x1290d  br.s     loc_12922
0x1290f  ldc.i4.1
0x12910  newarr   [mscorlib]System.Object
0x12915  dup
0x12916  ldc.i4.0
0x12917  ldstr    aOnerrortokenca// "OnErrorTokenCancel"
0x1291c  stelem.ref
0x1291d  callvirt instance void Microsoft.VisualStudio.Setup.ITester::Test(object[] args)
0x12922  ldarg.0
0x12923  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.InstallOperation::linkedCancellationTokenSource
0x12928  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel()
0x1292d  nop
0x1292e  ldarg.2
0x1292f  callvirt instance bool Microsoft.VisualStudio.Setup.Activities.ActivityEventArgs::get_Cancel()
0x12934  brtrue   loc_12C54
0x12939  ldarg.2
0x1293a  callvirt instance class Microsoft.VisualStudio.Setup.Activities.IActivity Microsoft.VisualStudio.Setup.Activities.ActivityEventArgs::get_Activity()
0x1293f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.IActivity::get_Package()
0x12944  brfalse  loc_12C54
0x12949  ldarg.2
0x1294a  callvirt instance class Microsoft.VisualStudio.Setup.Activities.IActivity Microsoft.VisualStudio.Setup.Activities.ActivityEventArgs::get_Activity()
0x1294f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.IActivity::get_Package()
0x12954  stloc.0
0x12955  ldnull
0x12956  stloc.1
0x12957  ldnull
0x12958  stloc.2
0x12959  ldnull
0x1295a  stloc.3
0x1295b  ldnull
0x1295c  stloc.s  4
0x1295e  ldnull
0x1295f  stloc.s  5
0x12961  ldarg.2
0x12962  callvirt instance class Microsoft.VisualStudio.Setup.Activities.IActivity Microsoft.VisualStudio.Setup.Activities.ActivityEventArgs::get_Activity()
0x12967  stloc.s  0xE
0x12969  ldloc.s  0xE
0x1296b  isinst   Microsoft.VisualStudio.Setup.Activities.Install
0x12970  stloc.s  0xA
0x12972  ldloc.s  0xA
0x12974  brtrue.s loc_129AB
0x12976  ldloc.s  0xE
0x12978  isinst   Microsoft.VisualStudio.Setup.Activities.DownloadPackage
0x1297d  stloc.s  0xB
0x1297f  ldloc.s  0xB
0x12981  brtrue   loc_12B4C
0x12986  ldloc.s  0xE
0x12988  isinst   Microsoft.VisualStudio.Setup.Activities.CachePackage
0x1298d  stloc.s  0xC
0x1298f  ldloc.s  0xC
0x12991  brtrue   loc_12B92
0x12996  ldloc.s  0xE
0x12998  isinst   Microsoft.VisualStudio.Setup.Activities.RunProductCommand
0x1299d  stloc.s  0xD
0x1299f  ldloc.s  0xD
0x129a1  brtrue   loc_12BA3
0x129a6  br       loc_12C20
0x129ab  ldloc.s  0xA
0x129ad  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction Microsoft.VisualStudio.Setup.Activities.Install::get_RequestedAction()
0x129b2  stloc.s  0xF
0x129b4  ldloca.s 0xF
0x129b6  constrained. [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction
0x129bc  callvirt instance string [mscorlib]System.Object::ToString()
0x129c1  stloc.1
0x129c2  ldloc.s  0xA
0x129c4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x129c9  brfalse  loc_12A98
0x129ce  ldloc.s  0xA
0x129d0  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x129d5  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsFailure(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult)
0x129da  brfalse  loc_12A98
0x129df  ldloc.s  0xA
0x129e1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x129e6  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_MessageId()
0x129eb  brtrue.s loc_12A04
0x129ed  ldloc.s  0xA
0x129ef  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x129f4  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x129f9  stloc.s  0x10
0x129fb  ldloca.s 0x10
0x129fd  call     instance string [mscorlib]System.Int32::ToString()
0x12a02  br.s     loc_12A19
0x12a04  ldloc.s  0xA
0x12a06  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x12a0b  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_MessageId()
0x12a10  stloc.s  0x10
0x12a12  ldloca.s 0x10
0x12a14  call     instance string [mscorlib]System.Int32::ToString()
0x12a19  stloc.2
0x12a1a  ldloc.s  0xA
0x12a1c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x12a21  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Message()
0x12a26  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12a2b  brfalse.s loc_12A3B
0x12a2d  ldloc.s  0xA
0x12a2f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x12a34  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x12a39  br.s     loc_12A47
0x12a3b  ldloc.s  0xA
0x12a3d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x12a42  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Message()
0x12a47  stloc.3
0x12a48  ldloc.s  0xA
0x12a4a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x12a4f  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage
0x12a54  dup
0x12a55  brtrue.s loc_12A5B
0x12a57  pop
0x12a58  ldnull
0x12a59  br.s     loc_12A60
0x12a5b  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallablePackage::get_WatsonLogFile()
0x12a60  stloc.s  4
0x12a62  ldloc.s  0xA
0x12a64  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x12a69  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage
0x12a6e  dup
0x12a6f  brtrue.s loc_12A75
0x12a71  pop
0x12a72  ldnull
0x12a73  br.s     loc_12A7A
0x12a75  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LogFile> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage::get_LogFiles()
0x12a7a  stloc.s  5
0x12a7c  ldarg.0
0x12a7d  call     instance class Microsoft.VisualStudio.Setup.ErrorReporter Microsoft.VisualStudio.Setup.InstallOperation::get_ErrorReporter()
0x12a82  dup
0x12a83  brtrue.s loc_12A8B
0x12a85  pop
0x12a86  br       loc_12C20
0x12a8b  ldloc.s  0xA
0x12a8d  ldloc.2
0x12a8e  call     instance void Microsoft.VisualStudio.Setup.ErrorReporter::AddInstallFailureToInstance(class Microsoft.VisualStudio.Setup.Activities.Install install, string returnCode)
0x12a93  br       loc_12C20
0x12a98  ldloc.s  0xA
0x12a9a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x12a9f  brtrue.s loc_12AFE
0x12aa1  ldarg.0
0x12aa2  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.InstallOperation::logger
0x12aa7  dup
0x12aa8  brtrue.s loc_12AAD
0x12aaa  pop
0x12aab  br.s     loc_12AD9
0x12aad  ldstr    aInstallActivit// "Install activity failed without return "...
0x12ab2  ldloc.s  0xA
0x12ab4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x12ab9  dup
0x12aba  brtrue.s loc_12AC0
0x12abc  pop
0x12abd  ldnull
0x12abe  br.s     loc_12AC5
0x12ac0  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x12ac5  ldstr    aSetupWillOnlyW// "'. Setup will only watson generic error"...
0x12aca  call     string [mscorlib]System.String::Concat(string, string, string)
0x12acf  call     T0x2B000003
0x12ad4  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x12ad9  ldarg.0
0x12ada  ldloc.s  0xA
0x12adc  call     instance string Microsoft.VisualStudio.Setup.InstallOperation::GetGenericErrorFromActivity(class Microsoft.VisualStudio.Setup.Activities.IActivity)
0x12ae1  stloc.2
0x12ae2  ldarg.0
0x12ae3  call     instance class Microsoft.VisualStudio.Setup.ErrorReporter Microsoft.VisualStudio.Setup.InstallOperation::get_ErrorReporter()
0x12ae8  dup
0x12ae9  brtrue.s loc_12AF1
0x12aeb  pop
0x12aec  br       loc_12C20
0x12af1  ldloc.s  0xA
0x12af3  ldloc.2
0x12af4  call     instance void Microsoft.VisualStudio.Setup.ErrorReporter::AddInstallFailureToInstance(class Microsoft.VisualStudio.Setup.Activities.Install install, string returnCode)
0x12af9  br       loc_12C20
0x12afe  ldarg.0
0x12aff  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.InstallOperation::logger
0x12b04  dup
0x12b05  brtrue.s loc_12B0A
0x12b07  pop
0x12b08  br.s     loc_12B47
0x12b0a  ldstr    aPackage0Succee// "Package '{0}' succeeded with return cod"...
0x12b0f  ldloc.s  0xA
0x12b11  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Activities.Activity::get_Package()
0x12b16  dup
0x12b17  brtrue.s loc_12B1D
0x12b19  pop
0x12b1a  ldnull
0x12b1b  br.s     loc_12B22
0x12b1d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x12b22  ldloc.s  0xA
0x12b24  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.Install::get_ReturnCode()
0x12b29  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x12b2e  box      [mscorlib]System.Int32
0x12b33  ldstr    aInstall// "Install"
0x12b38  call     string [mscorlib]System.String::Format(string, object, object, object)
0x12b3d  call     T0x2B000003
0x12b42  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x12b47  leave    loc_12C77
0x12b4c  ldstr    aDownloadpackag// "DownloadPackage"
0x12b51  stloc.1
0x12b52  ldloc.s  0xB
0x12b54  ldloca.s 2
0x12b56  ldloca.s 6
0x12b58  ldloca.s 7
0x12b5a  ldloca.s 8
0x12b5c  call     void Microsoft.VisualStudio.Setup.ErrorReporter::ParseDownloadFailure(class Microsoft.VisualStudio.Setup.Activities.DownloadPackage download, [out] string& errorCode, [out] string& description, [out] class [mscorlib]System.Collections.Generic.IEnumerable`1<string>& nonLocalizedDetails, [out] class [mscorlib]System.Collections.Generic.IEnumerable`1<string>& localizedDetails)
0x12b61  ldloc.s  7
0x12b63  brfalse.s loc_12B72
0x12b65  ldstr    asc_82420// ";"
0x12b6a  ldloc.s  7
0x12b6c  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x12b71  stloc.3
0x12b72  ldarg.0
0x12b73  call     instance class Microsoft.VisualStudio.Setup.ErrorReporter Microsoft.VisualStudio.Setup.InstallOperation::get_ErrorReporter()
0x12b78  dup
0x12b79  brtrue.s loc_12B81
0x12b7b  pop
0x12b7c  br       loc_12C20
0x12b81  ldloc.s  0xB
0x12b83  ldloc.2
0x12b84  ldloc.s  6
0x12b86  ldloc.s  8
0x12b88  call     instance void Microsoft.VisualStudio.Setup.ErrorReporter::AddDownloadFailureToInstance(class Microsoft.VisualStudio.Setup.Activities.DownloadPackage download, string returnCode, string description, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> details)
0x12b8d  br       loc_12C20
0x12b92  ldstr    aCachepackage// "CachePackage"
0x12b97  stloc.1
0x12b98  ldarg.0
0x12b99  ldloc.s  0xC
0x12b9b  call     instance string Microsoft.VisualStudio.Setup.InstallOperation::GetGenericErrorFromActivity(class Microsoft.VisualStudio.Setup.Activities.IActivity)
0x12ba0  stloc.2
0x12ba1  br.s     loc_12C20
0x12ba3  ldloc.s  0xD
0x12ba5  callvirt instance string Microsoft.VisualStudio.Setup.Activities.RunProductCommand::get_WatsonAction()
0x12baa  stloc.1
0x12bab  ldloc.s  0xD
0x12bad  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.RunProductCommand::get_ReturnCode()
0x12bb2  dup
0x12bb3  brtrue.s loc_12BB9
0x12bb5  pop
0x12bb6  ldnull
0x12bb7  br.s     loc_12BC7
0x12bb9  call     instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x12bbe  stloc.s  0x10
0x12bc0  ldloca.s 0x10
0x12bc2  call     instance string [mscorlib]System.Int32::ToString()
0x12bc7  stloc.2
0x12bc8  ldloc.s  0xD
0x12bca  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult Microsoft.VisualStudio.Setup.Activities.RunProductCommand::get_ReturnCode()
0x12bcf  dup
0x12bd0  brtrue.s loc_12BD6
0x12bd2  pop
0x12bd3  ldnull
0x12bd4  br.s     loc_12BDB
0x12bd6  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_Details()
0x12bdb  stloc.3
0x12bdc  ldloc.s  0xD
0x12bde  callvirt instance string Microsoft.VisualStudio.Setup.Activities.RunProductCommand::get_LogFile()
0x12be3  stloc.s  4
0x12be5  ldarg.0
0x12be6  call     instance class Microsoft.VisualStudio.Setup.ErrorReporter Microsoft.VisualStudio.Setup.InstallOperation::get_ErrorReporter()
0x12beb  dup
0x12bec  brtrue.s loc_12BF1
0x12bee  pop
0x12bef  br.s     loc_12BF8
0x12bf1  ldloc.s  0xD
0x12bf3  call     instance void Microsoft.VisualStudio.Setup.ErrorReporter::AddProductCommandFailureToInstance(class Microsoft.VisualStudio.Setup.Activities.RunProductCommand runProductCommand)
0x12bf8  ldloc.s  0xD
0x12bfa  isinst   Microsoft.VisualStudio.Setup.Activities.ExtensibilityFinalize
0x12bff  stloc.s  9
0x12c01  ldloc.s  9
0x12c03  brfalse.s loc_12C20
0x12c05  ldloc.s  9
0x12c07  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.IPackageProgress> Microsoft.VisualStudio.Setup.Activities.ExtensibilityFinalize::get_PackagesToFinalize()
0x12c0c  brfalse.s loc_12C20
0x12c0e  ldarg.0
0x12c0f  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.IPackageProgress> Microsoft.VisualStudio.Setup.InstallOperation::otherFailedPackages
0x12c14  ldloc.s  9
0x12c16  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.IPackageProgress> Microsoft.VisualStudio.Setup.Activities.ExtensibilityFinalize::get_PackagesToFinalize()
0x12c1b  call     T0x2B0000D0
0x12c20  ldarg.0
0x12c21  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.InstallOperation::services
0x12c26  dup
0x12c27  brtrue.s loc_12C2C
0x12c29  pop
0x12c2a  br.s     loc_12C54
0x12c2c  ldc.i4.0
0x12c2d  call     T0x2B0000D1
0x12c32  dup
  ... truncated ...
```
