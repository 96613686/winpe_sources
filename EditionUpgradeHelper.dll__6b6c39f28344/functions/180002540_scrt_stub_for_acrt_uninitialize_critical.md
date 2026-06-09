# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002540`
- end: `0x180002543`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001990`
- `0x1800019c0`
- `0x180001a64`
- `0x180001a80`
- `0x180001c20`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002540  mov     al, 1
0x180002542  retn
```
