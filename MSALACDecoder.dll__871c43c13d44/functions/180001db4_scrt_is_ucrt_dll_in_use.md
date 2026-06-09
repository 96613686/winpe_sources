# __scrt_is_ucrt_dll_in_use

- ea: `0x180001db4`
- end: `0x180001dc0`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800015a0`
- `0x1800015e0`
- `0x180001678`
- `0x1800016c8`
- `0x18000175c`
- `0x180001890`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001db4  xor     eax, eax
0x180001db6  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001dbc  setnz   al
0x180001dbf  retn
```
