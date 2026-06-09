# __scrt_is_ucrt_dll_in_use

- ea: `0x180002630`
- end: `0x18000263c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001da8`
- `0x180001de8`
- `0x180001e80`
- `0x180001ed0`
- `0x180001f64`
- `0x180002098`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002630  xor     eax, eax
0x180002632  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002638  setnz   al
0x18000263b  retn
```
