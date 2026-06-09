# __scrt_stub_for_acrt_uninitialize

- ea: `0x140002ca4`
- end: `0x140002ca7`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140002670`
- `0x140002974`
- `0x140002b14`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140002ca4  mov     al, 1
0x140002ca6  retn
```
