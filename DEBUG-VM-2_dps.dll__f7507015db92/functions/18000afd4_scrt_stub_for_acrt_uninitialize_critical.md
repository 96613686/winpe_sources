# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000afd4`
- end: `0x18000afd7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a194`
- `0x18000a1c4`
- `0x18000a268`
- `0x18000a284`
- `0x18000a424`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000afd4  mov     al, 1
0x18000afd6  retn
```
