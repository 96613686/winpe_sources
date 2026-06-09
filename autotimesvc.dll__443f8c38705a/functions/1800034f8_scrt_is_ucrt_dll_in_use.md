# __scrt_is_ucrt_dll_in_use

- ea: `0x1800034f8`
- end: `0x180003504`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002bcc`
- `0x180002c0c`
- `0x180002ca4`
- `0x180002cf4`
- `0x180002d88`
- `0x180002ebc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800034f8  xor     eax, eax
0x1800034fa  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003500  setnz   al
0x180003503  retn
```
