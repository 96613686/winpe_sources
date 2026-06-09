# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000295c`
- end: `0x18000295f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ebc`
- `0x180001eec`
- `0x180001f90`
- `0x180001fac`
- `0x18000214c`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000295c  mov     al, 1
0x18000295e  retn
```
