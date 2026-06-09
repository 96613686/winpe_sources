# __uncaught_exception(void)

- ea: `0x180001d28`
- end: `0x180001d34`
- name: `?__uncaught_exception@@YA_NXZ`
- size: `12`
- prototype: `_BOOL8(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000167c`
- `0x1800016bc`
- `0x180001754`
- `0x1800017a4`
- `0x180001838`
- `0x18000196c`

## pseudocode

```c
_BOOL8 __uncaught_exception(void)
{
  return dword_1800070B0 != 0;
}

```

## disassembly

```asm
0x180001d28  xor     eax, eax
0x180001d2a  cmp     cs:dword_1800070B0, eax
0x180001d30  setnz   al
0x180001d33  retn
```
