# sqlite3GetTempReg

- ea: `0x18004cfa0`
- end: `0x18004cfbf`
- name: `sqlite3GetTempReg`
- size: `31`
- prototype: ``
- caller_count: `30`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eb78`
- `0x1800189c8`
- `0x180037194`
- `0x1800399a0`
- `0x18003b070`
- `0x1800402cc`
- `0x180043968`
- `0x180050420`
- `0x180058070`
- `0x18005d030`
- `0x18005e000`
- `0x180069e7c`
- `0x18006c53c`
- `0x18006dca4`
- `0x18006ed84`
- `0x18006f8a4`
- `0x180070350`
- `0x1800706dc`
- `0x180072440`
- `0x180080628`
- `0x180082bf0`
- `0x1800866d4`
- `0x180087e6c`
- `0x1800972dc`
- `0x180097708`
- `0x180097878`
- `0x180097c40`
- `0x180097fa4`
- `0x180098540`
- `0x180098bfc`

## callees

- `0x18004cfa0`

## pseudocode

```c
__int64 __fastcall sqlite3GetTempReg(__int64 a1)
{
  char v1; // al
  unsigned __int8 v3; // al

  v1 = *(_BYTE *)(a1 + 31);
  if ( v1 )
  {
    v3 = v1 - 1;
    *(_BYTE *)(a1 + 31) = v3;
    return *(unsigned int *)(a1 + 4LL * v3 + 232);
  }
  else
  {
    return (unsigned int)++*(_DWORD *)(a1 + 60);
  }
}

```

## disassembly

```asm
0x18004cfa0  movzx   eax, byte ptr [rcx+1Fh]
0x18004cfa4  test    al, al
0x18004cfa6  jnz     short loc_18004CFAF
0x18004cfa8  inc     dword ptr [rcx+3Ch]
0x18004cfab  mov     eax, [rcx+3Ch]
0x18004cfae  retn
0x18004cfaf  dec     al
0x18004cfb1  movzx   eax, al
0x18004cfb4  mov     [rcx+1Fh], al
0x18004cfb7  mov     eax, [rcx+rax*4+0E8h]
0x18004cfbe  retn
```
