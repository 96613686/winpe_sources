# NGenTask.ContainerDirectoryInfo::.ctor

- ea: `0x3d90`
- end: `0x3dbb`
- name: `NGenTask.ContainerDirectoryInfo::.ctor`
- size: `43`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x310`
- `0x3ed0`
- `0x45f0`
- `0x4dc0`

## callees

- `0x3d90`
- `0x3de0`
- `0x3df0`
- `0x3e10`

## pseudocode

```c

```

## disassembly

```asm
0x3d90  ldarg.0
0x3d91  call     instance void [mscorlib]System.Object::.ctor()
0x3d96  ldarg.1
0x3d97  brtrue.s loc_3DA7
0x3d99  ldarg.0
0x3d9a  ldarg.0
0x3d9b  castclass NGenTask.ContainerRootDirectoryInfo
0x3da0  call     instance void NGenTask.ContainerDirectoryInfo::set_Root(class NGenTask.ContainerRootDirectoryInfo value)
0x3da5  br.s     loc_3DB3
0x3da7  ldarg.0
0x3da8  ldarg.1
0x3da9  callvirt instance class NGenTask.ContainerRootDirectoryInfo NGenTask.ContainerDirectoryInfo::get_Root()
0x3dae  call     instance void NGenTask.ContainerDirectoryInfo::set_Root(class NGenTask.ContainerRootDirectoryInfo value)
0x3db3  ldarg.0
0x3db4  ldarg.2
0x3db5  call     instance void NGenTask.ContainerDirectoryInfo::set_Directory(class [mscorlib]System.IO.DirectoryInfo value)
0x3dba  ret
```
