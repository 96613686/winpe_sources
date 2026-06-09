# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,double>(std::back_insert_iterator<std::_Fmt_buffer<char>>,double,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18002b584`
- end: `0x18002bc4e`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@N@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@NAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1738`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, double, __int64, __int64)`
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
- `0x18002b584`
- `0x180030078`
- `0x180030f80`
- `0x1800ca010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b89f`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002b89f`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18002b6a0`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18002b6a0`

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
0x18002b584  mov     rax, rsp
0x18002b587  mov     [rax+10h], rbx
0x18002b58b  push    rbp
0x18002b58c  push    rsi
0x18002b58d  push    rdi
0x18002b58e  push    r12
0x18002b590  push    r13
0x18002b592  push    r14
0x18002b594  push    r15
0x18002b596  lea     rbp, [rax-628h]
0x18002b59d  sub     rsp, 6F0h
0x18002b5a4  movaps  xmmword ptr [rax-48h], xmm6
0x18002b5a8  mov     rax, cs:__security_cookie
0x18002b5af  xor     rax, rsp
0x18002b5b2  mov     [rbp+620h+var_50], rax
0x18002b5b9  mov     r14, r9
0x18002b5bc  movaps  xmm6, xmm2
0x18002b5bf  mov     rbx, rdx
0x18002b5c2  mov     [rbp+620h+var_688], rcx
0x18002b5c6  mov     al, [r9+0Ah]
0x18002b5ca  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18002b5ce  mov     r9d, 2
0x18002b5d4  test    al, al
0x18002b5d6  jnz     short loc_18002B5DD
0x18002b5d8  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18002b5dd  xor     sil, sil
0x18002b5e0  mov     r13b, 65h ; 'e'
0x18002b5e3  mov     edx, [r14+4]
0x18002b5e7  xor     r15b, r15b
0x18002b5ea  movsx   ecx, byte ptr [r14+8]
0x18002b5ef  mov     edi, 4
0x18002b5f4  lea     r8d, [rdi-3]
0x18002b5f8  sub     ecx, 41h ; 'A'
0x18002b5fb  jz      short loc_18002B669
0x18002b5fd  sub     ecx, edi
0x18002b5ff  jz      short loc_18002B656
0x18002b601  sub     ecx, r8d
0x18002b604  jz      short loc_18002B643
0x18002b606  sub     ecx, r8d
0x18002b609  jz      short loc_18002B627
0x18002b60b  sub     ecx, 1Ah
0x18002b60e  jz      short loc_18002B66C
0x18002b610  sub     ecx, edi
0x18002b612  jz      short loc_18002B659
0x18002b614  sub     ecx, r8d
0x18002b617  jz      short loc_18002B646
0x18002b619  cmp     ecx, r8d
0x18002b61c  jz      short loc_18002B62A
0x18002b61e  lea     edi, [r8+2]
0x18002b622  mov     r15b, r8b
0x18002b625  jmp     short loc_18002B66F
0x18002b627  mov     sil, r8b
0x18002b62a  cmp     edx, 0FFFFFFFFh
0x18002b62d  jnz     short loc_18002B636
0x18002b62f  mov     edx, 6
0x18002b634  jmp     short loc_18002B63C
0x18002b636  test    edx, edx
0x18002b638  cmovz   edx, r8d
0x18002b63c  mov     edi, 3
0x18002b641  jmp     short loc_18002B66F
0x18002b643  mov     sil, r8b
0x18002b646  mov     eax, 6
0x18002b64b  cmp     edx, 0FFFFFFFFh
0x18002b64e  cmovz   edx, eax
0x18002b651  mov     edi, r9d
0x18002b654  jmp     short loc_18002B66F
0x18002b656  mov     sil, r8b
0x18002b659  mov     eax, 6
0x18002b65e  cmp     edx, 0FFFFFFFFh
0x18002b661  cmovz   edx, eax
0x18002b664  mov     edi, r8d
0x18002b667  jmp     short loc_18002B66F
0x18002b669  mov     sil, r8b
0x18002b66c  mov     r13b, 70h ; 'p'
0x18002b66f  xorps   xmm0, xmm0
0x18002b672  movups  [rsp+720h+var_6C8+8], xmm0
0x18002b677  mov     r12d, edx
0x18002b67a  mov     r8d, 432h
0x18002b680  cmp     edx, r8d
0x18002b683  cmovg   r12d, r8d
0x18002b687  mov     [rbp+620h+var_6A0], r12d
0x18002b68b  lea     ecx, [rdx-432h]
0x18002b691  xor     eax, eax
0x18002b693  cmp     edx, r8d
0x18002b696  cmovle  ecx, eax
0x18002b699  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18002b69d  movaps  xmm0, xmm6
0x18002b6a0  call    cs:__imp__o__dsign
0x18002b6a6  mov     edx, eax
0x18002b6a8  test    eax, eax
0x18002b6aa  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18002b6af  ucomisd xmm6, xmm6
0x18002b6b3  setp    al
0x18002b6b6  cmp     al, 1
0x18002b6b8  jnz     short loc_18002B6EF
0x18002b6ba  lea     rax, [rbp+620h+var_5C0]
0x18002b6be  lea     rcx, [rbp+620h+var_5BF]
0x18002b6c2  test    edx, edx
0x18002b6c4  cmovz   rcx, rax
0x18002b6c8  mov     qword ptr [rsp+720h+var_6C8+8], rcx
0x18002b6cd  mov     eax, dword ptr cs:aNan; "nan"
0x18002b6d3  mov     [rcx], ax
0x18002b6d6  mov     al, byte ptr cs:aNan+2; "n"
0x18002b6dc  mov     [rcx+2], al
0x18002b6df  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002b6e4  add     r9, 3
0x18002b6e8  mov     qword ptr [rsp+720h+var_6C8+8], r9
0x18002b6ed  jmp     short loc_18002B73C
0x18002b6ef  movaps  xmm3, xmm6
0x18002b6f2  lea     r8, [rbp+620h+var_57]
0x18002b6f9  lea     rdx, [rbp+620h+var_5C0]
0x18002b6fd  lea     rcx, [rsp+720h+var_6B8+8]
0x18002b702  cmp     r12d, 0FFFFFFFFh
0x18002b706  jnz     short loc_18002B71F
0x18002b708  test    r15b, r15b
0x18002b70b  jz      short loc_18002B714
0x18002b70d  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18002b712  jmp     short loc_18002B72D
0x18002b714  mov     [rsp+720h+var_700], edi
0x18002b718  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x18002b71d  jmp     short loc_18002B72D
0x18002b71f  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18002b724  mov     [rsp+720h+var_700], edi
0x18002b728  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x18002b72d  movaps  xmm0, [rsp+720h+var_6B8+8]
0x18002b732  movaps  [rsp+720h+var_6C8+8], xmm0
0x18002b737  movq    r9, xmm0
0x18002b73c  lea     rdx, [rbp+620h+var_5C0]
0x18002b740  mov     [rsp+720h+var_6D8], rdx
0x18002b745  mov     ecx, r9d
0x18002b748  sub     ecx, edx
0x18002b74a  mov     [rsp+720h+var_6E8], ecx
0x18002b74e  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18002b753  jz      short loc_18002B760
0x18002b755  lea     rdx, [rbp+620h+var_5BF]
0x18002b759  mov     [rsp+720h+var_6D8], rdx
0x18002b75e  jmp     short loc_18002B76D
0x18002b760  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18002b765  jz      short loc_18002B76D
0x18002b767  inc     ecx
0x18002b769  mov     [rsp+720h+var_6E8], ecx
0x18002b76d  test    sil, sil
0x18002b770  jz      short loc_18002B79F
0x18002b772  cmp     rdx, r9
0x18002b775  jz      short loc_18002B79B
0x18002b777  mov     cl, [rdx]
0x18002b779  lea     eax, [rcx-61h]
0x18002b77c  cmp     al, 19h
0x18002b77e  ja      short loc_18002B785
0x18002b780  sub     cl, 20h ; ' '
0x18002b783  mov     [rdx], cl
0x18002b785  inc     rdx
0x18002b788  cmp     rdx, r9
0x18002b78b  jnz     short loc_18002B777
0x18002b78d  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002b792  mov     rdx, [rsp+720h+var_6D8]
0x18002b797  mov     ecx, [rsp+720h+var_6E8]
0x18002b79b  add     r13b, 0E0h
0x18002b79f  movq    rax, xmm6
0x18002b7a4  shr     rax, 34h
0x18002b7a8  mov     r8d, 7FFh
0x18002b7ae  and     eax, r8d
0x18002b7b1  cmp     eax, r8d
0x18002b7b4  setnz   al
0x18002b7b7  xor     al, 1
0x18002b7b9  mov     byte ptr [rsp+720h+var_6F0], al
0x18002b7bd  mov     r15b, 0
0x18002b7c0  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002b7c5  mov     r10, r9
0x18002b7c8  mov     [rsp+720h+var_6D0], r9
0x18002b7cd  mov     r11, r9
0x18002b7d0  mov     [rbp+620h+var_690], r9
0x18002b7d4  mov     [rbp+620h+var_698], r9
0x18002b7d8  mov     r8d, 0
0x18002b7de  mov     [rsp+720h+var_6E4], r8d
0x18002b7e3  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002b7e8  xorps   xmm0, xmm0
0x18002b7eb  movups  [rbp+620h+var_600], xmm0
0x18002b7ef  mov     [rbp+620h+var_5F0], r8
0x18002b7f3  mov     [rbp+620h+var_5E8], 0Fh
0x18002b7fb  mov     byte ptr [rbp+620h+var_600], r8b
0x18002b7ff  jnz     loc_18002BA4C
0x18002b805  mov     r12b, [r14+0Bh]
0x18002b809  test    r12b, r12b
0x18002b80c  jnz     short loc_18002B81B
0x18002b80e  lea     rsi, [r14+0Ch]
0x18002b812  cmp     [rsi], r12b
0x18002b815  jz      loc_18002B983
0x18002b81b  mov     rax, rdx
0x18002b81e  cmp     rdx, r9
0x18002b821  jnb     short loc_18002B84E
0x18002b823  cmp     byte ptr [rax], 2Eh ; '.'
0x18002b826  jnz     short loc_18002B831
0x18002b828  mov     r11, rax
0x18002b82b  mov     [rbp+620h+var_690], rax
0x18002b82f  jmp     short loc_18002B83E
0x18002b831  cmp     [rax], r13b
0x18002b834  jnz     short loc_18002B83E
0x18002b836  mov     r10, rax
0x18002b839  mov     [rsp+720h+var_6D0], rax
0x18002b83e  inc     rax
0x18002b841  cmp     rax, r9
0x18002b844  jb      short loc_18002B823
0x18002b846  cmp     r10, r11
0x18002b849  mov     rax, r10
0x18002b84c  jb      short loc_18002B851
0x18002b84e  mov     rax, r11
0x18002b851  mov     [rbp+620h+var_698], rax
0x18002b855  test    r12b, r12b
0x18002b858  jz      short loc_18002B86D
0x18002b85a  cmp     r11, r9
0x18002b85d  jnz     short loc_18002B86D
0x18002b85f  inc     ecx
0x18002b861  mov     [rsp+720h+var_6E8], ecx
0x18002b865  mov     r15b, 1
0x18002b868  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002b86d  lea     rsi, [r14+0Ch]
0x18002b871  cmp     byte ptr [rsi], 0
0x18002b874  jz      loc_18002B983
0x18002b87a  mov     rax, [rbp+620h+arg_20]
0x18002b881  test    rax, rax
0x18002b884  jz      short loc_18002B89D
0x18002b886  mov     rcx, [rax+8]
0x18002b88a  mov     [rsp+720h+var_6A8], rcx
0x18002b88f  mov     rax, [rcx]
0x18002b892  mov     rax, [rax+8]
0x18002b896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b89b  jmp     short loc_18002B8AA
0x18002b89d  mov     cl, 1
0x18002b89f  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002b8a5  mov     [rsp+720h+var_6A8], rax
0x18002b8aa  lea     rcx, [rsp+720h+var_6B8+8]
0x18002b8af  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002b8b4  mov     rcx, rax
0x18002b8b7  mov     rax, [rax]
0x18002b8ba  lea     rdx, [rbp+620h+var_5E0]
0x18002b8be  mov     rax, [rax+28h]
0x18002b8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8c7  lea     rdx, [rbp+620h+var_5E0]
0x18002b8cb  lea     rcx, [rbp+620h+var_600]
0x18002b8cf  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002b8d4  lea     rcx, [rbp+620h+var_5E0]
0x18002b8d8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b8dd  nop
0x18002b8de  mov     rcx, [rsp+720h+var_6A8]
0x18002b8e3  test    rcx, rcx
0x18002b8e6  jz      short loc_18002B90C
0x18002b8e8  mov     rax, [rcx]
0x18002b8eb  mov     rax, [rax+10h]
0x18002b8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8f4  mov     rcx, rax
0x18002b8f7  test    rax, rax
0x18002b8fa  jz      short loc_18002B90C
0x18002b8fc  mov     rax, [rax]
0x18002b8ff  mov     edx, 1
0x18002b904  mov     rax, [rax]
0x18002b907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b90c  lea     rax, [rbp+620h+var_600]
0x18002b910  cmp     [rbp+620h+var_5E8], 0Fh
0x18002b915  cmova   rax, qword ptr [rbp+620h+var_600]
0x18002b91a  mov     r10, [rbp+620h+var_5F0]
0x18002b91e  mov     rdx, [rsp+720h+var_6D8]
0x18002b923  xor     r8d, r8d
0x18002b926  test    r10, r10
0x18002b929  jz      short loc_18002B95F
0x18002b92b  mov     r9, [rbp+620h+var_698]
0x18002b92f  sub     r9, rdx
0x18002b932  movsx   r11, byte ptr [rax]
0x18002b936  cmp     r9, r11
0x18002b939  jbe     short loc_18002B95F
0x18002b93b  add     r10, rax
0x18002b93e  movsx   rcx, r11b
0x18002b942  sub     r9, rcx
0x18002b945  inc     r8d
0x18002b948  lea     rcx, [rax+1]
0x18002b94c  cmp     rcx, r10
0x18002b94f  cmovz   rcx, rax
0x18002b953  mov     rax, rcx
0x18002b956  movsx   r11, byte ptr [rcx]
0x18002b95a  cmp     r9, r11
0x18002b95d  ja      short loc_18002B93E
0x18002b95f  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002b964  mov     ecx, [rsp+720h+var_6E8]
0x18002b968  add     ecx, r8d
0x18002b96b  mov     [rsp+720h+var_6E8], ecx
0x18002b96f  mov     r9, qword ptr [rsp+720h+var_6C8+8]
0x18002b974  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x18002b979  mov     r10, [rsp+720h+var_6D0]
0x18002b97e  mov     r8d, [rsp+720h+var_6E4]
0x18002b983  sub     edi, 1
0x18002b986  jz      loc_18002BA19
0x18002b98c  sub     edi, 1
0x18002b98f  jz      loc_18002BA3E
0x18002b995  cmp     edi, 1
0x18002b998  jnz     short loc_18002BA19
0x18002b99a  cmp     byte ptr [r14+0Bh], 0
0x18002b99f  jz      loc_18002BA48
0x18002b9a5  mov     al, [r14+8]
0x18002b9a9  sub     al, 47h ; 'G'
0x18002b9ab  test    al, 0DFh
  ... truncated ...
```
