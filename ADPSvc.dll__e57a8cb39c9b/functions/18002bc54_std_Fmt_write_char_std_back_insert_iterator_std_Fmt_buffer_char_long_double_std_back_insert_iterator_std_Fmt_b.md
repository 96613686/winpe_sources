# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,long double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18002bc54`
- end: `0x18002c31e`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@OAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1738`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, long double, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002daf4`

## callees

- `0x180002250`
- `0x180013830`
- `0x180018c48`
- `0x180018d74`
- `0x180018f20`
- `0x180020b94`
- `0x18002bc54`
- `0x180030078`
- `0x180030f80`
- `0x1800ca010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002bf6f`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002bf6f`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x18002bd70`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x18002bd70`

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
0x18002bc54  mov     rax, rsp
0x18002bc57  mov     [rax+10h], rbx
0x18002bc5b  push    rbp
0x18002bc5c  push    rsi
0x18002bc5d  push    rdi
0x18002bc5e  push    r12
0x18002bc60  push    r13
0x18002bc62  push    r14
0x18002bc64  push    r15
0x18002bc66  lea     rbp, [rax-628h]
0x18002bc6d  sub     rsp, 6F0h
0x18002bc74  movaps  xmmword ptr [rax-48h], xmm6
0x18002bc78  mov     rax, cs:__security_cookie
0x18002bc7f  xor     rax, rsp
0x18002bc82  mov     [rbp+620h+var_50], rax
0x18002bc89  mov     r14, r9
0x18002bc8c  movaps  xmm6, xmm2
0x18002bc8f  mov     rbx, rdx
0x18002bc92  mov     [rbp+620h+var_688], rcx
0x18002bc96  mov     al, [r9+0Ah]
0x18002bc9a  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18002bc9e  mov     r9d, 2
0x18002bca4  test    al, al
0x18002bca6  jnz     short loc_18002BCAD
0x18002bca8  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18002bcad  xor     sil, sil
0x18002bcb0  mov     r13b, 65h ; 'e'
0x18002bcb3  mov     edx, [r14+4]
0x18002bcb7  xor     r15b, r15b
0x18002bcba  movsx   ecx, byte ptr [r14+8]
0x18002bcbf  mov     edi, 4
0x18002bcc4  lea     r8d, [rdi-3]
0x18002bcc8  sub     ecx, 41h ; 'A'
0x18002bccb  jz      short loc_18002BD39
0x18002bccd  sub     ecx, edi
0x18002bccf  jz      short loc_18002BD26
0x18002bcd1  sub     ecx, r8d
0x18002bcd4  jz      short loc_18002BD13
0x18002bcd6  sub     ecx, r8d
0x18002bcd9  jz      short loc_18002BCF7
0x18002bcdb  sub     ecx, 1Ah
0x18002bcde  jz      short loc_18002BD3C
0x18002bce0  sub     ecx, edi
0x18002bce2  jz      short loc_18002BD29
0x18002bce4  sub     ecx, r8d
0x18002bce7  jz      short loc_18002BD16
0x18002bce9  cmp     ecx, r8d
0x18002bcec  jz      short loc_18002BCFA
0x18002bcee  lea     edi, [r8+2]
0x18002bcf2  mov     r15b, r8b
0x18002bcf5  jmp     short loc_18002BD3F
0x18002bcf7  mov     sil, r8b
0x18002bcfa  cmp     edx, 0FFFFFFFFh
0x18002bcfd  jnz     short loc_18002BD06
0x18002bcff  mov     edx, 6
0x18002bd04  jmp     short loc_18002BD0C
0x18002bd06  test    edx, edx
0x18002bd08  cmovz   edx, r8d
0x18002bd0c  mov     edi, 3
0x18002bd11  jmp     short loc_18002BD3F
0x18002bd13  mov     sil, r8b
0x18002bd16  mov     eax, 6
0x18002bd1b  cmp     edx, 0FFFFFFFFh
0x18002bd1e  cmovz   edx, eax
0x18002bd21  mov     edi, r9d
0x18002bd24  jmp     short loc_18002BD3F
0x18002bd26  mov     sil, r8b
0x18002bd29  mov     eax, 6
0x18002bd2e  cmp     edx, 0FFFFFFFFh
0x18002bd31  cmovz   edx, eax
0x18002bd34  mov     edi, r8d
0x18002bd37  jmp     short loc_18002BD3F
0x18002bd39  mov     sil, r8b
0x18002bd3c  mov     r13b, 70h ; 'p'
0x18002bd3f  xorps   xmm0, xmm0
0x18002bd42  movups  [rsp+720h+var_6C8+8], xmm0
0x18002bd47  mov     r12d, edx
0x18002bd4a  mov     r8d, 432h
0x18002bd50  cmp     edx, r8d
0x18002bd53  cmovg   r12d, r8d
0x18002bd57  mov     [rbp+620h+var_6A0], r12d
0x18002bd5b  lea     ecx, [rdx-432h]
0x18002bd61  xor     eax, eax
0x18002bd63  cmp     edx, r8d
0x18002bd66  cmovle  ecx, eax
0x18002bd69  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18002bd6d  movaps  xmm0, xmm6; X
0x18002bd70  call    cs:__imp__ldsign
0x18002bd76  mov     edx, eax
0x18002bd78  test    eax, eax
0x18002bd7a  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18002bd7f  ucomisd xmm6, xmm6
0x18002bd83  setp    al
0x18002bd86  cmp     al, 1
0x18002bd88  jnz     short loc_18002BDBF
0x18002bd8a  lea     rax, [rbp+620h+var_5C0]
0x18002bd8e  lea     rcx, [rbp+620h+var_5BF]
0x18002bd92  test    edx, edx
0x18002bd94  cmovz   rcx, rax
0x18002bd98  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x18002bd9d  mov     eax, dword ptr cs:aNan; "nan"
0x18002bda3  mov     [rcx], ax
0x18002bda6  mov     al, byte ptr cs:aNan+2; "n"
0x18002bdac  mov     [rcx+2], al
0x18002bdaf  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002bdb4  add     r9, 3
0x18002bdb8  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x18002bdbd  jmp     short loc_18002BE0C
0x18002bdbf  movaps  xmm3, xmm6
0x18002bdc2  lea     r8, [rbp+620h+var_57]
0x18002bdc9  lea     rdx, [rbp+620h+var_5C0]
0x18002bdcd  lea     rcx, [rsp+720h+var_6B8+8]
0x18002bdd2  cmp     r12d, 0FFFFFFFFh
0x18002bdd6  jnz     short loc_18002BDEF
0x18002bdd8  test    r15b, r15b
0x18002bddb  jz      short loc_18002BDE4
0x18002bddd  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18002bde2  jmp     short loc_18002BDFD
0x18002bde4  mov     [rsp+720h+var_700], edi
0x18002bde8  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x18002bded  jmp     short loc_18002BDFD
0x18002bdef  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18002bdf4  mov     [rsp+720h+var_700], edi
0x18002bdf8  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x18002bdfd  movaps  xmm0, [rsp+720h+var_6B8+8]
0x18002be02  movaps  [rsp+720h+var_6C8+8], xmm0
0x18002be07  movq    r9, xmm0
0x18002be0c  lea     rdx, [rbp+620h+var_5C0]
0x18002be10  mov     [rsp+720h+var_6D8], rdx
0x18002be15  mov     ecx, r9d
0x18002be18  sub     ecx, edx
0x18002be1a  mov     [rsp+720h+var_6E8], ecx
0x18002be1e  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18002be23  jz      short loc_18002BE30
0x18002be25  lea     rdx, [rbp+620h+var_5BF]
0x18002be29  mov     [rsp+720h+var_6D8], rdx
0x18002be2e  jmp     short loc_18002BE3D
0x18002be30  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18002be35  jz      short loc_18002BE3D
0x18002be37  inc     ecx
0x18002be39  mov     [rsp+720h+var_6E8], ecx
0x18002be3d  test    sil, sil
0x18002be40  jz      short loc_18002BE6F
0x18002be42  cmp     rdx, r9
0x18002be45  jz      short loc_18002BE6B
0x18002be47  mov     cl, [rdx]
0x18002be49  lea     eax, [rcx-61h]
0x18002be4c  cmp     al, 19h
0x18002be4e  ja      short loc_18002BE55
0x18002be50  sub     cl, 20h ; ' '
0x18002be53  mov     [rdx], cl
0x18002be55  inc     rdx
0x18002be58  cmp     rdx, r9
0x18002be5b  jnz     short loc_18002BE47
0x18002be5d  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002be62  mov     rdx, [rsp+720h+var_6D8]
0x18002be67  mov     ecx, [rsp+720h+var_6E8]
0x18002be6b  add     r13b, 0E0h
0x18002be6f  movq    rax, xmm6
0x18002be74  shr     rax, 34h
0x18002be78  mov     r8d, 7FFh
0x18002be7e  and     eax, r8d
0x18002be81  cmp     eax, r8d
0x18002be84  setnz   al
0x18002be87  xor     al, 1
0x18002be89  mov     byte ptr [rsp+720h+var_6F0], al
0x18002be8d  mov     r15b, 0
0x18002be90  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002be95  mov     r10, r9
0x18002be98  mov     [rsp+720h+var_6D0], r9
0x18002be9d  mov     r11, r9
0x18002bea0  mov     [rbp+620h+var_690], r9
0x18002bea4  mov     [rbp+620h+var_698], r9
0x18002bea8  mov     r8d, 0
0x18002beae  mov     [rsp+720h+var_6E4], r8d
0x18002beb3  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002beb8  xorps   xmm0, xmm0
0x18002bebb  movups  [rbp+620h+var_600], xmm0
0x18002bebf  mov     [rbp+620h+var_5F0], r8
0x18002bec3  mov     [rbp+620h+var_5E8], 0Fh
0x18002becb  mov     byte ptr [rbp+620h+var_600], r8b
0x18002becf  jnz     loc_18002C11C
0x18002bed5  mov     r12b, [r14+0Bh]
0x18002bed9  test    r12b, r12b
0x18002bedc  jnz     short loc_18002BEEB
0x18002bede  lea     rsi, [r14+0Ch]
0x18002bee2  cmp     [rsi], r12b
0x18002bee5  jz      loc_18002C053
0x18002beeb  mov     rax, rdx
0x18002beee  cmp     rdx, r9
0x18002bef1  jnb     short loc_18002BF1E
0x18002bef3  cmp     byte ptr [rax], 2Eh ; '.'
0x18002bef6  jnz     short loc_18002BF01
0x18002bef8  mov     r11, rax
0x18002befb  mov     [rbp+620h+var_690], rax
0x18002beff  jmp     short loc_18002BF0E
0x18002bf01  cmp     [rax], r13b
0x18002bf04  jnz     short loc_18002BF0E
0x18002bf06  mov     r10, rax
0x18002bf09  mov     [rsp+720h+var_6D0], rax
0x18002bf0e  inc     rax
0x18002bf11  cmp     rax, r9
0x18002bf14  jb      short loc_18002BEF3
0x18002bf16  cmp     r10, r11
0x18002bf19  mov     rax, r10
0x18002bf1c  jb      short loc_18002BF21
0x18002bf1e  mov     rax, r11
0x18002bf21  mov     [rbp+620h+var_698], rax
0x18002bf25  test    r12b, r12b
0x18002bf28  jz      short loc_18002BF3D
0x18002bf2a  cmp     r11, r9
0x18002bf2d  jnz     short loc_18002BF3D
0x18002bf2f  inc     ecx
0x18002bf31  mov     [rsp+720h+var_6E8], ecx
0x18002bf35  mov     r15b, 1
0x18002bf38  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002bf3d  lea     rsi, [r14+0Ch]
0x18002bf41  cmp     byte ptr [rsi], 0
0x18002bf44  jz      loc_18002C053
0x18002bf4a  mov     rax, [rbp+620h+arg_20]
0x18002bf51  test    rax, rax
0x18002bf54  jz      short loc_18002BF6D
0x18002bf56  mov     rcx, [rax+8]
0x18002bf5a  mov     [rsp+720h+var_6A8], rcx
0x18002bf5f  mov     rax, [rcx]
0x18002bf62  mov     rax, [rax+8]
0x18002bf66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf6b  jmp     short loc_18002BF7A
0x18002bf6d  mov     cl, 1
0x18002bf6f  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002bf75  mov     [rsp+720h+var_6A8], rax
0x18002bf7a  lea     rcx, [rsp+720h+var_6B8+8]
0x18002bf7f  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002bf84  mov     rcx, rax
0x18002bf87  mov     rax, [rax]
0x18002bf8a  lea     rdx, [rbp+620h+var_5E0]
0x18002bf8e  mov     rax, [rax+28h]
0x18002bf92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf97  lea     rdx, [rbp+620h+var_5E0]
0x18002bf9b  lea     rcx, [rbp+620h+var_600]
0x18002bf9f  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002bfa4  lea     rcx, [rbp+620h+var_5E0]
0x18002bfa8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002bfad  nop
0x18002bfae  mov     rcx, [rsp+720h+var_6A8]
0x18002bfb3  test    rcx, rcx
0x18002bfb6  jz      short loc_18002BFDC
0x18002bfb8  mov     rax, [rcx]
0x18002bfbb  mov     rax, [rax+10h]
0x18002bfbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfc4  mov     rcx, rax
0x18002bfc7  test    rax, rax
0x18002bfca  jz      short loc_18002BFDC
0x18002bfcc  mov     rax, [rax]
0x18002bfcf  mov     edx, 1
0x18002bfd4  mov     rax, [rax]
0x18002bfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfdc  lea     rax, [rbp+620h+var_600]
0x18002bfe0  cmp     [rbp+620h+var_5E8], 0Fh
0x18002bfe5  cmova   rax, qword ptr [rbp+620h+var_600]
0x18002bfea  mov     r10, [rbp+620h+var_5F0]
0x18002bfee  mov     rdx, [rsp+720h+var_6D8]
0x18002bff3  xor     r8d, r8d
0x18002bff6  test    r10, r10
0x18002bff9  jz      short loc_18002C02F
0x18002bffb  mov     r9, [rbp+620h+var_698]
0x18002bfff  sub     r9, rdx
0x18002c002  movsx   r11, byte ptr [rax]
0x18002c006  cmp     r9, r11
0x18002c009  jbe     short loc_18002C02F
0x18002c00b  add     r10, rax
0x18002c00e  movsx   rcx, r11b
0x18002c012  sub     r9, rcx
0x18002c015  inc     r8d
0x18002c018  lea     rcx, [rax+1]
0x18002c01c  cmp     rcx, r10
0x18002c01f  cmovz   rcx, rax
0x18002c023  mov     rax, rcx
0x18002c026  movsx   r11, byte ptr [rcx]
0x18002c02a  cmp     r9, r11
0x18002c02d  ja      short loc_18002C00E
0x18002c02f  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002c034  mov     ecx, [rsp+720h+var_6E8]
0x18002c038  add     ecx, r8d
0x18002c03b  mov     [rsp+720h+var_6E8], ecx
0x18002c03f  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002c044  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x18002c049  mov     r10, [rsp+720h+var_6D0]
0x18002c04e  mov     r8d, [rsp+720h+var_6E4]
0x18002c053  sub     edi, 1
0x18002c056  jz      loc_18002C0E9
0x18002c05c  sub     edi, 1
0x18002c05f  jz      loc_18002C10E
0x18002c065  cmp     edi, 1
0x18002c068  jnz     short loc_18002C0E9
0x18002c06a  cmp     byte ptr [r14+0Bh], 0
0x18002c06f  jz      loc_18002C118
0x18002c075  mov     al, [r14+8]
0x18002c079  sub     al, 47h ; 'G'
0x18002c07b  test    al, 0DFh
  ... truncated ...
```
