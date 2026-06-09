# CFormattedDateTime::ParseKeyword(wchar_t const *,unsigned __int64,tagFORMAT_OPTION,DATETIMEPARSE *,wchar_t const * *,unsigned __int64 *)

- ea: `0x180005090`
- end: `0x180005440`
- name: `?ParseKeyword@CFormattedDateTime@@AEAAJPEB_W_KW4tagFORMAT_OPTION@@PEAUDATETIMEPARSE@@PEAPEB_WPEA_K@Z`
- size: `944`
- prototype: `int __high(const wchar_t *, unsigned __int64, enum tagFORMAT_OPTION, struct DATETIMEPARSE *, const wchar_t **, unsigned __int64 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002320`
- `0x180003e40`
- `0x180005450`
- `0x180005794`
- `0x180005c10`

## callees

- `0x180005090`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x180005158`
- `api-ms-win-core-localization-l1-2-0!FindNLSStringEx` at `0x180005158`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800051aa`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800051aa`

## pseudocode

```c
__int64 __fastcall CFormattedDateTime::ParseKeyword(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        int a4,
        _DWORD *a5,
        _QWORD *a6,
        unsigned __int64 *a7)
{
  __int64 v7; // r15
  int v8; // r10d
  __int64 v9; // r13
  _QWORD *v10; // rbp
  unsigned __int64 v11; // r14
  unsigned __int64 cchValue; // rbx
  __int64 v13; // rax
  __int64 lpStringValue; // rdi
  _QWORD *v15; // r12
  DWORD v16; // edx
  int NLSString; // eax
  int v18; // eax
  int v19; // eax
  unsigned int v20; // edx
  __int64 result; // rax
  int *v22; // rcx
  int v23; // r9d
  _DWORD *v24; // r13
  int v25; // r15d
  int v26; // r8d
  _DWORD *v27; // r9
  _DWORD *v28; // rcx
  int v29; // r10d
  int v30; // r10d
  int v31; // r10d
  int v32; // r10d
  int v33; // edx
  int v34; // [rsp+50h] [rbp-58h]
  int pcchFound; // [rsp+54h] [rbp-54h] BYREF
  _DWORD *v36; // [rsp+58h] [rbp-50h]
  unsigned __int64 cchCount1; // [rsp+C0h] [rbp+18h]

  cchCount1 = a3;
  v7 = a1;
  v8 = a4;
  v34 = 0;
  v9 = a2;
  v36 = 0;
  v10 = *(_QWORD **)(a1 + 320);
  v11 = (unsigned __int64)&v10[4 * *(_QWORD *)(a1 + 328)];
  while ( (unsigned __int64)v10 < v11 )
  {
    cchValue = -1;
    v13 = 4 * (((__int64)(v11 - (_QWORD)v10) >> 5) / 2);
    lpStringValue = v10[v13 + 2];
    v15 = &v10[v13];
    do
      ++cchValue;
    while ( *(_WORD *)(lpStringValue + 2 * cchValue) );
    v16 = *(_DWORD *)(v7 + 188) | 0x100000;
    pcchFound = 0;
    NLSString = FindNLSStringEx(
                  (LPCWSTR)(v7 + 8),
                  v16,
                  (LPCWSTR)v9,
                  a3,
                  (LPCWSTR)lpStringValue,
                  cchValue,
                  &pcchFound,
                  0,
                  0,
                  0);
    if ( NLSString < 0 )
    {
      a3 = cchCount1;
      if ( *(_DWORD *)(v7 + 180) != 1028
        || cchCount1 < 2
        || cchValue < 2
        || *(_WORD *)(v9 + 2) != 21320
        || *(_WORD *)(lpStringValue + 2) != 21320 )
      {
        goto LABEL_7;
      }
      if ( *(_WORD *)v9 == 19978 )
      {
        if ( *(_WORD *)lpStringValue == 19979 )
          goto LABEL_14;
LABEL_7:
        v18 = CompareStringEx(
                (LPCWSTR)(v7 + 8),
                *(_DWORD *)(v7 + 188),
                (LPCWCH)v9,
                cchCount1,
                (LPCWCH)lpStringValue,
                cchValue,
                0,
                0,
                0);
        a3 = cchCount1;
        v19 = v18 - 1;
        if ( !v19 )
        {
LABEL_14:
          v8 = a4;
          v11 = (unsigned __int64)v15;
          continue;
        }
        if ( v19 != 2 )
        {
LABEL_9:
          v20 = -2147418113;
          goto LABEL_10;
        }
      }
      else if ( *(_WORD *)v9 != 19979 || *(_WORD *)lpStringValue != 19978 )
      {
        goto LABEL_7;
      }
      v8 = a4;
      v10 = v15 + 4;
      continue;
    }
    v22 = (int *)v15[3];
    v23 = NLSString + pcchFound;
    v8 = a4;
    if ( !v22 )
      goto LABEL_34;
    v24 = v36;
    v25 = v34;
    do
    {
      v26 = *v22;
      if ( a4 != 15 )
      {
        switch ( a4 )
        {
          case 3:
          case 4:
            if ( (unsigned int)(v26 - 3) > 1 )
              goto LABEL_32;
            goto LABEL_26;
          case 6:
          case 7:
            if ( (unsigned int)(v26 - 6) > 1 )
              goto LABEL_32;
            goto LABEL_26;
          case 10:
            if ( v26 != 10 )
              goto LABEL_32;
            goto LABEL_26;
        }
        if ( a4 != 16 )
          goto LABEL_32;
      }
      if ( (unsigned int)(v26 - 15) > 1 )
        goto LABEL_32;
LABEL_26:
      if ( !v24 || v23 > v25 || v23 == v25 && *v24 != a4 && v26 == a4 )
      {
        v25 = NLSString + pcchFound;
        v24 = v22;
      }
LABEL_32:
      v22 = (int *)*((_QWORD *)v22 + 3);
    }
    while ( v22 );
    v34 = v25;
    v7 = a1;
    v36 = v24;
    v9 = a2;
LABEL_34:
    v10 = (_QWORD *)*v15;
    a3 = cchCount1;
    v11 = *v15 + 32LL * v15[1];
  }
  v27 = v36;
  if ( v36 )
  {
    v33 = v36[4];
    if ( v8 != 3 )
    {
      switch ( v8 )
      {
        case 4:
          break;
        case 6:
        case 7:
          v28 = a5;
          a5[47] = v33;
          a5[44] |= 0x40000u;
          goto LABEL_59;
        case 10:
          v28 = a5;
          a5[45] = v33;
          a5[44] |= 0x10000u;
          goto LABEL_59;
        case 15:
        case 16:
          v28 = a5;
          a5[53] = v33;
          a5[44] |= 0x1000000u;
          goto LABEL_59;
        default:
          goto LABEL_9;
      }
    }
    v28 = a5;
    a5[52] = v33;
    a5[44] |= 0x800000u;
LABEL_59:
    if ( v34 > (int)a3 )
      goto LABEL_48;
    if ( v8 != *v27 )
      v28[44] |= 0x2000u;
    a3 -= v34;
    v9 += 2LL * v34;
    v20 = 0;
  }
  else
  {
    v28 = a5;
LABEL_48:
    if ( v8 == 3 )
      goto LABEL_49;
    v20 = 1;
    if ( v8 == 15 )
      goto LABEL_10;
    v29 = v8 - 4;
    if ( !v29 )
      goto LABEL_49;
    v30 = v29 - 2;
    if ( !v30 )
      goto LABEL_10;
    v31 = v30 - 1;
    if ( !v31 )
      goto LABEL_10;
    v32 = v31 - 3;
    if ( !v32 )
    {
LABEL_49:
      v28[44] |= 0x4000u;
      v20 = 0;
      goto LABEL_10;
    }
    if ( v32 != 6 )
      goto LABEL_9;
  }
LABEL_10:
  result = v20;
  *a6 = v9;
  *a7 = a3;
  return result;
}

```

## disassembly

```asm
0x180005090  mov     [rsp+arg_18], r9d
0x180005095  mov     qword ptr [rsp+cchCount1], r8
0x18000509a  mov     [rsp+arg_8], rdx
0x18000509f  mov     [rsp+arg_0], rcx
0x1800050a4  push    rbx
0x1800050a5  push    rbp
0x1800050a6  push    rdi
0x1800050a7  push    r13
0x1800050a9  push    r14
0x1800050ab  push    r15
0x1800050ad  sub     rsp, 78h
0x1800050b1  mov     r15, rcx
0x1800050b4  mov     [rsp+0A8h+var_38], rsi
0x1800050b9  xor     ecx, ecx
0x1800050bb  mov     [rsp+0A8h+var_40], r12
0x1800050c0  mov     r10d, r9d
0x1800050c3  mov     [rsp+0A8h+var_58], ecx
0x1800050c7  mov     r13, rdx
0x1800050ca  mov     [rsp+0A8h+var_50], rcx
0x1800050cf  mov     r14, [r15+148h]
0x1800050d6  mov     rbp, [r15+140h]
0x1800050dd  shl     r14, 5
0x1800050e1  add     r14, rbp
0x1800050e4  cmp     rbp, r14
0x1800050e7  jnb     loc_180005363
0x1800050ed  mov     rax, r14
0x1800050f0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800050f7  sub     rax, rbp
0x1800050fa  sar     rax, 5
0x1800050fe  cqo
0x180005100  sub     rax, rdx
0x180005103  sar     rax, 1
0x180005106  shl     rax, 5
0x18000510a  mov     rdi, [rax+rbp+10h]
0x18000510f  lea     r12, [rax+rbp]
0x180005113  inc     rbx
0x180005116  cmp     word ptr [rdi+rbx*2], 0
0x18000511b  jnz     short loc_180005113
0x18000511d  mov     edx, [r15+0BCh]
0x180005124  lea     rax, [rsp+0A8h+var_54]
0x180005129  mov     [rsp+0A8h+sortHandle], rcx; sortHandle
0x18000512e  mov     r9d, r8d; cchSource
0x180005131  mov     [rsp+0A8h+lpReserved], rcx; lpReserved
0x180005136  bts     edx, 14h; dwFindNLSStringFlags
0x18000513a  mov     [rsp+0A8h+lpVersionInformation], rcx; lpVersionInformation
0x18000513f  mov     r8, r13; lpStringSource
0x180005142  mov     [rsp+0A8h+pcchFound], rax; pcchFound
0x180005147  mov     [rsp+0A8h+var_54], ecx
0x18000514b  lea     rcx, [r15+8]; lpLocaleName
0x18000514f  mov     [rsp+0A8h+cchValue], ebx; cchValue
0x180005153  mov     [rsp+0A8h+lpStringValue], rdi; lpStringValue
0x180005158  call    cs:__imp_FindNLSStringEx
0x18000515e  test    eax, eax
0x180005160  jns     loc_18000525E
0x180005166  cmp     dword ptr [r15+0B4h], 404h
0x180005171  mov     r8, qword ptr [rsp+0A8h+cchCount1]
0x180005179  jz      loc_180005238
0x18000517f  xor     edx, edx
0x180005181  lea     rcx, [r15+8]; lpLocaleName
0x180005185  mov     [rsp+0A8h+lpReserved], rdx; lParam
0x18000518a  mov     r9d, r8d; cchCount1
0x18000518d  mov     [rsp+0A8h+lpVersionInformation], rdx; lpReserved
0x180005192  mov     r8, r13; lpString1
0x180005195  mov     [rsp+0A8h+pcchFound], rdx; lpVersionInformation
0x18000519a  mov     edx, [r15+0BCh]; dwCmpFlags
0x1800051a1  mov     [rsp+0A8h+cchValue], ebx; cchCount2
0x1800051a5  mov     [rsp+0A8h+lpStringValue], rdi; lpString2
0x1800051aa  call    cs:__imp_CompareStringEx
0x1800051b0  mov     r8, qword ptr [rsp+0A8h+cchCount1]
0x1800051b8  sub     eax, 1
0x1800051bb  jz      short loc_180005226
0x1800051bd  cmp     eax, 2
0x1800051c0  jz      loc_180005333
0x1800051c6  mov     edx, 8000FFFFh; jumptable 0000000180087150 default case, cases 5,8,9,11-14
0x1800051cb  mov     rcx, [rsp+0A8h+arg_28]
0x1800051d3  mov     eax, edx
0x1800051d5  mov     r12, [rsp+0A8h+var_40]
0x1800051da  mov     rsi, [rsp+0A8h+var_38]
0x1800051df  mov     [rcx], r13
0x1800051e2  mov     rcx, [rsp+0A8h+arg_30]
0x1800051ea  mov     [rcx], r8
0x1800051ed  add     rsp, 78h
0x1800051f1  pop     r15
0x1800051f3  pop     r14
0x1800051f5  pop     r13
0x1800051f7  pop     rdi
0x1800051f8  pop     rbp
0x1800051f9  pop     rbx
0x1800051fa  retn
0x1800051fb  cmp     [rdi+2], ax
0x1800051ff  jnz     loc_18000517F
0x180005205  movzx   eax, word ptr [r13+0]
0x18000520a  mov     edx, 4E0Ah
0x18000520f  cmp     ax, dx
0x180005212  jnz     loc_18000531C
0x180005218  mov     eax, 4E0Bh
0x18000521d  cmp     [rdi], ax
0x180005220  jnz     loc_18000517F
0x180005226  mov     r10d, [rsp+0A8h+arg_18]
0x18000522e  mov     r14, r12
0x180005231  xor     ecx, ecx
0x180005233  jmp     loc_1800050E4
0x180005238  cmp     r8, 2
0x18000523c  jb      loc_18000517F
0x180005242  cmp     rbx, 2
0x180005246  jb      loc_18000517F
0x18000524c  mov     eax, 5348h
0x180005251  cmp     [r13+2], ax
0x180005256  jnz     loc_18000517F
0x18000525c  jmp     short loc_1800051FB
0x18000525e  mov     r9d, [rsp+0A8h+var_54]
0x180005263  mov     rcx, [r12+18h]
0x180005268  add     r9d, eax
0x18000526b  mov     r10d, [rsp+0A8h+arg_18]
0x180005273  test    rcx, rcx
0x180005276  jz      short loc_1800052E5
0x180005278  mov     r13, [rsp+0A8h+var_50]
0x18000527d  mov     r15d, [rsp+0A8h+var_58]
0x180005282  mov     r8d, [rcx]
0x180005285  cmp     r10d, 0Fh
0x180005289  jz      short loc_18000529C
0x18000528b  cmp     r10d, 3
0x18000528f  jnz     short loc_180005304
0x180005291  lea     eax, [r8-3]
0x180005295  cmp     eax, 1
0x180005298  jbe     short loc_1800052A5
0x18000529a  jmp     short loc_1800052C2
0x18000529c  lea     eax, [r8-0Fh]
0x1800052a0  cmp     eax, 1
0x1800052a3  ja      short loc_1800052C2
0x1800052a5  test    r13, r13
0x1800052a8  jz      short loc_1800052BC
0x1800052aa  cmp     r9d, r15d
0x1800052ad  jg      short loc_1800052BC
0x1800052af  jnz     short loc_1800052C2
0x1800052b1  cmp     [r13+0], r10d
0x1800052b5  jz      short loc_1800052C2
0x1800052b7  cmp     r8d, r10d
0x1800052ba  jnz     short loc_1800052C2
0x1800052bc  mov     r15d, r9d
0x1800052bf  mov     r13, rcx
0x1800052c2  mov     rcx, [rcx+18h]
0x1800052c6  test    rcx, rcx
0x1800052c9  jnz     short loc_180005282
0x1800052cb  mov     [rsp+0A8h+var_58], r15d
0x1800052d0  mov     r15, [rsp+0A8h+arg_0]
0x1800052d8  mov     [rsp+0A8h+var_50], r13
0x1800052dd  mov     r13, [rsp+0A8h+arg_8]
0x1800052e5  mov     r14, [r12+8]
0x1800052ea  mov     rbp, [r12]
0x1800052ee  mov     r8, qword ptr [rsp+0A8h+cchCount1]
0x1800052f6  shl     r14, 5
0x1800052fa  add     r14, rbp
0x1800052fd  xor     ecx, ecx
0x1800052ff  jmp     loc_1800050E4
0x180005304  mov     edx, r10d
0x180005307  sub     edx, 4
0x18000530a  jz      short loc_180005291
0x18000530c  sub     edx, 2
0x18000530f  jnz     short loc_180005347
0x180005311  lea     eax, [r8-6]
0x180005315  cmp     eax, 1
0x180005318  ja      short loc_1800052C2
0x18000531a  jmp     short loc_1800052A5
0x18000531c  mov     ecx, 4E0Bh
0x180005321  cmp     ax, cx
0x180005324  jnz     loc_18000517F
0x18000532a  cmp     [rdi], dx
0x18000532d  jnz     loc_18000517F
0x180005333  mov     r10d, [rsp+0A8h+arg_18]
0x18000533b  lea     rbp, [r12+20h]
0x180005340  xor     ecx, ecx
0x180005342  jmp     loc_1800050E4
0x180005347  sub     edx, 1
0x18000534a  jz      short loc_180005311
0x18000534c  sub     edx, 3
0x18000534f  jz      loc_180005425
0x180005355  cmp     edx, 6
0x180005358  jnz     loc_1800052C2
0x18000535e  jmp     loc_18000529C
0x180005363  mov     r9, [rsp+0A8h+var_50]
0x180005368  test    r9, r9
0x18000536b  jnz     short loc_1800053C9
0x18000536d  mov     rcx, [rsp+0A8h+arg_20]
0x180005375  cmp     r10d, 3
0x180005379  jnz     short loc_18000538C
0x18000537b  or      dword ptr [rcx+0B0h], 4000h
0x180005385  xor     edx, edx
0x180005387  jmp     loc_1800051CB
0x18000538c  mov     edx, 1
0x180005391  cmp     r10d, 0Fh
0x180005395  jz      loc_1800051CB
0x18000539b  sub     r10d, 4
0x18000539f  jz      short loc_18000537B
0x1800053a1  sub     r10d, 2
0x1800053a5  jz      loc_1800051CB
0x1800053ab  sub     r10d, edx
0x1800053ae  jz      loc_1800051CB
0x1800053b4  sub     r10d, 3
0x1800053b8  jz      short loc_18000537B
0x1800053ba  cmp     r10d, 6
0x1800053be  jz      loc_1800051CB
0x1800053c4  jmp     def_180087150; jumptable 0000000180087150 default case, cases 5,8,9,11-14
0x1800053c9  mov     edx, [r9+10h]
0x1800053cd  cmp     r10d, 3
0x1800053d1  jnz     short loc_180005413
0x1800053d3  mov     rcx, [rsp+0A8h+arg_20]; jumptable 0000000180087150 case 4
0x1800053db  mov     [rcx+0D0h], edx
0x1800053e1  or      dword ptr [rcx+0B0h], 800000h
0x1800053eb  movsxd  r11, [rsp+0A8h+var_58]
0x1800053f0  mov     eax, [rcx+0B0h]
0x1800053f6  cmp     r11d, r8d
0x1800053f9  jg      loc_180005375
0x1800053ff  cmp     r10d, [r9]
0x180005402  jnz     short loc_180005434
0x180005404  sub     r8, r11
0x180005407  lea     r13, [r13+r11*2+0]
0x18000540c  xor     edx, edx
0x18000540e  jmp     loc_1800051CB
0x180005413  lea     eax, [r10-4]; switch 13 cases
0x180005417  cmp     eax, 0Ch
0x18000541a  ja      def_180087150; jumptable 0000000180087150 default case, cases 5,8,9,11-14
0x180005420  jmp     loc_18008713C
0x180005425  cmp     r8d, 0Ah
0x180005429  jnz     loc_1800052C2
0x18000542f  jmp     loc_1800052A5
0x180005434  bts     eax, 0Dh
0x180005438  mov     [rcx+0B0h], eax
0x18000543e  jmp     short loc_180005404
0x18008713c  lea     r11, __ImageBase
0x180087143  cdqe
0x180087145  mov     ecx, ds:(jpt_180087150 - 180000000h)[r11+rax*4]
0x18008714d  add     rcx, r11
0x180087150  jmp     rcx; switch jump
0x180087152  mov     rcx, [rsp+0A8h+arg_20]; jumptable 0000000180087150 case 10
0x18008715a  mov     [rcx+0B4h], edx
0x180087160  or      dword ptr [rcx+0B0h], 10000h
0x18008716a  jmp     loc_1800053EB
0x18008716f  mov     rcx, [rsp+0A8h+arg_20]; jumptable 0000000180087150 cases 6,7
0x180087177  mov     [rcx+0BCh], edx
0x18008717d  or      dword ptr [rcx+0B0h], 40000h
0x180087187  jmp     loc_1800053EB
0x18008718c  mov     rcx, [rsp+0A8h+arg_20]; jumptable 0000000180087150 cases 15,16
0x180087194  mov     [rcx+0D4h], edx
0x18008719a  or      dword ptr [rcx+0B0h], 1000000h
0x1800871a4  jmp     loc_1800053EB
```
