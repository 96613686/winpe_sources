# MSCryptDecrypt

- ea: `0x18000d630`
- end: `0x18000dca0`
- name: `MSCryptDecrypt`
- size: `1648`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000c860`
- `0x180066428`

## callees

- `0x18000c7d0`
- `0x18000d630`
- `0x18000dca8`
- `0x18000e318`
- `0x18000ecb0`
- `0x18000ee60`
- `0x180054280`

## string_xrefs

- `0x18000d86a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d90a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d94e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000d9a5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000da0d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000da4f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000da92`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000dad9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000dbff`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000dc1e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000dc50`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptDecrypt(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        __int64 a4,
        _QWORD *a5,
        int a6,
        unsigned __int64 a7,
        unsigned int a8,
        _DWORD *a9,
        int a10)
{
  __int64 v10; // r11
  unsigned __int64 v11; // rbx
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // eax
  int v15; // edx
  unsigned int v16; // ebx
  int v17; // r8d
  __int64 v19; // rdi
  int v20; // edx
  int v21; // r8d
  unsigned __int64 v22; // rdx

  v10 = a3;
  v11 = a2;
  if ( !a1 || *(_DWORD *)(a1 + 4) != 1297306443 )
  {
    v16 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        30);
    return v16;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 12) - 4) > 1 && *(_DWORD *)(a1 + 8) != 65545 && a4 )
  {
    v16 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        40);
    return v16;
  }
  LODWORD(v12) = a10;
  if ( (a10 & 0xFFFFFEB8) != 0
    || (v13 = *(_QWORD *)(a1 + 32),
        LODWORD(a2) = a10 & ~*(_DWORD *)(v13 + 36),
        ((unsigned __int8)a10 & (unsigned __int8)~*(_BYTE *)(v13 + 36) & 0x40) != 0) )
  {
    v16 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a10,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        51);
    return v16;
  }
  if ( !a9 )
  {
    v16 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 1082);
    return v16;
  }
  v14 = *(_DWORD *)(a1 + 8);
  if ( v14 == 65543 )
  {
LABEL_10:
    v16 = MSBlockDecrypt(a1, a4, (_DWORD)a5, a6, v11, v10, a7, a8, (__int64)a9, a10);
    if ( (v16 & 0x80000000) != 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        v17,
        (unsigned int)"Status",
        v16,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        192);
    }
    return v16;
  }
  if ( v14 != 65545 )
  {
    v22 = 0x180000000uLL;
    switch ( v14 )
    {
      case 65537:
        *a9 = v10;
        if ( !a7 )
          return 0;
        if ( (unsigned int)v10 > a8 )
          return (unsigned int)-1073741789;
        if ( !(_DWORD)v10 )
          return 0;
        if ( v11 && !a5 && v10 + v11 >= v11 && v10 + a7 >= a7 )
        {
          SymCryptRc4Crypt(a1 + 320, v11, a7, v10);
          return 0;
        }
        v16 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            0x80000000,
            a7,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            96);
        return v16;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
      case 65542:
        goto LABEL_10;
      case 65544:
        if ( (a10 & 0xFFFFFFBF) != 0
          || (LODWORD(v12) = *(_DWORD *)(a1 + 20), !(_DWORD)v12)
          || (LODWORD(v22) = (unsigned int)v10 % (unsigned int)v12) != 0
          || !v11
          || (LODWORD(v12) = (_DWORD)a5, !a5)
          || a6 != 8
          || v10 + v11 < v11
          || (LODWORD(v22) = a8, a7 + a8 < a7) )
        {
          v16 = -1073741811;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v22,
              v12,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
              213);
          return v16;
        }
        *a9 = v10;
        if ( !a7 )
          return 0;
        if ( (unsigned int)v10 <= a8 )
        {
          SymCryptXtsAesDecrypt(a1 + 128, *(_DWORD *)(a1 + 20), *a5, v11, a7, v10);
          return 0;
        }
        break;
      default:
        v16 = -1073741637;
        DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 1267);
        return v16;
    }
    return (unsigned int)-1073741789;
  }
  *a9 = v10;
  if ( v11 && !a7 )
    return 0;
  if ( (unsigned int)v10 > a8 )
    return (unsigned int)-1073741789;
  if ( a5 || a6 || a10 || v10 + v11 < v11 || v10 + a7 < a7 )
  {
    v16 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a10,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        132);
    return v16;
  }
  if ( !a4
    || *(_DWORD *)a4 < 0x58u
    || *(_DWORD *)(a4 + 4) != 1
    || (v12 = *(_QWORD *)(a4 + 8)) == 0
    || (LODWORD(a2) = *(_DWORD *)(a4 + 80), (a2 & 0xFFFFFFFC) != 0)
    || (a2 & 3) != 0 && !*(_QWORD *)(a4 + 56)
    || *(_DWORD *)(a4 + 16) != 12
    || (v19 = *(_QWORD *)(a4 + 40)) == 0
    || *(_DWORD *)(a4 + 48) != 16
    || (_DWORD)a2 )
  {
    v16 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        v12,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        146);
    return v16;
  }
  if ( (unsigned int)SymCryptChaCha20Poly1305Decrypt(
                       (int)a1 + 60,
                       *(_DWORD *)(a1 + 56),
                       v12,
                       12,
                       *(_QWORD *)(a4 + 24),
                       *(unsigned int *)(a4 + 32),
                       v11,
                       a7,
                       v10,
                       v19,
                       16) )
  {
    v16 = -1073700862;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        v21,
        (unsigned int)"Status",
        2,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        165);
    return v16;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d630  mov     [rsp+arg_0], rbx
0x18000d635  push    rdi
0x18000d636  sub     rsp, 60h
0x18000d63a  mov     r11d, r8d
0x18000d63d  mov     r10, r9
0x18000d640  mov     rbx, rdx
0x18000d643  test    rcx, rcx
0x18000d646  jz      loc_18000D920
0x18000d64c  cmp     dword ptr [rcx+4], 4D53534Bh
0x18000d653  jnz     loc_18000D920
0x18000d659  mov     eax, [rcx+0Ch]
0x18000d65c  sub     eax, 4
0x18000d65f  cmp     eax, 1
0x18000d662  jbe     short loc_18000D676
0x18000d664  cmp     dword ptr [rcx+8], 10009h
0x18000d66b  jz      short loc_18000D676
0x18000d66d  test    r9, r9
0x18000d670  jnz     loc_18000DAAB
0x18000d676  mov     r8d, [rsp+68h+arg_48]
0x18000d67e  test    r8d, 0FFFFFEB8h
0x18000d685  jnz     loc_18000D9DF
0x18000d68b  mov     rax, [rcx+20h]
0x18000d68f  mov     edx, [rax+24h]
0x18000d692  not     edx
0x18000d694  and     edx, r8d
0x18000d697  test    dl, 40h
0x18000d69a  jnz     loc_18000D9DF
0x18000d6a0  mov     r9, [rsp+68h+arg_40]
0x18000d6a8  test    r9, r9
0x18000d6ab  jz      loc_18000DC18
0x18000d6b1  mov     eax, [rcx+8]
0x18000d6b4  cmp     eax, 10007h
0x18000d6b9  jnz     short loc_18000D717
0x18000d6bb  mov     eax, [rsp+68h+arg_38]; jumptable 000000018000D8A2 cases 65538-65542
0x18000d6c2  mov     rdx, r10
0x18000d6c5  mov     dword ptr [rsp+68h+var_20], r8d
0x18000d6ca  mov     r8, [rsp+68h+arg_20]
0x18000d6d2  mov     [rsp+68h+var_28], r9
0x18000d6d7  mov     r9d, [rsp+68h+arg_28]
0x18000d6df  mov     dword ptr [rsp+68h+var_30], eax
0x18000d6e3  mov     rax, [rsp+68h+arg_30]
0x18000d6eb  mov     [rsp+68h+var_38], rax
0x18000d6f0  mov     dword ptr [rsp+68h+var_40], r11d
0x18000d6f5  mov     [rsp+68h+var_48], rbx
0x18000d6fa  call    MSBlockDecrypt
0x18000d6ff  mov     ebx, eax
0x18000d701  test    eax, eax
0x18000d703  js      loc_18000DA26
0x18000d709  mov     eax, ebx
0x18000d70b  mov     rbx, [rsp+68h+arg_0]
0x18000d710  add     rsp, 60h
0x18000d714  pop     rdi
0x18000d715  retn
0x18000d717  cmp     eax, 10009h
0x18000d71c  jnz     loc_18000D883
0x18000d722  mov     [r9], r11d
0x18000d725  mov     r9, [rsp+68h+arg_30]
0x18000d72d  test    rbx, rbx
0x18000d730  jnz     loc_18000DC72
0x18000d736  cmp     r11d, [rsp+68h+arg_38]
0x18000d73e  ja      loc_18000DC40
0x18000d744  cmp     [rsp+68h+arg_20], 0
0x18000d74d  jnz     loc_18000D977
0x18000d753  cmp     [rsp+68h+arg_28], 0
0x18000d75b  jnz     loc_18000D977
0x18000d761  test    r8d, r8d
0x18000d764  jnz     loc_18000D977
0x18000d76a  lea     rax, [r11+rbx]
0x18000d76e  cmp     rax, rbx
0x18000d771  jb      loc_18000D977
0x18000d777  lea     rax, [r11+r9]
0x18000d77b  cmp     rax, r9
0x18000d77e  jb      loc_18000D977
0x18000d784  test    r10, r10
0x18000d787  jz      loc_18000DA64
0x18000d78d  cmp     dword ptr [r10], 58h ; 'X'
0x18000d791  jb      loc_18000DA64
0x18000d797  cmp     dword ptr [r10+4], 1
0x18000d79c  jnz     loc_18000DA64
0x18000d7a2  mov     r8, [r10+8]
0x18000d7a6  test    r8, r8
0x18000d7a9  jz      loc_18000DA64
0x18000d7af  mov     edx, [r10+50h]
0x18000d7b3  test    edx, 0FFFFFFFCh
0x18000d7b9  jnz     loc_18000DA64
0x18000d7bf  test    dl, 3
0x18000d7c2  jnz     loc_18000DB52
0x18000d7c8  cmp     dword ptr [r10+10h], 0Ch
0x18000d7cd  jnz     loc_18000DA64
0x18000d7d3  mov     rdi, [r10+28h]
0x18000d7d7  test    rdi, rdi
0x18000d7da  jz      loc_18000DA64
0x18000d7e0  cmp     dword ptr [r10+30h], 10h
0x18000d7e5  jnz     loc_18000DA64
0x18000d7eb  test    edx, edx
0x18000d7ed  jnz     loc_18000DA64
0x18000d7f3  mov     eax, [r10+20h]
0x18000d7f7  mov     edx, [rcx+38h]
0x18000d7fa  add     rcx, 3Ch ; '<'
0x18000d7fe  mov     [rsp+68h+var_18], 10h
0x18000d807  mov     [rsp+68h+var_20], rdi
0x18000d80c  mov     [rsp+68h+var_28], r11
0x18000d811  mov     [rsp+68h+var_30], r9
0x18000d816  mov     r9d, 0Ch
0x18000d81c  mov     [rsp+68h+var_38], rbx
0x18000d821  mov     [rsp+68h+var_40], rax
0x18000d826  mov     rax, [r10+18h]
0x18000d82a  mov     [rsp+68h+var_48], rax
0x18000d82f  call    SymCryptChaCha20Poly1305Decrypt
0x18000d834  test    eax, eax
0x18000d836  jz      loc_18000D9CF
0x18000d83c  mov     ebx, 0C000A002h
0x18000d841  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d848  lea     rax, WPP_GLOBAL_Control
0x18000d84f  cmp     rcx, rax
0x18000d852  jz      loc_18000D709
0x18000d858  test    byte ptr [rcx+1Ch], 1
0x18000d85c  jz      loc_18000D709
0x18000d862  mov     dword ptr [rsp+68h+var_38], 4A5h
0x18000d86a  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d871  mov     [rsp+68h+var_40], rax
0x18000d876  mov     dword ptr [rsp+68h+var_48], 0C000A002h
0x18000d87e  jmp     loc_18000D962
0x18000d883  add     eax, 0FFFEFFFFh; switch 8 cases
0x18000d888  cmp     eax, 7
0x18000d88b  ja      def_18000D8A2; jumptable 000000018000D8A2 default case, case 65543
0x18000d891  lea     rdx, cs:180000000h
0x18000d898  mov     eax, ds:(jpt_18000D8A2 - 180000000h)[rdx+rax*4]
0x18000d89f  add     rax, rdx
0x18000d8a2  jmp     rax; switch jump
0x18000d8a8  test    r8d, 0FFFFFFBFh; jumptable 000000018000D8A2 case 65544
0x18000d8af  jnz     short loc_18000D8DC
0x18000d8b1  mov     r8d, [rcx+14h]
0x18000d8b5  test    r8d, r8d
0x18000d8b8  jz      short loc_18000D8DC
0x18000d8ba  xor     edx, edx
0x18000d8bc  mov     eax, r11d
0x18000d8bf  div     r8d
0x18000d8c2  test    edx, edx
0x18000d8c4  jnz     short loc_18000D8DC
0x18000d8c6  test    rbx, rbx
0x18000d8c9  jz      short loc_18000D8DC
0x18000d8cb  mov     r8, [rsp+68h+arg_20]
0x18000d8d3  test    r8, r8
0x18000d8d6  jnz     loc_18000DB62
0x18000d8dc  mov     ebx, 0C000000Dh
0x18000d8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8e8  lea     rax, WPP_GLOBAL_Control
0x18000d8ef  cmp     rcx, rax
0x18000d8f2  jz      loc_18000D709
0x18000d8f8  test    byte ptr [rcx+1Ch], 1
0x18000d8fc  jz      loc_18000D709
0x18000d902  mov     dword ptr [rsp+68h+var_38], 4D5h
0x18000d90a  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d911  mov     [rsp+68h+var_40], rax
0x18000d916  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000d91e  jmp     short loc_18000D962
0x18000d920  mov     ebx, 0C0000008h
0x18000d925  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d92c  lea     rax, WPP_GLOBAL_Control
0x18000d933  cmp     rcx, rax
0x18000d936  jz      loc_18000D709
0x18000d93c  test    byte ptr [rcx+1Ch], 1
0x18000d940  jz      loc_18000D709
0x18000d946  mov     dword ptr [rsp+68h+var_38], 41Eh
0x18000d94e  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d955  mov     [rsp+68h+var_40], rax
0x18000d95a  mov     dword ptr [rsp+68h+var_48], 0C0000008h
0x18000d962  mov     rcx, [rcx+10h]
0x18000d966  lea     r9, aStatus; "Status"
0x18000d96d  call    WPP_SF_sDsd
0x18000d972  jmp     loc_18000D709
0x18000d977  mov     ebx, 0C000000Dh
0x18000d97c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d983  lea     rax, WPP_GLOBAL_Control
0x18000d98a  cmp     rcx, rax
0x18000d98d  jz      loc_18000D709
0x18000d993  test    byte ptr [rcx+1Ch], 1
0x18000d997  jz      loc_18000D709
0x18000d99d  mov     dword ptr [rsp+68h+var_38], 484h
0x18000d9a5  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000d9ac  mov     [rsp+68h+var_40], rax
0x18000d9b1  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000d9b9  jmp     short loc_18000D962
0x18000d9bb  mov     r8, [rsp+68h+arg_30]; jumptable 000000018000D8A2 case 65537
0x18000d9c3  mov     [r9], r11d
0x18000d9c6  test    r8, r8
0x18000d9c9  jnz     loc_18000DAF2
0x18000d9cf  xor     ebx, ebx
0x18000d9d1  mov     eax, ebx
0x18000d9d3  mov     rbx, [rsp+68h+arg_0]
0x18000d9d8  add     rsp, 60h
0x18000d9dc  pop     rdi
0x18000d9dd  retn
0x18000d9df  mov     ebx, 0C000000Dh
0x18000d9e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9eb  lea     rax, WPP_GLOBAL_Control
0x18000d9f2  cmp     rcx, rax
0x18000d9f5  jz      loc_18000D709
0x18000d9fb  test    byte ptr [rcx+1Ch], 1
0x18000d9ff  jz      loc_18000D709
0x18000da05  mov     dword ptr [rsp+68h+var_38], 433h
0x18000da0d  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da14  mov     [rsp+68h+var_40], rax
0x18000da19  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000da21  jmp     loc_18000D962
0x18000da26  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da2d  lea     rax, WPP_GLOBAL_Control
0x18000da34  cmp     rcx, rax
0x18000da37  jz      loc_18000D709
0x18000da3d  test    byte ptr [rcx+1Ch], 1
0x18000da41  jz      loc_18000D709
0x18000da47  mov     dword ptr [rsp+68h+var_38], 4C0h
0x18000da4f  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da56  mov     [rsp+68h+var_40], rax
0x18000da5b  mov     dword ptr [rsp+68h+var_48], ebx
0x18000da5f  jmp     loc_18000D962
0x18000da64  mov     ebx, 0C000000Dh
0x18000da69  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da70  lea     rax, WPP_GLOBAL_Control
0x18000da77  cmp     rcx, rax
0x18000da7a  jz      loc_18000D709
0x18000da80  test    byte ptr [rcx+1Ch], 1
0x18000da84  jz      loc_18000D709
0x18000da8a  mov     dword ptr [rsp+68h+var_38], 492h
0x18000da92  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000da99  mov     [rsp+68h+var_40], rax
0x18000da9e  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000daa6  jmp     loc_18000D962
0x18000daab  mov     ebx, 0C000000Dh
0x18000dab0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dab7  lea     rax, WPP_GLOBAL_Control
0x18000dabe  cmp     rcx, rax
0x18000dac1  jz      loc_18000D709
0x18000dac7  test    byte ptr [rcx+1Ch], 1
0x18000dacb  jz      loc_18000D709
0x18000dad1  mov     dword ptr [rsp+68h+var_38], 428h
0x18000dad9  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dae0  mov     [rsp+68h+var_40], rax
0x18000dae5  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000daed  jmp     loc_18000D962
0x18000daf2  cmp     r11d, [rsp+68h+arg_38]
0x18000dafa  ja      loc_18000DC40
0x18000db00  test    r11d, r11d
0x18000db03  jz      loc_18000D9CF
0x18000db09  test    rbx, rbx
0x18000db0c  jz      loc_18000DBD1
0x18000db12  cmp     [rsp+68h+arg_20], 0
0x18000db1b  jnz     loc_18000DBD1
0x18000db21  lea     rax, [r11+rbx]
0x18000db25  mov     r9, r11
0x18000db28  cmp     rax, rbx
0x18000db2b  jb      loc_18000DBD1
0x18000db31  lea     rax, [r11+r8]
0x18000db35  cmp     rax, r8
0x18000db38  jb      loc_18000DBD1
0x18000db3e  add     rcx, 140h
0x18000db45  mov     rdx, rbx
0x18000db48  call    SymCryptRc4Crypt
0x18000db4d  jmp     loc_18000D9CF
0x18000db52  cmp     qword ptr [r10+38h], 0
0x18000db57  jnz     loc_18000D7C8
0x18000db5d  jmp     loc_18000DA64
0x18000db62  cmp     [rsp+68h+arg_28], 8
0x18000db6a  jnz     loc_18000D8DC
0x18000db70  lea     rax, [r11+rbx]
0x18000db74  cmp     rax, rbx
0x18000db77  jb      loc_18000D8DC
0x18000db7d  mov     r10, [rsp+68h+arg_30]
0x18000db85  mov     edx, [rsp+68h+arg_38]
0x18000db8c  lea     rax, [r10+rdx]
0x18000db90  cmp     rax, r10
0x18000db93  jb      loc_18000D8DC
0x18000db99  mov     [r9], r11d
0x18000db9c  test    r10, r10
0x18000db9f  jz      loc_18000D9CF
0x18000dba5  cmp     r11d, edx
0x18000dba8  ja      loc_18000DC40
0x18000dbae  mov     edx, [rcx+14h]
0x18000dbb1  mov     r9, rbx
0x18000dbb4  mov     r8, [r8]
0x18000dbb7  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18000dbbb  mov     [rsp+68h+var_40], r11
0x18000dbc0  mov     [rsp+68h+var_48], r10
0x18000dbc5  call    SymCryptXtsAesDecrypt
0x18000dbca  xor     ebx, ebx
0x18000dbcc  jmp     loc_18000D709
0x18000dbd1  mov     ebx, 0C000000Dh
0x18000dbd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbdd  lea     rax, WPP_GLOBAL_Control
0x18000dbe4  cmp     rcx, rax
0x18000dbe7  jz      loc_18000D709
0x18000dbed  test    byte ptr [rcx+1Ch], 1
0x18000dbf1  jz      loc_18000D709
0x18000dbf7  mov     dword ptr [rsp+68h+var_38], 460h
0x18000dbff  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dc06  mov     [rsp+68h+var_40], rax
0x18000dc0b  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000dc13  jmp     loc_18000D962
0x18000dc18  mov     r9d, 43Ah
  ... truncated ...
```
