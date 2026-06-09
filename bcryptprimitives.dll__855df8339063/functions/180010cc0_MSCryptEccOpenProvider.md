# MSCryptEccOpenProvider

- ea: `0x180010cc0`
- end: `0x180010ed0`
- name: `MSCryptEccOpenProvider`
- size: `528`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011730`
- `0x180050d40`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800102a0`
- `0x180010cc0`
- `0x180021a50`
- `0x180022340`

## string_xrefs

- `0x180010dbf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180010e0b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180010e62`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180010eb7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccOpenProvider(__int64 *a1, char *a2, char *a3, unsigned int a4)
{
  char *v5; // r11
  wchar_t **v7; // r10
  unsigned int i; // r9d
  char *v9; // rax
  int v10; // ecx
  unsigned int v11; // edi
  wchar_t *v12; // rsi
  __int64 v13; // rax
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rbx
  unsigned int v17; // edi
  __int64 v19; // r9
  int Curve; // eax

  v5 = a2;
  if ( !a1 || (_DWORD)a3 )
  {
    v17 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        54);
  }
  else
  {
    v7 = &off_180084710;
    if ( !a4 )
      v7 = &off_1800847D0;
    for ( i = 0; i < 4; ++i )
    {
      v9 = v5;
      a3 = (char *)((char *)v7[6 * i] - v5);
      do
      {
        v10 = *(unsigned __int16 *)&a3[(_QWORD)v9];
        LODWORD(a2) = *(unsigned __int16 *)v9 - v10;
        if ( (_DWORD)a2 )
          break;
        v9 += 2;
      }
      while ( v10 );
      if ( !(_DWORD)a2 )
      {
        v11 = (unsigned int)v7[6 * i + 1];
        if ( v11 )
        {
          v12 = v7[6 * i + 3];
          v13 = SafeAllocaAllocateFromHeap(24);
          v16 = v13;
          if ( v13 )
          {
            *(_QWORD *)(v13 + 12) = 0;
            *(_DWORD *)(v13 + 20) = 0;
            *(_DWORD *)v13 = 24;
            *(_DWORD *)(v13 + 4) = 1297301836;
            *(_DWORD *)(v13 + 8) = v11;
            if ( !v12 )
              goto LABEL_15;
            v19 = -1;
            while ( v12[++v19] != 0 )
              ;
            Curve = LoadCurve((_QWORD *)(v13 + 16), v11, v12, 2 * (int)v19 + 2);
            v17 = Curve;
            if ( Curve < 0 )
            {
              DebugTraceError(
                (unsigned int)Curve,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                2661);
              MSCryptEccCloseProvider(v16, 0, a4);
            }
            else
            {
LABEL_15:
              *a1 = v16;
              return 0;
            }
          }
          else
          {
            v17 = -1073741801;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v14,
                v15,
                (unsigned int)"Status",
                23,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                85);
          }
          return v17;
        }
        break;
      }
    }
    v17 = -1073741637;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        77);
  }
  return v17;
}

```

## disassembly

```asm
0x180010cc0  push    rbx
0x180010cc2  push    rbp
0x180010cc3  push    rsi
0x180010cc4  push    rdi
0x180010cc5  push    r14
0x180010cc7  push    r15
0x180010cc9  sub     rsp, 48h
0x180010ccd  mov     ebp, r9d
0x180010cd0  mov     r11, rdx
0x180010cd3  mov     r14, rcx
0x180010cd6  test    rcx, rcx
0x180010cd9  jz      loc_180010E89
0x180010cdf  test    r8d, r8d
0x180010ce2  jnz     loc_180010E89
0x180010ce8  test    r9d, r9d
0x180010ceb  lea     rax, off_1800847D0; "ECDH_P256"
0x180010cf2  lea     r10, off_180084710; "ECDSA_P256"
0x180010cf9  cmovz   r10, rax
0x180010cfd  xor     r15d, r15d
0x180010d00  mov     r9d, r15d
0x180010d03  cmp     r9d, 4
0x180010d07  jnb     loc_180010D99
0x180010d0d  mov     eax, r9d
0x180010d10  lea     rsi, [rax+rax*2]
0x180010d14  mov     rax, r11
0x180010d17  add     rsi, rsi
0x180010d1a  mov     r8, [r10+rsi*8]
0x180010d1e  sub     r8, r11
0x180010d21  movzx   edx, word ptr [rax]
0x180010d24  movzx   ecx, word ptr [rax+r8]
0x180010d29  sub     edx, ecx
0x180010d2b  jnz     short loc_180010D35
0x180010d2d  add     rax, 2
0x180010d31  test    ecx, ecx
0x180010d33  jnz     short loc_180010D21
0x180010d35  test    edx, edx
0x180010d37  jz      short loc_180010D3E
0x180010d39  inc     r9d
0x180010d3c  jmp     short loc_180010D03
0x180010d3e  mov     edi, [r10+rsi*8+8]
0x180010d43  test    edi, edi
0x180010d45  jz      short loc_180010D99
0x180010d47  mov     rsi, [r10+rsi*8+18h]
0x180010d4c  mov     ecx, 18h
0x180010d51  call    SafeAllocaAllocateFromHeap
0x180010d56  mov     rbx, rax
0x180010d59  test    rax, rax
0x180010d5c  jz      loc_180010DE5
0x180010d62  mov     [rax+0Ch], r15
0x180010d66  mov     [rax+14h], r15d
0x180010d6a  mov     dword ptr [rax], 18h
0x180010d70  mov     dword ptr [rax+4], 4D53414Ch
0x180010d77  mov     [rax+8], edi
0x180010d7a  test    rsi, rsi
0x180010d7d  jnz     loc_180010E21
0x180010d83  mov     [r14], rbx
0x180010d86  mov     edi, r15d
0x180010d89  mov     eax, edi
0x180010d8b  add     rsp, 48h
0x180010d8f  pop     r15
0x180010d91  pop     r14
0x180010d93  pop     rdi
0x180010d94  pop     rsi
0x180010d95  pop     rbp
0x180010d96  pop     rbx
0x180010d97  retn
0x180010d99  mov     edi, 0C00000BBh
0x180010d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010da5  lea     rax, WPP_GLOBAL_Control
0x180010dac  cmp     rcx, rax
0x180010daf  jz      short loc_180010D89
0x180010db1  test    byte ptr [rcx+1Ch], 1
0x180010db5  jz      short loc_180010D89
0x180010db7  mov     [rsp+78h+var_48], 0A4Dh
0x180010dbf  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010dc6  mov     [rsp+78h+var_50], rax
0x180010dcb  mov     [rsp+78h+var_58], 0C00000BBh
0x180010dd3  mov     rcx, [rcx+10h]
0x180010dd7  lea     r9, aStatus; "Status"
0x180010dde  call    WPP_SF_sDsd
0x180010de3  jmp     short loc_180010D89
0x180010de5  mov     edi, 0C0000017h
0x180010dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180010df1  lea     rax, WPP_GLOBAL_Control
0x180010df8  cmp     rcx, rax
0x180010dfb  jz      short loc_180010D89
0x180010dfd  test    byte ptr [rcx+1Ch], 1
0x180010e01  jz      short loc_180010D89
0x180010e03  mov     [rsp+78h+var_48], 0A55h
0x180010e0b  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010e12  mov     [rsp+78h+var_50], rax
0x180010e17  mov     [rsp+78h+var_58], 0C0000017h
0x180010e1f  jmp     short loc_180010DD3
0x180010e21  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180010e28  nop     dword ptr [rax+rax+00000000h]
0x180010e30  cmp     [rsi+r9*2+2], r15w
0x180010e36  lea     r9, [r9+1]
0x180010e3a  jnz     short loc_180010E30
0x180010e3c  lea     r9d, ds:2[r9*2]
0x180010e44  mov     r8, rsi
0x180010e47  lea     rcx, [rax+10h]
0x180010e4b  mov     edx, edi
0x180010e4d  call    LoadCurve
0x180010e52  mov     edi, eax
0x180010e54  test    eax, eax
0x180010e56  jns     loc_180010D83
0x180010e5c  mov     r9d, 0A65h
0x180010e62  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010e69  lea     rdx, aStatus; "Status"
0x180010e70  mov     ecx, eax
0x180010e72  call    DebugTraceError
0x180010e77  mov     r8d, ebp
0x180010e7a  xor     edx, edx
0x180010e7c  mov     rcx, rbx
0x180010e7f  call    MSCryptEccCloseProvider
0x180010e84  jmp     loc_180010D89
0x180010e89  mov     edi, 0C000000Dh
0x180010e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e95  lea     rax, WPP_GLOBAL_Control
0x180010e9c  cmp     rcx, rax
0x180010e9f  jz      loc_180010D89
0x180010ea5  test    byte ptr [rcx+1Ch], 1
0x180010ea9  jz      loc_180010D89
0x180010eaf  mov     [rsp+78h+var_48], 0A36h
0x180010eb7  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010ebe  mov     [rsp+78h+var_50], rax
0x180010ec3  mov     [rsp+78h+var_58], 0C000000Dh
0x180010ecb  jmp     loc_180010DD3
```
