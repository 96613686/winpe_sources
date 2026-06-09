# __scrt_is_ucrt_dll_in_use

- ea: `0x180001cb4`
- end: `0x180001cc0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800015ac`
- `0x1800015ec`
- `0x180001684`
- `0x1800016d4`
- `0x180001768`
- `0x18000189c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001cb4  xor     eax, eax
0x180001cb6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001cbc  setnz   al
0x180001cbf  retn
```
