# ValidateEccKey

- ea: `0x18001ffa0`
- end: `0x180020207`
- name: `ValidateEccKey`
- size: `615`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001fad0`
- `0x18006bf40`
- `0x18006c080`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18001ffa0`

## string_xrefs

- `0x1800200a9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18002017f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall ValidateEccKey(__int64 a1, __int64 a2, int a3, int a4, _QWORD *a5)
{
  int v5; // ebx
  __int64 i; // rax
  __int64 *v8; // rcx
  char *v9; // rax
  int v10; // r9d
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v14; // rax

  v5 = a2;
  if ( a1 && a5 )
  {
    if ( *(_DWORD *)(a1 + 4) == 1297304409 )
    {
      if ( a4 && !*(_QWORD *)(a1 + 16) )
      {
        v12 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            a3,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            67);
      }
      else
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= 4 )
          {
            v12 = -1073741811;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                a2,
                a3,
                (unsigned int)"Status",
                13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                116);
            return v12;
          }
          v8 = qword_180084718;
          a2 = 6 * i;
          if ( !v5 )
            v8 = &qword_1800847D8;
          if ( *(_DWORD *)(a1 + 8) == LODWORD(v8[6 * i]) )
            break;
        }
        if ( !a4 )
          goto LABEL_17;
        v9 = " ";
        if ( !v5 )
          v9 = " ";
        v10 = *(_DWORD *)&v9[8 * a2];
        v11 = *(_DWORD *)(**(_QWORD **)(a1 + 16) + 12LL);
        if ( v10 )
        {
          if ( v10 != v11 )
          {
            v12 = -1073741811;
            DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 613);
            return v12;
          }
          goto LABEL_17;
        }
        if ( (unsigned int)(v11 - 14) <= 0x34 )
        {
LABEL_17:
          if ( !a3 || (v14 = *(_QWORD *)(a1 + 24)) != 0 && *(_BYTE *)(v14 + 4) )
          {
            *a5 = a1;
            return 0;
          }
          else
          {
            v12 = -1073741811;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                a2,
                a3,
                (unsigned int)"Status",
                13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                125);
          }
          return v12;
        }
        v12 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            a3,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            91);
      }
    }
    else
    {
      v12 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          60);
    }
  }
  else
  {
    v12 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        51);
  }
  return v12;
}

```

## disassembly

```asm
0x18001ffa0  mov     [rsp+arg_0], rbx
0x18001ffa5  mov     [rsp+arg_8], rsi
0x18001ffaa  push    rdi
0x18001ffab  sub     rsp, 40h
0x18001ffaf  mov     ebx, edx
0x18001ffb1  mov     r10, rcx
0x18001ffb4  test    rcx, rcx
0x18001ffb7  jz      loc_18002007F
0x18001ffbd  mov     r11, [rsp+48h+arg_20]
0x18001ffc2  test    r11, r11
0x18001ffc5  jz      loc_18002007F
0x18001ffcb  cmp     dword ptr [rcx+4], 4D534B59h
0x18001ffd2  jnz     loc_18002010A
0x18001ffd8  test    r9d, r9d
0x18001ffdb  jz      short loc_18001FFE8
0x18001ffdd  cmp     qword ptr [rcx+10h], 0
0x18001ffe2  jz      loc_18002013D
0x18001ffe8  xor     eax, eax
0x18001ffea  lea     rsi, qword_1800847D8
0x18001fff1  lea     rdi, qword_180084718
0x18001fff8  nop     dword ptr [rax+rax+00000000h]
0x180020000  cmp     eax, 4
0x180020003  jnb     loc_1800201D4
0x180020009  lea     rdx, [rax+rax*2]
0x18002000d  mov     rcx, rdi
0x180020010  add     rdx, rdx
0x180020013  test    ebx, ebx
0x180020015  cmovz   rcx, rsi
0x180020019  mov     ecx, [rcx+rdx*8]
0x18002001c  cmp     [r10+8], ecx
0x180020020  jz      short loc_180020026
0x180020022  inc     eax
0x180020024  jmp     short loc_180020000
0x180020026  test    r9d, r9d
0x180020029  jz      short loc_180020062
0x18002002b  test    ebx, ebx
0x18002002d  lea     rcx, aEck2+4; " "
0x180020034  lea     rax, aEcs2+4; " "
0x18002003b  cmovz   rax, rcx
0x18002003f  mov     r9d, [rax+rdx*8]
0x180020043  mov     rax, [r10+10h]
0x180020047  mov     rcx, [rax]
0x18002004a  mov     eax, [rcx+0Ch]
0x18002004d  test    r9d, r9d
0x180020050  jnz     loc_180020170
0x180020056  add     eax, 0FFFFFFF2h
0x180020059  cmp     eax, 34h ; '4'
0x18002005c  ja      loc_1800201A1
0x180020062  test    r8d, r8d
0x180020065  jnz     short loc_1800200CB
0x180020067  mov     [r11], r10
0x18002006a  xor     ebx, ebx
0x18002006c  mov     rsi, [rsp+48h+arg_8]
0x180020071  mov     eax, ebx
0x180020073  mov     rbx, [rsp+48h+arg_0]
0x180020078  add     rsp, 40h
0x18002007c  pop     rdi
0x18002007d  retn
0x18002007f  mov     ebx, 0C000000Dh
0x180020084  mov     rcx, cs:WPP_GLOBAL_Control
0x18002008b  lea     rax, WPP_GLOBAL_Control
0x180020092  cmp     rcx, rax
0x180020095  jz      short loc_18002006C
0x180020097  test    byte ptr [rcx+1Ch], 1
0x18002009b  jz      short loc_18002006C
0x18002009d  mov     [rsp+48h+var_18], 233h
0x1800200a5  mov     rcx, [rcx+10h]
0x1800200a9  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800200b0  mov     [rsp+48h+var_20], rax
0x1800200b5  lea     r9, aStatus; "Status"
0x1800200bc  mov     [rsp+48h+var_28], 0C000000Dh
0x1800200c4  call    WPP_SF_sDsd
0x1800200c9  jmp     short loc_18002006C
0x1800200cb  mov     rax, [r10+18h]
0x1800200cf  test    rax, rax
0x1800200d2  jz      short loc_1800200DA
0x1800200d4  cmp     byte ptr [rax+4], 0
0x1800200d8  jnz     short loc_180020067
0x1800200da  mov     ebx, 0C000000Dh
0x1800200df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200e6  lea     rax, WPP_GLOBAL_Control
0x1800200ed  cmp     rcx, rax
0x1800200f0  jz      loc_18002006C
0x1800200f6  test    byte ptr [rcx+1Ch], 1
0x1800200fa  jz      loc_18002006C
0x180020100  mov     [rsp+48h+var_18], 27Dh
0x180020108  jmp     short loc_1800200A5
0x18002010a  mov     ebx, 0C000000Dh
0x18002010f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020116  lea     rax, WPP_GLOBAL_Control
0x18002011d  cmp     rcx, rax
0x180020120  jz      loc_18002006C
0x180020126  test    byte ptr [rcx+1Ch], 1
0x18002012a  jz      loc_18002006C
0x180020130  mov     [rsp+48h+var_18], 23Ch
0x180020138  jmp     loc_1800200A5
0x18002013d  mov     ebx, 0C000000Dh
0x180020142  mov     rcx, cs:WPP_GLOBAL_Control
0x180020149  lea     rax, WPP_GLOBAL_Control
0x180020150  cmp     rcx, rax
0x180020153  jz      loc_18002006C
0x180020159  test    byte ptr [rcx+1Ch], 1
0x18002015d  jz      loc_18002006C
0x180020163  mov     [rsp+48h+var_18], 243h
0x18002016b  jmp     loc_1800200A5
0x180020170  cmp     r9d, eax
0x180020173  jz      loc_180020062
0x180020179  mov     r9d, 265h
0x18002017f  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020186  lea     rdx, aStatus; "Status"
0x18002018d  mov     ecx, 0C000000Dh
0x180020192  mov     ebx, 0C000000Dh
0x180020197  call    DebugTraceError
0x18002019c  jmp     loc_18002006C
0x1800201a1  mov     ebx, 0C000000Dh
0x1800201a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201ad  lea     rax, WPP_GLOBAL_Control
0x1800201b4  cmp     rcx, rax
0x1800201b7  jz      loc_18002006C
0x1800201bd  test    byte ptr [rcx+1Ch], 1
0x1800201c1  jz      loc_18002006C
0x1800201c7  mov     [rsp+48h+var_18], 25Bh
0x1800201cf  jmp     loc_1800200A5
0x1800201d4  mov     ebx, 0C000000Dh
0x1800201d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201e0  lea     rax, WPP_GLOBAL_Control
0x1800201e7  cmp     rcx, rax
0x1800201ea  jz      loc_18002006C
0x1800201f0  test    byte ptr [rcx+1Ch], 1
0x1800201f4  jz      loc_18002006C
0x1800201fa  mov     [rsp+48h+var_18], 274h
0x180020202  jmp     loc_1800200A5
```
