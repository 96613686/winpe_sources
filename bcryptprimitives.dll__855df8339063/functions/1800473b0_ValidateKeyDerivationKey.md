# ValidateKeyDerivationKey

- ea: `0x1800473b0`
- end: `0x180047472`
- name: `ValidateKeyDerivationKey`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004729c`
- `0x18006c410`

## callees

- `0x18000ee60`
- `0x1800473b0`

## string_xrefs

- `0x1800473f5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180047445`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall ValidateKeyDerivationKey(__int64 a1, _QWORD *a2, int a3)
{
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        75);
    return 3221225480LL;
  }
  if ( *(_DWORD *)(a1 + 4) == 1297304409 )
  {
    *a2 = a1;
    return 0;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return 3221225480LL;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    (_DWORD)a2,
    a3,
    (unsigned int)"Status",
    8,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
    84);
  return 3221225480LL;
}

```

## disassembly

```asm
0x1800473b0  sub     rsp, 48h
0x1800473b4  test    rcx, rcx
0x1800473b7  jz      short loc_180047428
0x1800473b9  cmp     dword ptr [rcx+4], 4D534B59h
0x1800473c0  jnz     short loc_1800473CD
0x1800473c2  mov     [rdx], rcx
0x1800473c5  xor     eax, eax
0x1800473c7  add     rsp, 48h
0x1800473cb  retn
0x1800473cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800473d4  lea     rax, WPP_GLOBAL_Control
0x1800473db  cmp     rcx, rax
0x1800473de  jz      short loc_1800473E6
0x1800473e0  test    byte ptr [rcx+1Ch], 1
0x1800473e4  jnz     short loc_1800473F1
0x1800473e6  mov     eax, 0C0000008h
0x1800473eb  add     rsp, 48h
0x1800473ef  retn
0x1800473f1  mov     rcx, [rcx+10h]
0x1800473f5  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800473fc  mov     [rsp+48h+var_18], 154h
0x180047404  lea     r9, aStatus; "Status"
0x18004740b  mov     [rsp+48h+var_20], rax
0x180047410  mov     [rsp+48h+var_28], 0C0000008h
0x180047418  call    WPP_SF_sDsd
0x18004741d  mov     eax, 0C0000008h
0x180047422  add     rsp, 48h
0x180047426  retn
0x180047428  mov     rcx, cs:WPP_GLOBAL_Control
0x18004742f  lea     rax, WPP_GLOBAL_Control
0x180047436  cmp     rcx, rax
0x180047439  jz      short loc_1800473E6
0x18004743b  test    byte ptr [rcx+1Ch], 1
0x18004743f  jz      short loc_1800473E6
0x180047441  mov     rcx, [rcx+10h]
0x180047445  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004744c  mov     [rsp+48h+var_18], 14Bh
0x180047454  lea     r9, aStatus; "Status"
0x18004745b  mov     [rsp+48h+var_20], rax
0x180047460  mov     [rsp+48h+var_28], 0C0000008h
0x180047468  call    WPP_SF_sDsd
0x18004746d  jmp     loc_1800473E6
```
