# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180003444`
- end: `0x180003447`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800027d0`
- `0x180002800`
- `0x1800028a4`
- `0x1800028c0`
- `0x180002a60`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180003444  mov     al, 1
0x180003446  retn
```
