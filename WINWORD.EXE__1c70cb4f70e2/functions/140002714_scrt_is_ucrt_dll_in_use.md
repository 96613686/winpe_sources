# __scrt_is_ucrt_dll_in_use

- ea: `0x140002714`
- end: `0x140002720`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001a80`
- `0x140001af8`
- `0x140001c1c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002714  xor     eax, eax
0x140002716  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x14000271c  setnz   al
0x14000271f  retn
```
