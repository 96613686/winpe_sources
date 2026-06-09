# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800023bc`
- end: `0x1800023bf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016c0`
- `0x1800016f0`
- `0x180001794`
- `0x1800017b0`
- `0x180001950`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800023bc  mov     al, 1
0x1800023be  retn
```
