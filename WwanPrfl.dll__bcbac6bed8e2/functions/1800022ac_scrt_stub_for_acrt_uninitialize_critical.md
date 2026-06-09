# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800022ac`
- end: `0x1800022af`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001758`
- `0x180001788`
- `0x18000182c`
- `0x180001848`
- `0x1800019e8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800022ac  mov     al, 1
0x1800022ae  retn
```
