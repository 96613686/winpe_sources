# MSCryptEccExportKeyPair

- ea: `0x180045b60`
- end: `0x18004610c`
- name: `MSCryptEccExportKeyPair`
- size: `1452`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180045ae0`
- `0x180045b20`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180045b60`
- `0x180046120`
- `0x180046410`
- `0x180046658`
- `0x18007f765`

## string_xrefs

- `0x180045d46`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045d89`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045e14`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045e66`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045ebf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045efc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045f9a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180045ff3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004602d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800460ba`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800460d8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180082715`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccExportKeyPair(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        int a8)
{
  const wchar_t *v9; // rbx
  __int64 *v11; // r12
  __int64 v12; // rax
  int v13; // esi
  __int64 *v14; // rcx
  char *v15; // rax
  int v16; // ecx
  __int64 v17; // rax
  int v18; // edx
  int v19; // r8d
  int v20; // ebp
  int v21; // eax
  unsigned int v22; // ebx
  _QWORD *v24; // rcx
  int KeyMagicForAlgId; // eax
  __int64 v26; // r9
  __int64 v27; // rcx
  _DWORD v28[4]; // [rsp+40h] [rbp-28h] BYREF

  v9 = (const wchar_t *)a3;
  v28[0] = 0;
  if ( !a7 )
  {
    if ( a2 )
    {
      v22 = -1073741637;
      DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2874);
      return v22;
    }
    if ( a1 )
    {
      if ( *(_DWORD *)(a1 + 4) == 1297304409 )
      {
        v11 = *(__int64 **)(a1 + 16);
        if ( v11 )
        {
          v12 = 0;
          a3 = &qword_180084718;
          while ( 1 )
          {
            if ( (unsigned int)v12 >= 4 )
            {
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  a2,
                  (unsigned int)&qword_180084718,
                  (unsigned int)"Status",
                  13,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                  116);
                v24 = WPP_GLOBAL_Control;
              }
              goto LABEL_34;
            }
            v13 = *(_DWORD *)(a1 + 8);
            a2 = 6 * v12;
            v14 = &qword_180084718;
            if ( !a8 )
              v14 = &qword_1800847D8;
            if ( v13 == LODWORD(v14[6 * v12]) )
              break;
            v12 = (unsigned int)(v12 + 1);
          }
          v15 = " ";
          if ( !a8 )
            v15 = " ";
          v16 = *(_DWORD *)&v15[8 * a2];
          v17 = *v11;
          if ( !v16 )
          {
            if ( (unsigned int)(*(_DWORD *)(v17 + 12) - 14) <= 0x34 )
              goto LABEL_16;
            v24 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                a2,
                (unsigned int)&qword_180084718,
                (unsigned int)"Status",
                13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                91);
              v24 = WPP_GLOBAL_Control;
            }
            goto LABEL_34;
          }
          if ( v16 != *(_DWORD *)(v17 + 12) )
          {
            DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 613);
            v24 = WPP_GLOBAL_Control;
            goto LABEL_34;
          }
LABEL_16:
          if ( (*(_BYTE *)(a1 + 32) & 2) == 0 )
          {
            v22 = -1073741816;
            v26 = 2889;
            v27 = 3221225480LL;
LABEL_69:
            DebugTraceError(v27, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v26);
            return v22;
          }
          if ( !wcscmp_0(v9, L"PUBLICBLOB") )
          {
            KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(v13, (_DWORD)v11, a8, 0, (__int64)v28);
            v22 = KeyMagicForAlgId;
            if ( KeyMagicForAlgId < 0 )
            {
              v26 = 2914;
LABEL_68:
              v27 = (unsigned int)KeyMagicForAlgId;
              goto LABEL_69;
            }
            v20 = 0;
            if ( v28[0] != 1346650949 && v28[0] != 1347109701 )
              goto LABEL_38;
          }
          else
          {
            if ( wcscmp_0(v9, L"PRIVATEBLOB") )
            {
              if ( !wcscmp_0(v9, L"ECCPUBLICBLOB") )
              {
                v20 = 0;
              }
              else
              {
                if ( wcscmp_0(v9, L"ECCPRIVATEBLOB") )
                {
                  if ( !wcscmp_0(v9, L"ECCFULLPUBLICBLOB") )
                  {
                    v20 = 0;
                  }
                  else
                  {
                    if ( wcscmp_0(v9, L"ECCFULLPRIVATEBLOB") )
                    {
                      v22 = -1073741637;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v18,
                          v19,
                          (unsigned int)"Status",
                          187,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                          144);
                      }
                      return v22;
                    }
                    v20 = 1;
                  }
                  goto LABEL_24;
                }
                v20 = 1;
              }
LABEL_38:
              v21 = ExportEccKeyBlobWithoutParameters(a1, a4, a5, a6, a8, v20);
LABEL_25:
              v22 = v21;
              if ( v21 < 0 )
                DebugTraceError(
                  (unsigned int)v21,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                  2974);
              else
                return 0;
              return v22;
            }
            v20 = 1;
            KeyMagicForAlgId = MSCryptEcGetKeyMagicForAlgId(v13, (_DWORD)v11, a8, 1, (__int64)v28);
            v22 = KeyMagicForAlgId;
            if ( KeyMagicForAlgId < 0 )
            {
              v26 = 2930;
              goto LABEL_68;
            }
            if ( v28[0] != 1447314245 && v28[0] != 1447772997 )
              goto LABEL_38;
          }
LABEL_24:
          v21 = ExportEccKeyBlobWithParameters(a1, a4, a5, a6, a8, v20);
          goto LABEL_25;
        }
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            0,
            (_DWORD)a3,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            67);
          v24 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            0,
            (_DWORD)a3,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            60);
          v24 = WPP_GLOBAL_Control;
        }
      }
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0,
          (_DWORD)a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          51);
        v24 = WPP_GLOBAL_Control;
      }
    }
LABEL_34:
    v22 = -1073741811;
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v24[2],
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        66);
    return v22;
  }
  v22 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      51);
  return v22;
}

```

## disassembly

```asm
0x180045b60  mov     [rsp+arg_10], rbx
0x180045b65  mov     [rsp+arg_18], rbp
0x180045b6a  push    rsi
0x180045b6b  push    rdi
0x180045b6c  push    r15
0x180045b6e  sub     rsp, 50h
0x180045b72  cmp     [rsp+68h+arg_30], 0
0x180045b7a  mov     r15, r9
0x180045b7d  mov     rbx, r8
0x180045b80  mov     [rsp+68h+var_28], 0
0x180045b88  mov     rdi, rcx
0x180045b8b  jnz     loc_180045DEA
0x180045b91  test    rdx, rdx
0x180045b94  jnz     loc_180046027
0x180045b9a  mov     [rsp+68h+arg_0], r12
0x180045b9f  mov     [rsp+68h+arg_8], r14
0x180045ba4  test    rcx, rcx
0x180045ba7  jz      loc_180045D6C
0x180045bad  cmp     dword ptr [rcx+4], 4D534B59h
0x180045bb4  jnz     loc_180045E41
0x180045bba  mov     r12, [rcx+10h]
0x180045bbe  test    r12, r12
0x180045bc1  jz      loc_180045E9A
0x180045bc7  mov     r14d, [rsp+68h+arg_38]
0x180045bcf  lea     r9, qword_1800847D8
0x180045bd6  xor     eax, eax
0x180045bd8  lea     r8, qword_180084718
0x180045bdf  nop
0x180045be0  cmp     eax, 4
0x180045be3  jnb     loc_180045FCE
0x180045be9  mov     esi, [rdi+8]
0x180045bec  lea     rdx, [rax+rax*2]
0x180045bf0  add     rdx, rdx
0x180045bf3  mov     rcx, r8
0x180045bf6  test    r14d, r14d
0x180045bf9  cmovz   rcx, r9
0x180045bfd  cmp     esi, [rcx+rdx*8]
0x180045c00  jz      short loc_180045C06
0x180045c02  inc     eax
0x180045c04  jmp     short loc_180045BE0
0x180045c06  test    r14d, r14d
0x180045c09  lea     rcx, aEck2+4; " "
0x180045c10  lea     rax, aEcs2+4; " "
0x180045c17  cmovz   rax, rcx
0x180045c1b  mov     ecx, [rax+rdx*8]
0x180045c1e  mov     rax, [r12]
0x180045c22  test    ecx, ecx
0x180045c24  jnz     loc_180045EF3
0x180045c2a  mov     eax, [rax+0Ch]
0x180045c2d  sub     eax, 0Eh
0x180045c30  cmp     eax, 34h ; '4'
0x180045c33  ja      loc_180045F75
0x180045c39  test    byte ptr [rdi+20h], 2
0x180045c3d  jz      loc_18004604F
0x180045c43  lea     rdx, aPublicblob; "PUBLICBLOB"
0x180045c4a  mov     rcx, rbx; String1
0x180045c4d  call    wcscmp_0
0x180045c52  test    eax, eax
0x180045c54  jz      loc_180045F30
0x180045c5a  lea     rdx, aPrivateblob; "PRIVATEBLOB"
0x180045c61  mov     rcx, rbx; String1
0x180045c64  call    wcscmp_0
0x180045c69  test    eax, eax
0x180045c6b  jz      loc_18004606F
0x180045c71  lea     rdx, aEccpublicblob; "ECCPUBLICBLOB"
0x180045c78  mov     rcx, rbx; String1
0x180045c7b  call    wcscmp_0
0x180045c80  test    eax, eax
0x180045c82  jz      loc_180045DBF
0x180045c88  lea     rdx, aEccprivateblob; "ECCPRIVATEBLOB"
0x180045c8f  mov     rcx, rbx; String1
0x180045c92  call    wcscmp_0
0x180045c97  test    eax, eax
0x180045c99  jz      loc_1800460A3
0x180045c9f  lea     rdx, aEccfullpublicb; "ECCFULLPUBLICBLOB"
0x180045ca6  mov     rcx, rbx; String1
0x180045ca9  call    wcscmp_0
0x180045cae  test    eax, eax
0x180045cb0  jz      loc_1800460AD
0x180045cb6  lea     rdx, aEccfullprivate; "ECCFULLPRIVATEBLOB"
0x180045cbd  mov     rcx, rbx; String1
0x180045cc0  call    wcscmp_0
0x180045cc5  test    eax, eax
0x180045cc7  jnz     short loc_180045D20
0x180045cc9  mov     ebp, 1
0x180045cce  mov     r9, [rsp+68h+arg_28]
0x180045cd6  mov     rdx, r15
0x180045cd9  mov     r8d, [rsp+68h+arg_20]
0x180045ce1  mov     rcx, rdi
0x180045ce4  mov     dword ptr [rsp+68h+var_40], ebp
0x180045ce8  mov     dword ptr [rsp+68h+var_48], r14d
0x180045ced  call    ExportEccKeyBlobWithParameters
0x180045cf2  mov     ebx, eax
0x180045cf4  test    eax, eax
0x180045cf6  js      loc_1800460B4
0x180045cfc  xor     ebx, ebx
0x180045cfe  mov     r12, [rsp+68h+arg_0]
0x180045d03  mov     r14, [rsp+68h+arg_8]
0x180045d08  lea     r11, [rsp+68h+var_18]
0x180045d0d  mov     eax, ebx
0x180045d0f  mov     rbx, [r11+30h]
0x180045d13  mov     rbp, [r11+38h]
0x180045d17  mov     rsp, r11
0x180045d1a  pop     r15
0x180045d1c  pop     rdi
0x180045d1d  pop     rsi
0x180045d1e  retn
0x180045d20  mov     ebx, 0C00000BBh
0x180045d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d2c  lea     rdi, WPP_GLOBAL_Control
0x180045d33  cmp     rcx, rdi
0x180045d36  jz      short loc_180045CFE
0x180045d38  test    byte ptr [rcx+1Ch], 1
0x180045d3c  jz      short loc_180045CFE
0x180045d3e  mov     [rsp+68h+var_38], 0B90h
0x180045d46  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045d4d  mov     [rsp+68h+var_40], rsi
0x180045d52  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x180045d5a  mov     rcx, [rcx+10h]
0x180045d5e  lea     r9, aStatus; "Status"
0x180045d65  call    WPP_SF_sDsd
0x180045d6a  jmp     short loc_180045CFE
0x180045d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180045d73  lea     rdi, WPP_GLOBAL_Control
0x180045d7a  cmp     rcx, rdi
0x180045d7d  jz      short loc_180045D89
0x180045d7f  test    byte ptr [rcx+1Ch], 1
0x180045d83  jnz     loc_1800460D4
0x180045d89  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045d90  mov     ebx, 0C000000Dh
0x180045d95  cmp     rcx, rdi
0x180045d98  jz      loc_180045CFE
0x180045d9e  test    byte ptr [rcx+1Ch], 1
0x180045da2  jz      loc_180045CFE
0x180045da8  mov     [rsp+68h+var_38], 0B42h
0x180045db0  mov     [rsp+68h+var_40], rsi
0x180045db5  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x180045dbd  jmp     short loc_180045D5A
0x180045dbf  xor     ebp, ebp
0x180045dc1  mov     r9, [rsp+68h+arg_28]
0x180045dc9  mov     rdx, r15
0x180045dcc  mov     r8d, [rsp+68h+arg_20]
0x180045dd4  mov     rcx, rdi
0x180045dd7  mov     dword ptr [rsp+68h+var_40], ebp
0x180045ddb  mov     dword ptr [rsp+68h+var_48], r14d
0x180045de0  call    ExportEccKeyBlobWithoutParameters
0x180045de5  jmp     loc_180045CF2
0x180045dea  mov     ebx, 0C000000Dh
0x180045def  mov     rcx, cs:WPP_GLOBAL_Control
0x180045df6  lea     rdi, WPP_GLOBAL_Control
0x180045dfd  cmp     rcx, rdi
0x180045e00  jz      loc_180045D08
0x180045e06  test    byte ptr [rcx+1Ch], 1
0x180045e0a  jz      loc_180045D08
0x180045e10  mov     rcx, [rcx+10h]
0x180045e14  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045e1b  mov     [rsp+68h+var_38], 0B33h
0x180045e23  lea     r9, aStatus; "Status"
0x180045e2a  mov     [rsp+68h+var_40], rsi
0x180045e2f  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x180045e37  call    WPP_SF_sDsd
0x180045e3c  jmp     loc_180045D08
0x180045e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e48  lea     rdi, WPP_GLOBAL_Control
0x180045e4f  cmp     rcx, rdi
0x180045e52  jz      loc_180045D89
0x180045e58  test    byte ptr [rcx+1Ch], 1
0x180045e5c  jz      loc_180045D89
0x180045e62  mov     rcx, [rcx+10h]
0x180045e66  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045e6d  mov     [rsp+68h+var_38], 23Ch
0x180045e75  lea     r9, aStatus; "Status"
0x180045e7c  mov     [rsp+68h+var_40], rsi
0x180045e81  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x180045e89  call    WPP_SF_sDsd
0x180045e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180045e95  jmp     loc_180045D90
0x180045e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ea1  lea     rdi, WPP_GLOBAL_Control
0x180045ea8  cmp     rcx, rdi
0x180045eab  jz      loc_180045D89
0x180045eb1  test    byte ptr [rcx+1Ch], 1
0x180045eb5  jz      loc_180045D89
0x180045ebb  mov     rcx, [rcx+10h]
0x180045ebf  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045ec6  mov     [rsp+68h+var_38], 243h
0x180045ece  lea     r9, aStatus; "Status"
0x180045ed5  mov     [rsp+68h+var_40], rsi
0x180045eda  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x180045ee2  call    WPP_SF_sDsd
0x180045ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180045eee  jmp     loc_180045D90
0x180045ef3  cmp     ecx, [rax+0Ch]
0x180045ef6  jz      loc_180045C39
0x180045efc  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045f03  mov     r9d, 265h
0x180045f09  mov     r8, rsi
0x180045f0c  lea     rdx, aStatus; "Status"
0x180045f13  mov     ecx, 0C000000Dh
0x180045f18  call    DebugTraceError
0x180045f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f24  lea     rdi, WPP_GLOBAL_Control
0x180045f2b  jmp     loc_180045D90
0x180045f30  lea     rax, [rsp+68h+var_28]
0x180045f35  xor     r9d, r9d
0x180045f38  mov     r8d, r14d
0x180045f3b  mov     [rsp+68h+var_48], rax
0x180045f40  mov     rdx, r12
0x180045f43  mov     ecx, esi
0x180045f45  call    MSCryptEcGetKeyMagicForAlgId
0x180045f4a  mov     ebx, eax
0x180045f4c  test    eax, eax
0x180045f4e  js      loc_180046064
0x180045f54  mov     eax, [rsp+68h+var_28]
0x180045f58  xor     ebp, ebp
0x180045f5a  cmp     eax, 50444345h
0x180045f5f  jz      loc_180045CCE
0x180045f65  cmp     eax, 504B4345h
0x180045f6a  jnz     loc_180045DC1
0x180045f70  jmp     loc_180045CCE
0x180045f75  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f7c  lea     rdi, WPP_GLOBAL_Control
0x180045f83  cmp     rcx, rdi
0x180045f86  jz      loc_180045D89
0x180045f8c  test    byte ptr [rcx+1Ch], 1
0x180045f90  jz      loc_180045D89
0x180045f96  mov     rcx, [rcx+10h]
0x180045f9a  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045fa1  mov     [rsp+68h+var_38], 25Bh
0x180045fa9  lea     r9, aStatus; "Status"
0x180045fb0  mov     [rsp+68h+var_40], rsi
0x180045fb5  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x180045fbd  call    WPP_SF_sDsd
0x180045fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180045fc9  jmp     loc_180045D90
0x180045fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180045fd5  lea     rdi, WPP_GLOBAL_Control
0x180045fdc  cmp     rcx, rdi
0x180045fdf  jz      loc_180045D89
0x180045fe5  test    byte ptr [rcx+1Ch], 1
0x180045fe9  jz      loc_180045D89
0x180045fef  mov     rcx, [rcx+10h]
0x180045ff3  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180045ffa  mov     [rsp+68h+var_38], 274h
0x180046002  lea     r9, aStatus; "Status"
0x180046009  mov     [rsp+68h+var_40], rsi
0x18004600e  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x180046016  call    WPP_SF_sDsd
0x18004601b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046022  jmp     loc_180045D90
0x180046027  mov     r9d, 0B3Ah
0x18004602d  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046034  lea     rdx, aStatus; "Status"
0x18004603b  mov     ecx, 0C00000BBh
0x180046040  mov     ebx, 0C00000BBh
0x180046045  call    DebugTraceError
0x18004604a  jmp     loc_180045D08
0x18004604f  mov     ebx, 0C0000008h
0x180046054  mov     r9d, 0B49h
0x18004605a  mov     ecx, 0C0000008h
0x18004605f  jmp     loc_18008270E
0x180046064  mov     r9d, 0B62h
0x18004606a  jmp     loc_18008270C
0x18004606f  lea     rax, [rsp+68h+var_28]
0x180046074  mov     ebp, 1
0x180046079  mov     r9d, ebp
0x18004607c  mov     [rsp+68h+var_48], rax
0x180046081  mov     r8d, r14d
0x180046084  mov     rdx, r12
0x180046087  mov     ecx, esi
0x180046089  call    MSCryptEcGetKeyMagicForAlgId
0x18004608e  mov     ebx, eax
0x180046090  test    eax, eax
0x180046092  jns     loc_180082727
0x180046098  mov     r9d, 0B72h
0x18004609e  jmp     loc_18008270C
0x1800460a3  mov     ebp, 1
0x1800460a8  jmp     loc_180045DC1
0x1800460ad  xor     ebp, ebp
0x1800460af  jmp     loc_180045CCE
0x1800460b4  mov     r9d, 0B9Eh
0x1800460ba  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800460c1  lea     rdx, aStatus; "Status"
0x1800460c8  mov     ecx, ebx
0x1800460ca  call    DebugTraceError
0x1800460cf  jmp     loc_180045CFE
0x1800460d4  mov     rcx, [rcx+10h]
0x1800460d8  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800460df  mov     [rsp+68h+var_38], 233h
0x1800460e7  lea     r9, aStatus; "Status"
0x1800460ee  mov     [rsp+68h+var_40], rsi
0x1800460f3  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x1800460fb  call    WPP_SF_sDsd
0x180046100  mov     rcx, cs:WPP_GLOBAL_Control
0x180046107  jmp     loc_180045D90
0x18008270c  mov     ecx, eax
0x18008270e  lea     rdx, aStatus; "Status"
0x180082715  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008271c  call    DebugTraceError
0x180082721  nop
  ... truncated ...
```
