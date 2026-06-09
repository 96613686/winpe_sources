# __scrt_is_ucrt_dll_in_use

- ea: `0x18000310c`
- end: `0x180003118`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002744`
- `0x180002784`
- `0x18000281c`
- `0x18000286c`
- `0x180002900`
- `0x180002a34`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000310c  xor     eax, eax
0x18000310e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003114  setnz   al
0x180003117  retn
```
