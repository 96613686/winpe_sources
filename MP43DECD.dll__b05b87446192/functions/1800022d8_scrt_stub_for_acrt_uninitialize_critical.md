# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800022d8`
- end: `0x1800022db`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a38`
- `0x180001a68`
- `0x180001b0c`
- `0x180001b28`
- `0x180001cc8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800022d8  mov     al, 1
0x1800022da  retn
```
