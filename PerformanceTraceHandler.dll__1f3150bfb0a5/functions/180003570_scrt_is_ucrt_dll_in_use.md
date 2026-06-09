# __scrt_is_ucrt_dll_in_use

- ea: `0x180003570`
- end: `0x18000357c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002c24`
- `0x180002c64`
- `0x180002cfc`
- `0x180002d4c`
- `0x180002de0`
- `0x180002f14`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003570  xor     eax, eax
0x180003572  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003578  setnz   al
0x18000357b  retn
```
