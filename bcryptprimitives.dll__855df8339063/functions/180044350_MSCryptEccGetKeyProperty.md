# MSCryptEccGetKeyProperty

- ea: `0x180044350`
- end: `0x180044903`
- name: `MSCryptEccGetKeyProperty`
- size: `1459`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180043fa0`
- `0x180044180`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180044350`
- `0x180063170`
- `0x18007f765`

## string_xrefs

- `0x180044514`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180044543`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180044641`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180044679`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800446dc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180044719`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800447ab`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800447e9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180044842`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180044889`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800825bc`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccGetKeyProperty(
        __int64 a1,
        __int64 a2,
        int *a3,
        unsigned int a4,
        unsigned int *a5,
        __int64 a6,
        int a7)
{
  int *v8; // r14
  const wchar_t *v9; // rdi
  _QWORD *v11; // r13
  __int64 i; // rax
  __int64 *v13; // rcx
  _DWORD *v14; // rsi
  char *v15; // rax
  int v16; // r15d
  int v17; // ecx
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // edx
  int v21; // eax
  unsigned int v22; // ebx
  _QWORD *v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned int v31; // ecx
  __int64 j; // rcx
  char v33; // [rsp+30h] [rbp-58h]

  v8 = a3;
  v9 = (const wchar_t *)a2;
  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 4) == 1297304409 )
    {
      v11 = *(_QWORD **)(a1 + 16);
      if ( v11 )
      {
        LODWORD(a3) = a7;
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= 4 )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                a2,
                a7,
                (unsigned int)"Status",
                13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                116);
              v25 = WPP_GLOBAL_Control;
            }
            goto LABEL_34;
          }
          v13 = qword_180084718;
          a2 = 6 * i;
          if ( !a7 )
            v13 = &qword_1800847D8;
          if ( *(_DWORD *)(a1 + 8) == LODWORD(v13[6 * i]) )
            break;
        }
        v14 = (_DWORD *)*v11;
        v15 = " ";
        if ( !a7 )
          v15 = " ";
        v16 = v14[3];
        v17 = *(_DWORD *)&v15[8 * a2];
        if ( !v17 )
        {
          if ( (unsigned int)(v16 - 14) <= 0x34 )
            goto LABEL_14;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              a2,
              a7,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              91);
            v25 = WPP_GLOBAL_Control;
          }
          goto LABEL_34;
        }
        if ( v17 != v16 )
        {
          DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 613);
          v25 = WPP_GLOBAL_Control;
          goto LABEL_34;
        }
LABEL_14:
        if ( !wcscmp_0(v9, L"ECCParameters") )
        {
          if ( !v14 )
          {
            v22 = -1073741801;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v18,
                v19,
                (unsigned int)"Status",
                23,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                150);
            return v22;
          }
          v20 = v14[5] + v14[6] + 5 * v16 + v14[4] + 28;
          *a5 = v20;
          if ( v8 )
          {
            if ( a4 >= v20 )
            {
              *v8 = 1;
              v8[1] = v14[1];
              v8[2] = v14[2];
              v8[3] = v14[3];
              v8[4] = v14[4];
              v8[5] = v14[5];
              v8[6] = v14[6];
              memcpy_0(v8 + 7, v14 + 7, (unsigned int)(v14[4] + v14[5] + v14[6] + 5 * v14[3]));
              return 0;
            }
            return (unsigned int)-1073741789;
          }
          v22 = 0;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v22;
          v33 = -93;
        }
        else
        {
          if ( !wcscmp_0(v9, L"ECCCurveName") )
          {
            v26 = v11[2];
            if ( !v26 )
            {
              v22 = -1073741811;
              DebugTraceError(
                3221225485LL,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                3525);
              return v22;
            }
            v29 = -1;
            while ( *(_WORD *)(v26 + 2 * v29++ + 2) != 0 )
              ;
            v31 = 2 * v29 + 2;
            *a5 = v31;
            if ( !v8 )
              return 0;
            if ( a4 >= v31 )
            {
              memcpy_0(v8, *(const void **)(*(_QWORD *)(a1 + 16) + 16LL), v31);
              return 0;
            }
            return (unsigned int)-1073741789;
          }
          if ( wcscmp_0(v9, L"KeyLength") && wcscmp_0(v9, L"KeyStrength") )
          {
            if ( !wcscmp_0(v9, L"PublicKeyLength") )
            {
              *a5 = 4;
              if ( v8 )
              {
                if ( a4 >= 4 )
                {
                  v21 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL) + 12LL);
LABEL_22:
                  *v8 = v21;
                  return 0;
                }
                return (unsigned int)-1073741789;
              }
              v27 = 3575;
            }
            else
            {
              if ( wcscmp_0(v9, L"SignatureLength") )
              {
                v22 = -1073741637;
                v27 = 3627;
                v28 = 3221225659LL;
                goto LABEL_78;
              }
              *a5 = 4;
              if ( v8 )
              {
                if ( a4 >= 4 )
                {
                  for ( j = 0; (unsigned int)j < 4; j = (unsigned int)(j + 1) )
                  {
                    if ( *(_DWORD *)(a1 + 8) == LODWORD(qword_180084718[6 * j]) )
                    {
                      v21 = 2 * *(_DWORD *)(**(_QWORD **)(a1 + 16) + 16LL);
                      if ( v21 )
                        goto LABEL_22;
                      break;
                    }
                  }
                  v22 = -1073741816;
                  v27 = 3618;
                  v28 = 3221225480LL;
                }
                else
                {
                  v22 = -1073741789;
                  v27 = 3602;
                  v28 = 3221225507LL;
                }
                goto LABEL_78;
              }
              v27 = 3595;
            }
            v22 = 0;
            v28 = 0;
LABEL_78:
            DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v27);
            return v22;
          }
          *a5 = 4;
          if ( v8 )
          {
            if ( a4 >= 4 )
            {
              v21 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL) + 24LL);
              goto LABEL_22;
            }
            return (unsigned int)-1073741789;
          }
          v22 = 0;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v22;
          v33 = -29;
        }
        WPP_SF_sDsd(
          v24[2],
          v20,
          v19,
          (unsigned int)"Status",
          0,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          v33);
        return v22;
      }
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          67);
        v25 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          60);
        v25 = WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        51);
      v25 = WPP_GLOBAL_Control;
    }
  }
LABEL_34:
  v22 = -1073741811;
  if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      v25[2],
      a2,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      140);
  return v22;
}

```

## disassembly

```asm
0x180044350  push    rbx
0x180044352  push    rbp
0x180044353  push    rsi
0x180044354  push    rdi
0x180044355  push    r12
0x180044357  push    r13
0x180044359  push    r14
0x18004435b  push    r15
0x18004435d  sub     rsp, 48h
0x180044361  mov     r12d, r9d
0x180044364  mov     r14, r8
0x180044367  mov     rdi, rdx
0x18004436a  mov     rbx, rcx
0x18004436d  test    rcx, rcx
0x180044370  jz      loc_180044526
0x180044376  cmp     dword ptr [rcx+4], 4D534B59h
0x18004437d  jnz     loc_18004461C
0x180044383  mov     r13, [rcx+10h]
0x180044387  test    r13, r13
0x18004438a  jz      loc_1800446B7
0x180044390  mov     r8d, [rsp+88h+arg_30]
0x180044398  lea     r9, qword_1800847D8
0x18004439f  xor     eax, eax
0x1800443a1  lea     r10, qword_180084718
0x1800443a8  nop     dword ptr [rax+rax+00000000h]
0x1800443b0  cmp     eax, 4
0x1800443b3  jnb     loc_18004481D
0x1800443b9  lea     rdx, [rax+rax*2]
0x1800443bd  mov     rcx, r10
0x1800443c0  add     rdx, rdx
0x1800443c3  test    r8d, r8d
0x1800443c6  cmovz   rcx, r9
0x1800443ca  mov     ecx, [rcx+rdx*8]
0x1800443cd  cmp     [rbx+8], ecx
0x1800443d0  jz      short loc_1800443D6
0x1800443d2  inc     eax
0x1800443d4  jmp     short loc_1800443B0
0x1800443d6  mov     rsi, [r13+0]
0x1800443da  lea     rcx, aEck2+4; " "
0x1800443e1  test    r8d, r8d
0x1800443e4  lea     rax, aEcs2+4; " "
0x1800443eb  cmovz   rax, rcx
0x1800443ef  mov     r15d, [rsi+0Ch]
0x1800443f3  mov     ecx, [rax+rdx*8]
0x1800443f6  test    ecx, ecx
0x1800443f8  jnz     loc_180044710
0x1800443fe  lea     eax, [r15-0Eh]
0x180044402  cmp     eax, 34h ; '4'
0x180044405  ja      loc_1800447C4
0x18004440b  lea     rdx, aEccparameters; "ECCParameters"
0x180044412  mov     rcx, rdi; String1
0x180044415  call    wcscmp_0
0x18004441a  test    eax, eax
0x18004441c  jz      loc_1800444C3
0x180044422  lea     rdx, aEcccurvename; "ECCCurveName"
0x180044429  mov     rcx, rdi; String1
0x18004442c  call    wcscmp_0
0x180044431  test    eax, eax
0x180044433  jz      loc_180044876
0x180044439  lea     rdx, aKeylength; "KeyLength"
0x180044440  mov     rcx, rdi; String1
0x180044443  call    wcscmp_0
0x180044448  test    eax, eax
0x18004444a  jz      loc_1800445EB
0x180044450  lea     rdx, aKeystrength; "KeyStrength"
0x180044457  mov     rcx, rdi; String1
0x18004445a  call    wcscmp_0
0x18004445f  test    eax, eax
0x180044461  jz      loc_1800445EB
0x180044467  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x18004446e  mov     rcx, rdi; String1
0x180044471  call    wcscmp_0
0x180044476  test    eax, eax
0x180044478  jnz     loc_1800448B6
0x18004447e  mov     rax, [rsp+88h+arg_20]
0x180044486  mov     dword ptr [rax], 4
0x18004448c  test    r14, r14
0x18004448f  jz      loc_1800448AB
0x180044495  cmp     r12d, 4
0x180044499  jb      loc_1800446AD
0x18004449f  mov     rax, [rbx+10h]
0x1800444a3  mov     rcx, [rax+8]
0x1800444a7  mov     eax, [rcx+0Ch]
0x1800444aa  mov     [r14], eax
0x1800444ad  xor     ebx, ebx
0x1800444af  mov     eax, ebx
0x1800444b1  add     rsp, 48h
0x1800444b5  pop     r15
0x1800444b7  pop     r14
0x1800444b9  pop     r13
0x1800444bb  pop     r12
0x1800444bd  pop     rdi
0x1800444be  pop     rsi
0x1800444bf  pop     rbp
0x1800444c0  pop     rbx
0x1800444c1  retn
0x1800444c3  test    rsi, rsi
0x1800444c6  jz      loc_18004477D
0x1800444cc  mov     edx, [rsi+10h]
0x1800444cf  lea     ecx, [r15+r15*4]
0x1800444d3  add     ecx, [rsi+18h]
0x1800444d6  add     edx, 1Ch
0x1800444d9  add     ecx, [rsi+14h]
0x1800444dc  mov     rax, [rsp+88h+arg_20]
0x1800444e4  add     edx, ecx
0x1800444e6  mov     [rax], edx
0x1800444e8  test    r14, r14
0x1800444eb  jnz     loc_18004458C
0x1800444f1  xor     ebx, ebx
0x1800444f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800444fa  lea     rdi, WPP_GLOBAL_Control
0x180044501  cmp     rcx, rdi
0x180044504  jz      short loc_1800444AF
0x180044506  test    byte ptr [rcx+1Ch], 1
0x18004450a  jz      short loc_1800444AF
0x18004450c  mov     dword ptr [rsp+88h+var_58], 0DA3h
0x180044514  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004451b  mov     [rsp+88h+var_60], rsi
0x180044520  mov     [rsp+88h+var_68], ebx
0x180044524  jmp     short loc_180044577
0x180044526  mov     rcx, cs:WPP_GLOBAL_Control
0x18004452d  lea     rdi, WPP_GLOBAL_Control
0x180044534  cmp     rcx, rdi
0x180044537  jz      short loc_180044543
0x180044539  test    byte ptr [rcx+1Ch], 1
0x18004453d  jnz     loc_180044675
0x180044543  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004454a  mov     ebx, 0C000000Dh
0x18004454f  cmp     rcx, rdi
0x180044552  jz      loc_1800444AF
0x180044558  test    byte ptr [rcx+1Ch], 1
0x18004455c  jz      loc_1800444AF
0x180044562  mov     dword ptr [rsp+88h+var_58], 0D8Ch
0x18004456a  mov     [rsp+88h+var_60], rsi
0x18004456f  mov     [rsp+88h+var_68], 0C000000Dh
0x180044577  mov     rcx, [rcx+10h]
0x18004457b  lea     r9, aStatus; "Status"
0x180044582  call    WPP_SF_sDsd
0x180044587  jmp     loc_1800444AF
0x18004458c  cmp     r12d, edx
0x18004458f  jb      loc_1800446AD
0x180044595  mov     dword ptr [r14], 1
0x18004459c  lea     rdx, [rsi+1Ch]; Src
0x1800445a0  mov     eax, [rsi+4]
0x1800445a3  lea     rcx, [r14+1Ch]; void *
0x1800445a7  mov     [r14+4], eax
0x1800445ab  mov     eax, [rsi+8]
0x1800445ae  mov     [r14+8], eax
0x1800445b2  mov     eax, [rsi+0Ch]
0x1800445b5  mov     [r14+0Ch], eax
0x1800445b9  mov     eax, [rsi+10h]
0x1800445bc  mov     [r14+10h], eax
0x1800445c0  mov     eax, [rsi+14h]
0x1800445c3  mov     [r14+14h], eax
0x1800445c7  mov     eax, [rsi+18h]
0x1800445ca  mov     [r14+18h], eax
0x1800445ce  mov     eax, [rsi+0Ch]
0x1800445d1  lea     r8d, [rax+rax*4]
0x1800445d5  add     r8d, [rsi+18h]
0x1800445d9  add     r8d, [rsi+14h]
0x1800445dd  add     r8d, [rsi+10h]; Size
0x1800445e1  call    memcpy_0
0x1800445e6  jmp     loc_1800444AD
0x1800445eb  mov     rax, [rsp+88h+arg_20]
0x1800445f3  mov     dword ptr [rax], 4
0x1800445f9  test    r14, r14
0x1800445fc  jz      loc_18004474D
0x180044602  cmp     r12d, 4
0x180044606  jb      loc_1800446AD
0x18004460c  mov     rax, [rbx+10h]
0x180044610  mov     rcx, [rax+8]
0x180044614  mov     eax, [rcx+18h]
0x180044617  jmp     loc_1800444AA
0x18004461c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044623  lea     rdi, WPP_GLOBAL_Control
0x18004462a  cmp     rcx, rdi
0x18004462d  jz      loc_180044543
0x180044633  test    byte ptr [rcx+1Ch], 1
0x180044637  jz      loc_180044543
0x18004463d  mov     rcx, [rcx+10h]
0x180044641  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044648  mov     dword ptr [rsp+88h+var_58], 23Ch
0x180044650  lea     r9, aStatus; "Status"
0x180044657  mov     [rsp+88h+var_60], rsi
0x18004465c  mov     [rsp+88h+var_68], 0C000000Dh
0x180044664  call    WPP_SF_sDsd
0x180044669  mov     rcx, cs:WPP_GLOBAL_Control
0x180044670  jmp     loc_18004454A
0x180044675  mov     rcx, [rcx+10h]
0x180044679  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044680  mov     dword ptr [rsp+88h+var_58], 233h
0x180044688  lea     r9, aStatus; "Status"
0x18004468f  mov     [rsp+88h+var_60], rsi
0x180044694  mov     [rsp+88h+var_68], 0C000000Dh
0x18004469c  call    WPP_SF_sDsd
0x1800446a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446a8  jmp     loc_18004454A
0x1800446ad  mov     ebx, 0C0000023h
0x1800446b2  jmp     loc_1800444AF
0x1800446b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800446be  lea     rdi, WPP_GLOBAL_Control
0x1800446c5  cmp     rcx, rdi
0x1800446c8  jz      loc_180044543
0x1800446ce  test    byte ptr [rcx+1Ch], 1
0x1800446d2  jz      loc_180044543
0x1800446d8  mov     rcx, [rcx+10h]
0x1800446dc  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800446e3  mov     dword ptr [rsp+88h+var_58], 243h
0x1800446eb  lea     r9, aStatus; "Status"
0x1800446f2  mov     [rsp+88h+var_60], rsi
0x1800446f7  mov     [rsp+88h+var_68], 0C000000Dh
0x1800446ff  call    WPP_SF_sDsd
0x180044704  mov     rcx, cs:WPP_GLOBAL_Control
0x18004470b  jmp     loc_18004454A
0x180044710  cmp     ecx, r15d
0x180044713  jz      loc_18004440B
0x180044719  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044720  mov     r9d, 265h
0x180044726  mov     r8, rsi
0x180044729  lea     rdx, aStatus; "Status"
0x180044730  mov     ecx, 0C000000Dh
0x180044735  call    DebugTraceError
0x18004473a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044741  lea     rdi, WPP_GLOBAL_Control
0x180044748  jmp     loc_18004454A
0x18004474d  xor     ebx, ebx
0x18004474f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044756  lea     rdi, WPP_GLOBAL_Control
0x18004475d  cmp     rcx, rdi
0x180044760  jz      loc_1800444AF
0x180044766  test    byte ptr [rcx+1Ch], 1
0x18004476a  jz      loc_1800444AF
0x180044770  mov     dword ptr [rsp+88h+var_58], 0DE3h
0x180044778  jmp     loc_180044514
0x18004477d  mov     ebx, 0C0000017h
0x180044782  mov     rcx, cs:WPP_GLOBAL_Control
0x180044789  lea     rdi, WPP_GLOBAL_Control
0x180044790  cmp     rcx, rdi
0x180044793  jz      loc_1800444AF
0x180044799  test    byte ptr [rcx+1Ch], 1
0x18004479d  jz      loc_1800444AF
0x1800447a3  mov     dword ptr [rsp+88h+var_58], 0D96h
0x1800447ab  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800447b2  mov     [rsp+88h+var_60], rsi
0x1800447b7  mov     [rsp+88h+var_68], 0C0000017h
0x1800447bf  jmp     loc_180044577
0x1800447c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800447cb  lea     rdi, WPP_GLOBAL_Control
0x1800447d2  cmp     rcx, rdi
0x1800447d5  jz      loc_180044543
0x1800447db  test    byte ptr [rcx+1Ch], 1
0x1800447df  jz      loc_180044543
0x1800447e5  mov     rcx, [rcx+10h]
0x1800447e9  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800447f0  mov     dword ptr [rsp+88h+var_58], 25Bh
0x1800447f8  lea     r9, aStatus; "Status"
0x1800447ff  mov     [rsp+88h+var_60], rsi
0x180044804  mov     [rsp+88h+var_68], 0C000000Dh
0x18004480c  call    WPP_SF_sDsd
0x180044811  mov     rcx, cs:WPP_GLOBAL_Control
0x180044818  jmp     loc_18004454A
0x18004481d  mov     rcx, cs:WPP_GLOBAL_Control
0x180044824  lea     rdi, WPP_GLOBAL_Control
0x18004482b  cmp     rcx, rdi
0x18004482e  jz      loc_180044543
0x180044834  test    byte ptr [rcx+1Ch], 1
0x180044838  jz      loc_180044543
0x18004483e  mov     rcx, [rcx+10h]
0x180044842  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044849  mov     dword ptr [rsp+88h+var_58], 274h
0x180044851  lea     r9, aStatus; "Status"
0x180044858  mov     [rsp+88h+var_60], rsi
0x18004485d  mov     [rsp+88h+var_68], 0C000000Dh
0x180044865  call    WPP_SF_sDsd
0x18004486a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044871  jmp     loc_18004454A
0x180044876  mov     rcx, [r13+10h]
0x18004487a  test    rcx, rcx
0x18004487d  jnz     loc_18008254A
0x180044883  mov     r9d, 0DC5h
0x180044889  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180044890  lea     rdx, aStatus; "Status"
0x180044897  mov     ecx, 0C000000Dh
0x18004489c  mov     ebx, 0C000000Dh
0x1800448a1  call    DebugTraceError
0x1800448a6  jmp     loc_1800444AF
0x1800448ab  mov     r9d, 0DF7h
0x1800448b1  jmp     loc_18008259F
0x1800448b6  lea     rdx, aSignaturelengt; "SignatureLength"
0x1800448bd  mov     rcx, rdi; String1
0x1800448c0  call    wcscmp_0
0x1800448c5  test    eax, eax
0x1800448c7  jnz     loc_1800825A5
0x1800448cd  mov     rax, [rsp+88h+arg_20]
0x1800448d5  mov     dword ptr [rax], 4
0x1800448db  test    r14, r14
0x1800448de  jz      loc_180082599
0x1800448e4  cmp     r12d, 4
0x1800448e8  jnb     loc_1800825CE
0x1800448ee  mov     ebx, 0C0000023h
  ... truncated ...
```
