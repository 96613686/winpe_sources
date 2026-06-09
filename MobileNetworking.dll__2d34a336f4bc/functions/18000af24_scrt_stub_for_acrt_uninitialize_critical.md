# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000af24`
- end: `0x18000af27`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180009a08`
- `0x180009a38`
- `0x180009adc`
- `0x180009af8`
- `0x180009c98`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000af24  mov     al, 1
0x18000af26  retn
```
