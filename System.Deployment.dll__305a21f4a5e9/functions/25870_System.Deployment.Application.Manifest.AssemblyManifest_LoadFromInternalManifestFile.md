# System.Deployment.Application.Manifest.AssemblyManifest::LoadFromInternalManifestFile

- ea: `0x25870`
- end: `0x259cc`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::LoadFromInternalManifestFile`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x248b0`
- `0x259d0`

## callees

- `0xdba0`
- `0x146f0`
- `0x17d40`
- `0x1a850`
- `0x1a9b0`
- `0x1ac40`
- `0x23020`
- `0x24880`
- `0x24970`
- `0x24a70`
- `0x25670`
- `0x25710`
- `0x25760`
- `0x25870`
- `0x27390`

## string_xrefs

- `0x2589b`: `id1Manifest is parsed successfully.`
- `0x2590b`: `Ex_CannotLoadInternalManifest`
- `0x25965`: `Ex_CannotLoadInternalManifest`
- `0x259b6`: `Ex_CannotLoadInternalManifest`
- `0x2592c`: `_complibIdentity =`
- `0x25995`: `Ex_EmptyIdentityInternalManifest`

## pseudocode

```c

```

## disassembly

```asm
0x25870  ldnull
0x25871  stloc.0
0x25872  ldnull
0x25873  stloc.1
0x25874  ldnull
0x25875  stloc.2
0x25876  ldnull
0x25877  stloc.3
0x25878  ldc.i4.1
0x25879  stloc.s  4
0x2587b  ldarg.1
0x2587c  ldc.i4.1
0x2587d  newobj   instance void System.Deployment.Application.PEStream::.ctor(string filePath, bool partialConstruct)
0x25882  stloc.1
0x25883  ldloc.1
0x25884  callvirt instance unsigned int8[] System.Deployment.Application.PEStream::GetDefaultId1ManifestResource()
0x25889  stloc.0
0x2588a  ldloc.0
0x2588b  brfalse.s loc_258AC
0x2588d  ldloc.0
0x2588e  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x25893  stloc.2
0x25894  ldloc.2
0x25895  newobj   instance void System.Deployment.Application.Manifest.AssemblyManifest::.ctor(class [mscorlib]System.IO.Stream stream)
0x2589a  stloc.3
0x2589b  ldstr    aId1manifestIsP// "id1Manifest is parsed successfully."
0x258a0  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x258a5  ldarg.0
0x258a6  ldc.i4.1
0x258a7  stfld    bool System.Deployment.Application.Manifest.AssemblyManifest::_id1ManifestPresent
0x258ac  ldloc.1
0x258ad  callvirt instance bool System.Deployment.Application.PEStream::get_IsImageFileDll()
0x258b2  stloc.s  4
0x258b4  leave.s  loc_258ED
0x258b6  stloc.s  5
0x258b8  ldloc.s  5
0x258ba  ldarg.1
0x258bb  call     void System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper(class [mscorlib]System.Exception exception, string filePath)
0x258c0  leave.s  loc_258ED
0x258c2  stloc.s  6
0x258c4  ldloc.s  6
0x258c6  ldarg.1
0x258c7  call     void System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper(class [mscorlib]System.Exception exception, string filePath)
0x258cc  leave.s  loc_258ED
0x258ce  stloc.s  7
0x258d0  ldloc.s  7
0x258d2  ldarg.1
0x258d3  call     void System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper(class [mscorlib]System.Exception exception, string filePath)
0x258d8  leave.s  loc_258ED
0x258da  ldloc.1
0x258db  brfalse.s loc_258E3
0x258dd  ldloc.1
0x258de  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x258e3  ldloc.2
0x258e4  brfalse.s loc_258EC
0x258e6  ldloc.2
0x258e7  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x258ec  endfinally
0x258ed  ldloc.3
0x258ee  brfalse  loc_259AB
0x258f3  ldloc.3
0x258f4  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x258f9  callvirt instance bool System.Deployment.Application.DefinitionIdentity::get_IsEmpty()
0x258fe  brtrue.s loc_25956
0x25900  ldarg.0
0x25901  ldarg.1
0x25902  call     instance bool System.Deployment.Application.Manifest.AssemblyManifest::LoadFromPEResources(string filePath)
0x25907  brtrue.s loc_25920
0x25909  ldc.i4.s 0xC
0x2590b  ldstr    aExCannotloadin// "Ex_CannotLoadInternalManifest"
0x25910  call     string System.Deployment.Application.Resources::GetString(string s)
0x25915  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2591a  ldarg.1
0x2591b  call     void System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper(class [mscorlib]System.Exception exception, string filePath)
0x25920  ldarg.0
0x25921  ldarg.1
0x25922  call     class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::ExtractIdentityFromCompLibAssembly(string filePath)
0x25927  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::_complibIdentity
0x2592c  ldstr    aComplibidentit// "_complibIdentity ="
0x25931  ldarg.0
0x25932  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::_complibIdentity
0x25937  brfalse.s loc_25946
0x25939  ldarg.0
0x2593a  ldfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::_complibIdentity
0x2593f  callvirt instance string [mscorlib]System.Object::ToString()
0x25944  br.s     loc_2594B
0x25946  ldstr    aNull// "null"
0x2594b  call     string [mscorlib]System.String::Concat(string, string)
0x25950  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x25955  ret
0x25956  ldloc.s  4
0x25958  brtrue.s loc_25993
0x2595a  ldarg.0
0x2595b  ldarg.1
0x2595c  call     instance bool System.Deployment.Application.Manifest.AssemblyManifest::LoadFromCompLibAssembly(string filePath)
0x25961  brtrue.s loc_2597A
0x25963  ldc.i4.s 0xC
0x25965  ldstr    aExCannotloadin// "Ex_CannotLoadInternalManifest"
0x2596a  call     string System.Deployment.Application.Resources::GetString(string s)
0x2596f  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25974  ldarg.1
0x25975  call     void System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper(class [mscorlib]System.Exception exception, string filePath)
0x2597a  ldarg.0
0x2597b  ldloc.3
0x2597c  callvirt instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x25981  stfld    class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::_id1Identity
0x25986  ldarg.0
0x25987  ldloc.3
0x25988  callvirt instance string System.Deployment.Application.Manifest.AssemblyManifest::get_RequestedExecutionLevel()
0x2598d  stfld    string System.Deployment.Application.Manifest.AssemblyManifest::_id1RequestedExecutionLevel
0x25992  ret
0x25993  ldc.i4.s 0xC
0x25995  ldstr    aExEmptyidentit// "Ex_EmptyIdentityInternalManifest"
0x2599a  call     string System.Deployment.Application.Resources::GetString(string s)
0x2599f  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x259a4  ldarg.1
0x259a5  call     void System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper(class [mscorlib]System.Exception exception, string filePath)
0x259aa  ret
0x259ab  ldarg.0
0x259ac  ldarg.1
0x259ad  call     instance bool System.Deployment.Application.Manifest.AssemblyManifest::LoadFromCompLibAssembly(string filePath)
0x259b2  brtrue.s loc_259CB
0x259b4  ldc.i4.s 0xC
0x259b6  ldstr    aExCannotloadin// "Ex_CannotLoadInternalManifest"
0x259bb  call     string System.Deployment.Application.Resources::GetString(string s)
0x259c0  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x259c5  ldarg.1
0x259c6  call     void System.Deployment.Application.Manifest.AssemblyManifest::ManifestLoadExceptionHelper(class [mscorlib]System.Exception exception, string filePath)
0x259cb  ret
```
