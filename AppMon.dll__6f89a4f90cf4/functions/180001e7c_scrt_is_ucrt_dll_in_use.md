# __scrt_is_ucrt_dll_in_use

- ea: `0x180001e7c`
- end: `0x180001e88`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001644`
- `0x180001684`
- `0x18000171c`
- `0x18000176c`
- `0x180001800`
- `0x180001934`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001e7c  xor     eax, eax
0x180001e7e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e84  setnz   al
0x180001e87  retn
```
