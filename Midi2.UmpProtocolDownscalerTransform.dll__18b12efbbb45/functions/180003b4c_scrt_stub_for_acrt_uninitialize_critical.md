# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180003b4c`
- end: `0x180003b4f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003060`
- `0x180003090`
- `0x180003134`
- `0x180003150`
- `0x1800032f0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180003b4c  mov     al, 1
0x180003b4e  retn
```
