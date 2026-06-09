# ___scrt_is_ucrt_dll_in_use

- ea: `0x408bf9`
- end: `0x408c05`
- name: `___scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `BOOL()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x40844e`
- `0x4084b9`
- `0x4085d4`

## pseudocode

```c
BOOL __scrt_is_ucrt_dll_in_use()
{
  return dword_427418 != 0;
}

```

## disassembly

```asm
0x408bf9  xor     eax, eax
0x408bfb  cmp     dword_427418, eax
0x408c01  setnz   al
0x408c04  retn
```
