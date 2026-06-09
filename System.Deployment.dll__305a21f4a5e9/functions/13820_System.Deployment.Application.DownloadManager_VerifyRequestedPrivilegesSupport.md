# System.Deployment.Application.DownloadManager::VerifyRequestedPrivilegesSupport

- ea: `0x13820`
- end: `0x1388a`
- name: `System.Deployment.Application.DownloadManager::VerifyRequestedPrivilegesSupport`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x13720`

## callees

- `0x13820`
- `0x13890`
- `0x17d40`
- `0x23da0`
- `0x23dd0`
- `0x24390`
- `0x248b0`
- `0x24a00`
- `0x24a10`
- `0x24f90`

## pseudocode

```c

```

## disassembly

```asm
0x13820  ldarg.0
0x13821  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x13826  ldc.i4.0
0x13827  ldelem.ref
0x13828  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_CustomHostSpecified()
0x1382d  brfalse.s loc_13830
0x1382f  ret
0x13830  ldarg.1
0x13831  ldarg.0
0x13832  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x13837  ldc.i4.0
0x13838  ldelem.ref
0x13839  callvirt instance class System.Deployment.Application.Manifest.DependentAssembly System.Deployment.Application.Manifest.EntryPoint::get_Assembly()
0x1383e  callvirt instance string System.Deployment.Application.Manifest.DependentAssembly::get_Codebase()
0x13843  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x13848  stloc.0
0x13849  ldloc.0
0x1384a  call     bool [mscorlib]System.IO.File::Exists(string)
0x1384f  brfalse.s loc_13874
0x13851  ldloc.0
0x13852  newobj   instance void System.Deployment.Application.Manifest.AssemblyManifest::.ctor(string filePath)
0x13857  stloc.1
0x13858  ldloc.1
0x13859  callvirt instance bool System.Deployment.Application.Manifest.AssemblyManifest::get_Id1ManifestPresent()
0x1385e  brfalse.s loc_13889
0x13860  ldloc.1
0x13861  callvirt instance string System.Deployment.Application.Manifest.AssemblyManifest::get_Id1RequestedExecutionLevel()
0x13866  brfalse.s loc_13889
0x13868  ldloc.1
0x13869  callvirt instance string System.Deployment.Application.Manifest.AssemblyManifest::get_Id1RequestedExecutionLevel()
0x1386e  call     void System.Deployment.Application.DownloadManager::VerifyRequestedPrivilegesSupport(string requestedExecutionLevel)
0x13873  ret
0x13874  ldstr    aMainExe// "Main exe="
0x13879  ldloc.0
0x1387a  ldstr    aDoesNotExistNo// " does not exist. No Requested Privilige"...
0x1387f  call     string [mscorlib]System.String::Concat(string, string, string)
0x13884  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x13889  ret
```
