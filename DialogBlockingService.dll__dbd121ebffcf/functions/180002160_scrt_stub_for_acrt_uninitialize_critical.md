# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002160`
- end: `0x180002163`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001720`
- `0x180001750`
- `0x1800017f4`
- `0x180001810`
- `0x1800019b0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002160  mov     al, 1
0x180002162  retn
```
