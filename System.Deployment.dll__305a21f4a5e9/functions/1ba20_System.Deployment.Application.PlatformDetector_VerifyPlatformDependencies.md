# System.Deployment.Application.PlatformDetector::VerifyPlatformDependencies

- ea: `0x1ba20`
- end: `0x1bfed`
- name: `System.Deployment.Application.PlatformDetector::VerifyPlatformDependencies`
- size: `1485`
- prototype: ``
- caller_count: `2`
- callee_count: `50`
- tags: `registry_config, broker_com_uri`

## callers

- `0xba90`
- `0x11a20`

## callees

- `0xdab0`
- `0xdd30`
- `0xdd50`
- `0xdd80`
- `0xdf60`
- `0xdf70`
- `0x147a0`
- `0x147b0`
- `0x14900`
- `0x14950`
- `0x14a30`
- `0x14af0`
- `0x17cd0`
- `0x17d50`
- `0x1a420`
- `0x1a510`
- `0x1b240`
- `0x1b390`
- `0x1b540`
- `0x1b690`
- `0x1b880`
- `0x1ba00`
- `0x1ba20`
- `0x1bff0`
- `0x1c010`
- `0x1c030`
- `0x23020`
- `0x23650`
- `0x23c40`
- `0x23dc0`
- `0x23e70`
- `0x23e80`
- `0x23e90`
- `0x23ea0`
- `0x23eb0`
- `0x23ec0`
- `0x24380`
- `0x243b0`
- `0x243d0`
- `0x243e0`
- `0x24400`
- `0x24970`
- `0x24b30`
- `0x24bf0`
- `0x24c50`
- `0x24e90`
- `0x24f90`
- `0x25060`
- `0x2ab10`
- `0x2c030`

## string_xrefs

- `0x1bc83`: `ErrorMessage_CompatiblePlatformDetectionFailed`
- `0x1bcce`: `Ex_SemanticallyInvalidDeploymentManifest`
- `0x1bcda`: `Ex_DepMissingCompatibleFrameworks`
- `0x1bd06`: `PlatformMicrosoftCommonLanguageRuntime`
- `0x1bda1`: `PlatformMicrosoftCommonLanguageRuntime`
- `0x1bd4e`: `CompatibleRuntimeFound`

## pseudocode

```c

```

## disassembly

```asm
0x1ba20  ldstr    aVerifyplatform// "VerifyPlatformDependencies called."
0x1ba25  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1ba2a  ldnull
0x1ba2b  stloc.0
0x1ba2c  ldarg.1
0x1ba2d  callvirt instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x1ba32  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.Description::get_SupportUri()
0x1ba37  stloc.1
0x1ba38  ldc.i4.0
0x1ba39  stloc.2
0x1ba3a  ldarg.0
0x1ba3b  callvirt instance class System.Deployment.Application.Manifest.DependentOS System.Deployment.Application.Manifest.AssemblyManifest::get_DependentOS()
0x1ba40  stloc.3
0x1ba41  ldloc.3
0x1ba42  brfalse  loc_1BB56
0x1ba47  ldloc.3
0x1ba48  callvirt instance unsigned int16 System.Deployment.Application.Manifest.DependentOS::get_MajorVersion()
0x1ba4d  ldloc.3
0x1ba4e  callvirt instance unsigned int16 System.Deployment.Application.Manifest.DependentOS::get_MinorVersion()
0x1ba53  ldloc.3
0x1ba54  callvirt instance unsigned int16 System.Deployment.Application.Manifest.DependentOS::get_BuildNumber()
0x1ba59  ldloc.3
0x1ba5a  callvirt instance unsigned int8 System.Deployment.Application.Manifest.DependentOS::get_ServicePackMajor()
0x1ba5f  ldloc.3
0x1ba60  callvirt instance unsigned int8 System.Deployment.Application.Manifest.DependentOS::get_ServicePackMinor()
0x1ba65  ldnull
0x1ba66  ldnull
0x1ba67  newobj   instance void OSDependency::.ctor(unsigned int32 dwMajorVersion, unsigned int32 dwMinorVersion, unsigned int32 dwBuildNumber, unsigned int16 wServicePackMajor, unsigned int16 wServicePackMinor, string suiteName, string productName)
0x1ba6c  stloc.s  0xA
0x1ba6e  ldloca.s 0xA
0x1ba70  call     bool System.Deployment.Application.PlatformDetector::VerifyOSDependency(class OSDependency& osd)
0x1ba75  brtrue   loc_1BB56
0x1ba7a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1ba7f  stloc.s  0xB
0x1ba81  ldc.i4.8
0x1ba82  newarr   [mscorlib]System.String
0x1ba87  dup
0x1ba88  ldc.i4.0
0x1ba89  ldloc.3
0x1ba8a  callvirt instance unsigned int16 System.Deployment.Application.Manifest.DependentOS::get_MajorVersion()
0x1ba8f  stloc.s  0xD
0x1ba91  ldloca.s 0xD
0x1ba93  call     instance string [mscorlib]System.UInt16::ToString()
0x1ba98  stelem.ref
0x1ba99  dup
0x1ba9a  ldc.i4.1
0x1ba9b  ldstr    asc_36E38// "."
0x1baa0  stelem.ref
0x1baa1  dup
0x1baa2  ldc.i4.2
0x1baa3  ldloc.3
0x1baa4  callvirt instance unsigned int16 System.Deployment.Application.Manifest.DependentOS::get_MinorVersion()
0x1baa9  stloc.s  0xD
0x1baab  ldloca.s 0xD
0x1baad  call     instance string [mscorlib]System.UInt16::ToString()
0x1bab2  stelem.ref
0x1bab3  dup
0x1bab4  ldc.i4.3
0x1bab5  ldstr    asc_36E38// "."
0x1baba  stelem.ref
0x1babb  dup
0x1babc  ldc.i4.4
0x1babd  ldloc.3
0x1babe  callvirt instance unsigned int16 System.Deployment.Application.Manifest.DependentOS::get_BuildNumber()
0x1bac3  stloc.s  0xD
0x1bac5  ldloca.s 0xD
0x1bac7  call     instance string [mscorlib]System.UInt16::ToString()
0x1bacc  stelem.ref
0x1bacd  dup
0x1bace  ldc.i4.5
0x1bacf  ldstr    asc_36E38// "."
0x1bad4  stelem.ref
0x1bad5  dup
0x1bad6  ldc.i4.6
0x1bad7  ldloc.3
0x1bad8  callvirt instance unsigned int8 System.Deployment.Application.Manifest.DependentOS::get_ServicePackMajor()
0x1badd  stloc.s  0xE
0x1badf  ldloca.s 0xE
0x1bae1  call     instance string [mscorlib]System.Byte::ToString()
0x1bae6  stelem.ref
0x1bae7  dup
0x1bae8  ldc.i4.7
0x1bae9  ldloc.3
0x1baea  callvirt instance unsigned int8 System.Deployment.Application.Manifest.DependentOS::get_ServicePackMinor()
0x1baef  stloc.s  0xE
0x1baf1  ldloca.s 0xE
0x1baf3  call     instance string [mscorlib]System.Byte::ToString()
0x1baf8  stelem.ref
0x1baf9  call     string [mscorlib]System.String::Concat(string[])
0x1bafe  stloc.s  0xC
0x1bb00  ldloc.s  0xB
0x1bb02  ldstr    aPlatformmicros// "PlatformMicrosoftWindowsOperatingSystem"
0x1bb07  call     string System.Deployment.Application.Resources::GetString(string s)
0x1bb0c  ldloc.s  0xC
0x1bb0e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x1bb13  pop
0x1bb14  ldloc.s  0xB
0x1bb16  callvirt instance string [mscorlib]System.Object::ToString()
0x1bb1b  stloc.0
0x1bb1c  ldloc.3
0x1bb1d  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.DependentOS::get_SupportUrl()
0x1bb22  ldnull
0x1bb23  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1bb28  brfalse.s loc_1BB31
0x1bb2a  ldloc.3
0x1bb2b  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.DependentOS::get_SupportUrl()
0x1bb30  stloc.1
0x1bb31  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1bb36  ldstr    aErrormessagePl// "ErrorMessage_PlatformDetectionFailed"
0x1bb3b  call     string System.Deployment.Application.Resources::GetString(string s)
0x1bb40  ldc.i4.1
0x1bb41  newarr   [mscorlib]System.Object
0x1bb46  dup
0x1bb47  ldc.i4.0
0x1bb48  ldloc.0
0x1bb49  stelem.ref
0x1bb4a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1bb4f  ldloc.1
0x1bb50  newobj   instance void System.Deployment.Application.DependentPlatformMissingException::.ctor(string message, class [System]System.Uri supportUrl)
0x1bb55  throw
0x1bb56  call     bool System.Deployment.Application.PlatformDetector::IsWin8orLater()
0x1bb5b  brfalse.s loc_1BB6E
0x1bb5d  ldarg.0
0x1bb5e  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x1bb63  ldc.i4.0
0x1bb64  ldelem.ref
0x1bb65  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_HostInBrowser()
0x1bb6a  brtrue.s loc_1BB6E
0x1bb6c  ldc.i4.1
0x1bb6d  stloc.2
0x1bb6e  ldsfld   class [mscorlib]System.Version System.Deployment.Application.Constants::V2CLRVersion
0x1bb73  stloc.s  4
0x1bb75  ldloc.s  4
0x1bb77  ldc.i4.3
0x1bb78  callvirt instance string [mscorlib]System.Version::ToString(int32)
0x1bb7d  stloc.s  5
0x1bb7f  ldarg.0
0x1bb80  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1bb85  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_ProcessorArchitecture()
0x1bb8a  stloc.s  6
0x1bb8c  ldloc.1
0x1bb8d  stloc.s  7
0x1bb8f  ldarg.0
0x1bb90  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_CLRDependentAssembly()
0x1bb95  brfalse.s loc_1BBFE
0x1bb97  ldarg.0
0x1bb98  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_CLRDependentAssembly()
0x1bb9d  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x1bba2  callvirt instance class [mscorlib]System.Version System.Deployment.Application.ReferenceIdentity::get_Version()
0x1bba7  stloc.s  4
0x1bba9  ldloc.s  4
0x1bbab  ldc.i4.3
0x1bbac  callvirt instance string [mscorlib]System.Version::ToString(int32)
0x1bbb1  stloc.s  5
0x1bbb3  ldarg.0
0x1bbb4  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_CLRDependentAssembly()
0x1bbb9  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x1bbbe  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_ProcessorArchitecture()
0x1bbc3  stloc.s  6
0x1bbc5  ldarg.0
0x1bbc6  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_CLRDependentAssembly()
0x1bbcb  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.DependentAssembly::get_SupportUrl()
0x1bbd0  ldnull
0x1bbd1  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1bbd6  brfalse.s loc_1BBE5
0x1bbd8  ldarg.0
0x1bbd9  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_CLRDependentAssembly()
0x1bbde  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.DependentAssembly::get_SupportUrl()
0x1bbe3  stloc.s  7
0x1bbe5  ldarg.0
0x1bbe6  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_CLRDependentAssembly()
0x1bbeb  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Description()
0x1bbf0  brfalse.s loc_1BBFE
0x1bbf2  ldarg.0
0x1bbf3  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.AssemblyManifest::get_CLRDependentAssembly()
0x1bbf8  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Description()
0x1bbfd  stloc.0
0x1bbfe  ldarg.1
0x1bbff  callvirt instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x1bc04  brfalse  loc_1BCBE
0x1bc09  ldc.i4.0
0x1bc0a  stloc.s  0xF
0x1bc0c  ldc.i4.0
0x1bc0d  stloc.s  0x10
0x1bc0f  br.s     loc_1BC3B
0x1bc11  ldarg.1
0x1bc12  callvirt instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x1bc17  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Deployment.Application.CompatibleFramework> System.Deployment.Application.CompatibleFrameworks::get_Frameworks()
0x1bc1c  ldloc.s  0x10
0x1bc1e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Deployment.Application.CompatibleFramework>::get_Item(!!T0)
0x1bc23  ldloca.s 4
0x1bc25  ldloca.s 5
0x1bc27  ldloc.s  6
0x1bc29  call     bool System.Deployment.Application.PlatformDetector::CheckCompatibleFramework(class System.Deployment.Application.CompatibleFramework framework, class [mscorlib]System.Version& clrVersion, string& clrVersionString, string clrProcArch)
0x1bc2e  brfalse.s loc_1BC35
0x1bc30  ldc.i4.1
0x1bc31  stloc.s  0xF
0x1bc33  br.s     loc_1BC4F
0x1bc35  ldloc.s  0x10
0x1bc37  ldc.i4.1
0x1bc38  add
0x1bc39  stloc.s  0x10
0x1bc3b  ldloc.s  0x10
0x1bc3d  ldarg.1
0x1bc3e  callvirt instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x1bc43  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Deployment.Application.CompatibleFramework> System.Deployment.Application.CompatibleFrameworks::get_Frameworks()
0x1bc48  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Deployment.Application.CompatibleFramework>::get_Count()
0x1bc4d  blt.s    loc_1BC11
0x1bc4f  ldloc.s  0xF
0x1bc51  brtrue   loc_1BD4E
0x1bc56  ldarg.1
0x1bc57  callvirt instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x1bc5c  callvirt instance class [System]System.Uri System.Deployment.Application.CompatibleFrameworks::get_SupportUrl()
0x1bc61  ldnull
0x1bc62  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1bc67  brfalse.s loc_1BC77
0x1bc69  ldarg.1
0x1bc6a  callvirt instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x1bc6f  callvirt instance class [System]System.Uri System.Deployment.Application.CompatibleFrameworks::get_SupportUrl()
0x1bc74  stloc.1
0x1bc75  br.s     loc_1BC7A
0x1bc77  ldloc.s  7
0x1bc79  stloc.1
0x1bc7a  ldloc.2
0x1bc7b  brfalse.s loc_1BC7E
0x1bc7d  ret
0x1bc7e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1bc83  ldstr    aErrormessageCo_0// "ErrorMessage_CompatiblePlatformDetectio"...
0x1bc88  call     string System.Deployment.Application.Resources::GetString(string s)
0x1bc8d  ldc.i4.1
0x1bc8e  newarr   [mscorlib]System.Object
0x1bc93  dup
0x1bc94  ldc.i4.0
0x1bc95  ldarg.1
0x1bc96  callvirt instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x1bc9b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Deployment.Application.CompatibleFramework> System.Deployment.Application.CompatibleFrameworks::get_Frameworks()
0x1bca0  ldc.i4.0
0x1bca1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Deployment.Application.CompatibleFramework>::get_Item(!!T0)
0x1bca6  call     string System.Deployment.Application.PlatformDetector::FormatFrameworkString(class System.Deployment.Application.CompatibleFramework framework)
0x1bcab  stelem.ref
0x1bcac  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1bcb1  ldloc.1
0x1bcb2  ldarg.1
0x1bcb3  callvirt instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x1bcb8  newobj   instance void System.Deployment.Application.CompatibleFrameworkMissingException::.ctor(string message, class [System]System.Uri supportUrl, class System.Deployment.Application.CompatibleFrameworks compatibleFrameworks)
0x1bcbd  throw
0x1bcbe  ldloc.s  4
0x1bcc0  ldsfld   class [mscorlib]System.Version System.Deployment.Application.Constants::V4CLRVersion
0x1bcc5  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1bcca  brfalse.s loc_1BCEF
0x1bccc  ldc.i4.s 0x10
0x1bcce  ldstr    aExSemantically// "Ex_SemanticallyInvalidDeploymentManifes"...
0x1bcd3  call     string System.Deployment.Application.Resources::GetString(string s)
0x1bcd8  ldc.i4.s 0xC
0x1bcda  ldstr    aExDepmissingco// "Ex_DepMissingCompatibleFrameworks"
0x1bcdf  call     string System.Deployment.Application.Resources::GetString(string s)
0x1bce4  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1bce9  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x1bcee  throw
0x1bcef  ldloc.s  4
0x1bcf1  ldloc.s  6
0x1bcf3  call     bool System.Deployment.Application.NativeMethods::VerifyCLRVersionInfo(class [mscorlib]System.Version v, string procArch)
0x1bcf8  brtrue.s loc_1BD4E
0x1bcfa  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1bcff  stloc.s  0x11
0x1bd01  ldloc.0
0x1bd02  brtrue.s loc_1BD20
0x1bd04  ldloc.s  0x11
0x1bd06  ldstr    aPlatformmicros_0// "PlatformMicrosoftCommonLanguageRuntime"
0x1bd0b  call     string System.Deployment.Application.Resources::GetString(string s)
0x1bd10  ldloc.s  5
0x1bd12  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x1bd17  pop
0x1bd18  ldloc.s  0x11
0x1bd1a  callvirt instance string [mscorlib]System.Object::ToString()
0x1bd1f  stloc.0
0x1bd20  ldloc.s  7
0x1bd22  stloc.1
0x1bd23  ldloc.2
0x1bd24  brfalse.s loc_1BD27
0x1bd26  ret
0x1bd27  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1bd2c  ldstr    aErrormessagePl// "ErrorMessage_PlatformDetectionFailed"
0x1bd31  call     string System.Deployment.Application.Resources::GetString(string s)
0x1bd36  ldc.i4.1
0x1bd37  newarr   [mscorlib]System.Object
0x1bd3c  dup
0x1bd3d  ldc.i4.0
0x1bd3e  ldloc.0
0x1bd3f  stelem.ref
0x1bd40  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1bd45  ldloc.1
0x1bd46  ldloc.s  5
0x1bd48  newobj   instance void System.Deployment.Application.SupportedRuntimeMissingException::.ctor(string message, class [System]System.Uri supportUrl, string supportedRuntimeVersion)
0x1bd4d  throw
0x1bd4e  ldstr    aCompatiblerunt// "CompatibleRuntimeFound"
0x1bd53  call     string System.Deployment.Application.Resources::GetString(string s)
0x1bd58  ldc.i4.1
0x1bd59  newarr   [mscorlib]System.Object
0x1bd5e  dup
  ... truncated ...
```
