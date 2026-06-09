# System.Deployment.Application.PlatformDetector::CheckCompatibleFramework

- ea: `0x1b390`
- end: `0x1b534`
- name: `System.Deployment.Application.PlatformDetector::CheckCompatibleFramework`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1ba20`

## callees

- `0xdef0`
- `0xdf00`
- `0xdf10`
- `0x17cb0`
- `0x17cd0`
- `0x1a510`
- `0x1b240`
- `0x1b2a0`
- `0x1b360`
- `0x1b390`
- `0x23020`

## string_xrefs

- `0x1b390`: `CheckCompatibleFramework called targetVersion:`
- `0x1b3ed`: `Install`
- `0x1b409`: `InstallSuccess`

## pseudocode

```c

```

## disassembly

```asm
0x1b390  ldstr    aCheckcompatibl// "CheckCompatibleFramework called targetV"...
0x1b395  ldarg.0
0x1b396  callvirt instance string System.Deployment.Application.CompatibleFramework::get_TargetVersion()
0x1b39b  ldstr    aProfile_0// " profile:"
0x1b3a0  ldarg.0
0x1b3a1  callvirt instance string System.Deployment.Application.CompatibleFramework::get_Profile()
0x1b3a6  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1b3ab  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1b3b0  ldarg.0
0x1b3b1  callvirt instance string System.Deployment.Application.CompatibleFramework::get_TargetVersion()
0x1b3b6  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1b3bb  stloc.0
0x1b3bc  ldnull
0x1b3bd  stloc.1
0x1b3be  ldnull
0x1b3bf  stloc.2
0x1b3c0  ldnull
0x1b3c1  stloc.3
0x1b3c2  ldc.i4.0
0x1b3c3  stloc.s  4
0x1b3c5  ldc.i4.0
0x1b3c6  stloc.s  5
0x1b3c8  ldloc.0
0x1b3c9  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x1b3ce  stloc.s  6
0x1b3d0  ldloc.s  6
0x1b3d2  ldc.i4.2
0x1b3d3  beq.s    loc_1B3DC
0x1b3d5  ldloc.s  6
0x1b3d7  ldc.i4.3
0x1b3d8  beq.s    loc_1B3FB
0x1b3da  br.s     loc_1B453
0x1b3dc  ldstr    aSoftwareMicros_2// "SOFTWARE\\Microsoft\\NET Framework Setu"...
0x1b3e1  ldarg.0
0x1b3e2  callvirt instance string System.Deployment.Application.CompatibleFramework::get_TargetVersion()
0x1b3e7  call     string [mscorlib]System.String::Concat(string, string)
0x1b3ec  stloc.1
0x1b3ed  ldstr    aInstall// "Install"
0x1b3f2  stloc.3
0x1b3f3  ldc.i4.1
0x1b3f4  stloc.s  4
0x1b3f6  br       loc_1B48A
0x1b3fb  ldloc.0
0x1b3fc  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x1b401  brtrue.s loc_1B414
0x1b403  ldstr    aSoftwareMicros_3// "SOFTWARE\\Microsoft\\NET Framework Setu"...
0x1b408  stloc.1
0x1b409  ldstr    aInstallsuccess// "InstallSuccess"
0x1b40e  stloc.3
0x1b40f  ldc.i4.1
0x1b410  stloc.s  4
0x1b412  br.s     loc_1B48A
0x1b414  ldstr    aSoftwareMicros_2// "SOFTWARE\\Microsoft\\NET Framework Setu"...
0x1b419  ldloc.0
0x1b41a  ldc.i4.2
0x1b41b  callvirt instance string [mscorlib]System.Version::ToString(int32)
0x1b420  call     string [mscorlib]System.String::Concat(string, string)
0x1b425  stloc.1
0x1b426  ldstr    aVersion// "Version"
0x1b42b  stloc.3
0x1b42c  ldstr    aClient// "Client"
0x1b431  ldarg.0
0x1b432  callvirt instance string System.Deployment.Application.CompatibleFramework::get_Profile()
0x1b437  ldc.i4.5
0x1b438  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1b43d  brfalse.s loc_1B48A
0x1b43f  ldstr    aSoftwareMicros_4// "SOFTWARE\\Microsoft\\NET Framework Setu"...
0x1b444  ldloc.0
0x1b445  ldc.i4.2
0x1b446  callvirt instance string [mscorlib]System.Version::ToString(int32)
0x1b44b  call     string [mscorlib]System.String::Concat(string, string)
0x1b450  stloc.2
0x1b451  br.s     loc_1B48A
0x1b453  ldstr    aSoftwareMicros_2// "SOFTWARE\\Microsoft\\NET Framework Setu"...
0x1b458  ldloc.0
0x1b459  ldc.i4.1
0x1b45a  callvirt instance string [mscorlib]System.Version::ToString(int32)
0x1b45f  call     string [mscorlib]System.String::Concat(string, string)
0x1b464  stloc.1
0x1b465  ldarg.0
0x1b466  callvirt instance string System.Deployment.Application.CompatibleFramework::get_Profile()
0x1b46b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b470  brtrue.s loc_1B484
0x1b472  ldloc.1
0x1b473  ldstr    asc_36B74// "\\"
0x1b478  ldarg.0
0x1b479  callvirt instance string System.Deployment.Application.CompatibleFramework::get_Profile()
0x1b47e  call     string [mscorlib]System.String::Concat(string, string, string)
0x1b483  stloc.1
0x1b484  ldstr    aTargetversion// "TargetVersion"
0x1b489  stloc.3
0x1b48a  ldloc.1
0x1b48b  ldloc.3
0x1b48c  ldloc.0
0x1b48d  ldloc.s  4
0x1b48f  call     bool System.Deployment.Application.PlatformDetector::DetectFrameworkInRegistry(string setupKeyPath, string setupValueName, class [mscorlib]System.Version versionRequired, bool detectInstallValue)
0x1b494  brtrue.s loc_1B4A8
0x1b496  ldloc.2
0x1b497  brfalse.s loc_1B4A5
0x1b499  ldloc.2
0x1b49a  ldloc.3
0x1b49b  ldloc.0
0x1b49c  ldloc.s  4
0x1b49e  call     bool System.Deployment.Application.PlatformDetector::DetectFrameworkInRegistry(string setupKeyPath, string setupValueName, class [mscorlib]System.Version versionRequired, bool detectInstallValue)
0x1b4a3  br.s     loc_1B4A9
0x1b4a5  ldc.i4.0
0x1b4a6  br.s     loc_1B4A9
0x1b4a8  ldc.i4.1
0x1b4a9  stloc.s  5
0x1b4ab  ldloc.s  5
0x1b4ad  brtrue.s loc_1B4D1
0x1b4af  ldloc.0
0x1b4b0  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x1b4b5  ldc.i4.4
0x1b4b6  blt.s    loc_1B4D1
0x1b4b8  ldarg.0
0x1b4b9  callvirt instance string System.Deployment.Application.CompatibleFramework::get_SupportedRuntime()
0x1b4be  ldarg.0
0x1b4bf  callvirt instance string System.Deployment.Application.CompatibleFramework::get_TargetVersion()
0x1b4c4  ldarg.0
0x1b4c5  callvirt instance string System.Deployment.Application.CompatibleFramework::get_Profile()
0x1b4ca  call     bool System.Deployment.Application.PlatformDetector::DetectTFMInRegistry(string clrVersion, string frameworkVersion, string profile)
0x1b4cf  stloc.s  5
0x1b4d1  ldloc.s  5
0x1b4d3  brfalse.s loc_1B532
0x1b4d5  ldarg.0
0x1b4d6  callvirt instance string System.Deployment.Application.CompatibleFramework::get_SupportedRuntime()
0x1b4db  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1b4e0  stloc.s  7
0x1b4e2  ldloc.s  7
0x1b4e4  ldarg.3
0x1b4e5  call     bool System.Deployment.Application.NativeMethods::VerifyCLRVersionInfo(class [mscorlib]System.Version v, string procArch)
0x1b4ea  brtrue.s loc_1B51F
0x1b4ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1b4f1  ldstr    aClrmissingforf// "CLRMissingForFoundFramework"
0x1b4f6  call     string System.Deployment.Application.Resources::GetString(string s)
0x1b4fb  ldc.i4.2
0x1b4fc  newarr   [mscorlib]System.Object
0x1b501  dup
0x1b502  ldc.i4.0
0x1b503  ldarg.0
0x1b504  callvirt instance string System.Deployment.Application.CompatibleFramework::get_SupportedRuntime()
0x1b509  stelem.ref
0x1b50a  dup
0x1b50b  ldc.i4.1
0x1b50c  ldarg.0
0x1b50d  call     string System.Deployment.Application.PlatformDetector::FormatFrameworkString(class System.Deployment.Application.CompatibleFramework framework)
0x1b512  stelem.ref
0x1b513  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b518  call     void System.Deployment.Application.Logger::AddWarningInformation(string message)
0x1b51d  ldc.i4.0
0x1b51e  ret
0x1b51f  ldarg.2
0x1b520  ldarg.0
0x1b521  callvirt instance string System.Deployment.Application.CompatibleFramework::get_SupportedRuntime()
0x1b526  stind.ref
0x1b527  ldarg.1
0x1b528  ldarg.2
0x1b529  ldind.ref
0x1b52a  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1b52f  stind.ref
0x1b530  ldc.i4.1
0x1b531  ret
0x1b532  ldc.i4.0
0x1b533  ret
```
