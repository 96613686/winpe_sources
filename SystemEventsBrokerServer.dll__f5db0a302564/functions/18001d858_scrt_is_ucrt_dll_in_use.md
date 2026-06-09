# __scrt_is_ucrt_dll_in_use

- ea: `0x18001d858`
- end: `0x18001d864`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001cfb8`
- `0x18001cff8`
- `0x18001d090`
- `0x18001d0e0`
- `0x18001d174`
- `0x18001d2a8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18001d858  xor     eax, eax
0x18001d85a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18001d860  setnz   al
0x18001d863  retn
```
