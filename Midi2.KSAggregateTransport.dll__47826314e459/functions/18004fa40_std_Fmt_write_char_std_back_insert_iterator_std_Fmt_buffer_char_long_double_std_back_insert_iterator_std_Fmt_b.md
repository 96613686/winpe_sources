# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,long double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18004fa40`
- end: `0x18005010a`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@OAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
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
- `0x18004fa40`
- `0x180053d44`
- `0x180054654`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18004fd5b`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18004fd5b`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x18004fb5c`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x18004fb5c`

## pseudocode

```c
_QWORD *__fastcall std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(
        _QWORD *a1,
        __int64 a2,
        long double a3,
        __int64 a4,
        __int64 a5)
{
  char v7; // si
  char v8; // r13
  int v9; // edx
  char v10; // r15
  int v11; // edi
  int v12; // r12d
  int v13; // ecx
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
  v9 = *(_DWORD *)(a4 + 4);
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
      if ( v9 == -1 )
        v9 = 6;
      v11 = 2;
      goto LABEL_28;
    case 'G':
      v7 = 1;
LABEL_13:
      if ( v9 == -1 )
      {
        v9 = 6;
      }
      else if ( !v9 )
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
  if ( v9 == -1 )
    v9 = 6;
  v11 = 1;
LABEL_28:
  v61 = 0;
  v12 = v9;
  if ( v9 > 1074 )
    v12 = 1074;
  v63 = v12;
  v13 = v9 - 1074;
  if ( v9 <= 1074 )
    v13 = 0;
  v57 = v13;
  v53 = _ldsign(a3) != 0;
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
        *(_BYTE *)(*(_QWORD *)(a2 + 8) + (*(_QWORD *)(a2 + 16))++) = v46;
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
0x18004fa40  mov     rax, rsp
0x18004fa43  mov     [rax+10h], rbx
0x18004fa47  push    rbp
0x18004fa48  push    rsi
0x18004fa49  push    rdi
0x18004fa4a  push    r12
0x18004fa4c  push    r13
0x18004fa4e  push    r14
0x18004fa50  push    r15
0x18004fa52  lea     rbp, [rax-628h]
0x18004fa59  sub     rsp, 6F0h
0x18004fa60  movaps  xmmword ptr [rax-48h], xmm6
0x18004fa64  mov     rax, cs:__security_cookie
0x18004fa6b  xor     rax, rsp
0x18004fa6e  mov     [rbp+620h+var_50], rax
0x18004fa75  mov     r14, r9
0x18004fa78  movaps  xmm6, xmm2
0x18004fa7b  mov     rbx, rdx
0x18004fa7e  mov     [rbp+620h+var_688], rcx
0x18004fa82  mov     al, [r9+0Ah]
0x18004fa86  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18004fa8a  mov     r9d, 2
0x18004fa90  test    al, al
0x18004fa92  jnz     short loc_18004FA99
0x18004fa94  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18004fa99  xor     sil, sil
0x18004fa9c  mov     r13b, 65h ; 'e'
0x18004fa9f  mov     edx, [r14+4]
0x18004faa3  xor     r15b, r15b
0x18004faa6  movsx   ecx, byte ptr [r14+8]
0x18004faab  mov     edi, 4
0x18004fab0  lea     r8d, [rdi-3]
0x18004fab4  sub     ecx, 41h ; 'A'
0x18004fab7  jz      short loc_18004FB25
0x18004fab9  sub     ecx, edi
0x18004fabb  jz      short loc_18004FB12
0x18004fabd  sub     ecx, r8d
0x18004fac0  jz      short loc_18004FAFF
0x18004fac2  sub     ecx, r8d
0x18004fac5  jz      short loc_18004FAE3
0x18004fac7  sub     ecx, 1Ah
0x18004faca  jz      short loc_18004FB28
0x18004facc  sub     ecx, edi
0x18004face  jz      short loc_18004FB15
0x18004fad0  sub     ecx, r8d
0x18004fad3  jz      short loc_18004FB02
0x18004fad5  cmp     ecx, r8d
0x18004fad8  jz      short loc_18004FAE6
0x18004fada  lea     edi, [r8+2]
0x18004fade  mov     r15b, r8b
0x18004fae1  jmp     short loc_18004FB2B
0x18004fae3  mov     sil, r8b
0x18004fae6  cmp     edx, 0FFFFFFFFh
0x18004fae9  jnz     short loc_18004FAF2
0x18004faeb  mov     edx, 6
0x18004faf0  jmp     short loc_18004FAF8
0x18004faf2  test    edx, edx
0x18004faf4  cmovz   edx, r8d
0x18004faf8  mov     edi, 3
0x18004fafd  jmp     short loc_18004FB2B
0x18004faff  mov     sil, r8b
0x18004fb02  mov     eax, 6
0x18004fb07  cmp     edx, 0FFFFFFFFh
0x18004fb0a  cmovz   edx, eax
0x18004fb0d  mov     edi, r9d
0x18004fb10  jmp     short loc_18004FB2B
0x18004fb12  mov     sil, r8b
0x18004fb15  mov     eax, 6
0x18004fb1a  cmp     edx, 0FFFFFFFFh
0x18004fb1d  cmovz   edx, eax
0x18004fb20  mov     edi, r8d
0x18004fb23  jmp     short loc_18004FB2B
0x18004fb25  mov     sil, r8b
0x18004fb28  mov     r13b, 70h ; 'p'
0x18004fb2b  xorps   xmm0, xmm0
0x18004fb2e  movups  [rsp+720h+var_6C8+8], xmm0
0x18004fb33  mov     r12d, edx
0x18004fb36  mov     r8d, 432h
0x18004fb3c  cmp     edx, r8d
0x18004fb3f  cmovg   r12d, r8d
0x18004fb43  mov     [rbp+620h+var_6A0], r12d
0x18004fb47  lea     ecx, [rdx-432h]
0x18004fb4d  xor     eax, eax
0x18004fb4f  cmp     edx, r8d
0x18004fb52  cmovle  ecx, eax
0x18004fb55  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18004fb59  movaps  xmm0, xmm6; X
0x18004fb5c  call    cs:__imp__ldsign
0x18004fb62  mov     edx, eax
0x18004fb64  test    eax, eax
0x18004fb66  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18004fb6b  ucomisd xmm6, xmm6
0x18004fb6f  setp    al
0x18004fb72  cmp     al, 1
0x18004fb74  jnz     short loc_18004FBAB
0x18004fb76  lea     rax, [rbp+620h+var_5C0]
0x18004fb7a  lea     rcx, [rbp+620h+var_5BF]
0x18004fb7e  test    edx, edx
0x18004fb80  cmovz   rcx, rax
0x18004fb84  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x18004fb89  mov     eax, dword ptr cs:aNan; "nan"
0x18004fb8f  mov     [rcx], ax
0x18004fb92  mov     al, byte ptr cs:aNan+2; "n"
0x18004fb98  mov     [rcx+2], al
0x18004fb9b  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18004fba0  add     r9, 3
0x18004fba4  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x18004fba9  jmp     short loc_18004FBF8
0x18004fbab  movaps  xmm3, xmm6
0x18004fbae  lea     r8, [rbp+620h+var_57]
0x18004fbb5  lea     rdx, [rbp+620h+var_5C0]
0x18004fbb9  lea     rcx, [rsp+720h+var_6B8+8]
0x18004fbbe  cmp     r12d, 0FFFFFFFFh
0x18004fbc2  jnz     short loc_18004FBDB
0x18004fbc4  test    r15b, r15b
0x18004fbc7  jz      short loc_18004FBD0
0x18004fbc9  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18004fbce  jmp     short loc_18004FBE9
0x18004fbd0  mov     [rsp+720h+var_700], edi
0x18004fbd4  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x18004fbd9  jmp     short loc_18004FBE9
0x18004fbdb  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18004fbe0  mov     [rsp+720h+var_700], edi
0x18004fbe4  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x18004fbe9  movaps  xmm0, [rsp+720h+var_6B8+8]
0x18004fbee  movaps  [rsp+720h+var_6C8+8], xmm0
0x18004fbf3  movq    r9, xmm0
0x18004fbf8  lea     rdx, [rbp+620h+var_5C0]
0x18004fbfc  mov     [rsp+720h+var_6D8], rdx
0x18004fc01  mov     ecx, r9d
0x18004fc04  sub     ecx, edx
0x18004fc06  mov     [rsp+720h+var_6E8], ecx
0x18004fc0a  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18004fc0f  jz      short loc_18004FC1C
0x18004fc11  lea     rdx, [rbp+620h+var_5BF]
0x18004fc15  mov     [rsp+720h+var_6D8], rdx
0x18004fc1a  jmp     short loc_18004FC29
0x18004fc1c  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18004fc21  jz      short loc_18004FC29
0x18004fc23  inc     ecx
0x18004fc25  mov     [rsp+720h+var_6E8], ecx
0x18004fc29  test    sil, sil
0x18004fc2c  jz      short loc_18004FC5B
0x18004fc2e  cmp     rdx, r9
0x18004fc31  jz      short loc_18004FC57
0x18004fc33  mov     cl, [rdx]
0x18004fc35  lea     eax, [rcx-61h]
0x18004fc38  cmp     al, 19h
0x18004fc3a  ja      short loc_18004FC41
0x18004fc3c  sub     cl, 20h ; ' '
0x18004fc3f  mov     [rdx], cl
0x18004fc41  inc     rdx
0x18004fc44  cmp     rdx, r9
0x18004fc47  jnz     short loc_18004FC33
0x18004fc49  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18004fc4e  mov     rdx, [rsp+720h+var_6D8]
0x18004fc53  mov     ecx, [rsp+720h+var_6E8]
0x18004fc57  add     r13b, 0E0h
0x18004fc5b  movq    rax, xmm6
0x18004fc60  shr     rax, 34h
0x18004fc64  mov     r8d, 7FFh
0x18004fc6a  and     eax, r8d
0x18004fc6d  cmp     eax, r8d
0x18004fc70  setnz   al
0x18004fc73  xor     al, 1
0x18004fc75  mov     byte ptr [rsp+720h+var_6F0], al
0x18004fc79  mov     r15b, 0
0x18004fc7c  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18004fc81  mov     r10, r9
0x18004fc84  mov     [rsp+720h+var_6D0], r9
0x18004fc89  mov     r11, r9
0x18004fc8c  mov     [rbp+620h+var_690], r9
0x18004fc90  mov     [rbp+620h+var_698], r9
0x18004fc94  mov     r8d, 0
0x18004fc9a  mov     [rsp+720h+var_6E4], r8d
0x18004fc9f  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18004fca4  xorps   xmm0, xmm0
0x18004fca7  movups  [rbp+620h+var_600], xmm0
0x18004fcab  mov     [rbp+620h+var_5F0], r8
0x18004fcaf  mov     [rbp+620h+var_5E8], 0Fh
0x18004fcb7  mov     byte ptr [rbp+620h+var_600], r8b
0x18004fcbb  jnz     loc_18004FF08
0x18004fcc1  mov     r12b, [r14+0Bh]
0x18004fcc5  test    r12b, r12b
0x18004fcc8  jnz     short loc_18004FCD7
0x18004fcca  lea     rsi, [r14+0Ch]
0x18004fcce  cmp     [rsi], r12b
0x18004fcd1  jz      loc_18004FE3F
0x18004fcd7  mov     rax, rdx
0x18004fcda  cmp     rdx, r9
0x18004fcdd  jnb     short loc_18004FD0A
0x18004fcdf  cmp     byte ptr [rax], 2Eh ; '.'
0x18004fce2  jnz     short loc_18004FCED
0x18004fce4  mov     r11, rax
0x18004fce7  mov     [rbp+620h+var_690], rax
0x18004fceb  jmp     short loc_18004FCFA
0x18004fced  cmp     [rax], r13b
0x18004fcf0  jnz     short loc_18004FCFA
0x18004fcf2  mov     r10, rax
0x18004fcf5  mov     [rsp+720h+var_6D0], rax
0x18004fcfa  inc     rax
0x18004fcfd  cmp     rax, r9
0x18004fd00  jb      short loc_18004FCDF
0x18004fd02  cmp     r10, r11
0x18004fd05  mov     rax, r10
0x18004fd08  jb      short loc_18004FD0D
0x18004fd0a  mov     rax, r11
0x18004fd0d  mov     [rbp+620h+var_698], rax
0x18004fd11  test    r12b, r12b
0x18004fd14  jz      short loc_18004FD29
0x18004fd16  cmp     r11, r9
0x18004fd19  jnz     short loc_18004FD29
0x18004fd1b  inc     ecx
0x18004fd1d  mov     [rsp+720h+var_6E8], ecx
0x18004fd21  mov     r15b, 1
0x18004fd24  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18004fd29  lea     rsi, [r14+0Ch]
0x18004fd2d  cmp     byte ptr [rsi], 0
0x18004fd30  jz      loc_18004FE3F
0x18004fd36  mov     rax, [rbp+620h+arg_20]
0x18004fd3d  test    rax, rax
0x18004fd40  jz      short loc_18004FD59
0x18004fd42  mov     rcx, [rax+8]
0x18004fd46  mov     [rsp+720h+var_6A8], rcx
0x18004fd4b  mov     rax, [rcx]
0x18004fd4e  mov     rax, [rax+8]
0x18004fd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd57  jmp     short loc_18004FD66
0x18004fd59  mov     cl, 1
0x18004fd5b  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18004fd61  mov     [rsp+720h+var_6A8], rax
0x18004fd66  lea     rcx, [rsp+720h+var_6B8+8]
0x18004fd6b  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18004fd70  mov     rcx, rax
0x18004fd73  mov     rax, [rax]
0x18004fd76  lea     rdx, [rbp+620h+var_5E0]
0x18004fd7a  mov     rax, [rax+28h]
0x18004fd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd83  lea     rdx, [rbp+620h+var_5E0]
0x18004fd87  lea     rcx, [rbp+620h+var_600]
0x18004fd8b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18004fd90  lea     rcx, [rbp+620h+var_5E0]
0x18004fd94  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004fd99  nop
0x18004fd9a  mov     rcx, [rsp+720h+var_6A8]
0x18004fd9f  test    rcx, rcx
0x18004fda2  jz      short loc_18004FDC8
0x18004fda4  mov     rax, [rcx]
0x18004fda7  mov     rax, [rax+10h]
0x18004fdab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fdb0  mov     rcx, rax
0x18004fdb3  test    rax, rax
0x18004fdb6  jz      short loc_18004FDC8
0x18004fdb8  mov     rax, [rax]
0x18004fdbb  mov     edx, 1
0x18004fdc0  mov     rax, [rax]
0x18004fdc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fdc8  lea     rax, [rbp+620h+var_600]
0x18004fdcc  cmp     [rbp+620h+var_5E8], 0Fh
0x18004fdd1  cmova   rax, qword ptr [rbp+620h+var_600]
0x18004fdd6  mov     r10, [rbp+620h+var_5F0]
0x18004fdda  mov     rdx, [rsp+720h+var_6D8]
0x18004fddf  xor     r8d, r8d
0x18004fde2  test    r10, r10
0x18004fde5  jz      short loc_18004FE1B
0x18004fde7  mov     r9, [rbp+620h+var_698]
0x18004fdeb  sub     r9, rdx
0x18004fdee  movsx   r11, byte ptr [rax]
0x18004fdf2  cmp     r9, r11
0x18004fdf5  jbe     short loc_18004FE1B
0x18004fdf7  add     r10, rax
0x18004fdfa  movsx   rcx, r11b
0x18004fdfe  sub     r9, rcx
0x18004fe01  inc     r8d
0x18004fe04  lea     rcx, [rax+1]
0x18004fe08  cmp     rcx, r10
0x18004fe0b  cmovz   rcx, rax
0x18004fe0f  mov     rax, rcx
0x18004fe12  movsx   r11, byte ptr [rcx]
0x18004fe16  cmp     r9, r11
0x18004fe19  ja      short loc_18004FDFA
0x18004fe1b  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18004fe20  mov     ecx, [rsp+720h+var_6E8]
0x18004fe24  add     ecx, r8d
0x18004fe27  mov     [rsp+720h+var_6E8], ecx
0x18004fe2b  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18004fe30  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x18004fe35  mov     r10, [rsp+720h+var_6D0]
0x18004fe3a  mov     r8d, [rsp+720h+var_6E4]
0x18004fe3f  sub     edi, 1
0x18004fe42  jz      loc_18004FED5
0x18004fe48  sub     edi, 1
0x18004fe4b  jz      loc_18004FEFA
0x18004fe51  cmp     edi, 1
0x18004fe54  jnz     short loc_18004FED5
0x18004fe56  cmp     byte ptr [r14+0Bh], 0
0x18004fe5b  jz      loc_18004FF04
0x18004fe61  mov     al, [r14+8]
0x18004fe65  sub     al, 47h ; 'G'
0x18004fe67  test    al, 0DFh
  ... truncated ...
```
