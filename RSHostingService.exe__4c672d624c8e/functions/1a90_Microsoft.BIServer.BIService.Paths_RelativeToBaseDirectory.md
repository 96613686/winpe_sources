# Microsoft.BIServer.BIService.Paths::RelativeToBaseDirectory

- ea: `0x1a90`
- end: `0x1aa6`
- name: `Microsoft.BIServer.BIService.Paths::RelativeToBaseDirectory`
- size: `22`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c50`
- `0x2860`
- `0x2b00`

## pseudocode

```c

```

## disassembly

```asm
0x1a90  call     string [mscorlib]System.IO.Directory::GetCurrentDirectory()
0x1a95  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::GetParent(string)
0x1a9a  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1a9f  ldarg.0
0x1aa0  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1aa5  ret
```
