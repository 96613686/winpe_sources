# __scrt_is_ucrt_dll_in_use

- ea: `0x1800024f4`
- end: `0x180002500`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001c68`
- `0x180001ca8`
- `0x180001d40`
- `0x180001d90`
- `0x180001e24`
- `0x180001f58`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800024f4  xor     eax, eax
0x1800024f6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800024fc  setnz   al
0x1800024ff  retn
```
