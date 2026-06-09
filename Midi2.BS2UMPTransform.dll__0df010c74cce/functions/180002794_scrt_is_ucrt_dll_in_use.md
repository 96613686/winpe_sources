# __scrt_is_ucrt_dll_in_use

- ea: `0x180002794`
- end: `0x1800027a0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001ef4`
- `0x180001f34`
- `0x180001fcc`
- `0x18000201c`
- `0x1800020b0`
- `0x1800021e4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002794  xor     eax, eax
0x180002796  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000279c  setnz   al
0x18000279f  retn
```
