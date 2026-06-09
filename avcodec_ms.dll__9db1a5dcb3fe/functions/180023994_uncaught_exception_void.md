# __uncaught_exception(void)

- ea: `0x180023994`
- end: `0x1800239a0`
- name: `?__uncaught_exception@@YA_NXZ`
- size: `12`
- prototype: `bool(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180023208`
- `0x180023244`
- `0x1800232d0`
- `0x180023330`
- `0x1800233b0`
- `0x1800234d4`

## pseudocode

```c
_BOOL8 __uncaught_exception(void)
{
  return dword_18004C0D0 != 0;
}

```

## disassembly

```asm
0x180023994  xor     eax, eax
0x180023996  cmp     cs:dword_18004C0D0, eax
0x18002399c  setnz   al
0x18002399f  retn
```
