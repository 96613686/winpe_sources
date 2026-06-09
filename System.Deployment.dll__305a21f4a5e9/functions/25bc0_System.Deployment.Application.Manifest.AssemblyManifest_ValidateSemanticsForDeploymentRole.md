# System.Deployment.Application.Manifest.AssemblyManifest::ValidateSemanticsForDeploymentRole

- ea: `0x25bc0`
- end: `0x26244`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::ValidateSemanticsForDeploymentRole`
- size: `1668`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, broker_com_uri`

## callers

- `0x250e0`

## callees

- `0xda80`
- `0xdaa0`
- `0xdab0`
- `0xdef0`
- `0xdf00`
- `0xdf10`
- `0xdf60`
- `0xdf70`
- `0x10160`
- `0x147a0`
- `0x147b0`
- `0x14ba0`
- `0x1b560`
- `0x21910`
- `0x23020`
- `0x23c70`
- `0x23cc0`
- `0x23cd0`
- `0x23fa0`
- `0x23fb0`
- `0x23fc0`
- `0x23fd0`
- `0x23fe0`
- `0x23ff0`
- `0x240c0`
- `0x240d0`
- `0x240e0`
- `0x24420`
- `0x24970`
- `0x24b20`
- `0x24b30`
- `0x24b90`
- `0x24c50`
- `0x24d10`
- `0x24dd0`
- `0x24e90`
- `0x24f90`
- `0x25bc0`
- `0x26af0`
- `0x26d30`

## string_xrefs

- `0x26231`: `Ex_SemanticallyInvalidDeploymentManifest`
- `0x25c32`: `Ex_DepWithUseManifestForTrust`
- `0x25db4`: `Ex_CompatibleFrameworksSupportUrlNoAbsolute`
- `0x25dd8`: `Ex_CompatibleFrameworksSupportUrlNotSupportedUriScheme`
- `0x25e06`: `Ex_CompatibleFrameworksSupportUrlTooLong`
- `0x260c1`: `Ex_DepProviderNotSupportedUriScheme`

## pseudocode

```c

```

## disassembly

```asm
0x25bc0  ldarg.0
0x25bc1  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x25bc6  call     void System.Deployment.Application.Manifest.AssemblyManifest::ValidateAssemblyIdentity(class System.Deployment.Application.DefinitionIdentity identity)
0x25bcb  ldarg.0
0x25bcc  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x25bd1  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken()
0x25bd6  brtrue.s loc_25BEA
0x25bd8  ldc.i4.s 0xC
0x25bda  ldstr    aExDepnotstrong// "Ex_DepNotStronglyNamed"
0x25bdf  call     string System.Deployment.Application.Resources::GetString(string s)
0x25be4  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25be9  throw
0x25bea  ldarg.0
0x25beb  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x25bf0  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_ProcessorArchitecture()
0x25bf5  call     bool System.Deployment.Application.PlatformDetector::IsSupportedProcessorArchitecture(string arch)
0x25bfa  brtrue.s loc_25C0E
0x25bfc  ldc.i4.s 0xC
0x25bfe  ldstr    aExDepprocarchn// "Ex_DepProcArchNotSupported"
0x25c03  call     string System.Deployment.Application.Resources::GetString(string s)
0x25c08  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25c0d  throw
0x25c0e  ldarg.0
0x25c0f  call     instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x25c14  brtrue.s loc_25C28
0x25c16  ldc.i4.s 0xC
0x25c18  ldstr    aExDepmissingde// "Ex_DepMissingDeploymentSection"
0x25c1d  call     string System.Deployment.Application.Resources::GetString(string s)
0x25c22  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25c27  throw
0x25c28  ldarg.0
0x25c29  call     instance bool System.Deployment.Application.Manifest.AssemblyManifest::get_UseManifestForTrust()
0x25c2e  brfalse.s loc_25C42
0x25c30  ldc.i4.s 0xC
0x25c32  ldstr    aExDepwithusema// "Ex_DepWithUseManifestForTrust"
0x25c37  call     string System.Deployment.Application.Resources::GetString(string s)
0x25c3c  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25c41  throw
0x25c42  ldarg.0
0x25c43  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x25c48  brfalse.s loc_25C6E
0x25c4a  ldarg.0
0x25c4b  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x25c50  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredPublisher()
0x25c55  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25c5a  brtrue.s loc_25C6E
0x25c5c  ldarg.0
0x25c5d  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x25c62  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredProduct()
0x25c67  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25c6c  brfalse.s loc_25C80
0x25c6e  ldc.i4.s 0xC
0x25c70  ldstr    aExDeppublisher// "Ex_DepPublisherProductRequired"
0x25c75  call     string System.Deployment.Application.Resources::GetString(string s)
0x25c7a  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25c7f  throw
0x25c80  ldarg.0
0x25c81  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x25c86  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredPublisher()
0x25c8b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x25c90  ldarg.0
0x25c91  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x25c96  callvirt instance string System.Deployment.Application.Manifest.Description::get_FilteredProduct()
0x25c9b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x25ca0  add
0x25ca1  ldc.i4   0x104
0x25ca6  ble.s    loc_25CBA
0x25ca8  ldc.i4.s 0xC
0x25caa  ldstr    aExPublisherpro// "Ex_PublisherProductNameTooLong"
0x25caf  call     string System.Deployment.Application.Resources::GetString(string s)
0x25cb4  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25cb9  throw
0x25cba  ldarg.0
0x25cbb  call     instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x25cc0  ldlen
0x25cc1  brfalse.s loc_25CD5
0x25cc3  ldc.i4.s 0xC
0x25cc5  ldstr    aExDepentrypoin// "Ex_DepEntryPointNotAllowed"
0x25cca  call     string System.Deployment.Application.Resources::GetString(string s)
0x25ccf  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25cd4  throw
0x25cd5  ldarg.0
0x25cd6  call     instance class System.Deployment.Application.Manifest.File[] System.Deployment.Application.Manifest.AssemblyManifest::get_Files()
0x25cdb  ldlen
0x25cdc  brfalse.s loc_25CF0
0x25cde  ldc.i4.s 0xC
0x25ce0  ldstr    aExDepfilenotal// "Ex_DepFileNotAllowed"
0x25ce5  call     string System.Deployment.Application.Resources::GetString(string s)
0x25cea  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25cef  throw
0x25cf0  ldarg.0
0x25cf1  call     instance class System.Deployment.Application.Manifest.FileAssociation[] System.Deployment.Application.Manifest.AssemblyManifest::get_FileAssociations()
0x25cf6  ldlen
0x25cf7  brfalse.s loc_25D0B
0x25cf9  ldc.i4.s 0xC
0x25cfb  ldstr    aExDepfileassoc// "Ex_DepFileAssocNotAllowed"
0x25d00  call     string System.Deployment.Application.Resources::GetString(string s)
0x25d05  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25d0a  throw
0x25d0b  ldarg.0
0x25d0c  call     instance class System.Deployment.Application.Manifest.Description System.Deployment.Application.Manifest.AssemblyManifest::get_Description()
0x25d11  callvirt instance string System.Deployment.Application.Manifest.Description::get_IconFile()
0x25d16  brfalse.s loc_25D2A
0x25d18  ldc.i4.s 0xC
0x25d1a  ldstr    aExDepiconfilen// "Ex_DepIconFileNotAllowed"
0x25d1f  call     string System.Deployment.Application.Resources::GetString(string s)
0x25d24  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25d29  throw
0x25d2a  ldarg.0
0x25d2b  call     instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x25d30  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_DisallowUrlActivation()
0x25d35  brfalse.s loc_25D56
0x25d37  ldarg.0
0x25d38  call     instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x25d3d  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_Install()
0x25d42  brtrue.s loc_25D56
0x25d44  ldc.i4.s 0xC
0x25d46  ldstr    aExDeponlineonl// "Ex_DepOnlineOnlyAndDisallowUrlActivatio"...
0x25d4b  call     string System.Deployment.Application.Resources::GetString(string s)
0x25d50  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25d55  throw
0x25d56  ldarg.0
0x25d57  call     instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x25d5c  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_DisallowUrlActivation()
0x25d61  brfalse.s loc_25D82
0x25d63  ldarg.0
0x25d64  call     instance class System.Deployment.Application.Manifest.Deployment System.Deployment.Application.Manifest.AssemblyManifest::get_Deployment()
0x25d69  callvirt instance bool System.Deployment.Application.Manifest.Deployment::get_TrustURLParameters()
0x25d6e  brfalse.s loc_25D82
0x25d70  ldc.i4.s 0xC
0x25d72  ldstr    aExDeptrusturla// "Ex_DepTrustUrlAndDisallowUrlActivation"
0x25d77  call     string System.Deployment.Application.Resources::GetString(string s)
0x25d7c  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25d81  throw
0x25d82  ldarg.0
0x25d83  call     instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x25d88  brfalse  loc_26066
0x25d8d  ldarg.0
0x25d8e  call     instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x25d93  callvirt instance class [System]System.Uri System.Deployment.Application.CompatibleFrameworks::get_SupportUrl()
0x25d98  ldnull
0x25d99  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x25d9e  brfalse.s loc_25E16
0x25da0  ldarg.0
0x25da1  call     instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x25da6  callvirt instance class [System]System.Uri System.Deployment.Application.CompatibleFrameworks::get_SupportUrl()
0x25dab  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x25db0  brtrue.s loc_25DC4
0x25db2  ldc.i4.s 0x11
0x25db4  ldstr    aExCompatiblefr_1// "Ex_CompatibleFrameworksSupportUrlNoAbso"...
0x25db9  call     string System.Deployment.Application.Resources::GetString(string s)
0x25dbe  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25dc3  throw
0x25dc4  ldarg.0
0x25dc5  call     instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x25dca  callvirt instance class [System]System.Uri System.Deployment.Application.CompatibleFrameworks::get_SupportUrl()
0x25dcf  call     bool System.Deployment.Application.UriHelper::IsSupportedScheme(class [System]System.Uri uri)
0x25dd4  brtrue.s loc_25DE8
0x25dd6  ldc.i4.s 0xC
0x25dd8  ldstr    aExCompatiblefr_2// "Ex_CompatibleFrameworksSupportUrlNotSup"...
0x25ddd  call     string System.Deployment.Application.Resources::GetString(string s)
0x25de2  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25de7  throw
0x25de8  ldarg.0
0x25de9  call     instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x25dee  callvirt instance class [System]System.Uri System.Deployment.Application.CompatibleFrameworks::get_SupportUrl()
0x25df3  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x25df8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x25dfd  ldc.i4   0x4000
0x25e02  ble.s    loc_25E16
0x25e04  ldc.i4.s 0x11
0x25e06  ldstr    aExCompatiblefr_3// "Ex_CompatibleFrameworksSupportUrlTooLon"...
0x25e0b  call     string System.Deployment.Application.Resources::GetString(string s)
0x25e10  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25e15  throw
0x25e16  ldarg.0
0x25e17  call     instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x25e1c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Deployment.Application.CompatibleFramework> System.Deployment.Application.CompatibleFrameworks::get_Frameworks()
0x25e21  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class System.Deployment.Application.CompatibleFramework>::get_Count()
0x25e26  ldc.i4.1
0x25e27  bge.s    loc_25E3B
0x25e29  ldc.i4.s 0xC
0x25e2b  ldstr    aExDepatleaston// "Ex_DepAtLeastOneFramework"
0x25e30  call     string System.Deployment.Application.Resources::GetString(string s)
0x25e35  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25e3a  throw
0x25e3b  ldc.i4.0
0x25e3c  stloc.0
0x25e3d  br       loc_26050
0x25e42  ldarg.0
0x25e43  call     instance class System.Deployment.Application.CompatibleFrameworks System.Deployment.Application.Manifest.AssemblyManifest::get_CompatibleFrameworks()
0x25e48  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class System.Deployment.Application.CompatibleFramework> System.Deployment.Application.CompatibleFrameworks::get_Frameworks()
0x25e4d  ldloc.0
0x25e4e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class System.Deployment.Application.CompatibleFramework>::get_Item(!!T0)
0x25e53  stloc.1
0x25e54  ldnull
0x25e55  stloc.2
0x25e56  ldloc.1
0x25e57  callvirt instance string System.Deployment.Application.CompatibleFramework::get_TargetVersion()
0x25e5c  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x25e61  stloc.2
0x25e62  leave.s  loc_25E9B
0x25e64  stloc.3
0x25e65  ldloc.3
0x25e66  call     bool System.Deployment.Application.ExceptionUtility::IsHardException(class [mscorlib]System.Exception exception)
0x25e6b  brfalse.s loc_25E6F
0x25e6d  rethrow
0x25e6f  ldc.i4.s 0xC
0x25e71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x25e76  ldstr    aExDepinvalidta// "Ex_DepInvalidTargetVersion"
0x25e7b  call     string System.Deployment.Application.Resources::GetString(string s)
0x25e80  ldc.i4.1
0x25e81  newarr   [mscorlib]System.Object
0x25e86  dup
0x25e87  ldc.i4.0
0x25e88  ldloc.1
0x25e89  callvirt instance string System.Deployment.Application.CompatibleFramework::get_TargetVersion()
0x25e8e  stelem.ref
0x25e8f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25e94  ldloc.3
0x25e95  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x25e9a  throw
0x25e9b  nop
0x25e9c  ldloc.1
0x25e9d  callvirt instance string System.Deployment.Application.CompatibleFramework::get_SupportedRuntime()
0x25ea2  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x25ea7  stloc.s  4
0x25ea9  leave.s  loc_25EE5
0x25eab  stloc.s  5
0x25ead  ldloc.s  5
0x25eaf  call     bool System.Deployment.Application.ExceptionUtility::IsHardException(class [mscorlib]System.Exception exception)
0x25eb4  brfalse.s loc_25EB8
0x25eb6  rethrow
0x25eb8  ldc.i4.s 0xC
0x25eba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x25ebf  ldstr    aExDepinvalidsu// "Ex_DepInvalidSupportedRuntime"
0x25ec4  call     string System.Deployment.Application.Resources::GetString(string s)
0x25ec9  ldc.i4.1
0x25eca  newarr   [mscorlib]System.Object
0x25ecf  dup
0x25ed0  ldc.i4.0
0x25ed1  ldloc.1
0x25ed2  callvirt instance string System.Deployment.Application.CompatibleFramework::get_SupportedRuntime()
0x25ed7  stelem.ref
0x25ed8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25edd  ldloc.s  5
0x25edf  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x25ee4  throw
0x25ee5  ldloc.2
0x25ee6  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x25eeb  stloc.s  6
0x25eed  ldloc.s  6
0x25eef  ldc.i4.2
0x25ef0  beq.s    loc_25EFC
0x25ef2  ldloc.s  6
0x25ef4  ldc.i4.3
0x25ef5  beq.s    loc_25F40
0x25ef7  br       loc_25FE0
0x25efc  ldloc.1
0x25efd  callvirt instance string System.Deployment.Application.CompatibleFramework::get_Profile()
0x25f02  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25f07  brtrue   loc_2604C
0x25f0c  ldc.i4.s 0xC
0x25f0e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x25f13  ldstr    aExDepunsupport// "Ex_DepUnsupportedFrameworkProfile"
0x25f18  call     string System.Deployment.Application.Resources::GetString(string s)
0x25f1d  ldc.i4.2
0x25f1e  newarr   [mscorlib]System.Object
0x25f23  dup
0x25f24  ldc.i4.0
0x25f25  ldloc.1
0x25f26  callvirt instance string System.Deployment.Application.CompatibleFramework::get_Profile()
0x25f2b  stelem.ref
0x25f2c  dup
0x25f2d  ldc.i4.1
0x25f2e  ldloc.1
0x25f2f  callvirt instance string System.Deployment.Application.CompatibleFramework::get_TargetVersion()
0x25f34  stelem.ref
0x25f35  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25f3a  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25f3f  throw
0x25f40  ldloc.2
0x25f41  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x25f46  ldc.i4.1
0x25f47  blt.s    loc_25F7D
0x25f49  ldloc.2
0x25f4a  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x25f4f  ldc.i4.5
0x25f50  bge.s    loc_25F7D
0x25f52  ldc.i4.s 0xC
0x25f54  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x25f59  ldstr    aExDepunsupport_0// "Ex_DepUnsupportedFrameworkTargetVersion"
0x25f5e  call     string System.Deployment.Application.Resources::GetString(string s)
0x25f63  ldc.i4.1
0x25f64  newarr   [mscorlib]System.Object
0x25f69  dup
0x25f6a  ldc.i4.0
0x25f6b  ldloc.1
0x25f6c  callvirt instance string System.Deployment.Application.CompatibleFramework::get_TargetVersion()
0x25f71  stelem.ref
  ... truncated ...
```
