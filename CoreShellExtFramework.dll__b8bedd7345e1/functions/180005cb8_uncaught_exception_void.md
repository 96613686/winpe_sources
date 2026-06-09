# __uncaught_exception(void)

- ea: `0x180005cb8`
- end: `0x180005cc4`
- name: `?__uncaught_exception@@YA_NXZ`
- size: `12`
- prototype: `_BOOL8(void)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180005474`
- `0x1800054b4`
- `0x18000554c`
- `0x18000559c`
- `0x180005630`
- `0x180005764`

## pseudocode

```c
_BOOL8 __uncaught_exception(void)
{
  return dword_18001F230 != 0;
}

```

## disassembly

```asm
0x180005cb8  xor     eax, eax
0x180005cba  cmp     cs:dword_18001F230, eax
0x180005cc0  setnz   al
0x180005cc3  retn
```
