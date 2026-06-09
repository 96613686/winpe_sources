# MayNeedExtendedLengthPrefix(PATHCCH_OPTIONS)

- ea: `0x180019e84`
- end: `0x180019e98`
- name: `?MayNeedExtendedLengthPrefix@@YA_NW4PATHCCH_OPTIONS@@@Z`
- size: `20`
- prototype: `bool __fastcall(enum PATHCCH_OPTIONS)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180019fb8`

## callees

- `0x180019e84`

## pseudocode

```c
bool __fastcall MayNeedExtendedLengthPrefix(enum PATHCCH_OPTIONS a1)
{
  return (a1 & 5) == 5 || (a1 & 0x10) != 0;
}

```

## disassembly

```asm
0x180019e84  mov     eax, ecx
0x180019e86  and     eax, 5
0x180019e89  cmp     al, 5
0x180019e8b  jz      short loc_180019E95
0x180019e8d  test    cl, 10h
0x180019e90  jnz     short loc_180019E95
0x180019e92  xor     al, al
0x180019e94  retn
0x180019e95  mov     al, 1
0x180019e97  retn
```
