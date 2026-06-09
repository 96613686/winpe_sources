# System.Deployment.Application.Manifest.AssemblyManifest::ValidateComponentDependency

- ea: `0x26ea0`
- end: `0x2724b`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::ValidateComponentDependency`
- size: `939`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x26250`

## callees

- `0xdd30`
- `0xdd40`
- `0xdd70`
- `0x10160`
- `0x147a0`
- `0x1b540`
- `0x21910`
- `0x219c0`
- `0x23020`
- `0x24380`
- `0x24390`
- `0x243b0`
- `0x243e0`
- `0x243f0`
- `0x24400`
- `0x24410`
- `0x24420`
- `0x26c10`
- `0x26ea0`
- `0x27340`

## string_xrefs

- `0x26f4a`: `Ex_DependencyNotRelativePath`
- `0x270c8`: `Ex_DependencyNotRelativePath`
- `0x271da`: `Ex_DependencySupportUrlNotSupportedUriScheme`

## pseudocode

```c

```

## disassembly

```asm
0x26ea0  ldarg.0
0x26ea1  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26ea6  call     void System.Deployment.Application.Manifest.AssemblyManifest::ValidateAssemblyIdentity(class System.Deployment.Application.ReferenceIdentity identity)
0x26eab  ldarg.0
0x26eac  callvirt instance bool System.Deployment.Application.Manifest.DependentAssembly::get_IsPreRequisite()
0x26eb1  brtrue   loc_27129
0x26eb6  ldarg.0
0x26eb7  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_ResourceFallbackCulture()
0x26ebc  brtrue   loc_26FB9
0x26ec1  ldarg.0
0x26ec2  callvirt instance class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.DependentAssembly::get_HashCollection()
0x26ec7  call     bool System.Deployment.Application.Manifest.AssemblyManifest::IsInvalidHash(class System.Deployment.Application.HashCollection hashCollection)
0x26ecc  brfalse.s loc_26EFE
0x26ece  ldc.i4.s 0x11
0x26ed0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x26ed5  ldstr    aExDependencyin// "Ex_DependencyInvalidHash"
0x26eda  call     string System.Deployment.Application.Resources::GetString(string s)
0x26edf  ldc.i4.1
0x26ee0  newarr   [mscorlib]System.Object
0x26ee5  dup
0x26ee6  ldc.i4.0
0x26ee7  ldarg.0
0x26ee8  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26eed  callvirt instance string [mscorlib]System.Object::ToString()
0x26ef2  stelem.ref
0x26ef3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26ef8  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26efd  throw
0x26efe  ldarg.0
0x26eff  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x26f04  brtrue.s loc_26F36
0x26f06  ldc.i4.s 0x11
0x26f08  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x26f0d  ldstr    aExDependencyno// "Ex_DependencyNoCodebase"
0x26f12  call     string System.Deployment.Application.Resources::GetString(string s)
0x26f17  ldc.i4.1
0x26f18  newarr   [mscorlib]System.Object
0x26f1d  dup
0x26f1e  ldc.i4.0
0x26f1f  ldarg.0
0x26f20  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26f25  callvirt instance string [mscorlib]System.Object::ToString()
0x26f2a  stelem.ref
0x26f2b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26f30  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26f35  throw
0x26f36  ldarg.0
0x26f37  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x26f3c  call     bool System.Deployment.Application.UriHelper::IsValidRelativeFilePath(string path)
0x26f41  brtrue.s loc_26F73
0x26f43  ldc.i4.s 0x11
0x26f45  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x26f4a  ldstr    aExDependencyno_0// "Ex_DependencyNotRelativePath"
0x26f4f  call     string System.Deployment.Application.Resources::GetString(string s)
0x26f54  ldc.i4.1
0x26f55  newarr   [mscorlib]System.Object
0x26f5a  dup
0x26f5b  ldc.i4.0
0x26f5c  ldarg.0
0x26f5d  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26f62  callvirt instance string [mscorlib]System.Object::ToString()
0x26f67  stelem.ref
0x26f68  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26f6d  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26f72  throw
0x26f73  ldarg.0
0x26f74  callvirt instance bool System.Deployment.Application.Manifest.DependentAssembly::get_IsOptional()
0x26f79  brfalse  loc_27178
0x26f7e  ldarg.0
0x26f7f  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Group()
0x26f84  brtrue   loc_27178
0x26f89  ldc.i4.s 0x11
0x26f8b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x26f90  ldstr    aExDependencyop// "Ex_DependencyOptionalButNoGroup"
0x26f95  call     string System.Deployment.Application.Resources::GetString(string s)
0x26f9a  ldc.i4.1
0x26f9b  newarr   [mscorlib]System.Object
0x26fa0  dup
0x26fa1  ldc.i4.0
0x26fa2  ldarg.0
0x26fa3  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26fa8  callvirt instance string [mscorlib]System.Object::ToString()
0x26fad  stelem.ref
0x26fae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26fb3  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26fb8  throw
0x26fb9  ldarg.0
0x26fba  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26fbf  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_Culture()
0x26fc4  brtrue.s loc_2703F
0x26fc6  ldarg.0
0x26fc7  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x26fcc  brfalse.s loc_26FFE
0x26fce  ldc.i4.s 0x11
0x26fd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x26fd5  ldstr    aExDependencyre// "Ex_DependencyResourceWithCodebase"
0x26fda  call     string System.Deployment.Application.Resources::GetString(string s)
0x26fdf  ldc.i4.1
0x26fe0  newarr   [mscorlib]System.Object
0x26fe5  dup
0x26fe6  ldc.i4.0
0x26fe7  ldarg.0
0x26fe8  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26fed  callvirt instance string [mscorlib]System.Object::ToString()
0x26ff2  stelem.ref
0x26ff3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26ff8  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26ffd  throw
0x26ffe  ldarg.0
0x26fff  callvirt instance class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.DependentAssembly::get_HashCollection()
0x27004  callvirt instance int32 System.Deployment.Application.HashCollection::get_Count()
0x27009  ldc.i4.0
0x2700a  ble      loc_27178
0x2700f  ldc.i4.s 0x11
0x27011  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x27016  ldstr    aExDependencyre_0// "Ex_DependencyResourceWithHash"
0x2701b  call     string System.Deployment.Application.Resources::GetString(string s)
0x27020  ldc.i4.1
0x27021  newarr   [mscorlib]System.Object
0x27026  dup
0x27027  ldc.i4.0
0x27028  ldarg.0
0x27029  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x2702e  callvirt instance string [mscorlib]System.Object::ToString()
0x27033  stelem.ref
0x27034  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27039  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2703e  throw
0x2703f  ldarg.0
0x27040  callvirt instance class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.DependentAssembly::get_HashCollection()
0x27045  call     bool System.Deployment.Application.Manifest.AssemblyManifest::IsInvalidHash(class System.Deployment.Application.HashCollection hashCollection)
0x2704a  brfalse.s loc_2707C
0x2704c  ldc.i4.s 0x11
0x2704e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x27053  ldstr    aExDependencyin// "Ex_DependencyInvalidHash"
0x27058  call     string System.Deployment.Application.Resources::GetString(string s)
0x2705d  ldc.i4.1
0x2705e  newarr   [mscorlib]System.Object
0x27063  dup
0x27064  ldc.i4.0
0x27065  ldarg.0
0x27066  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x2706b  callvirt instance string [mscorlib]System.Object::ToString()
0x27070  stelem.ref
0x27071  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27076  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2707b  throw
0x2707c  ldarg.0
0x2707d  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x27082  brtrue.s loc_270B4
0x27084  ldc.i4.s 0x11
0x27086  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2708b  ldstr    aExDependencyno// "Ex_DependencyNoCodebase"
0x27090  call     string System.Deployment.Application.Resources::GetString(string s)
0x27095  ldc.i4.1
0x27096  newarr   [mscorlib]System.Object
0x2709b  dup
0x2709c  ldc.i4.0
0x2709d  ldarg.0
0x2709e  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x270a3  callvirt instance string [mscorlib]System.Object::ToString()
0x270a8  stelem.ref
0x270a9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x270ae  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x270b3  throw
0x270b4  ldarg.0
0x270b5  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x270ba  call     bool System.Deployment.Application.UriHelper::IsValidRelativeFilePath(string path)
0x270bf  brtrue.s loc_270F1
0x270c1  ldc.i4.s 0x11
0x270c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x270c8  ldstr    aExDependencyno_0// "Ex_DependencyNotRelativePath"
0x270cd  call     string System.Deployment.Application.Resources::GetString(string s)
0x270d2  ldc.i4.1
0x270d3  newarr   [mscorlib]System.Object
0x270d8  dup
0x270d9  ldc.i4.0
0x270da  ldarg.0
0x270db  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x270e0  callvirt instance string [mscorlib]System.Object::ToString()
0x270e5  stelem.ref
0x270e6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x270eb  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x270f0  throw
0x270f1  ldarg.0
0x270f2  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_ResourceFallbackCulture()
0x270f7  brfalse.s loc_27178
0x270f9  ldc.i4.s 0x11
0x270fb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x27100  ldstr    aExDependencyre_1// "Ex_DependencyResourceWithFallback"
0x27105  call     string System.Deployment.Application.Resources::GetString(string s)
0x2710a  ldc.i4.1
0x2710b  newarr   [mscorlib]System.Object
0x27110  dup
0x27111  ldc.i4.0
0x27112  ldarg.0
0x27113  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x27118  callvirt instance string [mscorlib]System.Object::ToString()
0x2711d  stelem.ref
0x2711e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27123  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x27128  throw
0x27129  ldarg.0
0x2712a  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x2712f  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_Name()
0x27134  call     bool System.Deployment.Application.PlatformDetector::IsCLRDependencyText(string clrTextName)
0x27139  brtrue.s loc_27178
0x2713b  ldarg.0
0x2713c  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x27141  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_PublicKeyToken()
0x27146  brtrue.s loc_27178
0x27148  ldc.i4.s 0x11
0x2714a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2714f  ldstr    aExDependencyga// "Ex_DependencyGACNoPKT"
0x27154  call     string System.Deployment.Application.Resources::GetString(string s)
0x27159  ldc.i4.1
0x2715a  newarr   [mscorlib]System.Object
0x2715f  dup
0x27160  ldc.i4.0
0x27161  ldarg.0
0x27162  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x27167  callvirt instance string [mscorlib]System.Object::ToString()
0x2716c  stelem.ref
0x2716d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27172  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x27177  throw
0x27178  ldarg.0
0x27179  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.DependentAssembly::get_SupportUrl()
0x2717e  ldnull
0x2717f  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x27184  brfalse  loc_2724A
0x27189  ldarg.0
0x2718a  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.DependentAssembly::get_SupportUrl()
0x2718f  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x27194  brtrue.s loc_271C6
0x27196  ldc.i4.s 0x11
0x27198  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2719d  ldstr    aExDependencysu_0// "Ex_DependencySupportUrlNoAbsolute"
0x271a2  call     string System.Deployment.Application.Resources::GetString(string s)
0x271a7  ldc.i4.1
0x271a8  newarr   [mscorlib]System.Object
0x271ad  dup
0x271ae  ldc.i4.0
0x271af  ldarg.0
0x271b0  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x271b5  callvirt instance string [mscorlib]System.Object::ToString()
0x271ba  stelem.ref
0x271bb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x271c0  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x271c5  throw
0x271c6  ldarg.0
0x271c7  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.DependentAssembly::get_SupportUrl()
0x271cc  call     bool System.Deployment.Application.UriHelper::IsSupportedScheme(class [System]System.Uri uri)
0x271d1  brtrue.s loc_27203
0x271d3  ldc.i4.s 0xC
0x271d5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x271da  ldstr    aExDependencysu_1// "Ex_DependencySupportUrlNotSupportedUriS"...
0x271df  call     string System.Deployment.Application.Resources::GetString(string s)
0x271e4  ldc.i4.1
0x271e5  newarr   [mscorlib]System.Object
0x271ea  dup
0x271eb  ldc.i4.0
0x271ec  ldarg.0
0x271ed  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x271f2  callvirt instance string [mscorlib]System.Object::ToString()
0x271f7  stelem.ref
0x271f8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x271fd  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x27202  throw
0x27203  ldarg.0
0x27204  callvirt instance class [System]System.Uri System.Deployment.Application.Manifest.DependentAssembly::get_SupportUrl()
0x27209  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x2720e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x27213  ldc.i4   0x4000
0x27218  ble.s    loc_2724A
0x2721a  ldc.i4.s 0x11
0x2721c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x27221  ldstr    aExDependencysu_2// "Ex_DependencySupportUrlTooLong"
0x27226  call     string System.Deployment.Application.Resources::GetString(string s)
0x2722b  ldc.i4.1
0x2722c  newarr   [mscorlib]System.Object
0x27231  dup
0x27232  ldc.i4.0
0x27233  ldarg.0
0x27234  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x27239  callvirt instance string [mscorlib]System.Object::ToString()
0x2723e  stelem.ref
0x2723f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x27244  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x27249  throw
0x2724a  ret
```
