# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002830`
- end: `0x180002833`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b70`
- `0x180001ba0`
- `0x180001c44`
- `0x180001c60`
- `0x180001e00`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002830  mov     al, 1
0x180002832  retn
```
