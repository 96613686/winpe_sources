# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002884`
- end: `0x180002887`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016d0`
- `0x180001700`
- `0x1800017a4`
- `0x1800017c0`
- `0x180001960`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002884  mov     al, 1
0x180002886  retn
```
