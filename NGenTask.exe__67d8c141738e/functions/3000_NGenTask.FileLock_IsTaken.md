# NGenTask.FileLock::IsTaken

- ea: `0x3000`
- end: `0x3012`
- name: `NGenTask.FileLock::IsTaken`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x3000`

## pseudocode

```c

```

## disassembly

```asm
0x3000  ldarg.0
0x3001  call     void [mscorlib]System.IO.File::Delete(string)
0x3006  leave.s  loc_300B
0x3008  pop
0x3009  leave.s  loc_300B
0x300b  ldarg.0
0x300c  call     bool [mscorlib]System.IO.File::Exists(string)
0x3011  ret
```
