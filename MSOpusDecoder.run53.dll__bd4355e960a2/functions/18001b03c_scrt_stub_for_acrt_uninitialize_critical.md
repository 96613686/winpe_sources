# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18001b03c`
- end: `0x18001b03f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019cc`
- `0x1800019fc`
- `0x180001aa0`
- `0x180001abc`
- `0x180001c5c`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18001b03c  mov     al, 1
0x18001b03e  retn
```
