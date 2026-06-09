# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000219c`
- end: `0x18000219f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001610`
- `0x180001640`
- `0x1800016e4`
- `0x180001700`
- `0x1800018a0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000219c  mov     al, 1
0x18000219e  retn
```
