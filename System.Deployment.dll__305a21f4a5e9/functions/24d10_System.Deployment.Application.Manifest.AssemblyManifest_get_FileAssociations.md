# System.Deployment.Application.Manifest.AssemblyManifest::get_FileAssociations

- ea: `0x24d10`
- end: `0x24dcd`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::get_FileAssociations`
- size: `189`
- prototype: ``
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0xba90`
- `0x11d60`
- `0x122a0`
- `0x1d6f0`
- `0x1dfc0`
- `0x1fb50`
- `0x25bc0`
- `0x26250`

## callees

- `0x3d30`
- `0x3d40`
- `0x3e00`
- `0x4110`
- `0x4810`
- `0x147a0`
- `0x23020`
- `0x24440`
- `0x24d10`

## pseudocode

```c

```

## disassembly

```asm
0x24d10  ldarg.0
0x24d11  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_fileAssociations
0x24d16  brtrue   loc_24DC1
0x24d1b  ldarg.0
0x24d1c  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24d21  brtrue.s loc_24D26
0x24d23  ldnull
0x24d24  br.s     loc_24D31
0x24d26  ldarg.0
0x24d27  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24d2c  callvirt instance class System.Deployment.Internal.Isolation.ISection System.Deployment.Internal.Isolation.Manifest.ICMS::get_FileAssociationSection()
0x24d31  stloc.0
0x24d32  ldloc.0
0x24d33  brtrue.s loc_24D38
0x24d35  ldc.i4.0
0x24d36  br.s     loc_24D3E
0x24d38  ldloc.0
0x24d39  callvirt instance unsigned int32 System.Deployment.Internal.Isolation.ISection::get_Count()
0x24d3e  stloc.1
0x24d3f  ldloc.1
0x24d40  newarr   System.Deployment.Application.Manifest.FileAssociation
0x24d45  stloc.2
0x24d46  ldloc.1
0x24d47  ldc.i4.0
0x24d48  ble.un.s loc_24DB3
0x24d4a  ldc.i4.0
0x24d4b  stloc.3
0x24d4c  ldloc.1
0x24d4d  newarr   System.Deployment.Internal.Isolation.Manifest.IFileAssociationEntry
0x24d52  stloc.s  4
0x24d54  ldloc.0
0x24d55  callvirt instance object System.Deployment.Internal.Isolation.ISection::get__NewEnum()
0x24d5a  castclass System.Deployment.Internal.Isolation.IEnumUnknown
0x24d5f  stloc.s  5
0x24d61  ldloc.s  5
0x24d63  ldloc.1
0x24d64  ldloc.s  4
0x24d66  stloc.s  7
0x24d68  ldloc.s  7
0x24d6a  ldloca.s 3
0x24d6c  callvirt instance int32 System.Deployment.Internal.Isolation.IEnumUnknown::Next(unsigned int32 celt, [out] [hasfieldmarshal] object[] rgelt, unsigned int32& celtFetched)
0x24d71  stloc.s  6
0x24d73  ldloc.s  6
0x24d75  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x24d7a  ldloc.3
0x24d7b  ldloc.1
0x24d7c  beq.s    loc_24D90
0x24d7e  ldc.i4.s 0xD
0x24d80  ldstr    aExIsoenumfetch// "Ex_IsoEnumFetchNotEqualToCount"
0x24d85  call     string System.Deployment.Application.Resources::GetString(string s)
0x24d8a  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x24d8f  throw
0x24d90  ldc.i4.0
0x24d91  stloc.s  8
0x24d93  br.s     loc_24DAE
0x24d95  ldloc.2
0x24d96  ldloc.s  8
0x24d98  ldloc.s  4
0x24d9a  ldloc.s  8
0x24d9c  ldelem.ref
0x24d9d  callvirt instance class System.Deployment.Internal.Isolation.Manifest.FileAssociationEntry System.Deployment.Internal.Isolation.Manifest.IFileAssociationEntry::get_AllData()
0x24da2  newobj   instance void System.Deployment.Application.Manifest.FileAssociation::.ctor(class System.Deployment.Internal.Isolation.Manifest.FileAssociationEntry fileAssociationEntry)
0x24da7  stelem.ref
0x24da8  ldloc.s  8
0x24daa  ldc.i4.1
0x24dab  add
0x24dac  stloc.s  8
0x24dae  ldloc.s  8
0x24db0  ldloc.1
0x24db1  blt.un.s loc_24D95
0x24db3  ldarg.0
0x24db4  ldflda   object System.Deployment.Application.Manifest.AssemblyManifest::_fileAssociations
0x24db9  ldloc.2
0x24dba  ldnull
0x24dbb  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x24dc0  pop
0x24dc1  ldarg.0
0x24dc2  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_fileAssociations
0x24dc7  castclass class System.Deployment.Application.Manifest.FileAssociation[]
0x24dcc  ret
```
