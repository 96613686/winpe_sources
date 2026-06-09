# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800049bc`
- end: `0x1800049bf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003bec`
- `0x180003c14`
- `0x180003cc0`
- `0x180003cd4`
- `0x180003eac`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800049bc  mov     al, 1
0x1800049be  retn
```
