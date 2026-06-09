# SymCryptFdefSizeofIntFromDigits

- ea: `0x180014df8`
- end: `0x180014e0d`
- name: `SymCryptFdefSizeofIntFromDigits`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180011eec`
- `0x180014590`
- `0x180017d58`

## callees

- `0x180014df8`

## pseudocode

```c
__int64 __fastcall SymCryptFdefSizeofIntFromDigits(int a1)
{
  if ( (unsigned int)(a1 - 1) > 0x7FF )
    return 0;
  else
    return (unsigned int)((a1 << 6) + 32);
}

```

## disassembly

```asm
0x180014df8  lea     eax, [rcx-1]
0x180014dfb  cmp     eax, 7FFh
0x180014e00  ja      short loc_180014E0A
0x180014e02  shl     ecx, 6
0x180014e05  lea     eax, [rcx+20h]
0x180014e08  retn
0x180014e0a  xor     eax, eax
0x180014e0c  retn
```
