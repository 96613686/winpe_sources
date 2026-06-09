# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18004f370`
- end: `0x18004fa3a`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@N@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@NAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1738`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180051498`

## callees

- `0x180005020`
- `0x18002afd4`
- `0x18002b100`
- `0x18002b2ac`
- `0x1800342a8`
- `0x180034450`
- `0x18004f370`
- `0x180053d44`
- `0x180054654`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18004f68b`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18004f68b`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18004f48c`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18004f48c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,double>(
        _QWORD *a1,
        __int64 a2,
        double a3,
        __int64 a4,
        __int64 a5)
{
  char v7; // si
  char v8; // r13
  __int64 v9; // rdx
  char v10; // r15
  int v11; // edi
  int v12; // r12d
  __int64 v13; // rcx
  char *v14; // r9
  char *v15; // rdx
  int v16; // ecx
  bool v17; // al
  char v18; // r15
  char *v19; // r10
  char *v20; // r11
  int v21; // r8d
  char v22; // r12
  _BYTE *v23; // rsi
  char *v24; // rax
  char *v25; // rax
  __int64 v26; // rax
  void (__fastcall ***v27)(_QWORD, __int64); // rax
  char *v28; // rax
  int v29; // r8d
  unsigned __int64 v30; // r9
  unsigned __int64 v31; // r11
  char *v32; // r10
  char *v33; // rcx
  int v34; // edi
  int v35; // edi
  int v36; // eax
  int v37; // ecx
  bool v38; // al
  int v40; // esi
  int v41; // edi
  char v42; // al
  char *v43; // r15
  __int64 v44; // r14
  char *i; // r12
  char v46; // r13
  __int64 v47; // rbx
  char *j; // rsi
  char v49; // r12
  _QWORD *v50; // rdi
  char v51; // [rsp+39h] [rbp-CFh] BYREF
  char v52; // [rsp+3Ah] [rbp-CEh] BYREF
  bool v53; // [rsp+3Bh] [rbp-CDh] BYREF
  int v54; // [rsp+3Ch] [rbp-CCh] BYREF
  int v55; // [rsp+40h] [rbp-C8h] BYREF
  int v56; // [rsp+44h] [rbp-C4h] BYREF
  int v57; // [rsp+48h] [rbp-C0h]
  int v58; // [rsp+4Ch] [rbp-BCh] BYREF
  char *v59; // [rsp+50h] [rbp-B8h] BYREF
  char *v60; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v61; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v62; // [rsp+78h] [rbp-90h] BYREF
  int v63; // [rsp+88h] [rbp-80h] BYREF
  char *v64; // [rsp+90h] [rbp-78h] BYREF
  char *v65; // [rsp+98h] [rbp-70h] BYREF
  _QWORD *v66; // [rsp+A0h] [rbp-68h]
  _QWORD v67[16]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v68; // [rsp+128h] [rbp+20h] BYREF
  __int64 v69; // [rsp+138h] [rbp+30h]
  unsigned __int64 v70; // [rsp+140h] [rbp+38h]
  _BYTE v71[32]; // [rsp+148h] [rbp+40h] BYREF
  char v72; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v73[1384]; // [rsp+169h] [rbp+61h] BYREF
  _BYTE v74[7]; // [rsp+6D1h] [rbp+5C9h] BYREF

  v66 = a1;
  v51 = *(_BYTE *)(a4 + 10);
  if ( !v51 )
    v51 = 2;
  v7 = 0;
  v8 = 101;
  v9 = *(unsigned int *)(a4 + 4);
  v10 = 0;
  v11 = 4;
  switch ( *(_BYTE *)(a4 + 8) )
  {
    case 'A':
      v7 = 1;
      goto LABEL_27;
    case 'E':
      v7 = 1;
      goto LABEL_23;
    case 'F':
      v7 = 1;
LABEL_19:
      if ( (_DWORD)v9 == -1 )
        v9 = 6;
      v11 = 2;
      goto LABEL_28;
    case 'G':
      v7 = 1;
LABEL_13:
      if ( (_DWORD)v9 == -1 )
      {
        v9 = 6;
      }
      else if ( !(_DWORD)v9 )
      {
        v9 = 1;
      }
      v11 = 3;
      goto LABEL_28;
    case 'a':
LABEL_27:
      v8 = 112;
      goto LABEL_28;
  }
  if ( *(_BYTE *)(a4 + 8) != 101 )
  {
    if ( *(_BYTE *)(a4 + 8) != 102 )
    {
      if ( *(_BYTE *)(a4 + 8) != 103 )
      {
        v11 = 3;
        v10 = 1;
        goto LABEL_28;
      }
      goto LABEL_13;
    }
    goto LABEL_19;
  }
LABEL_23:
  if ( (_DWORD)v9 == -1 )
    v9 = 6;
  v11 = 1;
LABEL_28:
  v61 = 0;
  v12 = v9;
  if ( (int)v9 > 1074 )
    v12 = 1074;
  v63 = v12;
  v13 = (unsigned int)(v9 - 1074);
  if ( (int)v9 <= 1074 )
    v13 = 0;
  v57 = v13;
  v53 = (unsigned int)_o__dsign(v13, v9, 1074, 2) != 0;
  if ( v12 == -1 )
  {
    if ( v10 )
      std::_Floating_to_chars<0,double>(&v62, &v72, v74);
    else
      std::_Floating_to_chars<1,double>(&v62, &v72, v74);
  }
  else
  {
    std::_Floating_to_chars<2,double>(&v62, &v72, v74);
  }
  v61 = v62;
  v14 = (char *)v62;
  v15 = &v72;
  v59 = &v72;
  v16 = v62 - (unsigned int)&v72;
  v55 = v16;
  if ( v53 )
  {
    v15 = v73;
    v59 = v73;
  }
  else if ( v51 != 2 )
  {
    v55 = ++v16;
  }
  if ( v7 )
  {
    if ( v15 != (char *)v62 )
    {
      do
      {
        if ( (unsigned __int8)(*v15 - 97) <= 0x19u )
          *v15 -= 32;
        ++v15;
      }
      while ( v15 != v14 );
      v14 = (char *)v61;
      v15 = v59;
      v16 = v55;
    }
    v8 -= 32;
  }
  v17 = ((*(_QWORD *)&a3 >> 52) & 0x7FF) == 2047;
  v18 = 0;
  v52 = 0;
  v19 = v14;
  v60 = v14;
  v20 = v14;
  v65 = v14;
  v64 = v14;
  v21 = 0;
  v56 = 0;
  v58 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 15;
  LOBYTE(v68) = 0;
  if ( ((*(_QWORD *)&a3 >> 52) & 0x7FF) != 0x7FF )
  {
    v22 = *(_BYTE *)(a4 + 11);
    if ( v22 || (v23 = (_BYTE *)(a4 + 12), *(_BYTE *)(a4 + 12)) )
    {
      v24 = v15;
      if ( v15 >= v14 )
        goto LABEL_58;
      do
      {
        if ( *v24 == 46 )
        {
          v20 = v24;
          v65 = v24;
        }
        else if ( *v24 == v8 )
        {
          v19 = v24;
          v60 = v24;
        }
        ++v24;
      }
      while ( v24 < v14 );
      v25 = v19;
      if ( v19 >= v20 )
LABEL_58:
        v25 = v20;
      v64 = v25;
      if ( v22 && v20 == v14 )
      {
        v55 = ++v16;
        v18 = 1;
        v52 = 1;
      }
      v23 = (_BYTE *)(a4 + 12);
      if ( *(_BYTE *)(a4 + 12) )
      {
        if ( a5 )
        {
          *((_QWORD *)&v62 + 1) = *(_QWORD *)(a5 + 8);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v62 + 1) + 8LL))(*((_QWORD *)&v62 + 1));
        }
        else
        {
          *((_QWORD *)&v62 + 1) = std::locale::_Init(1);
        }
        v26 = std::use_facet<std::numpunct<char>>(&v62);
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v26 + 40LL))(v26, v71);
        std::string::operator=(&v68, v71);
        std::string::~string(v71);
        if ( *((_QWORD *)&v62 + 1) )
        {
          v27 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)&v62 + 1)
                                                                                          + 16LL))(*((_QWORD *)&v62 + 1));
          if ( v27 )
            (**v27)(v27, 1);
        }
        v28 = (char *)&v68;
        if ( v70 > 0xF )
          v28 = (char *)v68;
        v15 = v59;
        v29 = 0;
        if ( v69 )
        {
          v30 = v64 - v59;
          v31 = *v28;
          if ( v64 - v59 > v31 )
          {
            v32 = &v28[v69];
            do
            {
              v30 -= (char)v31;
              ++v29;
              v33 = v28 + 1;
              if ( v28 + 1 == v32 )
                v33 = v28;
              v28 = v33;
              v31 = *v33;
            }
            while ( v30 > v31 );
          }
        }
        v58 = v29;
        v16 = v29 + v55;
        v55 += v29;
        v14 = (char *)v61;
        v18 = v52;
        v19 = v60;
        v21 = v56;
      }
    }
    v34 = v11 - 1;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
      {
        v21 = v57;
LABEL_101:
        v56 = v21;
LABEL_102:
        v17 = 0;
        goto LABEL_103;
      }
      if ( v35 == 1 )
      {
        if ( *(_BYTE *)(a4 + 11) && ((*(_BYTE *)(a4 + 8) - 71) & 0xDF) == 0 )
        {
          v36 = (_DWORD)v19 - (_DWORD)v15;
          if ( !v18 )
            --v36;
          v21 = v63 + v57 - v36;
          v56 = v21;
          if ( v19 == v14 && COERCE_DOUBLE(*(_QWORD *)&a3 & _xmm) < 1.0 && a3 != 0.0 )
          {
            while ( v15 < v14 )
            {
              if ( *v15 == 48 )
              {
                v56 = ++v21;
              }
              else if ( *v15 != 46 )
              {
                goto LABEL_102;
              }
              ++v15;
            }
          }
        }
        goto LABEL_102;
      }
    }
    v21 = v57;
    if ( v57 && !*(_BYTE *)(a4 + 11) && !*v23 )
    {
      do
        v60 = --v19;
      while ( *v19 != v8 );
    }
    goto LABEL_101;
  }
LABEL_103:
  v37 = v21 + v16;
  v55 = v37;
  v38 = *(_BYTE *)(a4 + 13) && !*(_BYTE *)(a4 + 9) && !v17;
  LOBYTE(v54) = v38;
  v67[0] = &v51;
  v67[1] = &v53;
  v67[2] = &v54;
  v67[3] = &v55;
  v67[4] = a4;
  v67[5] = &a5;
  v67[6] = &v59;
  v67[7] = &v64;
  v67[8] = &v68;
  v67[9] = &v58;
  v67[10] = &v65;
  v67[11] = &v61;
  v67[12] = &v52;
  v67[13] = &v60;
  v67[14] = &v56;
  if ( v38 )
  {
    `std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
      v67,
      v66,
      a2);
    std::string::~string(&v68);
    return v66;
  }
  else
  {
    v40 = 0;
    v41 = 0;
    v42 = *(_BYTE *)(a4 + 9);
    if ( !v42 )
      v42 = 2;
    if ( v37 < *(_DWORD *)a4 )
    {
      switch ( v42 )
      {
        case 1:
          v41 = *(_DWORD *)a4 - v37;
          break;
        case 2:
          v40 = *(_DWORD *)a4 - v37;
          break;
        case 3:
          v40 = (*(_DWORD *)a4 - v37) / 2;
          v41 = *(_DWORD *)a4 - v37 - v40;
          break;
      }
    }
    v43 = (char *)(a4 + 15);
    v44 = a4 + 15 + *(unsigned __int8 *)(a4 + 14);
    while ( v40 > 0 )
    {
      for ( i = v43; i != (char *)v44; ++i )
      {
        v46 = *i;
        if ( (unsigned __int64)(*(_QWORD *)(a2 + 16) + 1LL) > *(_QWORD *)(a2 + 24) )
          (**(void (__fastcall ***)(__int64))a2)(a2);
        *(_BYTE *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 8)) = v46;
        ++*(_QWORD *)(a2 + 16);
      }
      --v40;
    }
    v47 = *(_QWORD *)`std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
                       v67,
                       &v63,
                       a2);
    while ( v41 > 0 )
    {
      for ( j = v43; j != (char *)v44; ++j )
      {
        v49 = *j;
        if ( (unsigned __int64)(*(_QWORD *)(v47 + 16) + 1LL) > *(_QWORD *)(v47 + 24) )
          (**(void (__fastcall ***)(__int64))v47)(v47);
        *(_BYTE *)(*(_QWORD *)(v47 + 16) + *(_QWORD *)(v47 + 8)) = v49;
        ++*(_QWORD *)(v47 + 16);
      }
      --v41;
    }
    v50 = v66;
    *v66 = v47;
    std::string::~string(&v68);
    return v50;
  }
}

```

## disassembly

```asm
0x18004f370  mov     rax, rsp
0x18004f373  mov     [rax+10h], rbx
0x18004f377  push    rbp
0x18004f378  push    rsi
0x18004f379  push    rdi
0x18004f37a  push    r12
0x18004f37c  push    r13
0x18004f37e  push    r14
0x18004f380  push    r15
0x18004f382  lea     rbp, [rax-628h]
0x18004f389  sub     rsp, 6F0h
0x18004f390  movaps  xmmword ptr [rax-48h], xmm6
0x18004f394  mov     rax, cs:__security_cookie
0x18004f39b  xor     rax, rsp
0x18004f39e  mov     [rbp+620h+var_50], rax
0x18004f3a5  mov     r14, r9
0x18004f3a8  movaps  xmm6, xmm2
0x18004f3ab  mov     rbx, rdx
0x18004f3ae  mov     [rbp+620h+var_688], rcx
0x18004f3b2  mov     al, [r9+0Ah]
0x18004f3b6  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18004f3ba  mov     r9d, 2
0x18004f3c0  test    al, al
0x18004f3c2  jnz     short loc_18004F3C9
0x18004f3c4  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18004f3c9  xor     sil, sil
0x18004f3cc  mov     r13b, 65h ; 'e'
0x18004f3cf  mov     edx, [r14+4]
0x18004f3d3  xor     r15b, r15b
0x18004f3d6  movsx   ecx, byte ptr [r14+8]
0x18004f3db  mov     edi, 4
0x18004f3e0  lea     r8d, [rdi-3]
0x18004f3e4  sub     ecx, 41h ; 'A'
0x18004f3e7  jz      short loc_18004F455
0x18004f3e9  sub     ecx, edi
0x18004f3eb  jz      short loc_18004F442
0x18004f3ed  sub     ecx, r8d
0x18004f3f0  jz      short loc_18004F42F
0x18004f3f2  sub     ecx, r8d
0x18004f3f5  jz      short loc_18004F413
0x18004f3f7  sub     ecx, 1Ah
0x18004f3fa  jz      short loc_18004F458
0x18004f3fc  sub     ecx, edi
0x18004f3fe  jz      short loc_18004F445
0x18004f400  sub     ecx, r8d
0x18004f403  jz      short loc_18004F432
0x18004f405  cmp     ecx, r8d
0x18004f408  jz      short loc_18004F416
0x18004f40a  lea     edi, [r8+2]
0x18004f40e  mov     r15b, r8b
0x18004f411  jmp     short loc_18004F45B
0x18004f413  mov     sil, r8b
0x18004f416  cmp     edx, 0FFFFFFFFh
0x18004f419  jnz     short loc_18004F422
0x18004f41b  mov     edx, 6
0x18004f420  jmp     short loc_18004F428
0x18004f422  test    edx, edx
0x18004f424  cmovz   edx, r8d
0x18004f428  mov     edi, 3
0x18004f42d  jmp     short loc_18004F45B
0x18004f42f  mov     sil, r8b
0x18004f432  mov     eax, 6
0x18004f437  cmp     edx, 0FFFFFFFFh
0x18004f43a  cmovz   edx, eax
0x18004f43d  mov     edi, r9d
0x18004f440  jmp     short loc_18004F45B
0x18004f442  mov     sil, r8b
0x18004f445  mov     eax, 6
0x18004f44a  cmp     edx, 0FFFFFFFFh
0x18004f44d  cmovz   edx, eax
0x18004f450  mov     edi, r8d
0x18004f453  jmp     short loc_18004F45B
0x18004f455  mov     sil, r8b
0x18004f458  mov     r13b, 70h ; 'p'
0x18004f45b  xorps   xmm0, xmm0
0x18004f45e  movups  [rsp+720h+var_6C8+8], xmm0
0x18004f463  mov     r12d, edx
0x18004f466  mov     r8d, 432h
0x18004f46c  cmp     edx, r8d
0x18004f46f  cmovg   r12d, r8d
0x18004f473  mov     [rbp+620h+var_6A0], r12d
0x18004f477  lea     ecx, [rdx-432h]
0x18004f47d  xor     eax, eax
0x18004f47f  cmp     edx, r8d
0x18004f482  cmovle  ecx, eax
0x18004f485  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18004f489  movaps  xmm0, xmm6
0x18004f48c  call    cs:__imp__o__dsign
0x18004f492  mov     edx, eax
0x18004f494  test    eax, eax
0x18004f496  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18004f49b  ucomisd xmm6, xmm6
0x18004f49f  setp    al
0x18004f4a2  cmp     al, 1
0x18004f4a4  jnz     short loc_18004F4DB
0x18004f4a6  lea     rax, [rbp+620h+var_5C0]
0x18004f4aa  lea     rcx, [rbp+620h+var_5BF]
0x18004f4ae  test    edx, edx
0x18004f4b0  cmovz   rcx, rax
0x18004f4b4  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x18004f4b9  mov     eax, dword ptr cs:aNan; "nan"
0x18004f4bf  mov     [rcx], ax
0x18004f4c2  mov     al, byte ptr cs:aNan+2; "n"
0x18004f4c8  mov     [rcx+2], al
0x18004f4cb  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18004f4d0  add     r9, 3
0x18004f4d4  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x18004f4d9  jmp     short loc_18004F528
0x18004f4db  movaps  xmm3, xmm6
0x18004f4de  lea     r8, [rbp+620h+var_57]
0x18004f4e5  lea     rdx, [rbp+620h+var_5C0]
0x18004f4e9  lea     rcx, [rsp+720h+var_6B8+8]
0x18004f4ee  cmp     r12d, 0FFFFFFFFh
0x18004f4f2  jnz     short loc_18004F50B
0x18004f4f4  test    r15b, r15b
0x18004f4f7  jz      short loc_18004F500
0x18004f4f9  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18004f4fe  jmp     short loc_18004F519
0x18004f500  mov     [rsp+720h+var_700], edi
0x18004f504  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x18004f509  jmp     short loc_18004F519
0x18004f50b  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18004f510  mov     [rsp+720h+var_700], edi
0x18004f514  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x18004f519  movaps  xmm0, [rsp+720h+var_6B8+8]
0x18004f51e  movaps  [rsp+720h+var_6C8+8], xmm0
0x18004f523  movq    r9, xmm0
0x18004f528  lea     rdx, [rbp+620h+var_5C0]
0x18004f52c  mov     [rsp+720h+var_6D8], rdx
0x18004f531  mov     ecx, r9d
0x18004f534  sub     ecx, edx
0x18004f536  mov     [rsp+720h+var_6E8], ecx
0x18004f53a  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18004f53f  jz      short loc_18004F54C
0x18004f541  lea     rdx, [rbp+620h+var_5BF]
0x18004f545  mov     [rsp+720h+var_6D8], rdx
0x18004f54a  jmp     short loc_18004F559
0x18004f54c  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18004f551  jz      short loc_18004F559
0x18004f553  inc     ecx
0x18004f555  mov     [rsp+720h+var_6E8], ecx
0x18004f559  test    sil, sil
0x18004f55c  jz      short loc_18004F58B
0x18004f55e  cmp     rdx, r9
0x18004f561  jz      short loc_18004F587
0x18004f563  mov     cl, [rdx]
0x18004f565  lea     eax, [rcx-61h]
0x18004f568  cmp     al, 19h
0x18004f56a  ja      short loc_18004F571
0x18004f56c  sub     cl, 20h ; ' '
0x18004f56f  mov     [rdx], cl
0x18004f571  inc     rdx
0x18004f574  cmp     rdx, r9
0x18004f577  jnz     short loc_18004F563
0x18004f579  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18004f57e  mov     rdx, [rsp+720h+var_6D8]
0x18004f583  mov     ecx, [rsp+720h+var_6E8]
0x18004f587  add     r13b, 0E0h
0x18004f58b  movq    rax, xmm6
0x18004f590  shr     rax, 34h
0x18004f594  mov     r8d, 7FFh
0x18004f59a  and     eax, r8d
0x18004f59d  cmp     eax, r8d
0x18004f5a0  setnz   al
0x18004f5a3  xor     al, 1
0x18004f5a5  mov     byte ptr [rsp+720h+var_6F0], al
0x18004f5a9  mov     r15b, 0
0x18004f5ac  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18004f5b1  mov     r10, r9
0x18004f5b4  mov     [rsp+720h+var_6D0], r9
0x18004f5b9  mov     r11, r9
0x18004f5bc  mov     [rbp+620h+var_690], r9
0x18004f5c0  mov     [rbp+620h+var_698], r9
0x18004f5c4  mov     r8d, 0
0x18004f5ca  mov     [rsp+720h+var_6E4], r8d
0x18004f5cf  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18004f5d4  xorps   xmm0, xmm0
0x18004f5d7  movups  [rbp+620h+var_600], xmm0
0x18004f5db  mov     [rbp+620h+var_5F0], r8
0x18004f5df  mov     [rbp+620h+var_5E8], 0Fh
0x18004f5e7  mov     byte ptr [rbp+620h+var_600], r8b
0x18004f5eb  jnz     loc_18004F838
0x18004f5f1  mov     r12b, [r14+0Bh]
0x18004f5f5  test    r12b, r12b
0x18004f5f8  jnz     short loc_18004F607
0x18004f5fa  lea     rsi, [r14+0Ch]
0x18004f5fe  cmp     [rsi], r12b
0x18004f601  jz      loc_18004F76F
0x18004f607  mov     rax, rdx
0x18004f60a  cmp     rdx, r9
0x18004f60d  jnb     short loc_18004F63A
0x18004f60f  cmp     byte ptr [rax], 2Eh ; '.'
0x18004f612  jnz     short loc_18004F61D
0x18004f614  mov     r11, rax
0x18004f617  mov     [rbp+620h+var_690], rax
0x18004f61b  jmp     short loc_18004F62A
0x18004f61d  cmp     [rax], r13b
0x18004f620  jnz     short loc_18004F62A
0x18004f622  mov     r10, rax
0x18004f625  mov     [rsp+720h+var_6D0], rax
0x18004f62a  inc     rax
0x18004f62d  cmp     rax, r9
0x18004f630  jb      short loc_18004F60F
0x18004f632  cmp     r10, r11
0x18004f635  mov     rax, r10
0x18004f638  jb      short loc_18004F63D
0x18004f63a  mov     rax, r11
0x18004f63d  mov     [rbp+620h+var_698], rax
0x18004f641  test    r12b, r12b
0x18004f644  jz      short loc_18004F659
0x18004f646  cmp     r11, r9
0x18004f649  jnz     short loc_18004F659
0x18004f64b  inc     ecx
0x18004f64d  mov     [rsp+720h+var_6E8], ecx
0x18004f651  mov     r15b, 1
0x18004f654  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18004f659  lea     rsi, [r14+0Ch]
0x18004f65d  cmp     byte ptr [rsi], 0
0x18004f660  jz      loc_18004F76F
0x18004f666  mov     rax, [rbp+620h+arg_20]
0x18004f66d  test    rax, rax
0x18004f670  jz      short loc_18004F689
0x18004f672  mov     rcx, [rax+8]
0x18004f676  mov     [rsp+720h+var_6A8], rcx
0x18004f67b  mov     rax, [rcx]
0x18004f67e  mov     rax, [rax+8]
0x18004f682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f687  jmp     short loc_18004F696
0x18004f689  mov     cl, 1
0x18004f68b  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18004f691  mov     [rsp+720h+var_6A8], rax
0x18004f696  lea     rcx, [rsp+720h+var_6B8+8]
0x18004f69b  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18004f6a0  mov     rcx, rax
0x18004f6a3  mov     rax, [rax]
0x18004f6a6  lea     rdx, [rbp+620h+var_5E0]
0x18004f6aa  mov     rax, [rax+28h]
0x18004f6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6b3  lea     rdx, [rbp+620h+var_5E0]
0x18004f6b7  lea     rcx, [rbp+620h+var_600]
0x18004f6bb  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18004f6c0  lea     rcx, [rbp+620h+var_5E0]
0x18004f6c4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004f6c9  nop
0x18004f6ca  mov     rcx, [rsp+720h+var_6A8]
0x18004f6cf  test    rcx, rcx
0x18004f6d2  jz      short loc_18004F6F8
0x18004f6d4  mov     rax, [rcx]
0x18004f6d7  mov     rax, [rax+10h]
0x18004f6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6e0  mov     rcx, rax
0x18004f6e3  test    rax, rax
0x18004f6e6  jz      short loc_18004F6F8
0x18004f6e8  mov     rax, [rax]
0x18004f6eb  mov     edx, 1
0x18004f6f0  mov     rax, [rax]
0x18004f6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6f8  lea     rax, [rbp+620h+var_600]
0x18004f6fc  cmp     [rbp+620h+var_5E8], 0Fh
0x18004f701  cmova   rax, qword ptr [rbp+620h+var_600]
0x18004f706  mov     r10, [rbp+620h+var_5F0]
0x18004f70a  mov     rdx, [rsp+720h+var_6D8]
0x18004f70f  xor     r8d, r8d
0x18004f712  test    r10, r10
0x18004f715  jz      short loc_18004F74B
0x18004f717  mov     r9, [rbp+620h+var_698]
0x18004f71b  sub     r9, rdx
0x18004f71e  movsx   r11, byte ptr [rax]
0x18004f722  cmp     r9, r11
0x18004f725  jbe     short loc_18004F74B
0x18004f727  add     r10, rax
0x18004f72a  movsx   rcx, r11b
0x18004f72e  sub     r9, rcx
0x18004f731  inc     r8d
0x18004f734  lea     rcx, [rax+1]
0x18004f738  cmp     rcx, r10
0x18004f73b  cmovz   rcx, rax
0x18004f73f  mov     rax, rcx
0x18004f742  movsx   r11, byte ptr [rcx]
0x18004f746  cmp     r9, r11
0x18004f749  ja      short loc_18004F72A
0x18004f74b  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18004f750  mov     ecx, [rsp+720h+var_6E8]
0x18004f754  add     ecx, r8d
0x18004f757  mov     [rsp+720h+var_6E8], ecx
0x18004f75b  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18004f760  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x18004f765  mov     r10, [rsp+720h+var_6D0]
0x18004f76a  mov     r8d, [rsp+720h+var_6E4]
0x18004f76f  sub     edi, 1
0x18004f772  jz      loc_18004F805
0x18004f778  sub     edi, 1
0x18004f77b  jz      loc_18004F82A
0x18004f781  cmp     edi, 1
0x18004f784  jnz     short loc_18004F805
0x18004f786  cmp     byte ptr [r14+0Bh], 0
0x18004f78b  jz      loc_18004F834
0x18004f791  mov     al, [r14+8]
0x18004f795  sub     al, 47h ; 'G'
0x18004f797  test    al, 0DFh
  ... truncated ...
```
