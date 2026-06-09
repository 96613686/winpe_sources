# __scrt_is_ucrt_dll_in_use

- ea: `0x180002454`
- end: `0x180002460`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001cdc`
- `0x180001d1c`
- `0x180001db4`
- `0x180001e04`
- `0x180001e98`
- `0x180001fcc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002454  xor     eax, eax
0x180002456  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000245c  setnz   al
0x18000245f  retn
```
