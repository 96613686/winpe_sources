# __scrt_is_ucrt_dll_in_use

- ea: `0x18000b5d0`
- end: `0x18000b5dc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000ad48`
- `0x18000ad88`
- `0x18000ae20`
- `0x18000ae70`
- `0x18000af04`
- `0x18000b038`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000b5d0  xor     eax, eax
0x18000b5d2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000b5d8  setnz   al
0x18000b5db  retn
```
