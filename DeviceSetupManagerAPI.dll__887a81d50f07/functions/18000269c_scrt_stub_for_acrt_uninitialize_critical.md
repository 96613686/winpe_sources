# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000269c`
- end: `0x18000269f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000194c`
- `0x18000197c`
- `0x180001a20`
- `0x180001a3c`
- `0x180001bdc`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000269c  mov     al, 1
0x18000269e  retn
```
