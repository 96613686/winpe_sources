# System.Deployment.Application.Manifest.AssemblyManifest::get_Files

- ea: `0x24dd0`
- end: `0x24e8d`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::get_Files`
- size: `189`
- prototype: ``
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0xf380`
- `0x10800`
- `0x13d80`
- `0x15210`
- `0x18f40`
- `0x25100`
- `0x25bc0`
- `0x26250`

## callees

- `0x3d30`
- `0x3d40`
- `0x3e00`
- `0x4030`
- `0x46e0`
- `0x147a0`
- `0x23020`
- `0x24600`
- `0x24dd0`

## pseudocode

```c

```

## disassembly

```asm
0x24dd0  ldarg.0
0x24dd1  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_files
0x24dd6  brtrue   loc_24E81
0x24ddb  ldarg.0
0x24ddc  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24de1  brtrue.s loc_24DE6
0x24de3  ldnull
0x24de4  br.s     loc_24DF1
0x24de6  ldarg.0
0x24de7  ldfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x24dec  callvirt instance class System.Deployment.Internal.Isolation.ISection System.Deployment.Internal.Isolation.Manifest.ICMS::get_FileSection()
0x24df1  stloc.0
0x24df2  ldloc.0
0x24df3  brtrue.s loc_24DF8
0x24df5  ldc.i4.0
0x24df6  br.s     loc_24DFE
0x24df8  ldloc.0
0x24df9  callvirt instance unsigned int32 System.Deployment.Internal.Isolation.ISection::get_Count()
0x24dfe  stloc.1
0x24dff  ldloc.1
0x24e00  newarr   System.Deployment.Application.Manifest.File
0x24e05  stloc.2
0x24e06  ldloc.1
0x24e07  ldc.i4.0
0x24e08  ble.un.s loc_24E73
0x24e0a  ldc.i4.0
0x24e0b  stloc.3
0x24e0c  ldloc.1
0x24e0d  newarr   System.Deployment.Internal.Isolation.Manifest.IFileEntry
0x24e12  stloc.s  4
0x24e14  ldloc.0
0x24e15  callvirt instance object System.Deployment.Internal.Isolation.ISection::get__NewEnum()
0x24e1a  castclass System.Deployment.Internal.Isolation.IEnumUnknown
0x24e1f  stloc.s  5
0x24e21  ldloc.s  5
0x24e23  ldloc.1
0x24e24  ldloc.s  4
0x24e26  stloc.s  7
0x24e28  ldloc.s  7
0x24e2a  ldloca.s 3
0x24e2c  callvirt instance int32 System.Deployment.Internal.Isolation.IEnumUnknown::Next(unsigned int32 celt, [out] [hasfieldmarshal] object[] rgelt, unsigned int32& celtFetched)
0x24e31  stloc.s  6
0x24e33  ldloc.s  6
0x24e35  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x24e3a  ldloc.3
0x24e3b  ldloc.1
0x24e3c  beq.s    loc_24E50
0x24e3e  ldc.i4.s 0xD
0x24e40  ldstr    aExIsoenumfetch// "Ex_IsoEnumFetchNotEqualToCount"
0x24e45  call     string System.Deployment.Application.Resources::GetString(string s)
0x24e4a  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x24e4f  throw
0x24e50  ldc.i4.0
0x24e51  stloc.s  8
0x24e53  br.s     loc_24E6E
0x24e55  ldloc.2
0x24e56  ldloc.s  8
0x24e58  ldloc.s  4
0x24e5a  ldloc.s  8
0x24e5c  ldelem.ref
0x24e5d  callvirt instance class System.Deployment.Internal.Isolation.Manifest.FileEntry System.Deployment.Internal.Isolation.Manifest.IFileEntry::get_AllData()
0x24e62  newobj   instance void System.Deployment.Application.Manifest.File::.ctor(class System.Deployment.Internal.Isolation.Manifest.FileEntry fileEntry)
0x24e67  stelem.ref
0x24e68  ldloc.s  8
0x24e6a  ldc.i4.1
0x24e6b  add
0x24e6c  stloc.s  8
0x24e6e  ldloc.s  8
0x24e70  ldloc.1
0x24e71  blt.un.s loc_24E55
0x24e73  ldarg.0
0x24e74  ldflda   object System.Deployment.Application.Manifest.AssemblyManifest::_files
0x24e79  ldloc.2
0x24e7a  ldnull
0x24e7b  call     object [mscorlib]System.Threading.Interlocked::CompareExchange(object&, object, object)
0x24e80  pop
0x24e81  ldarg.0
0x24e82  ldfld    object System.Deployment.Application.Manifest.AssemblyManifest::_files
0x24e87  castclass class System.Deployment.Application.Manifest.File[]
0x24e8c  ret
```
