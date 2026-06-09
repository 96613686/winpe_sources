# __scrt_is_ucrt_dll_in_use

- ea: `0x180001bb0`
- end: `0x180001bbc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001528`
- `0x180001568`
- `0x180001600`
- `0x180001650`
- `0x1800016e4`
- `0x180001818`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001bb0  xor     eax, eax
0x180001bb2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001bb8  setnz   al
0x180001bbb  retn
```
