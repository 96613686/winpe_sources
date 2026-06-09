# __scrt_is_ucrt_dll_in_use

- ea: `0x180002154`
- end: `0x180002160`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001940`
- `0x180001980`
- `0x180001a18`
- `0x180001a68`
- `0x180001afc`
- `0x180001c30`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002154  xor     eax, eax
0x180002156  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000215c  setnz   al
0x18000215f  retn
```
