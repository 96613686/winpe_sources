# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800029ec`
- end: `0x1800029ef`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a10`
- `0x180001a40`
- `0x180001ae4`
- `0x180001b00`
- `0x180001ca0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800029ec  mov     al, 1
0x1800029ee  retn
```
