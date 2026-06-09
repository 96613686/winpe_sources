# __scrt_is_ucrt_dll_in_use

- ea: `0x140006a10`
- end: `0x140006a1c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140005ddc`
- `0x140005e54`
- `0x140005f78`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140006a10  xor     eax, eax
0x140006a12  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140006a18  setnz   al
0x140006a1b  retn
```
