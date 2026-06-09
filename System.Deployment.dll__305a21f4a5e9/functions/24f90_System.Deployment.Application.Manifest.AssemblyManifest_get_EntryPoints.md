# System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints

- ea: `0x24f90`
- end: `0x2504e`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints`
- size: `190`
- prototype: ``
- caller_count: `10`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0xba90`
- `0xc1b0`
- `0x13820`
- `0x162f0`
- `0x1ba20`
- `0x1faf0`
- `0x1fe20`
- `0x25bc0`
- `0x26250`
- `0x29ab0`

## callees

- `0x3d30`
- `0x3d40`
- `0x3e00`
- `0x40b0`
- `0x4ea0`
- `0x147a0`
- `0x23020`
- `0x23d00`
- `0x24f90`

## pseudocode

```c

```

## disassembly

```asm
0x24f90  ldarg.0
0x24f91  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_entryPoints
0x24f96  brtrue   loc_25042
0x24f9b  ldarg.0
0x24f9c  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24fa1  brtrue.s loc_24FA6
0x24fa3  ldnull
0x24fa4  br.s     loc_24FB1
0x24fa6  ldarg.0
0x24fa7  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24fac  callvirt instance class System.Deployment.Internal.Isolation.ISection System.Deployment.Internal.Isolation.Manifest.ICMS::get_EntryPointSection()
0x24fb1  stloc.0
0x24fb2  ldloc.0
0x24fb3  brtrue.s loc_24FB8
0x24fb5  ldc.i4.0
0x24fb6  br.s     loc_24FBE
0x24fb8  ldloc.0
0x24fb9  callvirt instance unsigned int32 System.Deployment.Internal.Isolation.ISection::get_Count()
0x24fbe  stloc.1
0x24fbf  ldloc.1
0x24fc0  newarr   System.Deployment.Application.Manifest.EntryPoint
0x24fc5  stloc.2
0x24fc6  ldloc.1
0x24fc7  ldc.i4.0
0x24fc8  ble.un.s loc_25034
0x24fca  ldc.i4.0
0x24fcb  stloc.3
0x24fcc  ldloc.1
0x24fcd  newarr   System.Deployment.Internal.Isolation.Manifest.IEntryPointEntry
0x24fd2  stloc.s  4
0x24fd4  ldloc.0
0x24fd5  callvirt instance object System.Deployment.Internal.Isolation.ISection::get__NewEnum()
0x24fda  castclass System.Deployment.Internal.Isolation.IEnumUnknown
0x24fdf  stloc.s  5
0x24fe1  ldloc.s  5
0x24fe3  ldloc.1
0x24fe4  ldloc.s  4
0x24fe6  stloc.s  7
0x24fe8  ldloc.s  7
0x24fea  ldloca.s 3
0x24fec  callvirt instance int32 System.Deployment.Internal.Isolation.IEnumUnknown::Next(unsigned int32 celt, [out] [hasfieldmarshal] object[] rgelt, unsigned int32& celtFetched)
0x24ff1  stloc.s  6
0x24ff3  ldloc.s  6
0x24ff5  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x24ffa  ldloc.3
0x24ffb  ldloc.1
0x24ffc  beq.s    loc_25010
0x24ffe  ldc.i4.s 0xD
0x25000  ldstr    aExIsoenumfetch// "Ex_IsoEnumFetchNotEqualToCount"
0x25005  call     string System.Deployment.Application.Resources::GetString(string s)
0x2500a  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2500f  throw
0x25010  ldc.i4.0
0x25011  stloc.s  8
0x25013  br.s     loc_2502F
0x25015  ldloc.2
0x25016  ldloc.s  8
0x25018  ldloc.s  4
0x2501a  ldloc.s  8
0x2501c  ldelem.ref
0x2501d  callvirt instance class System.Deployment.Internal.Isolation.Manifest.EntryPointEntry System.Deployment.Internal.Isolation.Manifest.IEntryPointEntry::get_AllData()
0x25022  ldarg.0
0x25023  newobj   instance void System.Deployment.Application.Manifest.EntryPoint::.ctor(class System.Deployment.Internal.Isolation.Manifest.EntryPointEntry entryPointEntry, class System.Deployment.Application.Manifest.AssemblyManifest manifest)
0x25028  stelem.ref
0x25029  ldloc.s  8
0x2502b  ldc.i4.1
0x2502c  add
0x2502d  stloc.s  8
0x2502f  ldloc.s  8
0x25031  ldloc.1
0x25032  blt.un.s loc_25015
0x25034  ldarg.0
0x25035  ldflda   object System.Deployment.Application.Manifest.AssemblyManifest::_entryPoints
0x2503a  ldloc.2
0x2503b  ldnull
0x2503c  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x25041  pop
0x25042  ldarg.0
0x25043  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_entryPoints
0x25048  castclass class System.Deployment.Application.Manifest.EntryPoint[]
0x2504d  ret
```
