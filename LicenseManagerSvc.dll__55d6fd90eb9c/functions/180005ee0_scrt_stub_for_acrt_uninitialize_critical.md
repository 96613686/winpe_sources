# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180005ee0`
- end: `0x180005ee3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003740`
- `0x180003770`
- `0x180003814`
- `0x180003830`
- `0x1800039d0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180005ee0  mov     al, 1
0x180005ee2  retn
```
