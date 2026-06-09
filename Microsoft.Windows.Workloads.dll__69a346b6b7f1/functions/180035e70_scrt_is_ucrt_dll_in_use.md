# __scrt_is_ucrt_dll_in_use

- ea: `0x180035e70`
- end: `0x180035e7c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800350a4`
- `0x1800350e0`
- `0x18003516c`
- `0x1800351cc`
- `0x18003524c`
- `0x180035370`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180035e70  xor     eax, eax
0x180035e72  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180035e78  setnz   al
0x180035e7b  retn
```
