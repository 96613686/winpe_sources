# NGenTask.ContainerDirectoryInfo::GetHashCode

- ea: `0x3ea0`
- end: `0x3eb1`
- name: `NGenTask.ContainerDirectoryInfo::GetHashCode`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x3e00`

## pseudocode

```c

```

## disassembly

```asm
0x3ea0  ldarg.0
0x3ea1  call     instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x3ea6  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x3eab  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x3eb0  ret
```
