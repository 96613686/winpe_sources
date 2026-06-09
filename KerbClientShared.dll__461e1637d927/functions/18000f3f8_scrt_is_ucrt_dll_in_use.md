# __scrt_is_ucrt_dll_in_use

- ea: `0x18000f3f8`
- end: `0x18000f404`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000eb94`
- `0x18000ebd4`
- `0x18000ec6c`
- `0x18000ecbc`
- `0x18000ed50`
- `0x18000ee84`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000f3f8  xor     eax, eax
0x18000f3fa  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000f400  setnz   al
0x18000f403  retn
```
