# NGenTask.FileLock::Dispose

- ea: `0x3020`
- end: `0x302e`
- name: `NGenTask.FileLock::Dispose`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x3030`

## pseudocode

```c

```

## disassembly

```asm
0x3020  ldarg.0
0x3021  ldc.i4.1
0x3022  callvirt instance void NGenTask.FileLock::Dispose(bool disposing)
0x3027  ldarg.0
0x3028  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x302d  ret
```
