# System.Deployment.Application.Manifest.AssemblyManifest::ValidateApplicationDependency

- ea: `0x26d30`
- end: `0x26e9b`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::ValidateApplicationDependency`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x25bc0`

## callees

- `0xdab0`
- `0xdd30`
- `0xdd70`
- `0xdd80`
- `0x147a0`
- `0x147b0`
- `0x21910`
- `0x219c0`
- `0x21a80`
- `0x23020`
- `0x24380`
- `0x24390`
- `0x243f0`
- `0x24400`
- `0x24410`
- `0x24420`
- `0x24970`
- `0x26c10`
- `0x26d30`
- `0x27340`

## string_xrefs

- `0x26e13`: `Ex_DepAppRefInvalidCodebaseUri`
- `0x26e36`: `Ex_DepAppRefInvalidCodebaseUri`

## pseudocode

```c

```

## disassembly

```asm
0x26d30  ldarg.1
0x26d31  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26d36  call     void System.Deployment.Application.Manifest.AssemblyManifest::ValidateAssemblyIdentity(class System.Deployment.Application.ReferenceIdentity identity)
0x26d3b  ldarg.1
0x26d3c  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26d41  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_PublicKeyToken()
0x26d46  brtrue.s loc_26D5A
0x26d48  ldc.i4.s 0x11
0x26d4a  ldstr    aExDepapprefnot// "Ex_DepAppRefNotStrongNamed"
0x26d4f  call     string System.Deployment.Application.Resources::GetString(string s)
0x26d54  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26d59  throw
0x26d5a  ldarg.1
0x26d5b  callvirt instance class System.Deployment.Application.HashCollection System.Deployment.Application.Manifest.DependentAssembly::get_HashCollection()
0x26d60  call     bool System.Deployment.Application.Manifest.AssemblyManifest::IsInvalidHash(class System.Deployment.Application.HashCollection hashCollection)
0x26d65  brfalse.s loc_26D79
0x26d67  ldc.i4.s 0x11
0x26d69  ldstr    aExDepapprefhas// "Ex_DepAppRefHashInvalid"
0x26d6e  call     string System.Deployment.Application.Resources::GetString(string s)
0x26d73  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26d78  throw
0x26d79  ldarg.0
0x26d7a  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x26d7f  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_ProcessorArchitecture()
0x26d84  ldarg.1
0x26d85  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26d8a  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_ProcessorArchitecture()
0x26d8f  ldc.i4.5
0x26d90  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x26d95  brfalse.s loc_26DD5
0x26d97  ldc.i4.s 0x11
0x26d99  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x26d9e  ldstr    aExDepapprefpro// "Ex_DepAppRefProcArchMismatched"
0x26da3  call     string System.Deployment.Application.Resources::GetString(string s)
0x26da8  ldc.i4.2
0x26da9  newarr   [mscorlib]System.Object
0x26dae  dup
0x26daf  ldc.i4.0
0x26db0  ldarg.1
0x26db1  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26db6  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_ProcessorArchitecture()
0x26dbb  stelem.ref
0x26dbc  dup
0x26dbd  ldc.i4.1
0x26dbe  ldarg.0
0x26dbf  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x26dc4  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_ProcessorArchitecture()
0x26dc9  stelem.ref
0x26dca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26dcf  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26dd4  throw
0x26dd5  ldarg.1
0x26dd6  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_ResourceFallbackCulture()
0x26ddb  brtrue.s loc_26DED
0x26ddd  ldarg.1
0x26dde  callvirt instance bool System.Deployment.Application.Manifest.DependentAssembly::get_IsPreRequisite()
0x26de3  brtrue.s loc_26DED
0x26de5  ldarg.1
0x26de6  callvirt instance bool System.Deployment.Application.Manifest.DependentAssembly::get_IsOptional()
0x26deb  brfalse.s loc_26DFF
0x26ded  ldc.i4.s 0x11
0x26def  ldstr    aExDepapprefpre// "Ex_DepAppRefPrereqOrOptionalOrResourceF"...
0x26df4  call     string System.Deployment.Application.Resources::GetString(string s)
0x26df9  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26dfe  throw
0x26dff  ldnull
0x26e00  stloc.0
0x26e01  ldarg.1
0x26e02  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x26e07  ldc.i4.0
0x26e08  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x26e0d  stloc.0
0x26e0e  leave.s  loc_26E24
0x26e10  stloc.1
0x26e11  ldc.i4.s 0x11
0x26e13  ldstr    aExDepapprefinv// "Ex_DepAppRefInvalidCodebaseUri"
0x26e18  call     string System.Deployment.Application.Resources::GetString(string s)
0x26e1d  ldloc.1
0x26e1e  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x26e23  throw
0x26e24  ldloc.0
0x26e25  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x26e2a  brfalse.s loc_26E46
0x26e2c  ldloc.0
0x26e2d  call     bool System.Deployment.Application.UriHelper::IsSupportedScheme(class [System]System.Uri uri)
0x26e32  brtrue.s loc_26E46
0x26e34  ldc.i4.s 0x11
0x26e36  ldstr    aExDepapprefinv// "Ex_DepAppRefInvalidCodebaseUri"
0x26e3b  call     string System.Deployment.Application.Resources::GetString(string s)
0x26e40  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26e45  throw
0x26e46  ldarg.1
0x26e47  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26e4c  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_Name()
0x26e51  call     bool System.Deployment.Application.UriHelper::IsValidRelativeFilePath(string path)
0x26e56  brfalse.s loc_26E6A
0x26e58  ldarg.1
0x26e59  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26e5e  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_Name()
0x26e63  call     bool System.Deployment.Application.UriHelper::PathContainDirectorySeparators(string path)
0x26e68  brfalse.s loc_26E9A
0x26e6a  ldc.i4.s 0x11
0x26e6c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x26e71  ldstr    aExDepapprefinv_0// "Ex_DepAppRefInvalidIdentityName"
0x26e76  call     string System.Deployment.Application.Resources::GetString(string s)
0x26e7b  ldc.i4.1
0x26e7c  newarr   [mscorlib]System.Object
0x26e81  dup
0x26e82  ldc.i4.0
0x26e83  ldarg.1
0x26e84  callvirt instance class System.Deployment.Application.ReferenceIdentity System.Deployment.Application.Manifest.DependentAssembly::get_Identity()
0x26e89  callvirt instance string System.Deployment.Application.ReferenceIdentity::get_Name()
0x26e8e  stelem.ref
0x26e8f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x26e94  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x26e99  throw
0x26e9a  ret
```
