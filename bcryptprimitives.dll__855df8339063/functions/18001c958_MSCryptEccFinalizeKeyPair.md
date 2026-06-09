# MSCryptEccFinalizeKeyPair

- ea: `0x18001c958`
- end: `0x18001cc4b`
- name: `MSCryptEccFinalizeKeyPair`
- size: `755`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001c8f0`
- `0x18006bef0`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18001c958`
- `0x18001cc54`
- `0x180022874`
- `0x1800243b8`
- `0x180056cf0`

## string_xrefs

- `0x18001c983`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18001cbb6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccFinalizeKeyPair(__int64 a1, _QWORD *a2, int a3)
{
  int v3; // ebx
  __int64 i; // rcx
  __int64 *v6; // rax
  char *v7; // rax
  int v8; // ecx
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  _BYTE *v13; // rcx
  char v14; // [rsp+20h] [rbp-58h]
  char v15; // [rsp+30h] [rbp-48h]

  v3 = a3;
  if ( !a1 || (_DWORD)a2 && (_DWORD)a2 != 24 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        228);
    return v11;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        60);
      goto LABEL_24;
    }
    goto LABEL_27;
  }
  a2 = *(_QWORD **)(a1 + 16);
  if ( !a2 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        67);
      goto LABEL_24;
    }
    goto LABEL_27;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 4 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          116);
LABEL_24:
        v13 = WPP_GLOBAL_Control;
      }
LABEL_27:
      v11 = -1073741811;
      if ( v13 == (_BYTE *)&WPP_GLOBAL_Control || (v13[28] & 1) == 0 )
        return v11;
      v15 = -21;
      v14 = 13;
LABEL_30:
      WPP_SF_sDsd(
        *((_QWORD *)v13 + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        v14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        v15);
      return v11;
    }
    a3 = 6 * i;
    v6 = qword_180084718;
    if ( !v3 )
      v6 = &qword_1800847D8;
    if ( *(_DWORD *)(a1 + 8) == LODWORD(v6[6 * i]) )
      break;
  }
  v7 = " ";
  if ( !v3 )
    v7 = " ";
  a3 = *(_DWORD *)&v7[48 * i];
  v8 = *(_DWORD *)(*a2 + 12LL);
  if ( !a3 )
  {
    if ( (unsigned int)(v8 - 14) <= 0x34 )
      goto LABEL_15;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        0,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        91);
      goto LABEL_24;
    }
    goto LABEL_27;
  }
  if ( a3 != v8 )
  {
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 613);
    goto LABEL_24;
  }
LABEL_15:
  if ( (*(_BYTE *)(a1 + 32) & 2) != 0 )
  {
    v11 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2802);
    return v11;
  }
  if ( *(_QWORD *)(a1 + 24) )
  {
LABEL_19:
    *(_DWORD *)(a1 + 32) |= 2u;
    return 0;
  }
  v9 = SymCryptEckeyAllocate(a2[1]);
  *(_QWORD *)(a1 + 24) = v9;
  if ( !v9 )
  {
    v11 = -1073741801;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v11;
    v15 = -4;
    v14 = 23;
    goto LABEL_30;
  }
  v10 = SymCryptEckeySetRandom(v3 != 0 ? 4096 : 0x2000, v9);
  if ( !v10 )
    goto LABEL_19;
  v11 = SymcryptErrorCodeToNtStatus(v10);
  DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2824);
  if ( (v11 & 0x80000000) != 0 )
  {
    SymCryptEckeyFree(*(_QWORD *)(a1 + 24));
    *(_QWORD *)(a1 + 24) = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x18001c958  push    rbx
0x18001c95a  push    rbp
0x18001c95b  push    rsi
0x18001c95c  push    rdi
0x18001c95d  push    r14
0x18001c95f  push    r15
0x18001c961  sub     rsp, 48h
0x18001c965  mov     ebx, r8d
0x18001c968  mov     rdi, rcx
0x18001c96b  test    rcx, rcx
0x18001c96e  jz      loc_18001CB88
0x18001c974  test    edx, edx
0x18001c976  jnz     loc_18001CC10
0x18001c97c  cmp     dword ptr [rcx+4], 4D534B59h
0x18001c983  lea     rbp, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c98a  mov     r15d, 0C000000Dh
0x18001c990  lea     rsi, aStatus; "Status"
0x18001c997  lea     r14, WPP_GLOBAL_Control
0x18001c99e  jnz     loc_18001CA74
0x18001c9a4  mov     rdx, [rcx+10h]
0x18001c9a8  test    rdx, rdx
0x18001c9ab  jz      loc_18001CAED
0x18001c9b1  xor     ecx, ecx
0x18001c9b3  cmp     ecx, 4
0x18001c9b6  jnb     loc_18001CAAD
0x18001c9bc  lea     r8, [rcx+rcx*2]
0x18001c9c0  add     r8, r8
0x18001c9c3  lea     r9, qword_1800847D8
0x18001c9ca  test    ebx, ebx
0x18001c9cc  lea     rax, qword_180084718
0x18001c9d3  cmovz   rax, r9
0x18001c9d7  mov     eax, [rax+r8*8]
0x18001c9db  cmp     [rdi+8], eax
0x18001c9de  jz      short loc_18001C9E4
0x18001c9e0  inc     ecx
0x18001c9e2  jmp     short loc_18001C9B3
0x18001c9e4  test    ebx, ebx
0x18001c9e6  lea     rcx, aEck2+4; " "
0x18001c9ed  lea     rax, aEcs2+4; " "
0x18001c9f4  cmovz   rax, rcx
0x18001c9f8  mov     r8d, [rax+r8*8]
0x18001c9fc  mov     rax, [rdx]
0x18001c9ff  mov     ecx, [rax+0Ch]
0x18001ca02  test    r8d, r8d
0x18001ca05  jnz     loc_18001CB3F
0x18001ca0b  lea     eax, [rcx-0Eh]
0x18001ca0e  cmp     eax, 34h ; '4'
0x18001ca11  ja      loc_18001CB61
0x18001ca17  test    byte ptr [rdi+20h], 2
0x18001ca1b  jnz     loc_18001CC1E
0x18001ca21  cmp     qword ptr [rdi+18h], 0
0x18001ca26  jnz     short loc_18001CA5E
0x18001ca28  mov     rcx, [rdx+8]
0x18001ca2c  call    SymCryptEckeyAllocate
0x18001ca31  mov     [rdi+18h], rax
0x18001ca35  test    rax, rax
0x18001ca38  jz      loc_18001CB09
0x18001ca3e  neg     ebx
0x18001ca40  mov     rdx, rax
0x18001ca43  sbb     ecx, ecx
0x18001ca45  and     ecx, 0FFFFF000h
0x18001ca4b  add     ecx, 2000h
0x18001ca51  call    SymCryptEckeySetRandom
0x18001ca56  test    eax, eax
0x18001ca58  jnz     loc_18001CBD6
0x18001ca5e  or      dword ptr [rdi+20h], 2
0x18001ca62  xor     ebx, ebx
0x18001ca64  mov     eax, ebx
0x18001ca66  add     rsp, 48h
0x18001ca6a  pop     r15
0x18001ca6c  pop     r14
0x18001ca6e  pop     rdi
0x18001ca6f  pop     rsi
0x18001ca70  pop     rbp
0x18001ca71  pop     rbx
0x18001ca72  retn
0x18001ca74  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca7b  cmp     rcx, r14
0x18001ca7e  jz      short loc_18001CAC3
0x18001ca80  test    byte ptr [rcx+1Ch], 1
0x18001ca84  jz      short loc_18001CAC3
0x18001ca86  mov     dword ptr [rsp+78h+var_48], 23Ch
0x18001ca8e  mov     rcx, [rcx+10h]
0x18001ca92  mov     r9, rsi
0x18001ca95  mov     [rsp+78h+var_50], rbp
0x18001ca9a  mov     dword ptr [rsp+78h+var_58], r15d
0x18001ca9f  call    WPP_SF_sDsd
0x18001caa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caab  jmp     short loc_18001CAC3
0x18001caad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cab4  cmp     rcx, r14
0x18001cab7  jz      short loc_18001CAC3
0x18001cab9  test    byte ptr [rcx+1Ch], 1
0x18001cabd  jnz     loc_18001CC3E
0x18001cac3  mov     ebx, 0C000000Dh
0x18001cac8  cmp     rcx, r14
0x18001cacb  jz      short loc_18001CA64
0x18001cacd  test    byte ptr [rcx+1Ch], 1
0x18001cad1  jz      short loc_18001CA64
0x18001cad3  mov     dword ptr [rsp+78h+var_48], 0AEBh
0x18001cadb  mov     [rsp+78h+var_50], rbp
0x18001cae0  mov     dword ptr [rsp+78h+var_58], r15d
0x18001cae5  mov     r9, rsi
0x18001cae8  jmp     loc_1800814EC
0x18001caed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caf4  cmp     rcx, r14
0x18001caf7  jz      short loc_18001CAC3
0x18001caf9  test    byte ptr [rcx+1Ch], 1
0x18001cafd  jz      short loc_18001CAC3
0x18001caff  mov     dword ptr [rsp+78h+var_48], 243h
0x18001cb07  jmp     short loc_18001CA8E
0x18001cb09  mov     ebx, 0C0000017h
0x18001cb0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb15  cmp     rcx, r14
0x18001cb18  jz      loc_18001CA64
0x18001cb1e  test    byte ptr [rcx+1Ch], 1
0x18001cb22  jz      loc_18001CA64
0x18001cb28  mov     dword ptr [rsp+78h+var_48], 0AFCh
0x18001cb30  mov     [rsp+78h+var_50], rbp
0x18001cb35  mov     dword ptr [rsp+78h+var_58], 0C0000017h
0x18001cb3d  jmp     short loc_18001CAE5
0x18001cb3f  cmp     r8d, ecx
0x18001cb42  jz      loc_18001CA17
0x18001cb48  mov     r9d, 265h
0x18001cb4e  mov     r8, rbp
0x18001cb51  mov     rdx, rsi
0x18001cb54  mov     ecx, r15d
0x18001cb57  call    DebugTraceError
0x18001cb5c  jmp     loc_18001CAA4
0x18001cb61  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb68  cmp     rcx, r14
0x18001cb6b  jz      loc_18001CAC3
0x18001cb71  test    byte ptr [rcx+1Ch], 1
0x18001cb75  jz      loc_18001CAC3
0x18001cb7b  mov     dword ptr [rsp+78h+var_48], 25Bh
0x18001cb83  jmp     loc_18001CA8E
0x18001cb88  mov     ebx, 0C000000Dh
0x18001cb8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb94  lea     r14, WPP_GLOBAL_Control
0x18001cb9b  cmp     rcx, r14
0x18001cb9e  jz      loc_18001CA64
0x18001cba4  test    byte ptr [rcx+1Ch], 1
0x18001cba8  jz      loc_18001CA64
0x18001cbae  mov     dword ptr [rsp+78h+var_48], 0AE4h
0x18001cbb6  lea     rbp, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001cbbd  mov     [rsp+78h+var_50], rbp
0x18001cbc2  lea     r9, aStatus; "Status"
0x18001cbc9  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18001cbd1  jmp     loc_1800814EC
0x18001cbd6  mov     ecx, eax
0x18001cbd8  call    SymcryptErrorCodeToNtStatus
0x18001cbdd  mov     ecx, eax
0x18001cbdf  mov     r9d, 0B08h
0x18001cbe5  mov     r8, rbp
0x18001cbe8  mov     rdx, rsi
0x18001cbeb  mov     ebx, eax
0x18001cbed  call    DebugTraceError
0x18001cbf2  test    ebx, ebx
0x18001cbf4  jns     loc_18001CA64
0x18001cbfa  mov     rcx, [rdi+18h]
0x18001cbfe  call    SymCryptEckeyFree
0x18001cc03  mov     qword ptr [rdi+18h], 0
0x18001cc0b  jmp     loc_18001CA64
0x18001cc10  cmp     edx, 18h
0x18001cc13  jnz     loc_18001CB88
0x18001cc19  jmp     loc_18001C97C
0x18001cc1e  mov     r9d, 0AF2h
0x18001cc24  mov     r8, rbp
0x18001cc27  mov     rdx, rsi
0x18001cc2a  mov     ecx, 0C0000008h
0x18001cc2f  mov     ebx, 0C0000008h
0x18001cc34  call    DebugTraceError
0x18001cc39  jmp     loc_18001CA64
0x18001cc3e  mov     dword ptr [rsp+78h+var_48], 274h
0x18001cc46  jmp     loc_18001CA8E
0x1800814ec  mov     rcx, [rcx+10h]
0x1800814f0  call    WPP_SF_sDsd
0x1800814f5  nop
0x1800814f6  jmp     loc_18001CA64
```
