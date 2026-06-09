# NGenTask.ContainerDirectoryInfo::SetDirectory

- ea: `0x3dc0`
- end: `0x3dd6`
- name: `NGenTask.ContainerDirectoryInfo::SetDirectory`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x3dc0`
- `0x3e00`
- `0x3e10`

## pseudocode

```c

```

## disassembly

```asm
0x3dc0  ldarg.0
0x3dc1  call     instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x3dc6  brfalse.s loc_3DCE
0x3dc8  newobj   instance void [mscorlib]System.ArgumentException::.ctor()
0x3dcd  throw
0x3dce  ldarg.0
0x3dcf  ldarg.1
0x3dd0  call     instance void NGenTask.ContainerDirectoryInfo::set_Directory(class [mscorlib]System.IO.DirectoryInfo value)
0x3dd5  ret
```
