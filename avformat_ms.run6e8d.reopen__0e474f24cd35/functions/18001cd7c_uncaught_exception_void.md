# __uncaught_exception(void)

- ea: `0x18001cd7c`
- end: `0x18001cd88`
- name: `?__uncaught_exception@@YA_NXZ`
- size: `12`
- prototype: `bool(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18001c5f0`
- `0x18001c62c`
- `0x18001c6b8`
- `0x18001c718`
- `0x18001c798`
- `0x18001c8bc`

## pseudocode

```c
_BOOL8 __uncaught_exception(void)
{
  return dword_1800310C0 != 0;
}

```

## disassembly

```asm
0x18001cd7c  xor     eax, eax
0x18001cd7e  cmp     cs:dword_1800310C0, eax
0x18001cd84  setnz   al
0x18001cd87  retn
```
