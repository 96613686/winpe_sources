# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180004390`
- end: `0x180004393`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003af0`
- `0x180003b18`
- `0x180003bc0`
- `0x180003bd4`
- `0x180003d68`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180004390  mov     al, 1
0x180004392  retn
```
