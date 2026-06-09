# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000209c`
- end: `0x18000209f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016e4`
- `0x180001714`
- `0x1800017b8`
- `0x1800017d4`
- `0x180001974`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000209c  mov     al, 1
0x18000209e  retn
```
