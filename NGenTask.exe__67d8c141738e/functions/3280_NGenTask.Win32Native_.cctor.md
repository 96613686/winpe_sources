# NGenTask.Win32Native::.cctor

- ea: `0x3280`
- end: `0x328b`
- name: `NGenTask.Win32Native::.cctor`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c

```

## disassembly

```asm
0x3280  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3285  stsfld   native int NGenTask.Win32Native::WTS_CURRENT_SERVER_HANDLE
0x328a  ret
```
