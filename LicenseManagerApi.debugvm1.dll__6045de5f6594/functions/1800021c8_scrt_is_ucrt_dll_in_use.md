# __scrt_is_ucrt_dll_in_use

- ea: `0x1800021c8`
- end: `0x1800021d4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001984`
- `0x1800019c4`
- `0x180001a5c`
- `0x180001aac`
- `0x180001b40`
- `0x180001c74`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800021c8  xor     eax, eax
0x1800021ca  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800021d0  setnz   al
0x1800021d3  retn
```
