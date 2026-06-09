# System.Deployment.Application.PEStream::GetId1ManifestResource

- ea: `0x1ac80`
- end: `0x1acf8`
- name: `System.Deployment.Application.PEStream::GetId1ManifestResource`
- size: `120`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1ac40`
- `0x1ac60`

## callees

- `0x1ac20`
- `0x1ac80`
- `0x1ad00`
- `0x23020`
- `0x2b990`
- `0x2b9a0`

## string_xrefs

- `0x1acc3`: `Ex_MultipleId1Manifest`

## pseudocode

```c

```

## disassembly

```asm
0x1ac80  ldc.i4.2
0x1ac81  newarr   [mscorlib]System.Object
0x1ac86  stloc.0
0x1ac87  ldloc.0
0x1ac88  ldc.i4.0
0x1ac89  ldc.i4.s 0x18
0x1ac8b  box      [mscorlib]System.UInt16
0x1ac90  stelem.ref
0x1ac91  ldloc.0
0x1ac92  ldc.i4.1
0x1ac93  call     unsigned int16 System.Deployment.Application.PEStream::get_Id1ManifestId()
0x1ac98  box      [mscorlib]System.UInt16
0x1ac9d  stelem.ref
0x1ac9e  ldarg.0
0x1ac9f  ldloc.0
0x1aca0  call     instance class ResourceComponent System.Deployment.Application.PEStream::RetrieveResource(object[] keys)
0x1aca5  stloc.1
0x1aca6  ldloc.1
0x1aca7  brfalse.s loc_1ACF6
0x1aca9  ldloc.1
0x1acaa  isinst   ResourceDirectory
0x1acaf  brfalse.s loc_1ACF6
0x1acb1  ldloc.1
0x1acb2  castclass ResourceDirectory
0x1acb7  stloc.2
0x1acb8  ldloc.2
0x1acb9  callvirt instance int32 ResourceDirectory::get_ResourceComponentCount()
0x1acbe  ldc.i4.1
0x1acbf  ble.s    loc_1ACD3
0x1acc1  ldc.i4.s 0xB
0x1acc3  ldstr    aExMultipleid1m// "Ex_MultipleId1Manifest"
0x1acc8  call     string System.Deployment.Application.Resources::GetString(string s)
0x1accd  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32, string)
0x1acd2  throw
0x1acd3  ldloc.2
0x1acd4  callvirt instance int32 ResourceDirectory::get_ResourceComponentCount()
0x1acd9  ldc.i4.1
0x1acda  bne.un.s loc_1ACF6
0x1acdc  ldloc.2
0x1acdd  ldc.i4.0
0x1acde  callvirt instance class ResourceComponent ResourceDirectory::GetResourceComponent(int32 index)
0x1ace3  stloc.3
0x1ace4  ldloc.3
0x1ace5  brfalse.s loc_1ACF6
0x1ace7  ldloc.3
0x1ace8  isinst   ResourceData
0x1aced  brfalse.s loc_1ACF6
0x1acef  ldloc.3
0x1acf0  castclass ResourceData
0x1acf5  ret
0x1acf6  ldnull
0x1acf7  ret
```
