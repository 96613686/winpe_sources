# System.Web.Compilation.BuildManager::SetPrecompilationInfo

- ea: `0x176e30`
- end: `0x176f0f`
- name: `System.Web.Compilation.BuildManager::SetPrecompilationInfo`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1751c0`

## callees

- `0x18990`
- `0x34fa0`
- `0x84f70`
- `0x160910`
- `0x160930`
- `0x176e30`
- `0x176f10`
- `0x1770f0`
- `0x177160`
- `0x17be90`
- `0x17beb0`
- `0x17bed0`

## string_xrefs

- `0x176ebc`: `Dir_not_empty_not_precomp`
- `0x176ef8`: `Cant_delete_dir`

## pseudocode

```c

```

## disassembly

```asm
0x176e30  ldarg.1
0x176e31  brfalse.s loc_176E3B
0x176e33  ldarg.1
0x176e34  callvirt instance class System.Web.Compilation.ClientBuildManagerParameter System.Web.Hosting.HostingEnvironmentParameters::get_ClientBuildManagerParameter()
0x176e39  brtrue.s loc_176E3C
0x176e3b  ret
0x176e3c  ldarg.0
0x176e3d  ldarg.1
0x176e3e  callvirt instance class System.Web.Compilation.ClientBuildManagerParameter System.Web.Hosting.HostingEnvironmentParameters::get_ClientBuildManagerParameter()
0x176e43  callvirt instance valuetype System.Web.Compilation.PrecompilationFlags System.Web.Compilation.ClientBuildManagerParameter::get_PrecompilationFlags()
0x176e48  stfld    valuetype System.Web.Compilation.PrecompilationFlags System.Web.Compilation.BuildManager::_precompilationFlags
0x176e4d  ldarg.0
0x176e4e  ldarg.1
0x176e4f  callvirt instance class System.Web.Compilation.ClientBuildManagerParameter System.Web.Hosting.HostingEnvironmentParameters::get_ClientBuildManagerParameter()
0x176e54  callvirt instance string System.Web.Compilation.ClientBuildManagerParameter::get_StrongNameKeyFile()
0x176e59  stfld    string System.Web.Compilation.BuildManager::_strongNameKeyFile
0x176e5e  ldarg.0
0x176e5f  ldarg.1
0x176e60  callvirt instance class System.Web.Compilation.ClientBuildManagerParameter System.Web.Hosting.HostingEnvironmentParameters::get_ClientBuildManagerParameter()
0x176e65  callvirt instance string System.Web.Compilation.ClientBuildManagerParameter::get_StrongNameKeyContainer()
0x176e6a  stfld    string System.Web.Compilation.BuildManager::_strongNameKeyContainer
0x176e6f  ldarg.0
0x176e70  ldarg.1
0x176e71  callvirt instance string System.Web.Hosting.HostingEnvironmentParameters::get_PrecompilationTargetPhysicalDirectory()
0x176e76  stfld    string System.Web.Compilation.BuildManager::_precompTargetPhysicalDir
0x176e7b  ldarg.0
0x176e7c  ldfld    string System.Web.Compilation.BuildManager::_precompTargetPhysicalDir
0x176e81  brtrue.s loc_176E84
0x176e83  ret
0x176e84  ldarg.0
0x176e85  ldfld    string System.Web.Compilation.BuildManager::_precompTargetPhysicalDir
0x176e8a  call     bool System.Web.UI.Util::IsNonEmptyDirectory(string dir)
0x176e8f  brfalse.s loc_176F08
0x176e91  ldarg.0
0x176e92  ldfld    valuetype System.Web.Compilation.PrecompilationFlags System.Web.Compilation.BuildManager::_precompilationFlags
0x176e97  ldc.i4.2
0x176e98  and
0x176e99  brtrue.s loc_176EAB
0x176e9b  ldstr    aDirNotEmpty// "Dir_not_empty"
0x176ea0  call     string System.Web.SR::GetString(string name)
0x176ea5  newobj   instance void System.Web.HttpException::.ctor(string message)
0x176eaa  throw
0x176eab  ldarg.0
0x176eac  ldfld    string System.Web.Compilation.BuildManager::_precompTargetPhysicalDir
0x176eb1  ldloca.s 0
0x176eb3  call     bool System.Web.Compilation.BuildManager::ReadPrecompMarkerFile(string appRoot, [out] bool& updatable)
0x176eb8  stloc.1
0x176eb9  ldloc.1
0x176eba  brtrue.s loc_176ECC
0x176ebc  ldstr    aDirNotEmptyNot// "Dir_not_empty_not_precomp"
0x176ec1  call     string System.Web.SR::GetString(string name)
0x176ec6  newobj   instance void System.Web.HttpException::.ctor(string message)
0x176ecb  throw
0x176ecc  ldarg.0
0x176ecd  call     instance bool System.Web.Compilation.BuildManager::DeletePrecompTargetDirectory()
0x176ed2  brtrue.s loc_176F08
0x176ed4  ldc.i4   0xFA
0x176ed9  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x176ede  ldarg.0
0x176edf  call     instance bool System.Web.Compilation.BuildManager::DeletePrecompTargetDirectory()
0x176ee4  brtrue.s loc_176F08
0x176ee6  ldc.i4   0x3E8
0x176eeb  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x176ef0  ldarg.0
0x176ef1  call     instance bool System.Web.Compilation.BuildManager::DeletePrecompTargetDirectory()
0x176ef6  brtrue.s loc_176F08
0x176ef8  ldstr    aCantDeleteDir// "Cant_delete_dir"
0x176efd  call     string System.Web.SR::GetString(string name)
0x176f02  newobj   instance void System.Web.HttpException::.ctor(string message)
0x176f07  throw
0x176f08  ldarg.0
0x176f09  call     instance void System.Web.Compilation.BuildManager::CreatePrecompMarkerFile()
0x176f0e  ret
```
