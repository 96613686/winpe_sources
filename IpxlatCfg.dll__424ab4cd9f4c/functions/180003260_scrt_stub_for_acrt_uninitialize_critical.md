# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180003260`
- end: `0x180003263`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001df0`
- `0x180001e20`
- `0x180001ec4`
- `0x180001ee0`
- `0x180002080`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180003260  mov     al, 1
0x180003262  retn
```
