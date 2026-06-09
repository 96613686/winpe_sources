# __scrt_is_ucrt_dll_in_use

- ea: `0x180001c44`
- end: `0x180001c50`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001598`
- `0x1800015d8`
- `0x180001670`
- `0x1800016c0`
- `0x180001754`
- `0x180001888`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001c44  xor     eax, eax
0x180001c46  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001c4c  setnz   al
0x180001c4f  retn
```
