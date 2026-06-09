# NGenTask.ContainerFileInfo::.ctor

- ea: `0x3d20`
- end: `0x3d3a`
- name: `NGenTask.ContainerFileInfo::.ctor`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x4270`
- `0x4980`

## callees

- `0x3d50`
- `0x3d70`
- `0x3de0`

## pseudocode

```c

```

## disassembly

```asm
0x3d20  ldarg.0
0x3d21  call     instance void [mscorlib]System.Object::.ctor()
0x3d26  ldarg.0
0x3d27  ldarg.1
0x3d28  callvirt instance class NGenTask.ContainerRootDirectoryInfo NGenTask.ContainerDirectoryInfo::get_Root()
0x3d2d  call     instance void NGenTask.ContainerFileInfo::set_Root(class NGenTask.ContainerRootDirectoryInfo value)
0x3d32  ldarg.0
0x3d33  ldarg.2
0x3d34  call     instance void NGenTask.ContainerFileInfo::set_LogFile(class [mscorlib]System.IO.FileInfo value)
0x3d39  ret
```
