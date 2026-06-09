# ___scrt_is_ucrt_dll_in_use

- ea: `0x40dc56`
- end: `0x40dc62`
- name: `___scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `BOOL()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x40d2d0`
- `0x40d33b`
- `0x40d456`

## pseudocode

```c
BOOL __scrt_is_ucrt_dll_in_use()
{
  return dword_43F6F8 != 0;
}

```

## disassembly

```asm
0x40dc56  xor     eax, eax
0x40dc58  cmp     dword_43F6F8, eax
0x40dc5e  setnz   al
0x40dc61  retn
```
