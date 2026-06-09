# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001c90`
- end: `0x180001c93`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015e4`
- `0x180001614`
- `0x1800016b8`
- `0x1800016d4`
- `0x180001874`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001c90  mov     al, 1
0x180001c92  retn
```
