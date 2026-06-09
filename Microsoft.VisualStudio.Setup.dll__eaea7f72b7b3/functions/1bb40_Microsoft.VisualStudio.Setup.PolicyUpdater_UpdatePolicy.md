# Microsoft.VisualStudio.Setup.PolicyUpdater::UpdatePolicy

- ea: `0x1bb40`
- end: `0x1bd13`
- name: `Microsoft.VisualStudio.Setup.PolicyUpdater::UpdatePolicy`
- size: `467`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1bae0`
- `0x1bb40`
- `0x22ac0`
- `0x22ad0`
- `0x22c50`
- `0x22c70`
- `0x3ead0`
- `0x3eae0`
- `0x3ebe0`
- `0x3ebf0`
- `0x3f330`
- `0x3f340`
- `0x41d70`

## string_xrefs

- `0x1bbc1`: `Changing policy CachePath from: `
- `0x1bc28`: `Invalid Cache Path`
- `0x1bcb7`: `Attempting to setpolicy SharedInstallationPath from: `

## pseudocode

```c

```

## disassembly

```asm
0x1bb40  ldarg.0
0x1bb41  ldfld    class Microsoft.VisualStudio.Setup.Services.IWritablePolicyService Microsoft.VisualStudio.Setup.PolicyUpdater::policyService
0x1bb46  stloc.0
0x1bb47  ldloc.0
0x1bb48  brfalse.s loc_1BB4D
0x1bb4a  ldarg.1
0x1bb4b  brtrue.s loc_1BB4F
0x1bb4d  ldc.i4.0
0x1bb4e  ret
0x1bb4f  ldc.i4.0
0x1bb50  stloc.1
0x1bb51  ldarg.1
0x1bb52  callvirt instance class Microsoft.VisualStudio.Setup.Serialization.CachePolicy Microsoft.VisualStudio.Setup.Serialization.PolicySettings::get_CachePolicy()
0x1bb57  brfalse  loc_1BC65
0x1bb5c  ldarg.1
0x1bb5d  callvirt instance class Microsoft.VisualStudio.Setup.Serialization.CachePolicy Microsoft.VisualStudio.Setup.Serialization.PolicySettings::get_CachePolicy()
0x1bb62  stloc.2
0x1bb63  ldloc.2
0x1bb64  brtrue.s loc_1BB69
0x1bb66  ldnull
0x1bb67  br.s     loc_1BB6F
0x1bb69  ldloc.2
0x1bb6a  call     instance string Microsoft.VisualStudio.Setup.Serialization.CachePolicy::get_Path()
0x1bb6f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1bb74  brtrue   loc_1BC56
0x1bb79  ldloc.0
0x1bb7a  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IPolicyService::get_IsCachePathSettable()
0x1bb7f  brfalse.s loc_1BBF4
0x1bb81  ldloc.2
0x1bb82  brtrue.s loc_1BB87
0x1bb84  ldnull
0x1bb85  br.s     loc_1BB8D
0x1bb87  ldloc.2
0x1bb88  call     instance string Microsoft.VisualStudio.Setup.Serialization.CachePolicy::get_Path()
0x1bb8d  ldloc.0
0x1bb8e  brtrue.s loc_1BB93
0x1bb90  ldnull
0x1bb91  br.s     loc_1BB99
0x1bb93  ldloc.0
0x1bb94  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_CachePath()
0x1bb99  ldc.i4.5
0x1bb9a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1bb9f  brtrue.s loc_1BBF4
0x1bba1  ldc.i4.1
0x1bba2  stloc.1
0x1bba3  ldarg.0
0x1bba4  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.PolicyUpdater::services
0x1bba9  ldloc.2
0x1bbaa  callvirt instance string Microsoft.VisualStudio.Setup.Serialization.CachePolicy::get_Path()
0x1bbaf  ldc.i4.0
0x1bbb0  call     void Microsoft.VisualStudio.Setup.Services.PolicyService::VerifyCustomPath(class [mscorlib]System.IServiceProvider services, string customPath, valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType pathType)
0x1bbb5  ldarg.0
0x1bbb6  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.PolicyUpdater::logger
0x1bbbb  dup
0x1bbbc  brtrue.s loc_1BBC1
0x1bbbe  pop
0x1bbbf  br.s     loc_1BBE6
0x1bbc1  ldstr    aChangingPolicy_0// "Changing policy CachePath from: "
0x1bbc6  ldloc.0
0x1bbc7  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_CachePath()
0x1bbcc  ldstr    aTo_0// ", to: "
0x1bbd1  ldloc.2
0x1bbd2  callvirt instance string Microsoft.VisualStudio.Setup.Serialization.CachePolicy::get_Path()
0x1bbd7  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1bbdc  call     T0x2B000003
0x1bbe1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1bbe6  ldloc.0
0x1bbe7  ldloc.2
0x1bbe8  callvirt instance string Microsoft.VisualStudio.Setup.Serialization.CachePolicy::get_Path()
0x1bbed  callvirt instance void Microsoft.VisualStudio.Setup.Services.IPolicyService::set_CachePath(string value)
0x1bbf2  br.s     loc_1BC56
0x1bbf4  ldloc.0
0x1bbf5  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IPolicyService::get_IsCachePathSettable()
0x1bbfa  brtrue.s loc_1BC56
0x1bbfc  ldloc.2
0x1bbfd  callvirt instance string Microsoft.VisualStudio.Setup.Serialization.CachePolicy::get_Path()
0x1bc02  ldc.i4.0
0x1bc03  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::NormalizePath(string, bool)
0x1bc08  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::RemoveTrailingBackslash(string)
0x1bc0d  stloc.3
0x1bc0e  ldloc.0
0x1bc0f  callvirt instance string Microsoft.VisualStudio.Setup.Services.IPolicyService::get_CachePath()
0x1bc14  ldc.i4.0
0x1bc15  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::NormalizePath(string, bool)
0x1bc1a  call     string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::RemoveTrailingBackslash(string)
0x1bc1f  ldloc.3
0x1bc20  ldc.i4.3
0x1bc21  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1bc26  brtrue.s loc_1BC56
0x1bc28  ldstr    aInvalidCachePa// "Invalid Cache Path"
0x1bc2d  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x1bc32  stloc.s  4
0x1bc34  ldarg.0
0x1bc35  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.PolicyUpdater::logger
0x1bc3a  dup
0x1bc3b  brtrue.s loc_1BC40
0x1bc3d  pop
0x1bc3e  br.s     loc_1BC53
0x1bc40  ldloc.s  4
0x1bc42  ldloc.s  4
0x1bc44  callvirt instance string [mscorlib]System.Object::ToString()
0x1bc49  call     T0x2B000003
0x1bc4e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x1bc53  ldloc.s  4
0x1bc55  throw
0x1bc56  ldarg.0
0x1bc57  ldloc.2
0x1bc58  callvirt instance bool Microsoft.VisualStudio.Setup.Serialization.CachePolicy::get_KeepDownloadedPayloads()
0x1bc5d  call     instance bool Microsoft.VisualStudio.Setup.PolicyUpdater::UpdateKeepDownloadPayloads(bool keepDownloadPayloads)
0x1bc62  ldloc.1
0x1bc63  or
0x1bc64  stloc.1
0x1bc65  ldarg.1
0x1bc66  callvirt instance string Microsoft.VisualStudio.Setup.Serialization.PolicySettings::get_SharedInstallationPath()
0x1bc6b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1bc70  brtrue.s loc_1BCE2
0x1bc72  ldarg.1
0x1bc73  callvirt instance string Microsoft.VisualStudio.Setup.Serialization.PolicySettings::get_SharedInstallationPath()
0x1bc78  stloc.s  5
0x1bc7a  ldloc.0
0x1bc7b  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IPolicyService::get_IsSharedInstallPathSettable()
0x1bc80  brfalse  loc_1BD11
0x1bc85  ldloc.1
0x1bc86  brtrue.s loc_1BC9B
0x1bc88  ldloc.0
0x1bc89  callvirt instance string Microsoft.VisualStudio.Setup.Services.IWritablePolicyService::get_SharedInstallationPath()
0x1bc8e  ldloc.s  5
0x1bc90  ldc.i4.5
0x1bc91  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1bc96  ldc.i4.0
0x1bc97  ceq
0x1bc99  br.s     loc_1BC9C
0x1bc9b  ldc.i4.1
0x1bc9c  stloc.1
0x1bc9d  ldarg.0
0x1bc9e  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.PolicyUpdater::services
0x1bca3  ldloc.s  5
0x1bca5  ldc.i4.1
0x1bca6  call     void Microsoft.VisualStudio.Setup.Services.PolicyService::VerifyCustomPath(class [mscorlib]System.IServiceProvider services, string customPath, valuetype Microsoft.VisualStudio.Setup.Validation.DrivePathType pathType)
0x1bcab  ldarg.0
0x1bcac  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.PolicyUpdater::logger
0x1bcb1  dup
0x1bcb2  brtrue.s loc_1BCB7
0x1bcb4  pop
0x1bcb5  br.s     loc_1BCD8
0x1bcb7  ldstr    aAttemptingToSe// "Attempting to setpolicy SharedInstallat"...
0x1bcbc  ldloc.0
0x1bcbd  callvirt instance string Microsoft.VisualStudio.Setup.Services.IWritablePolicyService::get_SharedInstallationPath()
0x1bcc2  ldstr    aTo_0// ", to: "
0x1bcc7  ldloc.s  5
0x1bcc9  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1bcce  call     T0x2B000003
0x1bcd3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1bcd8  ldloc.0
0x1bcd9  ldloc.s  5
0x1bcdb  callvirt instance void Microsoft.VisualStudio.Setup.Services.IWritablePolicyService::set_SharedInstallationPath(string value)
0x1bce0  br.s     loc_1BD11
0x1bce2  ldloc.0
0x1bce3  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IPolicyService::get_IsSharedInstallPathSettable()
0x1bce8  brfalse.s loc_1BD11
0x1bcea  ldarg.0
0x1bceb  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.PolicyUpdater::logger
0x1bcf0  dup
0x1bcf1  brtrue.s loc_1BCF6
0x1bcf3  pop
0x1bcf4  br.s     loc_1BD05
0x1bcf6  ldstr    aSetttingDefaul// "Settting default policy value"
0x1bcfb  call     T0x2B000003
0x1bd00  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1bd05  ldloc.0
0x1bd06  ldloc.0
0x1bd07  callvirt instance string Microsoft.VisualStudio.Setup.Services.IWritablePolicyService::get_SharedInstallationPath()
0x1bd0c  callvirt instance void Microsoft.VisualStudio.Setup.Services.IWritablePolicyService::set_SharedInstallationPath(string value)
0x1bd11  ldloc.1
0x1bd12  ret
```
