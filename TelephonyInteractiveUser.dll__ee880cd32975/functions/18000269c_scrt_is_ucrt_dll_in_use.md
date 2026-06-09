# __scrt_is_ucrt_dll_in_use

- ea: `0x18000269c`
- end: `0x1800026a8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001e08`
- `0x180001e48`
- `0x180001ee0`
- `0x180001f30`
- `0x180001fc4`
- `0x1800020f8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000269c  xor     eax, eax
0x18000269e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800026a4  setnz   al
0x1800026a7  retn
```
