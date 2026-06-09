# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18002494c`
- end: `0x180025016`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@N@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@NAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1738`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180026ec8`

## callees

- `0x180004180`
- `0x180022cc8`
- `0x180022df4`
- `0x180022fa0`
- `0x18002494c`
- `0x18002a6a0`
- `0x18002abe4`
- `0x18002ae0c`
- `0x18002b39c`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180024c67`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x180024c67`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x180024a68`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x180024a68`

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
0x18002494c  mov     rax, rsp
0x18002494f  mov     [rax+10h], rbx
0x180024953  push    rbp
0x180024954  push    rsi
0x180024955  push    rdi
0x180024956  push    r12
0x180024958  push    r13
0x18002495a  push    r14
0x18002495c  push    r15
0x18002495e  lea     rbp, [rax-628h]
0x180024965  sub     rsp, 6F0h
0x18002496c  movaps  xmmword ptr [rax-48h], xmm6
0x180024970  mov     rax, cs:__security_cookie
0x180024977  xor     rax, rsp
0x18002497a  mov     [rbp+620h+var_50], rax
0x180024981  mov     r14, r9
0x180024984  movaps  xmm6, xmm2
0x180024987  mov     rbx, rdx
0x18002498a  mov     [rbp+620h+var_688], rcx
0x18002498e  mov     al, [r9+0Ah]
0x180024992  mov     byte ptr [rsp+720h+var_6F0+1], al
0x180024996  mov     r9d, 2
0x18002499c  test    al, al
0x18002499e  jnz     short loc_1800249A5
0x1800249a0  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x1800249a5  xor     sil, sil
0x1800249a8  mov     r13b, 65h ; 'e'
0x1800249ab  mov     edx, [r14+4]
0x1800249af  xor     r15b, r15b
0x1800249b2  movsx   ecx, byte ptr [r14+8]
0x1800249b7  mov     edi, 4
0x1800249bc  lea     r8d, [rdi-3]
0x1800249c0  sub     ecx, 41h ; 'A'
0x1800249c3  jz      short loc_180024A31
0x1800249c5  sub     ecx, edi
0x1800249c7  jz      short loc_180024A1E
0x1800249c9  sub     ecx, r8d
0x1800249cc  jz      short loc_180024A0B
0x1800249ce  sub     ecx, r8d
0x1800249d1  jz      short loc_1800249EF
0x1800249d3  sub     ecx, 1Ah
0x1800249d6  jz      short loc_180024A34
0x1800249d8  sub     ecx, edi
0x1800249da  jz      short loc_180024A21
0x1800249dc  sub     ecx, r8d
0x1800249df  jz      short loc_180024A0E
0x1800249e1  cmp     ecx, r8d
0x1800249e4  jz      short loc_1800249F2
0x1800249e6  lea     edi, [r8+2]
0x1800249ea  mov     r15b, r8b
0x1800249ed  jmp     short loc_180024A37
0x1800249ef  mov     sil, r8b
0x1800249f2  cmp     edx, 0FFFFFFFFh
0x1800249f5  jnz     short loc_1800249FE
0x1800249f7  mov     edx, 6
0x1800249fc  jmp     short loc_180024A04
0x1800249fe  test    edx, edx
0x180024a00  cmovz   edx, r8d
0x180024a04  mov     edi, 3
0x180024a09  jmp     short loc_180024A37
0x180024a0b  mov     sil, r8b
0x180024a0e  mov     eax, 6
0x180024a13  cmp     edx, 0FFFFFFFFh
0x180024a16  cmovz   edx, eax
0x180024a19  mov     edi, r9d
0x180024a1c  jmp     short loc_180024A37
0x180024a1e  mov     sil, r8b
0x180024a21  mov     eax, 6
0x180024a26  cmp     edx, 0FFFFFFFFh
0x180024a29  cmovz   edx, eax
0x180024a2c  mov     edi, r8d
0x180024a2f  jmp     short loc_180024A37
0x180024a31  mov     sil, r8b
0x180024a34  mov     r13b, 70h ; 'p'
0x180024a37  xorps   xmm0, xmm0
0x180024a3a  movups  [rsp+720h+var_6C8+8], xmm0
0x180024a3f  mov     r12d, edx
0x180024a42  mov     r8d, 432h
0x180024a48  cmp     edx, r8d
0x180024a4b  cmovg   r12d, r8d
0x180024a4f  mov     [rbp+620h+var_6A0], r12d
0x180024a53  lea     ecx, [rdx-432h]
0x180024a59  xor     eax, eax
0x180024a5b  cmp     edx, r8d
0x180024a5e  cmovle  ecx, eax
0x180024a61  mov     dword ptr [rsp+720h+var_6E0], ecx
0x180024a65  movaps  xmm0, xmm6
0x180024a68  call    cs:__imp__o__dsign
0x180024a6e  mov     edx, eax
0x180024a70  test    eax, eax
0x180024a72  setnz   byte ptr [rsp+720h+var_6F0+3]
0x180024a77  ucomisd xmm6, xmm6
0x180024a7b  setp    al
0x180024a7e  cmp     al, 1
0x180024a80  jnz     short loc_180024AB7
0x180024a82  lea     rax, [rbp+620h+var_5C0]
0x180024a86  lea     rcx, [rbp+620h+var_5BF]
0x180024a8a  test    edx, edx
0x180024a8c  cmovz   rcx, rax
0x180024a90  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x180024a95  mov     eax, dword ptr cs:aNan; "nan"
0x180024a9b  mov     [rcx], ax
0x180024a9e  mov     al, byte ptr cs:aNan+2; "n"
0x180024aa4  mov     [rcx+2], al
0x180024aa7  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x180024aac  add     r9, 3
0x180024ab0  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x180024ab5  jmp     short loc_180024B04
0x180024ab7  movaps  xmm3, xmm6
0x180024aba  lea     r8, [rbp+620h+var_57]
0x180024ac1  lea     rdx, [rbp+620h+var_5C0]
0x180024ac5  lea     rcx, [rsp+720h+var_6B8+8]
0x180024aca  cmp     r12d, 0FFFFFFFFh
0x180024ace  jnz     short loc_180024AE7
0x180024ad0  test    r15b, r15b
0x180024ad3  jz      short loc_180024ADC
0x180024ad5  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x180024ada  jmp     short loc_180024AF5
0x180024adc  mov     [rsp+720h+var_700], edi
0x180024ae0  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x180024ae5  jmp     short loc_180024AF5
0x180024ae7  mov     dword ptr [rsp+720h+var_6F8], r12d
0x180024aec  mov     [rsp+720h+var_700], edi
0x180024af0  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x180024af5  movaps  xmm0, [rsp+720h+var_6B8+8]
0x180024afa  movaps  [rsp+720h+var_6C8+8], xmm0
0x180024aff  movq    r9, xmm0
0x180024b04  lea     rdx, [rbp+620h+var_5C0]
0x180024b08  mov     [rsp+720h+var_6D8], rdx
0x180024b0d  mov     ecx, r9d
0x180024b10  sub     ecx, edx
0x180024b12  mov     [rsp+720h+var_6E8], ecx
0x180024b16  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x180024b1b  jz      short loc_180024B28
0x180024b1d  lea     rdx, [rbp+620h+var_5BF]
0x180024b21  mov     [rsp+720h+var_6D8], rdx
0x180024b26  jmp     short loc_180024B35
0x180024b28  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x180024b2d  jz      short loc_180024B35
0x180024b2f  inc     ecx
0x180024b31  mov     [rsp+720h+var_6E8], ecx
0x180024b35  test    sil, sil
0x180024b38  jz      short loc_180024B67
0x180024b3a  cmp     rdx, r9
0x180024b3d  jz      short loc_180024B63
0x180024b3f  mov     cl, [rdx]
0x180024b41  lea     eax, [rcx-61h]
0x180024b44  cmp     al, 19h
0x180024b46  ja      short loc_180024B4D
0x180024b48  sub     cl, 20h ; ' '
0x180024b4b  mov     [rdx], cl
0x180024b4d  inc     rdx
0x180024b50  cmp     rdx, r9
0x180024b53  jnz     short loc_180024B3F
0x180024b55  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x180024b5a  mov     rdx, [rsp+720h+var_6D8]
0x180024b5f  mov     ecx, [rsp+720h+var_6E8]
0x180024b63  add     r13b, 0E0h
0x180024b67  movq    rax, xmm6
0x180024b6c  shr     rax, 34h
0x180024b70  mov     r8d, 7FFh
0x180024b76  and     eax, r8d
0x180024b79  cmp     eax, r8d
0x180024b7c  setnz   al
0x180024b7f  xor     al, 1
0x180024b81  mov     byte ptr [rsp+720h+var_6F0], al
0x180024b85  mov     r15b, 0
0x180024b88  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x180024b8d  mov     r10, r9
0x180024b90  mov     [rsp+720h+var_6D0], r9
0x180024b95  mov     r11, r9
0x180024b98  mov     [rbp+620h+var_690], r9
0x180024b9c  mov     [rbp+620h+var_698], r9
0x180024ba0  mov     r8d, 0
0x180024ba6  mov     [rsp+720h+var_6E4], r8d
0x180024bab  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x180024bb0  xorps   xmm0, xmm0
0x180024bb3  movups  [rbp+620h+var_600], xmm0
0x180024bb7  mov     [rbp+620h+var_5F0], r8
0x180024bbb  mov     [rbp+620h+var_5E8], 0Fh
0x180024bc3  mov     byte ptr [rbp+620h+var_600], r8b
0x180024bc7  jnz     loc_180024E14
0x180024bcd  mov     r12b, [r14+0Bh]
0x180024bd1  test    r12b, r12b
0x180024bd4  jnz     short loc_180024BE3
0x180024bd6  lea     rsi, [r14+0Ch]
0x180024bda  cmp     [rsi], r12b
0x180024bdd  jz      loc_180024D4B
0x180024be3  mov     rax, rdx
0x180024be6  cmp     rdx, r9
0x180024be9  jnb     short loc_180024C16
0x180024beb  cmp     byte ptr [rax], 2Eh ; '.'
0x180024bee  jnz     short loc_180024BF9
0x180024bf0  mov     r11, rax
0x180024bf3  mov     [rbp+620h+var_690], rax
0x180024bf7  jmp     short loc_180024C06
0x180024bf9  cmp     [rax], r13b
0x180024bfc  jnz     short loc_180024C06
0x180024bfe  mov     r10, rax
0x180024c01  mov     [rsp+720h+var_6D0], rax
0x180024c06  inc     rax
0x180024c09  cmp     rax, r9
0x180024c0c  jb      short loc_180024BEB
0x180024c0e  cmp     r10, r11
0x180024c11  mov     rax, r10
0x180024c14  jb      short loc_180024C19
0x180024c16  mov     rax, r11
0x180024c19  mov     [rbp+620h+var_698], rax
0x180024c1d  test    r12b, r12b
0x180024c20  jz      short loc_180024C35
0x180024c22  cmp     r11, r9
0x180024c25  jnz     short loc_180024C35
0x180024c27  inc     ecx
0x180024c29  mov     [rsp+720h+var_6E8], ecx
0x180024c2d  mov     r15b, 1
0x180024c30  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x180024c35  lea     rsi, [r14+0Ch]
0x180024c39  cmp     byte ptr [rsi], 0
0x180024c3c  jz      loc_180024D4B
0x180024c42  mov     rax, [rbp+620h+arg_20]
0x180024c49  test    rax, rax
0x180024c4c  jz      short loc_180024C65
0x180024c4e  mov     rcx, [rax+8]
0x180024c52  mov     [rsp+720h+var_6A8], rcx
0x180024c57  mov     rax, [rcx]
0x180024c5a  mov     rax, [rax+8]
0x180024c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c63  jmp     short loc_180024C72
0x180024c65  mov     cl, 1
0x180024c67  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x180024c6d  mov     [rsp+720h+var_6A8], rax
0x180024c72  lea     rcx, [rsp+720h+var_6B8+8]
0x180024c77  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x180024c7c  mov     rcx, rax
0x180024c7f  mov     rax, [rax]
0x180024c82  lea     rdx, [rbp+620h+var_5E0]
0x180024c86  mov     rax, [rax+28h]
0x180024c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c8f  lea     rdx, [rbp+620h+var_5E0]
0x180024c93  lea     rcx, [rbp+620h+var_600]
0x180024c97  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180024c9c  lea     rcx, [rbp+620h+var_5E0]
0x180024ca0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180024ca5  nop
0x180024ca6  mov     rcx, [rsp+720h+var_6A8]
0x180024cab  test    rcx, rcx
0x180024cae  jz      short loc_180024CD4
0x180024cb0  mov     rax, [rcx]
0x180024cb3  mov     rax, [rax+10h]
0x180024cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cbc  mov     rcx, rax
0x180024cbf  test    rax, rax
0x180024cc2  jz      short loc_180024CD4
0x180024cc4  mov     rax, [rax]
0x180024cc7  mov     edx, 1
0x180024ccc  mov     rax, [rax]
0x180024ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cd4  lea     rax, [rbp+620h+var_600]
0x180024cd8  cmp     [rbp+620h+var_5E8], 0Fh
0x180024cdd  cmova   rax, qword ptr [rbp+620h+var_600]
0x180024ce2  mov     r10, [rbp+620h+var_5F0]
0x180024ce6  mov     rdx, [rsp+720h+var_6D8]
0x180024ceb  xor     r8d, r8d
0x180024cee  test    r10, r10
0x180024cf1  jz      short loc_180024D27
0x180024cf3  mov     r9, [rbp+620h+var_698]
0x180024cf7  sub     r9, rdx
0x180024cfa  movsx   r11, byte ptr [rax]
0x180024cfe  cmp     r9, r11
0x180024d01  jbe     short loc_180024D27
0x180024d03  add     r10, rax
0x180024d06  movsx   rcx, r11b
0x180024d0a  sub     r9, rcx
0x180024d0d  inc     r8d
0x180024d10  lea     rcx, [rax+1]
0x180024d14  cmp     rcx, r10
0x180024d17  cmovz   rcx, rax
0x180024d1b  mov     rax, rcx
0x180024d1e  movsx   r11, byte ptr [rcx]
0x180024d22  cmp     r9, r11
0x180024d25  ja      short loc_180024D06
0x180024d27  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x180024d2c  mov     ecx, [rsp+720h+var_6E8]
0x180024d30  add     ecx, r8d
0x180024d33  mov     [rsp+720h+var_6E8], ecx
0x180024d37  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x180024d3c  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x180024d41  mov     r10, [rsp+720h+var_6D0]
0x180024d46  mov     r8d, [rsp+720h+var_6E4]
0x180024d4b  sub     edi, 1
0x180024d4e  jz      loc_180024DE1
0x180024d54  sub     edi, 1
0x180024d57  jz      loc_180024E06
0x180024d5d  cmp     edi, 1
0x180024d60  jnz     short loc_180024DE1
0x180024d62  cmp     byte ptr [r14+0Bh], 0
0x180024d67  jz      loc_180024E10
0x180024d6d  mov     al, [r14+8]
0x180024d71  sub     al, 47h ; 'G'
0x180024d73  test    al, 0DFh
  ... truncated ...
```
