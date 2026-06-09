# MSCryptEccSetKeyProperty

- ea: `0x180021f70`
- end: `0x180022335`
- name: `MSCryptEccSetKeyProperty`
- size: `965`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, _DWORD *, unsigned int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180021c50`
- `0x180021de0`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180021f70`
- `0x180022340`
- `0x1800228b0`
- `0x18006c254`
- `0x18007f765`

## string_xrefs

- `0x1800220e8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022106`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18002216e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800221b9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18002221b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022251`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180022296`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800222b0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800222d7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18008159c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetKeyProperty(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int a5)
{
  unsigned __int64 v5; // rdi
  _DWORD *v6; // r14
  const wchar_t *v7; // rsi
  __int64 *v9; // rcx
  int v10; // edx
  int v11; // r8d
  _WORD *v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // r9
  __int64 v15; // r9
  int Curve; // eax
  unsigned int v17; // ebx
  __int64 v19; // r9
  _QWORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rdx

  v5 = a4;
  v6 = a3;
  v7 = a2;
  if ( !a1 )
  {
    v17 = -1073741811;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        51);
      v20 = WPP_GLOBAL_Control;
    }
    goto LABEL_32;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    v17 = -1073741811;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v17;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        60);
      v20 = WPP_GLOBAL_Control;
    }
LABEL_32:
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v20[2],
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        162);
    return v17;
  }
  LODWORD(a3) = a5;
  for ( LODWORD(a2) = 0; ; LODWORD(a2) = (_DWORD)a2 + 1 )
  {
    if ( (unsigned int)a2 >= 4 )
    {
      v17 = -1073741811;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v17;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          a5,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          116);
        v20 = WPP_GLOBAL_Control;
      }
      goto LABEL_32;
    }
    v9 = &qword_180084718;
    if ( !a5 )
      v9 = &qword_1800847D8;
    if ( *(_DWORD *)(a1 + 8) == LODWORD(v9[6 * (unsigned int)a2]) )
      break;
  }
  if ( !wcscmp_0(v7, L"ECCParameters") )
  {
    if ( !*(_QWORD *)(a1 + 16) )
    {
      Curve = AssignGenericDomainParameters((_QWORD *)(a1 + 16), *(_DWORD *)(a1 + 8), v6, v5, 0, 0);
      v17 = Curve;
      if ( Curve >= 0 )
        return v17;
      v19 = 3767;
LABEL_48:
      DebugTraceError(
        (unsigned int)Curve,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        v19);
      return v17;
    }
    v21 = 3760;
    goto LABEL_51;
  }
  if ( wcscmp_0(v7, L"ECCCurveName") )
  {
    if ( !wcscmp_0(v7, L"KeyLength") || !wcscmp_0(v7, L"KeyStrength") )
    {
      if ( (_DWORD)v5 != 4 || !v6 || (v24 = *(_QWORD *)(a1 + 16)) == 0 )
      {
        v17 = -1073741811;
        v21 = 3812;
        v22 = 3221225485LL;
        goto LABEL_53;
      }
      v25 = *(_QWORD *)(v24 + 8);
      if ( *(_DWORD *)(v25 + 12) == *v6 || *(_DWORD *)(v25 + 24) == *v6 )
        return 0;
      v21 = 3825;
    }
    else
    {
      if ( (unsigned int)(*(_DWORD *)(a1 + 8) - 196615) <= 3 && !wcscmp_0(v7, L"PrivKeyVal") )
      {
        v23 = SetEccPrivateKeyVal(a1, v6, (unsigned int)v5);
        v17 = v23;
        if ( v23 >= 0 )
          return v17;
        v21 = 3839;
        v22 = (unsigned int)v23;
LABEL_53:
        DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v21);
        return v17;
      }
      v21 = 3846;
    }
LABEL_51:
    v17 = -1073741637;
    v22 = 3221225659LL;
    goto LABEL_53;
  }
  if ( !*(_QWORD *)(a1 + 16) )
  {
    if ( (unsigned int)v5 < 2 || !v6 )
      goto LABEL_42;
    v12 = v6;
    v13 = v5 >> 1;
    if ( v5 >> 1 )
    {
      while ( *v12 )
      {
        ++v12;
        if ( !--v13 )
          goto LABEL_17;
      }
      v14 = (v5 >> 1) - v13;
    }
    else
    {
LABEL_17:
      v14 = 0;
    }
    if ( v13 )
    {
      v15 = 2 * v14;
      if ( v5 != v15 )
      {
        Curve = LoadCurve(a1 + 16, *(unsigned int *)(a1 + 8), v6, (unsigned int)(v15 + 2));
        v17 = Curve;
        if ( Curve >= 0 )
          return v17;
        v19 = 3799;
        goto LABEL_48;
      }
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 1048);
    }
    else
    {
LABEL_42:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          17);
    }
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 3792);
    return 3221225485LL;
  }
  v17 = -1073741637;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v11,
      (unsigned int)"Status",
      187,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      200);
  return v17;
}

```

## disassembly

```asm
0x180021f70  push    rbx
0x180021f72  push    rbp
0x180021f73  push    rsi
0x180021f74  push    rdi
0x180021f75  push    r14
0x180021f77  sub     rsp, 40h
0x180021f7b  mov     edi, r9d
0x180021f7e  mov     r14, r8
0x180021f81  mov     rsi, rdx
0x180021f84  mov     rbx, rcx
0x180021f87  test    rcx, rcx
0x180021f8a  jz      loc_1800220C4
0x180021f90  cmp     dword ptr [rcx+4], 4D534B59h
0x180021f97  jnz     loc_180022159
0x180021f9d  mov     r8d, [rsp+68h+arg_20]
0x180021fa5  lea     r10, qword_1800847D8
0x180021fac  xor     ebp, ebp
0x180021fae  lea     r9, qword_180084718
0x180021fb5  mov     edx, ebp
0x180021fb7  cmp     edx, 4
0x180021fba  jnb     loc_1800220F1
0x180021fc0  test    r8d, r8d
0x180021fc3  mov     eax, edx
0x180021fc5  mov     rcx, r9
0x180021fc8  cmovz   rcx, r10
0x180021fcc  lea     rax, [rax+rax*2]
0x180021fd0  add     rax, rax
0x180021fd3  mov     eax, [rcx+rax*8]
0x180021fd6  cmp     [rbx+8], eax
0x180021fd9  jz      short loc_180021FDF
0x180021fdb  inc     edx
0x180021fdd  jmp     short loc_180021FB7
0x180021fdf  lea     rdx, aEccparameters; "ECCParameters"
0x180021fe6  mov     rcx, rsi; String1
0x180021fe9  call    wcscmp_0
0x180021fee  test    eax, eax
0x180021ff0  jz      loc_18002208E
0x180021ff6  lea     rdx, aEcccurvename; "ECCCurveName"
0x180021ffd  mov     rcx, rsi; String1
0x180022000  call    wcscmp_0
0x180022005  test    eax, eax
0x180022007  jnz     loc_1800815B5
0x18002200d  cmp     [rbx+10h], rbp
0x180022011  jnz     loc_1800221ED
0x180022017  cmp     edi, 2
0x18002201a  jb      loc_180022234
0x180022020  test    r14, r14
0x180022023  jz      loc_180022234
0x180022029  mov     rcx, rdi
0x18002202c  mov     rax, r14
0x18002202f  shr     rcx, 1
0x180022032  mov     r9, rcx
0x180022035  jz      short loc_180022046
0x180022037  cmp     [rax], bp
0x18002203a  jz      short loc_18002204B
0x18002203c  add     rax, 2
0x180022040  sub     rcx, 1
0x180022044  jnz     short loc_180022037
0x180022046  mov     r9, rbp
0x180022049  jmp     short loc_18002204E
0x18002204b  sub     r9, rcx
0x18002204e  test    rcx, rcx
0x180022051  jz      loc_180022234
0x180022057  add     r9, r9
0x18002205a  cmp     rdi, r9
0x18002205d  jz      loc_1800222B0
0x180022063  mov     edx, [rbx+8]
0x180022066  lea     rcx, [rbx+10h]
0x18002206a  add     r9d, 2
0x18002206e  mov     r8, r14
0x180022071  call    LoadCurve
0x180022076  mov     ebx, eax
0x180022078  test    eax, eax
0x18002207a  js      loc_180022290
0x180022080  mov     eax, ebx
0x180022082  add     rsp, 40h
0x180022086  pop     r14
0x180022088  pop     rdi
0x180022089  pop     rsi
0x18002208a  pop     rbp
0x18002208b  pop     rbx
0x18002208c  retn
0x18002208e  cmp     [rbx+10h], rbp
0x180022092  lea     rcx, [rbx+10h]
0x180022096  jnz     loc_180022285
0x18002209c  mov     edx, [rbx+8]
0x18002209f  mov     r9d, edi
0x1800220a2  mov     dword ptr [rsp+68h+var_40], ebp
0x1800220a6  mov     r8, r14
0x1800220a9  mov     [rsp+68h+var_48], rbp
0x1800220ae  call    AssignGenericDomainParameters
0x1800220b3  mov     ebx, eax
0x1800220b5  test    eax, eax
0x1800220b7  jns     short loc_180022080
0x1800220b9  mov     r9d, 0EB7h
0x1800220bf  jmp     loc_180022296
0x1800220c4  mov     ebx, 0C000000Dh
0x1800220c9  mov     ebp, ebx
0x1800220cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220d2  lea     rdi, WPP_GLOBAL_Control
0x1800220d9  cmp     rcx, rdi
0x1800220dc  jz      short loc_1800220E8
0x1800220de  test    byte ptr [rcx+1Ch], 1
0x1800220e2  jnz     loc_1800221B5
0x1800220e8  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800220ef  jmp     short loc_180022120
0x1800220f1  mov     ebx, 0C000000Dh
0x1800220f6  mov     ebp, ebx
0x1800220f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220ff  lea     rdi, WPP_GLOBAL_Control
0x180022106  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002210d  cmp     rcx, rdi
0x180022110  jz      loc_180022080
0x180022116  test    byte ptr [rcx+1Ch], 1
0x18002211a  jnz     loc_180022304
0x180022120  cmp     rcx, rdi
0x180022123  jz      loc_180022080
0x180022129  test    byte ptr [rcx+1Ch], 1
0x18002212d  jz      loc_180022080
0x180022133  mov     [rsp+68h+var_38], 0EA2h
0x18002213b  mov     [rsp+68h+var_40], rsi
0x180022140  mov     dword ptr [rsp+68h+var_48], ebp
0x180022144  mov     rcx, [rcx+10h]
0x180022148  lea     r9, aStatus; "Status"
0x18002214f  call    WPP_SF_sDsd
0x180022154  jmp     loc_180022080
0x180022159  mov     ebx, 0C000000Dh
0x18002215e  mov     ebp, ebx
0x180022160  mov     rcx, cs:WPP_GLOBAL_Control
0x180022167  lea     rdi, WPP_GLOBAL_Control
0x18002216e  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022175  cmp     rcx, rdi
0x180022178  jz      loc_180022080
0x18002217e  test    byte ptr [rcx+1Ch], 1
0x180022182  jz      short loc_180022120
0x180022184  mov     rcx, [rcx+10h]
0x180022188  lea     r9, aStatus; "Status"
0x18002218f  mov     [rsp+68h+var_38], 23Ch
0x180022197  mov     [rsp+68h+var_40], rsi
0x18002219c  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x1800221a4  call    WPP_SF_sDsd
0x1800221a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221b0  jmp     loc_180022120
0x1800221b5  mov     rcx, [rcx+10h]
0x1800221b9  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800221c0  mov     [rsp+68h+var_38], 233h
0x1800221c8  lea     r9, aStatus; "Status"
0x1800221cf  mov     [rsp+68h+var_40], rsi
0x1800221d4  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x1800221dc  call    WPP_SF_sDsd
0x1800221e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221e8  jmp     loc_180022120
0x1800221ed  mov     ebx, 0C00000BBh
0x1800221f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221f9  lea     rdi, WPP_GLOBAL_Control
0x180022200  cmp     rcx, rdi
0x180022203  jz      loc_180022080
0x180022209  test    byte ptr [rcx+1Ch], 1
0x18002220d  jz      loc_180022080
0x180022213  mov     [rsp+68h+var_38], 0EC8h
0x18002221b  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022222  mov     [rsp+68h+var_40], rsi
0x180022227  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x18002222f  jmp     loc_180022144
0x180022234  mov     rcx, cs:WPP_GLOBAL_Control
0x18002223b  lea     rdi, WPP_GLOBAL_Control
0x180022242  cmp     rcx, rdi
0x180022245  jz      short loc_180022251
0x180022247  test    byte ptr [rcx+1Ch], 1
0x18002224b  jnz     loc_1800222D3
0x180022251  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022258  mov     r9d, 0ED0h
0x18002225e  lea     rdx, aStatus; "Status"
0x180022265  mov     r8, rsi
0x180022268  mov     ecx, 0C000000Dh
0x18002226d  mov     ebx, 0C000000Dh
0x180022272  call    DebugTraceError
0x180022277  mov     eax, ebx
0x180022279  add     rsp, 40h
0x18002227d  pop     r14
0x18002227f  pop     rdi
0x180022280  pop     rsi
0x180022281  pop     rbp
0x180022282  pop     rbx
0x180022283  retn
0x180022285  mov     r9d, 0EB0h
0x18002228b  jmp     loc_180081580
0x180022290  mov     r9d, 0ED7h
0x180022296  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002229d  mov     ecx, eax
0x18002229f  lea     rdx, aStatus; "Status"
0x1800222a6  call    DebugTraceError
0x1800222ab  jmp     loc_180022080
0x1800222b0  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800222b7  mov     r9d, 418h
0x1800222bd  mov     r8, rsi
0x1800222c0  lea     rdx, aStatus; "Status"
0x1800222c7  mov     ecx, 0C000000Dh
0x1800222cc  call    DebugTraceError
0x1800222d1  jmp     short loc_180022258
0x1800222d3  mov     rcx, [rcx+10h]
0x1800222d7  lea     rsi, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800222de  mov     [rsp+68h+var_38], 411h
0x1800222e6  lea     r9, aStatus; "Status"
0x1800222ed  mov     [rsp+68h+var_40], rsi
0x1800222f2  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x1800222fa  call    WPP_SF_sDsd
0x1800222ff  jmp     loc_180022258
0x180022304  mov     rcx, [rcx+10h]
0x180022308  lea     r9, aStatus; "Status"
0x18002230f  mov     [rsp+68h+var_38], 274h
0x180022317  mov     [rsp+68h+var_40], rsi
0x18002231c  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x180022324  call    WPP_SF_sDsd
0x180022329  mov     rcx, cs:WPP_GLOBAL_Control
0x180022330  jmp     loc_180022120
0x18008157a  mov     r9d, 0EF1h
0x180081580  mov     ebx, 0C00000BBh
0x180081585  mov     ecx, 0C00000BBh
0x18008158a  jmp     short loc_18008159C
0x18008158c  mov     ebx, 0C000000Dh
0x180081591  mov     r9d, 0EE4h
0x180081597  mov     ecx, 0C000000Dh
0x18008159c  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800815a3  lea     rdx, aStatus; "Status"
0x1800815aa  call    DebugTraceError
0x1800815af  nop
0x1800815b0  jmp     loc_180022080
0x1800815b5  lea     rdx, aKeylength; "KeyLength"
0x1800815bc  mov     rcx, rsi; String1
0x1800815bf  call    wcscmp_0
0x1800815c4  test    eax, eax
0x1800815c6  jz      short loc_18008162B
0x1800815c8  lea     rdx, aKeystrength; "KeyStrength"
0x1800815cf  mov     rcx, rsi; String1
0x1800815d2  call    wcscmp_0
0x1800815d7  test    eax, eax
0x1800815d9  jz      short loc_18008162B
0x1800815db  mov     eax, [rbx+8]
0x1800815de  sub     eax, 30007h
0x1800815e3  cmp     eax, 3
0x1800815e6  ja      short loc_180081620
0x1800815e8  lea     rdx, aPrivkeyval; "PrivKeyVal"
0x1800815ef  mov     rcx, rsi; String1
0x1800815f2  call    wcscmp_0
0x1800815f7  test    eax, eax
0x1800815f9  jnz     short loc_180081620
0x1800815fb  mov     r8d, edi
0x1800815fe  mov     rdx, r14
0x180081601  mov     rcx, rbx
0x180081604  call    SetEccPrivateKeyVal
0x180081609  mov     ebx, eax
0x18008160b  test    eax, eax
0x18008160d  jns     loc_180022080
0x180081613  mov     r9d, 0EFFh
0x180081619  mov     ecx, eax
0x18008161b  jmp     loc_18008159C
0x180081620  mov     r9d, 0F06h
0x180081626  jmp     loc_180081580
0x18008162b  cmp     edi, 4
0x18008162e  jnz     loc_18008158C
0x180081634  test    r14, r14
0x180081637  jz      loc_18008158C
0x18008163d  mov     rax, [rbx+10h]
0x180081641  test    rax, rax
0x180081644  jz      loc_18008158C
0x18008164a  mov     rdx, [rax+8]
0x18008164e  mov     ecx, [r14]
0x180081651  cmp     [rdx+0Ch], ecx
0x180081654  jz      short loc_18008165F
0x180081656  cmp     [rdx+18h], ecx
0x180081659  jnz     loc_18008157A
0x18008165f  mov     ebx, ebp
0x180081661  jmp     loc_180022080
```
