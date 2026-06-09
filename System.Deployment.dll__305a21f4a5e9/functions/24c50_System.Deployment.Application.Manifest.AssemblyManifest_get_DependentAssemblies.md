# System.Deployment.Application.Manifest.AssemblyManifest::get_DependentAssemblies

- ea: `0x24c50`
- end: `0x24d0d`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::get_DependentAssemblies`
- size: `189`
- prototype: ``
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x15210`
- `0x18f40`
- `0x1ba20`
- `0x25050`
- `0x25060`
- `0x251a0`
- `0x25bc0`
- `0x26250`

## callees

- `0x3d30`
- `0x3d40`
- `0x3e00`
- `0x4080`
- `0x4d30`
- `0x147a0`
- `0x23020`
- `0x24190`
- `0x24c50`

## pseudocode

```c

```

## disassembly

```asm
0x24c50  ldarg.0
0x24c51  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_dependentAssemblies
0x24c56  brtrue   loc_24D01
0x24c5b  ldarg.0
0x24c5c  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24c61  brtrue.s loc_24C66
0x24c63  ldnull
0x24c64  br.s     loc_24C71
0x24c66  ldarg.0
0x24c67  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24c6c  callvirt instance class System.Deployment.Internal.Isolation.ISection System.Deployment.Internal.Isolation.Manifest.ICMS::get_AssemblyReferenceSection()
0x24c71  stloc.0
0x24c72  ldloc.0
0x24c73  brtrue.s loc_24C78
0x24c75  ldc.i4.0
0x24c76  br.s     loc_24C7E
0x24c78  ldloc.0
0x24c79  callvirt instance unsigned int32 System.Deployment.Internal.Isolation.ISection::get_Count()
0x24c7e  stloc.1
0x24c7f  ldloc.1
0x24c80  newarr   System.Deployment.Application.Manifest.DependentAssembly
0x24c85  stloc.2
0x24c86  ldloc.1
0x24c87  ldc.i4.0
0x24c88  ble.un.s loc_24CF3
0x24c8a  ldc.i4.0
0x24c8b  stloc.3
0x24c8c  ldloc.1
0x24c8d  newarr   System.Deployment.Internal.Isolation.Manifest.IAssemblyReferenceEntry
0x24c92  stloc.s  4
0x24c94  ldloc.0
0x24c95  callvirt instance object System.Deployment.Internal.Isolation.ISection::get__NewEnum()
0x24c9a  castclass System.Deployment.Internal.Isolation.IEnumUnknown
0x24c9f  stloc.s  5
0x24ca1  ldloc.s  5
0x24ca3  ldloc.1
0x24ca4  ldloc.s  4
0x24ca6  stloc.s  7
0x24ca8  ldloc.s  7
0x24caa  ldloca.s 3
0x24cac  callvirt instance int32 System.Deployment.Internal.Isolation.IEnumUnknown::Next(unsigned int32 celt, [out] [hasfieldmarshal] object[] rgelt, unsigned int32& celtFetched)
0x24cb1  stloc.s  6
0x24cb3  ldloc.s  6
0x24cb5  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x24cba  ldloc.3
0x24cbb  ldloc.1
0x24cbc  beq.s    loc_24CD0
0x24cbe  ldc.i4.s 0xD
0x24cc0  ldstr    aExIsoenumfetch// "Ex_IsoEnumFetchNotEqualToCount"
0x24cc5  call     string System.Deployment.Application.Resources::GetString(string s)
0x24cca  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x24ccf  throw
0x24cd0  ldc.i4.0
0x24cd1  stloc.s  8
0x24cd3  br.s     loc_24CEE
0x24cd5  ldloc.2
0x24cd6  ldloc.s  8
0x24cd8  ldloc.s  4
0x24cda  ldloc.s  8
0x24cdc  ldelem.ref
0x24cdd  callvirt instance class System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceEntry System.Deployment.Internal.Isolation.Manifest.IAssemblyReferenceEntry::get_AllData()
0x24ce2  newobj   instance void System.Deployment.Application.Manifest.DependentAssembly::.ctor(class System.Deployment.Internal.Isolation.Manifest.AssemblyReferenceEntry assemblyReferenceEntry)
0x24ce7  stelem.ref
0x24ce8  ldloc.s  8
0x24cea  ldc.i4.1
0x24ceb  add
0x24cec  stloc.s  8
0x24cee  ldloc.s  8
0x24cf0  ldloc.1
0x24cf1  blt.un.s loc_24CD5
0x24cf3  ldarg.0
0x24cf4  ldflda   object System.Deployment.Application.Manifest.AssemblyManifest::_dependentAssemblies
0x24cf9  ldloc.2
0x24cfa  ldnull
0x24cfb  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x24d00  pop
0x24d01  ldarg.0
0x24d02  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_dependentAssemblies
0x24d07  castclass class System.Deployment.Application.Manifest.DependentAssembly[]
0x24d0c  ret
```
