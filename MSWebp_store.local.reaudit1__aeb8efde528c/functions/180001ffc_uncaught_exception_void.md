# __uncaught_exception(void)

- ea: `0x180001ffc`
- end: `0x180002008`
- name: `?__uncaught_exception@@YA_NXZ`
- size: `12`
- prototype: `bool(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001788`
- `0x1800017c8`
- `0x18000186c`
- `0x1800018d4`
- `0x180001968`
- `0x180001a9c`

## pseudocode

```c
_BOOL8 __uncaught_exception(void)
{
  return dword_180045B00 != 0;
}

```

## disassembly

```asm
0x180001ffc  xor     eax, eax
0x180001ffe  cmp     cs:dword_180045B00, eax
0x180002004  setnz   al
0x180002007  retn
```
