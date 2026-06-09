# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800023ac`
- end: `0x1800023af`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000184c`
- `0x18000187c`
- `0x180001920`
- `0x18000193c`
- `0x180001adc`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800023ac  mov     al, 1
0x1800023ae  retn
```
