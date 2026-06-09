# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x14004a39c`
- end: `0x14004aa66`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@N@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@NAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1738`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, double, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14004cc34`

## callees

- `0x1400054c0`
- `0x140048718`
- `0x140048844`
- `0x1400489f0`
- `0x14004a39c`
- `0x140050554`
- `0x140050a18`
- `0x140050c40`
- `0x140051154`
- `0x14005a010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004a6b7`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x14004a6b7`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x14004a4b8`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x14004a4b8`

## pseudocode

```c
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
0x14004a39c  mov     rax, rsp
0x14004a39f  mov     [rax+10h], rbx
0x14004a3a3  push    rbp
0x14004a3a4  push    rsi
0x14004a3a5  push    rdi
0x14004a3a6  push    r12
0x14004a3a8  push    r13
0x14004a3aa  push    r14
0x14004a3ac  push    r15
0x14004a3ae  lea     rbp, [rax-628h]
0x14004a3b5  sub     rsp, 6F0h
0x14004a3bc  movaps  xmmword ptr [rax-48h], xmm6
0x14004a3c0  mov     rax, cs:__security_cookie
0x14004a3c7  xor     rax, rsp
0x14004a3ca  mov     [rbp+620h+var_50], rax
0x14004a3d1  mov     r14, r9
0x14004a3d4  movaps  xmm6, xmm2
0x14004a3d7  mov     rbx, rdx
0x14004a3da  mov     [rbp+620h+var_688], rcx
0x14004a3de  mov     al, [r9+0Ah]
0x14004a3e2  mov     byte ptr [rsp+720h+var_6F0+1], al
0x14004a3e6  mov     r9d, 2
0x14004a3ec  test    al, al
0x14004a3ee  jnz     short loc_14004A3F5
0x14004a3f0  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x14004a3f5  xor     sil, sil
0x14004a3f8  mov     r13b, 65h ; 'e'
0x14004a3fb  mov     edx, [r14+4]
0x14004a3ff  xor     r15b, r15b
0x14004a402  movsx   ecx, byte ptr [r14+8]
0x14004a407  mov     edi, 4
0x14004a40c  lea     r8d, [rdi-3]
0x14004a410  sub     ecx, 41h ; 'A'
0x14004a413  jz      short loc_14004A481
0x14004a415  sub     ecx, edi
0x14004a417  jz      short loc_14004A46E
0x14004a419  sub     ecx, r8d
0x14004a41c  jz      short loc_14004A45B
0x14004a41e  sub     ecx, r8d
0x14004a421  jz      short loc_14004A43F
0x14004a423  sub     ecx, 1Ah
0x14004a426  jz      short loc_14004A484
0x14004a428  sub     ecx, edi
0x14004a42a  jz      short loc_14004A471
0x14004a42c  sub     ecx, r8d
0x14004a42f  jz      short loc_14004A45E
0x14004a431  cmp     ecx, r8d
0x14004a434  jz      short loc_14004A442
0x14004a436  lea     edi, [r8+2]
0x14004a43a  mov     r15b, r8b
0x14004a43d  jmp     short loc_14004A487
0x14004a43f  mov     sil, r8b
0x14004a442  cmp     edx, 0FFFFFFFFh
0x14004a445  jnz     short loc_14004A44E
0x14004a447  mov     edx, 6
0x14004a44c  jmp     short loc_14004A454
0x14004a44e  test    edx, edx
0x14004a450  cmovz   edx, r8d
0x14004a454  mov     edi, 3
0x14004a459  jmp     short loc_14004A487
0x14004a45b  mov     sil, r8b
0x14004a45e  mov     eax, 6
0x14004a463  cmp     edx, 0FFFFFFFFh
0x14004a466  cmovz   edx, eax
0x14004a469  mov     edi, r9d
0x14004a46c  jmp     short loc_14004A487
0x14004a46e  mov     sil, r8b
0x14004a471  mov     eax, 6
0x14004a476  cmp     edx, 0FFFFFFFFh
0x14004a479  cmovz   edx, eax
0x14004a47c  mov     edi, r8d
0x14004a47f  jmp     short loc_14004A487
0x14004a481  mov     sil, r8b
0x14004a484  mov     r13b, 70h ; 'p'
0x14004a487  xorps   xmm0, xmm0
0x14004a48a  movups  [rsp+720h+var_6C8+8], xmm0
0x14004a48f  mov     r12d, edx
0x14004a492  mov     r8d, 432h
0x14004a498  cmp     edx, r8d
0x14004a49b  cmovg   r12d, r8d
0x14004a49f  mov     [rbp+620h+var_6A0], r12d
0x14004a4a3  lea     ecx, [rdx-432h]
0x14004a4a9  xor     eax, eax
0x14004a4ab  cmp     edx, r8d
0x14004a4ae  cmovle  ecx, eax
0x14004a4b1  mov     dword ptr [rsp+720h+var_6E0], ecx
0x14004a4b5  movaps  xmm0, xmm6
0x14004a4b8  call    cs:__imp__o__dsign
0x14004a4be  mov     edx, eax
0x14004a4c0  test    eax, eax
0x14004a4c2  setnz   byte ptr [rsp+720h+var_6F0+3]
0x14004a4c7  ucomisd xmm6, xmm6
0x14004a4cb  setp    al
0x14004a4ce  cmp     al, 1
0x14004a4d0  jnz     short loc_14004A507
0x14004a4d2  lea     rax, [rbp+620h+var_5C0]
0x14004a4d6  lea     rcx, [rbp+620h+var_5BF]
0x14004a4da  test    edx, edx
0x14004a4dc  cmovz   rcx, rax
0x14004a4e0  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x14004a4e5  mov     eax, dword ptr cs:aNan; "nan"
0x14004a4eb  mov     [rcx], ax
0x14004a4ee  mov     al, byte ptr cs:aNan+2; "n"
0x14004a4f4  mov     [rcx+2], al
0x14004a4f7  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x14004a4fc  add     r9, 3
0x14004a500  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x14004a505  jmp     short loc_14004A554
0x14004a507  movaps  xmm3, xmm6
0x14004a50a  lea     r8, [rbp+620h+var_57]
0x14004a511  lea     rdx, [rbp+620h+var_5C0]
0x14004a515  lea     rcx, [rsp+720h+var_6B8+8]
0x14004a51a  cmp     r12d, 0FFFFFFFFh
0x14004a51e  jnz     short loc_14004A537
0x14004a520  test    r15b, r15b
0x14004a523  jz      short loc_14004A52C
0x14004a525  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x14004a52a  jmp     short loc_14004A545
0x14004a52c  mov     [rsp+720h+var_700], edi
0x14004a530  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x14004a535  jmp     short loc_14004A545
0x14004a537  mov     dword ptr [rsp+720h+var_6F8], r12d
0x14004a53c  mov     [rsp+720h+var_700], edi
0x14004a540  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x14004a545  movaps  xmm0, [rsp+720h+var_6B8+8]
0x14004a54a  movaps  [rsp+720h+var_6C8+8], xmm0
0x14004a54f  movq    r9, xmm0
0x14004a554  lea     rdx, [rbp+620h+var_5C0]
0x14004a558  mov     [rsp+720h+var_6D8], rdx
0x14004a55d  mov     ecx, r9d
0x14004a560  sub     ecx, edx
0x14004a562  mov     [rsp+720h+var_6E8], ecx
0x14004a566  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x14004a56b  jz      short loc_14004A578
0x14004a56d  lea     rdx, [rbp+620h+var_5BF]
0x14004a571  mov     [rsp+720h+var_6D8], rdx
0x14004a576  jmp     short loc_14004A585
0x14004a578  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x14004a57d  jz      short loc_14004A585
0x14004a57f  inc     ecx
0x14004a581  mov     [rsp+720h+var_6E8], ecx
0x14004a585  test    sil, sil
0x14004a588  jz      short loc_14004A5B7
0x14004a58a  cmp     rdx, r9
0x14004a58d  jz      short loc_14004A5B3
0x14004a58f  mov     cl, [rdx]
0x14004a591  lea     eax, [rcx-61h]
0x14004a594  cmp     al, 19h
0x14004a596  ja      short loc_14004A59D
0x14004a598  sub     cl, 20h ; ' '
0x14004a59b  mov     [rdx], cl
0x14004a59d  inc     rdx
0x14004a5a0  cmp     rdx, r9
0x14004a5a3  jnz     short loc_14004A58F
0x14004a5a5  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x14004a5aa  mov     rdx, [rsp+720h+var_6D8]
0x14004a5af  mov     ecx, [rsp+720h+var_6E8]
0x14004a5b3  add     r13b, 0E0h
0x14004a5b7  movq    rax, xmm6
0x14004a5bc  shr     rax, 34h
0x14004a5c0  mov     r8d, 7FFh
0x14004a5c6  and     eax, r8d
0x14004a5c9  cmp     eax, r8d
0x14004a5cc  setnz   al
0x14004a5cf  xor     al, 1
0x14004a5d1  mov     byte ptr [rsp+720h+var_6F0], al
0x14004a5d5  mov     r15b, 0
0x14004a5d8  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x14004a5dd  mov     r10, r9
0x14004a5e0  mov     [rsp+720h+var_6D0], r9
0x14004a5e5  mov     r11, r9
0x14004a5e8  mov     [rbp+620h+var_690], r9
0x14004a5ec  mov     [rbp+620h+var_698], r9
0x14004a5f0  mov     r8d, 0
0x14004a5f6  mov     [rsp+720h+var_6E4], r8d
0x14004a5fb  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x14004a600  xorps   xmm0, xmm0
0x14004a603  movups  [rbp+620h+var_600], xmm0
0x14004a607  mov     [rbp+620h+var_5F0], r8
0x14004a60b  mov     [rbp+620h+var_5E8], 0Fh
0x14004a613  mov     byte ptr [rbp+620h+var_600], r8b
0x14004a617  jnz     loc_14004A864
0x14004a61d  mov     r12b, [r14+0Bh]
0x14004a621  test    r12b, r12b
0x14004a624  jnz     short loc_14004A633
0x14004a626  lea     rsi, [r14+0Ch]
0x14004a62a  cmp     [rsi], r12b
0x14004a62d  jz      loc_14004A79B
0x14004a633  mov     rax, rdx
0x14004a636  cmp     rdx, r9
0x14004a639  jnb     short loc_14004A666
0x14004a63b  cmp     byte ptr [rax], 2Eh ; '.'
0x14004a63e  jnz     short loc_14004A649
0x14004a640  mov     r11, rax
0x14004a643  mov     [rbp+620h+var_690], rax
0x14004a647  jmp     short loc_14004A656
0x14004a649  cmp     [rax], r13b
0x14004a64c  jnz     short loc_14004A656
0x14004a64e  mov     r10, rax
0x14004a651  mov     [rsp+720h+var_6D0], rax
0x14004a656  inc     rax
0x14004a659  cmp     rax, r9
0x14004a65c  jb      short loc_14004A63B
0x14004a65e  cmp     r10, r11
0x14004a661  mov     rax, r10
0x14004a664  jb      short loc_14004A669
0x14004a666  mov     rax, r11
0x14004a669  mov     [rbp+620h+var_698], rax
0x14004a66d  test    r12b, r12b
0x14004a670  jz      short loc_14004A685
0x14004a672  cmp     r11, r9
0x14004a675  jnz     short loc_14004A685
0x14004a677  inc     ecx
0x14004a679  mov     [rsp+720h+var_6E8], ecx
0x14004a67d  mov     r15b, 1
0x14004a680  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x14004a685  lea     rsi, [r14+0Ch]
0x14004a689  cmp     byte ptr [rsi], 0
0x14004a68c  jz      loc_14004A79B
0x14004a692  mov     rax, [rbp+620h+arg_20]
0x14004a699  test    rax, rax
0x14004a69c  jz      short loc_14004A6B5
0x14004a69e  mov     rcx, [rax+8]
0x14004a6a2  mov     [rsp+720h+var_6A8], rcx
0x14004a6a7  mov     rax, [rcx]
0x14004a6aa  mov     rax, [rax+8]
0x14004a6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a6b3  jmp     short loc_14004A6C2
0x14004a6b5  mov     cl, 1
0x14004a6b7  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x14004a6bd  mov     [rsp+720h+var_6A8], rax
0x14004a6c2  lea     rcx, [rsp+720h+var_6B8+8]
0x14004a6c7  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x14004a6cc  mov     rcx, rax
0x14004a6cf  mov     rax, [rax]
0x14004a6d2  lea     rdx, [rbp+620h+var_5E0]
0x14004a6d6  mov     rax, [rax+28h]
0x14004a6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a6df  lea     rdx, [rbp+620h+var_5E0]
0x14004a6e3  lea     rcx, [rbp+620h+var_600]
0x14004a6e7  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x14004a6ec  lea     rcx, [rbp+620h+var_5E0]
0x14004a6f0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004a6f5  nop
0x14004a6f6  mov     rcx, [rsp+720h+var_6A8]
0x14004a6fb  test    rcx, rcx
0x14004a6fe  jz      short loc_14004A724
0x14004a700  mov     rax, [rcx]
0x14004a703  mov     rax, [rax+10h]
0x14004a707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a70c  mov     rcx, rax
0x14004a70f  test    rax, rax
0x14004a712  jz      short loc_14004A724
0x14004a714  mov     rax, [rax]
0x14004a717  mov     edx, 1
0x14004a71c  mov     rax, [rax]
0x14004a71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a724  lea     rax, [rbp+620h+var_600]
0x14004a728  cmp     [rbp+620h+var_5E8], 0Fh
0x14004a72d  cmova   rax, qword ptr [rbp+620h+var_600]
0x14004a732  mov     r10, [rbp+620h+var_5F0]
0x14004a736  mov     rdx, [rsp+720h+var_6D8]
0x14004a73b  xor     r8d, r8d
0x14004a73e  test    r10, r10
0x14004a741  jz      short loc_14004A777
0x14004a743  mov     r9, [rbp+620h+var_698]
0x14004a747  sub     r9, rdx
0x14004a74a  movsx   r11, byte ptr [rax]
0x14004a74e  cmp     r9, r11
0x14004a751  jbe     short loc_14004A777
0x14004a753  add     r10, rax
0x14004a756  movsx   rcx, r11b
0x14004a75a  sub     r9, rcx
0x14004a75d  inc     r8d
0x14004a760  lea     rcx, [rax+1]
0x14004a764  cmp     rcx, r10
0x14004a767  cmovz   rcx, rax
0x14004a76b  mov     rax, rcx
0x14004a76e  movsx   r11, byte ptr [rcx]
0x14004a772  cmp     r9, r11
0x14004a775  ja      short loc_14004A756
0x14004a777  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x14004a77c  mov     ecx, [rsp+720h+var_6E8]
0x14004a780  add     ecx, r8d
0x14004a783  mov     [rsp+720h+var_6E8], ecx
0x14004a787  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x14004a78c  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x14004a791  mov     r10, [rsp+720h+var_6D0]
0x14004a796  mov     r8d, [rsp+720h+var_6E4]
0x14004a79b  sub     edi, 1
0x14004a79e  jz      loc_14004A831
0x14004a7a4  sub     edi, 1
0x14004a7a7  jz      loc_14004A856
0x14004a7ad  cmp     edi, 1
0x14004a7b0  jnz     short loc_14004A831
0x14004a7b2  cmp     byte ptr [r14+0Bh], 0
0x14004a7b7  jz      loc_14004A860
0x14004a7bd  mov     al, [r14+8]
0x14004a7c1  sub     al, 47h ; 'G'
0x14004a7c3  test    al, 0DFh
  ... truncated ...
```
