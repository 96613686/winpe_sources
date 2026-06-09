# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800025d4`
- end: `0x1800025d7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001c38`
- `0x180001c68`
- `0x180001d0c`
- `0x180001d28`
- `0x180001ec8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800025d4  mov     al, 1
0x1800025d6  retn
```
