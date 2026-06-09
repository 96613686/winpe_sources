# __scrt_is_user_matherr_present

- ea: `0x140001150`
- end: `0x14000115c`
- name: `__scrt_is_user_matherr_present`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d40`

## pseudocode

```c
_BOOL8 _scrt_is_user_matherr_present()
{
  return _scrt_default_matherr == 0;
}

```

## disassembly

```asm
0x140001150  xor     eax, eax
0x140001152  cmp     cs:__scrt_default_matherr, eax
0x140001158  setz    al
0x14000115b  retn
```
