# System.Deployment.Application.ComponentVerifier::VerifyStrongNameAssembly

- ea: `0x10650`
- end: `0x107fc`
- name: `System.Deployment.Application.ComponentVerifier::VerifyStrongNameAssembly`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x28df0`

## callees

- `0x4d0`
- `0xdaa0`
- `0x10650`
- `0x10800`
- `0x147a0`
- `0x1a850`
- `0x1ac40`
- `0x23020`
- `0x24970`
- `0x249f0`
- `0x25350`
- `0x25a00`

## pseudocode

```c

```

## disassembly

```asm
0x10650  ldarg.0
0x10651  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x10656  stloc.0
0x10657  ldarg.1
0x10658  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1065d  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken()
0x10662  brtrue.s loc_1068A
0x10664  ldc.i4.s 0x18
0x10666  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1066b  ldstr    aExStrongnameas// "Ex_StrongNameAsmWithNoPKT"
0x10670  call     string System.Deployment.Application.Resources::GetString(string s)
0x10675  ldc.i4.1
0x10676  newarr   [mscorlib]System.Object
0x1067b  dup
0x1067c  ldc.i4.0
0x1067d  ldloc.0
0x1067e  stelem.ref
0x1067f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10684  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x10689  throw
0x1068a  ldc.i4.0
0x1068b  stloc.1
0x1068c  ldarg.1
0x1068d  callvirt instance valuetype System.Deployment.Application.Manifest.ManifestSourceFormat System.Deployment.Application.Manifest.AssemblyManifest::get_ManifestSourceFormat()
0x10692  brtrue.s loc_106A0
0x10694  ldarg.1
0x10695  ldnull
0x10696  callvirt instance void System.Deployment.Application.Manifest.AssemblyManifest::ValidateSignature(class [mscorlib]System.IO.Stream s)
0x1069b  br       loc_107F3
0x106a0  ldarg.1
0x106a1  callvirt instance valuetype System.Deployment.Application.Manifest.ManifestSourceFormat System.Deployment.Application.Manifest.AssemblyManifest::get_ManifestSourceFormat()
0x106a6  ldc.i4.2
0x106a7  bne.un   loc_1078F
0x106ac  ldarg.1
0x106ad  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_ComplibIdentity()
0x106b2  brtrue.s loc_10721
0x106b4  ldnull
0x106b5  stloc.2
0x106b6  ldnull
0x106b7  stloc.3
0x106b8  ldnull
0x106b9  stloc.s  4
0x106bb  ldarg.0
0x106bc  ldc.i4.1
0x106bd  newobj   instance void System.Deployment.Application.PEStream::.ctor(string filePath, bool partialConstruct)
0x106c2  stloc.3
0x106c3  ldloc.3
0x106c4  callvirt instance unsigned int8[] System.Deployment.Application.PEStream::GetDefaultId1ManifestResource()
0x106c9  stloc.2
0x106ca  ldloc.2
0x106cb  brfalse.s loc_106D5
0x106cd  ldloc.2
0x106ce  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x106d3  stloc.s  4
0x106d5  ldloc.s  4
0x106d7  brfalse.s loc_106E6
0x106d9  ldarg.1
0x106da  ldloc.s  4
0x106dc  callvirt instance void System.Deployment.Application.Manifest.AssemblyManifest::ValidateSignature(class [mscorlib]System.IO.Stream s)
0x106e1  leave    loc_107F3
0x106e6  ldc.i4.s 0x1D
0x106e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x106ed  ldstr    aExStronglyname// "Ex_StronglyNamedAssemblyNotVerifiable"
0x106f2  call     string System.Deployment.Application.Resources::GetString(string s)
0x106f7  ldc.i4.1
0x106f8  newarr   [mscorlib]System.Object
0x106fd  dup
0x106fe  ldc.i4.0
0x106ff  ldloc.0
0x10700  stelem.ref
0x10701  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10706  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1070b  throw
0x1070c  ldloc.3
0x1070d  brfalse.s loc_10715
0x1070f  ldloc.3
0x10710  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x10715  ldloc.s  4
0x10717  brfalse.s loc_10720
0x10719  ldloc.s  4
0x1071b  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x10720  endfinally
0x10721  ldarg.1
0x10722  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_ComplibIdentity()
0x10727  ldarg.1
0x10728  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x1072d  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x10732  brtrue.s loc_1075A
0x10734  ldc.i4.s 0x1E
0x10736  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1073b  ldstr    aExIdentitiesdo// "Ex_IdentitiesDoNotMatchForMixedModeAsse"...
0x10740  call     string System.Deployment.Application.Resources::GetString(string s)
0x10745  ldc.i4.1
0x10746  newarr   [mscorlib]System.Object
0x1074b  dup
0x1074c  ldc.i4.0
0x1074d  ldloc.0
0x1074e  stelem.ref
0x1074f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10754  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x10759  throw
0x1075a  ldarg.0
0x1075b  ldc.i4.0
0x1075c  ldloca.s 5
0x1075e  call     bool Microsoft.Runtime.Hosting.StrongNameHelpers::StrongNameSignatureVerificationEx(string pwzFilePath, bool fForceVerification, [out] bool& pfWasVerified)
0x10763  brtrue.s loc_1078B
0x10765  ldc.i4.s 0x1A
0x10767  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1076c  ldstr    aExStrongnamesi// "Ex_StrongNameSignatureInvalid"
0x10771  call     string System.Deployment.Application.Resources::GetString(string s)
0x10776  ldc.i4.1
0x10777  newarr   [mscorlib]System.Object
0x1077c  dup
0x1077d  ldc.i4.0
0x1077e  ldloc.0
0x1077f  stelem.ref
0x10780  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10785  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1078a  throw
0x1078b  ldc.i4.1
0x1078c  stloc.1
0x1078d  br.s     loc_107F3
0x1078f  ldarg.1
0x10790  callvirt instance valuetype System.Deployment.Application.Manifest.ManifestSourceFormat System.Deployment.Application.Manifest.AssemblyManifest::get_ManifestSourceFormat()
0x10795  ldc.i4.1
0x10796  bne.un.s loc_107CD
0x10798  ldarg.0
0x10799  ldc.i4.0
0x1079a  ldloca.s 6
0x1079c  call     bool Microsoft.Runtime.Hosting.StrongNameHelpers::StrongNameSignatureVerificationEx(string pwzFilePath, bool fForceVerification, [out] bool& pfWasVerified)
0x107a1  brtrue.s loc_107C9
0x107a3  ldc.i4.s 0x1A
0x107a5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x107aa  ldstr    aExStrongnamesi// "Ex_StrongNameSignatureInvalid"
0x107af  call     string System.Deployment.Application.Resources::GetString(string s)
0x107b4  ldc.i4.1
0x107b5  newarr   [mscorlib]System.Object
0x107ba  dup
0x107bb  ldc.i4.0
0x107bc  ldloc.0
0x107bd  stelem.ref
0x107be  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x107c3  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x107c8  throw
0x107c9  ldc.i4.1
0x107ca  stloc.1
0x107cb  br.s     loc_107F3
0x107cd  ldc.i4.s 0x1D
0x107cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x107d4  ldstr    aExStronglyname// "Ex_StronglyNamedAssemblyNotVerifiable"
0x107d9  call     string System.Deployment.Application.Resources::GetString(string s)
0x107de  ldc.i4.1
0x107df  newarr   [mscorlib]System.Object
0x107e4  dup
0x107e5  ldc.i4.0
0x107e6  ldloc.0
0x107e7  stelem.ref
0x107e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x107ed  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x107f2  throw
0x107f3  ldarg.1
0x107f4  ldarg.0
0x107f5  ldloc.1
0x107f6  call     void System.Deployment.Application.ComponentVerifier::VerifyManifestComponentFiles(class System.Deployment.Application.Manifest.AssemblyManifest manifest, string componentPath, bool ignoreSelfReferentialFileHash)
0x107fb  ret
```
