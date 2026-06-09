# __scrt_is_ucrt_dll_in_use

- ea: `0x18000207c`
- end: `0x180002088`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001810`
- `0x180001850`
- `0x1800018e8`
- `0x180001938`
- `0x1800019cc`
- `0x180001b00`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000207c  xor     eax, eax
0x18000207e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002084  setnz   al
0x180002087  retn
```
