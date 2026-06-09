# MSCryptEncrypt

- ea: `0x18000b420`
- end: `0x18000b8b0`
- name: `MSCryptEncrypt`
- size: `1168`
- prototype: `__int64 __fastcall(__int64, _BYTE *, unsigned int, __int64, _QWORD *, int, unsigned __int64, unsigned int, unsigned int *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000afd0`

## callees

- `0x18000adc0`
- `0x18000b420`
- `0x18000b8b8`
- `0x18000ecb0`
- `0x18000ee60`
- `0x1800542c8`
- `0x180071200`

## string_xrefs

- `0x18000b66a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b6d3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b740`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b7a4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b829`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptEncrypt(
        __int64 a1,
        _BYTE *a2,
        unsigned int a3,
        __int64 a4,
        _QWORD *a5,
        int a6,
        unsigned __int64 a7,
        unsigned int a8,
        unsigned int *a9,
        int a10)
{
  _BYTE *v11; // r10
  int v13; // r9d
  int v14; // eax
  int v15; // edx
  unsigned int v16; // ebx
  int v17; // r8d
  unsigned __int64 v19; // rdx
  _BYTE *v20; // rbx
  __int64 v21; // r8
  __int64 v22; // r9
  char v23; // cl
  char v24; // al
  char v25; // al
  _QWORD *v26; // rcx
  unsigned int v27; // r9d
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 v30; // rsi
  __int64 v31; // rax
  int v32; // edx
  __int64 v33; // r10
  __int64 v34; // r11
  __int64 v35; // r8
  __int64 v36; // rbx
  char v37; // [rsp+30h] [rbp-38h]

  v11 = a2;
  if ( !a1 || *(_DWORD *)(a1 + 4) != 1297306443 )
    return (unsigned int)-1073741816;
  v13 = *(_DWORD *)(a1 + 12);
  if ( (unsigned int)(v13 - 4) > 1 && *(_DWORD *)(a1 + 8) != 65545 && a4 )
  {
    v16 = -1073741811;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v16;
    v37 = 37;
LABEL_32:
    WPP_SF_sDsd(
      v26[2],
      (_DWORD)a2,
      a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
      v37);
    return v16;
  }
  LODWORD(a2) = a10;
  if ( (a10 & 0xFFFFFF98) != 0
    || ((unsigned __int8)a10 & (unsigned __int8)~*(_BYTE *)(*(_QWORD *)(a1 + 32) + 36LL) & 0x40) != 0 )
  {
    v16 = -1073741811;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v16;
    v37 = 48;
    goto LABEL_32;
  }
  if ( !a9 )
  {
    v28 = 825;
LABEL_58:
    v16 = -1073741811;
    v29 = 3221225485LL;
LABEL_49:
    DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", v28);
    return v16;
  }
  if ( (a10 & 0x20) != 0 && (*(_DWORD *)(a1 + 8) != 65538 || v13 != 5) )
  {
    v28 = 833;
    goto LABEL_58;
  }
  v14 = *(_DWORD *)(a1 + 8);
  if ( v14 != 65543 )
  {
    switch ( v14 )
    {
      case 65537:
        v19 = a7;
        *a9 = a3;
        if ( !a7 )
          return 0;
        if ( a3 > a8 )
          return (unsigned int)-1073741789;
        if ( !a3 )
          return 0;
        if ( v11 )
        {
          if ( !a5 )
          {
            v20 = &v11[a3];
            if ( v20 >= v11 && a7 + a3 >= a7 )
            {
              v21 = *(unsigned __int8 *)(a1 + 576);
              for ( LOBYTE(v22) = *(_BYTE *)(a1 + 577); v11 < v20; v21 = (unsigned __int8)(v21 + 1) )
              {
                v23 = *(_BYTE *)(v21 + a1 + 320);
                ++v19;
                v22 = (unsigned __int8)(v23 + v22);
                v24 = *(_BYTE *)(v22 + a1 + 320);
                *(_BYTE *)(v21 + a1 + 320) = v24;
                *(_BYTE *)(v22 + a1 + 320) = v23;
                v25 = *v11++ ^ *(_BYTE *)((unsigned __int8)(v23 + v24) + a1 + 320);
                *(_BYTE *)(v19 - 1) = v25;
              }
              *(_BYTE *)(a1 + 576) = v21;
              *(_BYTE *)(a1 + 577) = v22;
              return 0;
            }
          }
        }
        v16 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a7,
            a3,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            103);
          return 3221225485LL;
        }
        return v16;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
      case 65542:
        goto LABEL_11;
      case 65544:
        if ( (a10 & 0xFFFFFFBF) == 0
          && (v27 = *(_DWORD *)(a1 + 20)) != 0
          && (LODWORD(a2) = a3 % v27) == 0
          && v11
          && a5
          && a6 == 8
          && &v11[a3] >= v11
          && (LODWORD(a2) = a8, a7 + a8 >= a7) )
        {
          *a9 = a3;
          if ( !a7 )
            return 0;
          if ( a3 > a8 )
          {
            return (unsigned int)-1073741789;
          }
          else
          {
            SymCryptXtsAesEncrypt(a1 + 128, *(_DWORD *)(a1 + 20), *a5, (_DWORD)v11, a7, a3);
            return 0;
          }
        }
        else
        {
          v16 = -1073741811;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)a2,
              a3,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
              222);
            return 3221225485LL;
          }
        }
        return v16;
      case 65545:
        *a9 = a3;
        if ( v11 && !a7 )
          return 0;
        if ( a3 > a8 )
          return (unsigned int)-1073741789;
        if ( a5 || a6 || a10 || (v30 = a3, &v11[a3] < v11) || a3 + a7 < a7 )
        {
          v28 = 907;
          goto LABEL_58;
        }
        v31 = validateAuthCipherModeInfo(a4);
        if ( !v31
          || (v35 = *(_QWORD *)(v31 + 8)) == 0
          || *(_DWORD *)(v31 + 16) != 12
          || (v36 = *(_QWORD *)(v31 + 40)) == 0
          || *(_DWORD *)(v31 + 48) != 16
          || *(_DWORD *)(v31 + 80) != v32 )
        {
          v28 = 921;
          goto LABEL_58;
        }
        if ( !(unsigned int)SymCryptChaCha20Poly1305Encrypt(
                              (int)v34 + 60,
                              *(_DWORD *)(v34 + 56),
                              v35,
                              12,
                              *(_QWORD *)(v31 + 24),
                              *(unsigned int *)(v31 + 32),
                              v33,
                              a7,
                              v30,
                              v36,
                              16) )
          return 0;
        v16 = -1073741174;
        v28 = 940;
        v29 = 3221226122LL;
        break;
      default:
        v16 = -1073741637;
        v28 = 1021;
        v29 = 3221225659LL;
        goto LABEL_49;
    }
    goto LABEL_49;
  }
LABEL_11:
  v16 = MSBlockEncrypt(a1, a4, (_DWORD)a5, a6, (__int64)v11, a3, a7, a8, (__int64)a9, a10 & 1, a10);
  if ( (v16 & 0x80000000) == 0
    || WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    return v16;
  }
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v15,
    v17,
    (unsigned int)"Status",
    v16,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
    200);
  return v16;
}

```

## disassembly

```asm
0x18000b420  mov     [rsp+arg_0], rbx
0x18000b425  mov     [rsp+arg_8], rsi
0x18000b42a  push    rdi
0x18000b42b  sub     rsp, 60h
0x18000b42f  mov     rbx, r9
0x18000b432  mov     r10, rdx
0x18000b435  mov     r11, rcx
0x18000b438  test    rcx, rcx
0x18000b43b  jz      loc_18000B636
0x18000b441  cmp     dword ptr [rcx+4], 4D53534Bh
0x18000b448  jnz     loc_18000B636
0x18000b44e  mov     r9d, [rcx+0Ch]
0x18000b452  lea     eax, [r9-4]
0x18000b456  cmp     eax, 1
0x18000b459  jbe     short loc_18000B46D
0x18000b45b  cmp     dword ptr [rcx+8], 10009h
0x18000b462  jz      short loc_18000B46D
0x18000b464  test    rbx, rbx
0x18000b467  jnz     loc_18000B7B9
0x18000b46d  mov     edx, [rsp+68h+arg_48]
0x18000b474  test    edx, 0FFFFFF98h
0x18000b47a  jnz     loc_18000B6A5
0x18000b480  mov     rax, [rcx+20h]
0x18000b484  mov     ecx, [rax+24h]
0x18000b487  not     ecx
0x18000b489  and     ecx, edx
0x18000b48b  test    cl, 40h
0x18000b48e  jnz     loc_18000B6A5
0x18000b494  mov     rcx, [rsp+68h+arg_40]
0x18000b49c  test    rcx, rcx
0x18000b49f  jz      loc_18000B80E
0x18000b4a5  test    dl, 20h
0x18000b4a8  jnz     loc_18000B841
0x18000b4ae  mov     eax, [r11+8]
0x18000b4b2  cmp     eax, 10007h
0x18000b4b7  jnz     short loc_18000B525
0x18000b4b9  mov     r9d, [rsp+68h+arg_28]; jumptable 000000018000B545 cases 65538-65542
0x18000b4c1  mov     eax, edx
0x18000b4c3  mov     dword ptr [rsp+68h+var_18], edx
0x18000b4c7  and     eax, 1
0x18000b4ca  mov     dword ptr [rsp+68h+var_20], eax
0x18000b4ce  mov     rdx, rbx
0x18000b4d1  mov     eax, [rsp+68h+arg_38]
0x18000b4d8  mov     [rsp+68h+var_28], rcx
0x18000b4dd  mov     rcx, r11
0x18000b4e0  mov     dword ptr [rsp+68h+var_30], eax
0x18000b4e4  mov     rax, [rsp+68h+arg_30]
0x18000b4ec  mov     [rsp+68h+var_38], rax
0x18000b4f1  mov     dword ptr [rsp+68h+var_40], r8d
0x18000b4f6  mov     r8, [rsp+68h+arg_20]
0x18000b4fe  mov     [rsp+68h+var_48], r10
0x18000b503  call    MSBlockEncrypt
0x18000b508  mov     ebx, eax
0x18000b50a  test    eax, eax
0x18000b50c  js      loc_18000B77B
0x18000b512  mov     eax, ebx
0x18000b514  mov     rbx, [rsp+68h+arg_0]
0x18000b519  mov     rsi, [rsp+68h+arg_8]
0x18000b51e  add     rsp, 60h
0x18000b522  pop     rdi
0x18000b523  retn
0x18000b525  add     eax, 0FFFEFFFFh; switch 9 cases
0x18000b52a  cmp     eax, 8
0x18000b52d  ja      def_18000B545; jumptable 000000018000B545 default case, case 65543
0x18000b533  lea     r9, cs:180000000h
0x18000b53a  mov     eax, ds:(jpt_18000B545 - 180000000h)[r9+rax*4]
0x18000b542  add     rax, r9
0x18000b545  jmp     rax; switch jump
0x18000b54b  mov     rdx, [rsp+68h+arg_30]; jumptable 000000018000B545 case 65537
0x18000b553  mov     [rcx], r8d
0x18000b556  test    rdx, rdx
0x18000b559  jz      loc_18000B621
0x18000b55f  cmp     r8d, [rsp+68h+arg_38]
0x18000b567  ja      loc_18000B85E
0x18000b56d  test    r8d, r8d
0x18000b570  jz      loc_18000B621
0x18000b576  test    r10, r10
0x18000b579  jz      loc_18000B640
0x18000b57f  cmp     [rsp+68h+arg_20], 0
0x18000b588  jnz     loc_18000B640
0x18000b58e  mov     eax, r8d
0x18000b591  lea     rbx, [rax+r10]
0x18000b595  cmp     rbx, r10
0x18000b598  jb      loc_18000B640
0x18000b59e  add     rax, rdx
0x18000b5a1  cmp     rax, rdx
0x18000b5a4  jb      loc_18000B640
0x18000b5aa  movzx   r8d, byte ptr [r11+240h]
0x18000b5b2  movzx   r9d, byte ptr [r11+241h]
0x18000b5ba  cmp     r10, rbx
0x18000b5bd  jnb     short loc_18000B613
0x18000b5bf  nop
0x18000b5c0  movzx   ecx, byte ptr [r8+r11+140h]
0x18000b5c9  lea     rdx, [rdx+1]
0x18000b5cd  lea     rax, [rcx+r9]
0x18000b5d1  movzx   r9d, al
0x18000b5d5  movzx   eax, byte ptr [r9+r11+140h]
0x18000b5de  mov     [r8+r11+140h], al
0x18000b5e6  add     rax, rcx
0x18000b5e9  mov     [r9+r11+140h], cl
0x18000b5f1  movzx   ecx, al
0x18000b5f4  movzx   eax, byte ptr [rcx+r11+140h]
0x18000b5fd  xor     al, [r10]
0x18000b600  inc     r10
0x18000b603  mov     [rdx-1], al
0x18000b606  lea     rax, [r8+1]
0x18000b60a  movzx   r8d, al
0x18000b60e  cmp     r10, rbx
0x18000b611  jb      short loc_18000B5C0
0x18000b613  mov     [r11+240h], r8b
0x18000b61a  mov     [r11+241h], r9b
0x18000b621  xor     ebx, ebx
0x18000b623  mov     eax, ebx
0x18000b625  mov     rbx, [rsp+68h+arg_0]
0x18000b62a  mov     rsi, [rsp+68h+arg_8]
0x18000b62f  add     rsp, 60h
0x18000b633  pop     rdi
0x18000b634  retn
0x18000b636  mov     ebx, 0C0000008h
0x18000b63b  jmp     loc_18000B512
0x18000b640  mov     ebx, 0C000000Dh
0x18000b645  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b64c  lea     rax, WPP_GLOBAL_Control
0x18000b653  cmp     rcx, rax
0x18000b656  jz      loc_18000B512
0x18000b65c  test    byte ptr [rcx+1Ch], 1
0x18000b660  jz      loc_18000B512
0x18000b666  mov     rcx, [rcx+10h]
0x18000b66a  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b671  mov     dword ptr [rsp+68h+var_38], 367h
0x18000b679  lea     r9, aStatus; "Status"
0x18000b680  mov     [rsp+68h+var_40], rax
0x18000b685  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000b68d  call    WPP_SF_sDsd
0x18000b692  mov     eax, ebx
0x18000b694  mov     rbx, [rsp+68h+arg_0]
0x18000b699  mov     rsi, [rsp+68h+arg_8]
0x18000b69e  add     rsp, 60h
0x18000b6a2  pop     rdi
0x18000b6a3  retn
0x18000b6a5  mov     ebx, 0C000000Dh
0x18000b6aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6b1  lea     rax, WPP_GLOBAL_Control
0x18000b6b8  cmp     rcx, rax
0x18000b6bb  jz      loc_18000B512
0x18000b6c1  test    byte ptr [rcx+1Ch], 1
0x18000b6c5  jz      loc_18000B512
0x18000b6cb  mov     dword ptr [rsp+68h+var_38], 330h
0x18000b6d3  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b6da  mov     [rsp+68h+var_40], rax
0x18000b6df  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000b6e7  mov     rcx, [rcx+10h]
0x18000b6eb  lea     r9, aStatus; "Status"
0x18000b6f2  call    WPP_SF_sDsd
0x18000b6f7  mov     eax, ebx
0x18000b6f9  mov     rbx, [rsp+68h+arg_0]
0x18000b6fe  mov     rsi, [rsp+68h+arg_8]
0x18000b703  add     rsp, 60h
0x18000b707  pop     rdi
0x18000b708  retn
0x18000b70a  test    edx, 0FFFFFFBFh; jumptable 000000018000B545 case 65544
0x18000b710  jz      loc_18000B7EC
0x18000b716  mov     ebx, 0C000000Dh
0x18000b71b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b722  lea     rax, WPP_GLOBAL_Control
0x18000b729  cmp     rcx, rax
0x18000b72c  jz      loc_18000B512
0x18000b732  test    byte ptr [rcx+1Ch], 1
0x18000b736  jz      loc_18000B512
0x18000b73c  mov     rcx, [rcx+10h]
0x18000b740  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b747  mov     dword ptr [rsp+68h+var_38], 3DEh
0x18000b74f  lea     r9, aStatus; "Status"
0x18000b756  mov     [rsp+68h+var_40], rax
0x18000b75b  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x18000b763  call    WPP_SF_sDsd
0x18000b768  mov     rsi, [rsp+68h+arg_8]
0x18000b76d  mov     eax, ebx
0x18000b76f  mov     rbx, [rsp+68h+arg_0]
0x18000b774  add     rsp, 60h
0x18000b778  pop     rdi
0x18000b779  retn
0x18000b77b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b782  lea     rax, WPP_GLOBAL_Control
0x18000b789  cmp     rcx, rax
0x18000b78c  jz      loc_18000B512
0x18000b792  test    byte ptr [rcx+1Ch], 1
0x18000b796  jz      loc_18000B512
0x18000b79c  mov     dword ptr [rsp+68h+var_38], 3C8h
0x18000b7a4  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b7ab  mov     [rsp+68h+var_40], rax
0x18000b7b0  mov     dword ptr [rsp+68h+var_48], ebx
0x18000b7b4  jmp     loc_18000B6E7
0x18000b7b9  mov     ebx, 0C000000Dh
0x18000b7be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7c5  lea     rax, WPP_GLOBAL_Control
0x18000b7cc  cmp     rcx, rax
0x18000b7cf  jz      loc_18000B512
0x18000b7d5  test    byte ptr [rcx+1Ch], 1
0x18000b7d9  jz      loc_18000B512
0x18000b7df  mov     dword ptr [rsp+68h+var_38], 325h
0x18000b7e7  jmp     loc_18000B6D3
0x18000b7ec  mov     r9d, [r11+14h]
0x18000b7f0  test    r9d, r9d
0x18000b7f3  jz      loc_18000B716
0x18000b7f9  xor     edx, edx
0x18000b7fb  mov     eax, r8d
0x18000b7fe  div     r9d
0x18000b801  test    edx, edx
0x18000b803  jnz     loc_18000B716
0x18000b809  jmp     loc_18007FDE3
0x18000b80e  mov     r9d, 339h
0x18000b814  jmp     loc_18007FCF0
0x18000b819  mov     ebx, 0C00000BBh; jumptable 000000018000B545 default case, case 65543
0x18000b81e  mov     r9d, 3FDh
0x18000b824  mov     ecx, 0C00000BBh
0x18000b829  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b830  lea     rdx, aStatus; "Status"
0x18000b837  call    DebugTraceError
0x18000b83c  jmp     loc_18000B512
0x18000b841  cmp     dword ptr [r11+8], 10002h
0x18000b849  jnz     loc_18007FCFF
0x18000b84f  cmp     r9d, 5
0x18000b853  jz      loc_18000B4AE
0x18000b859  jmp     loc_18007FCFF
0x18000b85e  mov     ebx, 0C0000023h
0x18000b863  jmp     loc_18000B512
0x18000b868  mov     rdi, [rsp+68h+arg_30]; jumptable 000000018000B545 case 65545
0x18000b870  mov     [rcx], r8d
0x18000b873  test    r10, r10
0x18000b876  jz      loc_18007FD07
0x18000b87c  test    rdi, rdi
0x18000b87f  jz      loc_18000B621
0x18000b885  jmp     loc_18007FD07
0x18007fcea  mov     r9d, 38Bh
0x18007fcf0  mov     ebx, 0C000000Dh
0x18007fcf5  mov     ecx, 0C000000Dh
0x18007fcfa  jmp     loc_18000B829
0x18007fcff  mov     r9d, 341h
0x18007fd05  jmp     short loc_18007FCF0
0x18007fd07  cmp     r8d, [rsp+68h+arg_38]
0x18007fd0f  ja      loc_18000B85E
0x18007fd15  cmp     [rsp+68h+arg_20], 0
0x18007fd1e  jnz     short loc_18007FCEA
0x18007fd20  cmp     [rsp+68h+arg_28], 0
0x18007fd28  jnz     short loc_18007FCEA
0x18007fd2a  test    edx, edx
0x18007fd2c  jnz     short loc_18007FCEA
0x18007fd2e  mov     esi, r8d
0x18007fd31  lea     rax, [rsi+r10]
0x18007fd35  cmp     rax, r10
0x18007fd38  jb      short loc_18007FCEA
0x18007fd3a  lea     rax, [rsi+rdi]
0x18007fd3e  cmp     rax, rdi
0x18007fd41  jb      short loc_18007FCEA
0x18007fd43  mov     rcx, rbx
0x18007fd46  call    validateAuthCipherModeInfo
0x18007fd4b  mov     r9, rax
0x18007fd4e  test    rax, rax
0x18007fd51  jz      loc_18007FDD8
0x18007fd57  mov     r8, [rax+8]
0x18007fd5b  test    r8, r8
0x18007fd5e  jz      short loc_18007FDD8
0x18007fd60  cmp     dword ptr [rax+10h], 0Ch
0x18007fd64  jnz     short loc_18007FDD8
0x18007fd66  mov     rbx, [rax+28h]
0x18007fd6a  test    rbx, rbx
0x18007fd6d  jz      short loc_18007FDD8
0x18007fd6f  cmp     dword ptr [rax+30h], 10h
0x18007fd73  jnz     short loc_18007FDD8
0x18007fd75  cmp     [rax+50h], edx
0x18007fd78  jnz     short loc_18007FDD8
0x18007fd7a  mov     eax, [rax+20h]
0x18007fd7d  lea     rcx, [r11+3Ch]
0x18007fd81  mov     edx, [r11+38h]
0x18007fd85  mov     [rsp+68h+var_18], 10h
0x18007fd8e  mov     [rsp+68h+var_20], rbx
0x18007fd93  mov     [rsp+68h+var_28], rsi
0x18007fd98  mov     [rsp+68h+var_30], rdi
0x18007fd9d  mov     [rsp+68h+var_38], r10
0x18007fda2  mov     [rsp+68h+var_40], rax
0x18007fda7  mov     rax, [r9+18h]
0x18007fdab  mov     r9d, 0Ch
0x18007fdb1  mov     [rsp+68h+var_48], rax
0x18007fdb6  call    SymCryptChaCha20Poly1305Encrypt
0x18007fdbb  test    eax, eax
0x18007fdbd  jz      loc_18000B621
0x18007fdc3  mov     ebx, 0C000028Ah
0x18007fdc8  mov     r9d, 3ACh
0x18007fdce  mov     ecx, 0C000028Ah
0x18007fdd3  jmp     loc_18000B829
0x18007fdd8  mov     r9d, 399h
0x18007fdde  jmp     loc_18007FCF0
0x18007fde3  test    r10, r10
0x18007fde6  jz      loc_18000B716
0x18007fdec  mov     rbx, [rsp+68h+arg_20]
0x18007fdf4  test    rbx, rbx
0x18007fdf7  jz      loc_18000B716
0x18007fdfd  cmp     [rsp+68h+arg_28], 8
0x18007fe05  jnz     loc_18000B716
  ... truncated ...
```
