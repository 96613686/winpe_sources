# System.Deployment.Application.ComponentVerifier::VerifySimplyNamedAssembly

- ea: `0x105d0`
- end: `0x1064f`
- name: `System.Deployment.Application.ComponentVerifier::VerifySimplyNamedAssembly`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x28da0`

## callees

- `0xdaa0`
- `0x105d0`
- `0x147a0`
- `0x23020`
- `0x24970`
- `0x249f0`
- `0x25350`

## string_xrefs

- `0x1062f`: `Ex_SimplyNamedAsmWithStrongNameComplib`

## pseudocode

```c

```

## disassembly

```asm
0x105d0  ldarg.0
0x105d1  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x105d6  stloc.0
0x105d7  ldarg.1
0x105d8  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x105dd  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken()
0x105e2  brfalse.s loc_1060A
0x105e4  ldc.i4.s 0x18
0x105e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x105eb  ldstr    aExSimplynameda// "Ex_SimplyNamedAsmWithPKT"
0x105f0  call     string System.Deployment.Application.Resources::GetString(string s)
0x105f5  ldc.i4.1
0x105f6  newarr   [mscorlib]System.Object
0x105fb  dup
0x105fc  ldc.i4.0
0x105fd  ldloc.0
0x105fe  stelem.ref
0x105ff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10604  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x10609  throw
0x1060a  ldarg.1
0x1060b  callvirt instance valuetype System.Deployment.Application.Manifest.ManifestSourceFormat System.Deployment.Application.Manifest.AssemblyManifest::get_ManifestSourceFormat()
0x10610  ldc.i4.2
0x10611  bne.un.s loc_1064E
0x10613  ldarg.1
0x10614  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_ComplibIdentity()
0x10619  brfalse.s loc_1064E
0x1061b  ldarg.1
0x1061c  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_ComplibIdentity()
0x10621  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken()
0x10626  brfalse.s loc_1064E
0x10628  ldc.i4.s 0x1E
0x1062a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x1062f  ldstr    aExSimplynameda_0// "Ex_SimplyNamedAsmWithStrongNameComplib"
0x10634  call     string System.Deployment.Application.Resources::GetString(string s)
0x10639  ldc.i4.1
0x1063a  newarr   [mscorlib]System.Object
0x1063f  dup
0x10640  ldc.i4.0
0x10641  ldloc.0
0x10642  stelem.ref
0x10643  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10648  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x1064d  throw
0x1064e  ret
```
