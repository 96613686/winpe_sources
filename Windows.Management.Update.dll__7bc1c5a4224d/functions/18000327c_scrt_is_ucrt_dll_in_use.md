# __scrt_is_ucrt_dll_in_use

- ea: `0x18000327c`
- end: `0x180003288`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002914`
- `0x180002954`
- `0x1800029ec`
- `0x180002a3c`
- `0x180002ad0`
- `0x180002c04`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000327c  xor     eax, eax
0x18000327e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003284  setnz   al
0x180003287  retn
```
