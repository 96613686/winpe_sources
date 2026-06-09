# std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,float>(std::back_insert_iterator<std::_Fmt_buffer<char>>,float,std::_Basic_format_specs<char> const &,std::_Lazy_locale)

- ea: `0x18002f348`
- end: `0x18002fa0a`
- name: `??$_Fmt_write@DV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@std@@M@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@D@std@@@0@V10@MAEBU?$_Basic_format_specs@D@0@V_Lazy_locale@0@@Z`
- size: `1730`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180032164`

## callees

- `0x180004410`
- `0x18002f348`
- `0x180035ca4`
- `0x1800361c4`
- `0x18003641c`
- `0x1800369ac`
- `0x18003bf00`
- `0x18003bff8`
- `0x18003c0fc`
- `0x180041010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002f65d`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002f65d`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18002f465`
- `api-ms-win-crt-private-l1-1-0!_o__fdsign` at `0x18002f465`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,float>(
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
  _OWORD *v14; // rax
  char *v15; // r9
  char *v16; // rdx
  unsigned int v17; // ecx
  bool v18; // al
  char v19; // r15
  char *v20; // r10
  char *v21; // r11
  int v22; // r8d
  char v23; // r12
  _BYTE *v24; // rsi
  char *v25; // rax
  char *v26; // rax
  __int64 v27; // rax
  void (__fastcall ***v28)(_QWORD, __int64); // rax
  char *v29; // rax
  int v30; // r8d
  unsigned __int64 v31; // r9
  unsigned __int64 v32; // r11
  char *v33; // r10
  char *v34; // rcx
  int v35; // edi
  int v36; // edi
  int v37; // eax
  signed int v38; // ecx
  bool v39; // al
  int v41; // esi
  int v42; // edi
  char v43; // al
  int v44; // edi
  char *v45; // r15
  __int64 v46; // r14
  char *i; // r12
  char v48; // r13
  __int64 v49; // rbx
  char *j; // rsi
  char v51; // r12
  _QWORD *v52; // rdi
  char v53; // [rsp+39h] [rbp-CFh] BYREF
  char v54; // [rsp+3Ah] [rbp-CEh] BYREF
  bool v55; // [rsp+3Bh] [rbp-CDh] BYREF
  int v56; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int v57; // [rsp+40h] [rbp-C8h] BYREF
  int v58; // [rsp+44h] [rbp-C4h] BYREF
  int v59; // [rsp+48h] [rbp-C0h]
  int v60; // [rsp+4Ch] [rbp-BCh] BYREF
  char *v61; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v62[3]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+70h] [rbp-98h] BYREF
  char *v64; // [rsp+78h] [rbp-90h] BYREF
  char v65[8]; // [rsp+80h] [rbp-88h] BYREF
  struct std::locale::_Locimp *v66; // [rsp+88h] [rbp-80h]
  char *v67; // [rsp+90h] [rbp-78h] BYREF
  _QWORD *v68; // [rsp+98h] [rbp-70h]
  _QWORD v69[16]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v70; // [rsp+128h] [rbp+20h] BYREF
  __int64 v71; // [rsp+138h] [rbp+30h]
  unsigned __int64 v72; // [rsp+140h] [rbp+38h]
  _BYTE v73[32]; // [rsp+148h] [rbp+40h] BYREF
  char v74; // [rsp+168h] [rbp+60h] BYREF
  _BYTE v75[1384]; // [rsp+169h] [rbp+61h] BYREF
  _BYTE v76[7]; // [rsp+6D1h] [rbp+5C9h] BYREF

  v68 = a1;
  v53 = *(_BYTE *)(a4 + 10);
  if ( !v53 )
    v53 = 2;
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
  *(_OWORD *)&v62[1] = 0;
  v12 = v9;
  if ( (int)v9 > 1074 )
    v12 = 1074;
  LODWORD(v63) = v12;
  v13 = (unsigned int)(v9 - 1074);
  if ( (int)v9 <= 1074 )
    v13 = 0;
  v59 = v13;
  v55 = (unsigned int)_o__fdsign(v13, v9, 1074, 2) != 0;
  if ( v12 == -1 )
  {
    if ( v10 )
      v14 = (_OWORD *)std::to_chars(v65, &v74, v76);
    else
      v14 = (_OWORD *)std::to_chars(v65, &v74, v76);
  }
  else
  {
    v14 = (_OWORD *)std::to_chars(v65, &v74, v76);
  }
  *(_OWORD *)&v62[1] = *v14;
  v15 = (char *)v62[1];
  v16 = &v74;
  v61 = &v74;
  v17 = LODWORD(v62[1]) - (unsigned int)&v74;
  v57 = v17;
  if ( v55 )
  {
    v16 = v75;
    v61 = v75;
  }
  else if ( v53 != 2 )
  {
    v57 = ++v17;
  }
  if ( v7 )
  {
    if ( v16 != (char *)v62[1] )
    {
      do
      {
        if ( (unsigned __int8)(*v16 - 97) <= 0x19u )
          *v16 -= 32;
        ++v16;
      }
      while ( v16 != v15 );
      v15 = (char *)v62[1];
      v16 = v61;
      v17 = v57;
    }
    v8 -= 32;
  }
  v18 = (_mm_cvtsi128_si32(*(__m128i *)&a3) & 0x7F800000) == 2139095040;
  v19 = 0;
  v54 = 0;
  v20 = v15;
  v62[0] = v15;
  v21 = v15;
  v67 = v15;
  v64 = v15;
  v22 = 0;
  v58 = 0;
  v60 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 15;
  LOBYTE(v70) = 0;
  if ( !v18 )
  {
    v23 = *(_BYTE *)(a4 + 11);
    if ( v23 || (v24 = (_BYTE *)(a4 + 12), *(_BYTE *)(a4 + 12)) )
    {
      v25 = v16;
      if ( v16 >= v15 )
        goto LABEL_58;
      do
      {
        if ( *v25 == 46 )
        {
          v21 = v25;
          v67 = v25;
        }
        else if ( *v25 == v8 )
        {
          v20 = v25;
          v62[0] = v25;
        }
        ++v25;
      }
      while ( v25 < v15 );
      v26 = v20;
      if ( v20 >= v21 )
LABEL_58:
        v26 = v21;
      v64 = v26;
      if ( v23 && v21 == v15 )
      {
        v57 = ++v17;
        v19 = 1;
        v54 = 1;
      }
      v24 = (_BYTE *)(a4 + 12);
      if ( *(_BYTE *)(a4 + 12) )
      {
        if ( a5 )
        {
          v66 = *(struct std::locale::_Locimp **)(a5 + 8);
          (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v66 + 8LL))(v66);
        }
        else
        {
          v66 = std::locale::_Init(1);
        }
        v27 = std::use_facet<std::numpunct<char>>(v65);
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v27 + 40LL))(v27, v73);
        std::string::operator=(&v70, v73);
        std::string::~string(v73);
        if ( v66 )
        {
          v28 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v66 + 16LL))(v66);
          if ( v28 )
            (**v28)(v28, 1);
        }
        v29 = (char *)&v70;
        if ( v72 > 0xF )
          v29 = (char *)v70;
        v16 = v61;
        v30 = 0;
        if ( v71 )
        {
          v31 = v64 - v61;
          v32 = *v29;
          if ( v64 - v61 > v32 )
          {
            v33 = &v29[v71];
            do
            {
              v31 -= (char)v32;
              ++v30;
              v34 = v29 + 1;
              if ( v29 + 1 == v33 )
                v34 = v29;
              v29 = v34;
              v32 = *v34;
            }
            while ( v31 > v32 );
          }
        }
        v60 = v30;
        v17 = v30 + v57;
        v57 += v30;
        v15 = (char *)v62[1];
        v19 = v54;
        v20 = (char *)v62[0];
        v22 = v58;
      }
    }
    v35 = v11 - 1;
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( !v36 )
      {
        v22 = v59;
LABEL_101:
        v58 = v22;
LABEL_102:
        v18 = 0;
        goto LABEL_103;
      }
      if ( v36 == 1 )
      {
        if ( *(_BYTE *)(a4 + 11) && ((*(_BYTE *)(a4 + 8) - 71) & 0xDF) == 0 )
        {
          v37 = (_DWORD)v20 - (_DWORD)v16;
          if ( !v19 )
            --v37;
          v22 = v63 + v59 - v37;
          v58 = v22;
          if ( v20 == v15 && COERCE_FLOAT(LODWORD(a3) & _xmm) < 1.0 && *(float *)&a3 != 0.0 )
          {
            while ( v16 < v15 )
            {
              if ( *v16 == 48 )
              {
                v58 = ++v22;
              }
              else if ( *v16 != 46 )
              {
                goto LABEL_102;
              }
              ++v16;
            }
          }
        }
        goto LABEL_102;
      }
    }
    v22 = v59;
    if ( v59 && !*(_BYTE *)(a4 + 11) && !*v24 )
    {
      do
        v62[0] = --v20;
      while ( *v20 != v8 );
    }
    goto LABEL_101;
  }
LABEL_103:
  v38 = v22 + v17;
  v57 = v38;
  v39 = *(_BYTE *)(a4 + 13) && !*(_BYTE *)(a4 + 9) && !v18;
  LOBYTE(v56) = v39;
  v69[0] = &v53;
  v69[1] = &v55;
  v69[2] = &v56;
  v69[3] = &v57;
  v69[4] = a4;
  v69[5] = &a5;
  v69[6] = &v61;
  v69[7] = &v64;
  v69[8] = &v70;
  v69[9] = &v60;
  v69[10] = &v67;
  v69[11] = &v62[1];
  v69[12] = &v54;
  v69[13] = v62;
  v69[14] = &v58;
  if ( v39 )
  {
    `std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
      v69,
      v68,
      a2);
    std::string::~string(&v70);
    return v68;
  }
  v41 = 0;
  v42 = 0;
  v43 = *(_BYTE *)(a4 + 9);
  if ( !v43 )
    v43 = 2;
  if ( v38 < *(_DWORD *)a4 )
  {
    switch ( v43 )
    {
      case 1:
        v44 = *(_DWORD *)a4;
        break;
      case 2:
        v41 = *(_DWORD *)a4 - v38;
        goto LABEL_120;
      case 3:
        v41 = (*(_DWORD *)a4 - v38) / 2;
        v44 = *(_DWORD *)a4 - v41;
        break;
      default:
        goto LABEL_120;
    }
    v42 = v44 - v38;
  }
LABEL_120:
  v45 = (char *)(a4 + 15);
  v46 = a4 + 15 + *(unsigned __int8 *)(a4 + 14);
  while ( v41 > 0 )
  {
    for ( i = v45; i != (char *)v46; ++i )
    {
      v48 = *i;
      if ( (unsigned __int64)(*(_QWORD *)(a2 + 16) + 1LL) > *(_QWORD *)(a2 + 24) )
        (**(void (__fastcall ***)(__int64))a2)(a2);
      *(_BYTE *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 8)) = v48;
      ++*(_QWORD *)(a2 + 16);
    }
    --v41;
  }
  v49 = *(_QWORD *)`std::_Fmt_write<char,std::back_insert_iterator<std::_Fmt_buffer<char>>,long double>'::`2'::_lambda_1_::operator()(
                     v69,
                     &v63,
                     a2);
  while ( v42 > 0 )
  {
    for ( j = v45; j != (char *)v46; ++j )
    {
      v51 = *j;
      if ( (unsigned __int64)(*(_QWORD *)(v49 + 16) + 1LL) > *(_QWORD *)(v49 + 24) )
        (**(void (__fastcall ***)(__int64))v49)(v49);
      *(_BYTE *)(*(_QWORD *)(v49 + 8) + (*(_QWORD *)(v49 + 16))++) = v51;
    }
    --v42;
  }
  v52 = v68;
  *v68 = v49;
  std::string::~string(&v70);
  return v52;
}

```

## disassembly

```asm
0x18002f348  mov     rax, rsp
0x18002f34b  mov     [rax+10h], rbx
0x18002f34f  push    rbp
0x18002f350  push    rsi
0x18002f351  push    rdi
0x18002f352  push    r12
0x18002f354  push    r13
0x18002f356  push    r14
0x18002f358  push    r15
0x18002f35a  lea     rbp, [rax-628h]
0x18002f361  sub     rsp, 6F0h
0x18002f368  movaps  xmmword ptr [rax-48h], xmm6
0x18002f36c  mov     rax, cs:__security_cookie
0x18002f373  xor     rax, rsp
0x18002f376  mov     [rbp+620h+var_50], rax
0x18002f37d  mov     r14, r9
0x18002f380  movaps  xmm6, xmm2
0x18002f383  mov     rbx, rdx
0x18002f386  mov     [rbp+620h+var_690], rcx
0x18002f38a  mov     al, [r9+0Ah]
0x18002f38e  mov     byte ptr [rsp+720h+var_6F0+1], al
0x18002f392  mov     r9d, 2
0x18002f398  test    al, al
0x18002f39a  jnz     short loc_18002F3A1
0x18002f39c  mov     byte ptr [rsp+720h+var_6F0+1], r9b
0x18002f3a1  xor     sil, sil
0x18002f3a4  mov     r13b, 65h ; 'e'
0x18002f3a7  mov     edx, [r14+4]
0x18002f3ab  xor     r15b, r15b
0x18002f3ae  movsx   ecx, byte ptr [r14+8]
0x18002f3b3  mov     edi, 4
0x18002f3b8  lea     r8d, [rdi-3]
0x18002f3bc  sub     ecx, 41h ; 'A'
0x18002f3bf  jz      short loc_18002F42D
0x18002f3c1  sub     ecx, edi
0x18002f3c3  jz      short loc_18002F41A
0x18002f3c5  sub     ecx, r8d
0x18002f3c8  jz      short loc_18002F407
0x18002f3ca  sub     ecx, r8d
0x18002f3cd  jz      short loc_18002F3EB
0x18002f3cf  sub     ecx, 1Ah
0x18002f3d2  jz      short loc_18002F430
0x18002f3d4  sub     ecx, edi
0x18002f3d6  jz      short loc_18002F41D
0x18002f3d8  sub     ecx, r8d
0x18002f3db  jz      short loc_18002F40A
0x18002f3dd  cmp     ecx, r8d
0x18002f3e0  jz      short loc_18002F3EE
0x18002f3e2  lea     edi, [r8+2]
0x18002f3e6  mov     r15b, r8b
0x18002f3e9  jmp     short loc_18002F433
0x18002f3eb  mov     sil, r8b
0x18002f3ee  cmp     edx, 0FFFFFFFFh
0x18002f3f1  jnz     short loc_18002F3FA
0x18002f3f3  mov     edx, 6
0x18002f3f8  jmp     short loc_18002F400
0x18002f3fa  test    edx, edx
0x18002f3fc  cmovz   edx, r8d
0x18002f400  mov     edi, 3
0x18002f405  jmp     short loc_18002F433
0x18002f407  mov     sil, r8b
0x18002f40a  mov     eax, 6
0x18002f40f  cmp     edx, 0FFFFFFFFh
0x18002f412  cmovz   edx, eax
0x18002f415  mov     edi, r9d
0x18002f418  jmp     short loc_18002F433
0x18002f41a  mov     sil, r8b
0x18002f41d  mov     eax, 6
0x18002f422  cmp     edx, 0FFFFFFFFh
0x18002f425  cmovz   edx, eax
0x18002f428  mov     edi, r8d
0x18002f42b  jmp     short loc_18002F433
0x18002f42d  mov     sil, r8b
0x18002f430  mov     r13b, 70h ; 'p'
0x18002f433  xorps   xmm0, xmm0
0x18002f436  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18002f43b  mov     r12d, edx
0x18002f43e  mov     r8d, 432h
0x18002f444  cmp     edx, r8d
0x18002f447  cmovg   r12d, r8d
0x18002f44b  mov     dword ptr [rsp+720h+var_6B8], r12d
0x18002f450  lea     ecx, [rdx-432h]
0x18002f456  xor     eax, eax
0x18002f458  cmp     edx, r8d
0x18002f45b  cmovle  ecx, eax
0x18002f45e  mov     dword ptr [rsp+720h+var_6E0], ecx
0x18002f462  movaps  xmm0, xmm6
0x18002f465  call    cs:__imp__o__fdsign
0x18002f46b  mov     edx, eax
0x18002f46d  test    eax, eax
0x18002f46f  setnz   byte ptr [rsp+720h+var_6F0+3]
0x18002f474  ucomiss xmm6, xmm6
0x18002f477  setp    al
0x18002f47a  cmp     al, 1
0x18002f47c  jnz     short loc_18002F4B3
0x18002f47e  lea     rax, [rbp+620h+var_5C0]
0x18002f482  lea     rcx, [rbp+620h+var_5BF]
0x18002f486  test    edx, edx
0x18002f488  cmovz   rcx, rax
0x18002f48c  mov     qword ptr [rsp+720h+var_6D0+8], rcx
0x18002f491  mov     eax, dword ptr cs:aNan; "nan"
0x18002f497  mov     [rcx], ax
0x18002f49a  mov     al, byte ptr cs:aNan+2; "n"
0x18002f4a0  mov     [rcx+2], al
0x18002f4a3  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002f4a8  add     r9, 3
0x18002f4ac  mov     qword ptr [rsp+720h+var_6D0+8], r9
0x18002f4b1  jmp     short loc_18002F4FE
0x18002f4b3  movaps  xmm3, xmm6
0x18002f4b6  lea     r8, [rbp+620h+var_57]
0x18002f4bd  lea     rdx, [rbp+620h+var_5C0]
0x18002f4c1  lea     rcx, [rsp+720h+var_6A8]
0x18002f4c6  cmp     r12d, 0FFFFFFFFh
0x18002f4ca  jnz     short loc_18002F4E3
0x18002f4cc  test    r15b, r15b
0x18002f4cf  jz      short loc_18002F4D8
0x18002f4d1  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0M@Z; std::to_chars(char * const,char * const,float)
0x18002f4d6  jmp     short loc_18002F4F1
0x18002f4d8  mov     [rsp+720h+var_700], edi
0x18002f4dc  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@@Z; std::to_chars(char * const,char * const,float,std::chars_format)
0x18002f4e1  jmp     short loc_18002F4F1
0x18002f4e3  mov     dword ptr [rsp+720h+var_6F8], r12d
0x18002f4e8  mov     [rsp+720h+var_700], edi
0x18002f4ec  call    ?to_chars@std@@YA?AUto_chars_result@1@QEAD0MW4chars_format@1@H@Z; std::to_chars(char * const,char * const,float,std::chars_format,int)
0x18002f4f1  movups  xmm0, xmmword ptr [rax]
0x18002f4f4  movups  xmmword ptr [rsp+720h+var_6D0+8], xmm0
0x18002f4f9  movq    r9, xmm0
0x18002f4fe  lea     rdx, [rbp+620h+var_5C0]
0x18002f502  mov     [rsp+720h+var_6D8], rdx
0x18002f507  mov     ecx, r9d
0x18002f50a  sub     ecx, edx
0x18002f50c  mov     [rsp+720h+var_6E8], ecx
0x18002f510  cmp     byte ptr [rsp+720h+var_6F0+3], 0
0x18002f515  jz      short loc_18002F522
0x18002f517  lea     rdx, [rbp+620h+var_5BF]
0x18002f51b  mov     [rsp+720h+var_6D8], rdx
0x18002f520  jmp     short loc_18002F52F
0x18002f522  cmp     byte ptr [rsp+720h+var_6F0+1], 2
0x18002f527  jz      short loc_18002F52F
0x18002f529  inc     ecx
0x18002f52b  mov     [rsp+720h+var_6E8], ecx
0x18002f52f  test    sil, sil
0x18002f532  jz      short loc_18002F561
0x18002f534  cmp     rdx, r9
0x18002f537  jz      short loc_18002F55D
0x18002f539  mov     cl, [rdx]
0x18002f53b  lea     eax, [rcx-61h]
0x18002f53e  cmp     al, 19h
0x18002f540  ja      short loc_18002F547
0x18002f542  sub     cl, 20h ; ' '
0x18002f545  mov     [rdx], cl
0x18002f547  inc     rdx
0x18002f54a  cmp     rdx, r9
0x18002f54d  jnz     short loc_18002F539
0x18002f54f  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002f554  mov     rdx, [rsp+720h+var_6D8]
0x18002f559  mov     ecx, [rsp+720h+var_6E8]
0x18002f55d  add     r13b, 0E0h
0x18002f561  movd    eax, xmm6
0x18002f565  mov     r8d, 7F800000h
0x18002f56b  and     eax, r8d
0x18002f56e  cmp     eax, r8d
0x18002f571  setnz   al
0x18002f574  xor     al, 1
0x18002f576  mov     byte ptr [rsp+720h+var_6F0], al
0x18002f57a  mov     r15b, 0
0x18002f57d  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002f582  mov     r10, r9
0x18002f585  mov     qword ptr [rsp+720h+var_6D0], r9
0x18002f58a  mov     r11, r9
0x18002f58d  mov     [rbp+620h+var_698], r9
0x18002f591  mov     [rsp+720h+var_6B0], r9
0x18002f596  mov     r8d, 0
0x18002f59c  mov     [rsp+720h+var_6E4], r8d
0x18002f5a1  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002f5a6  xorps   xmm0, xmm0
0x18002f5a9  movups  [rbp+620h+var_600], xmm0
0x18002f5ad  mov     [rbp+620h+var_5F0], r8
0x18002f5b1  mov     [rbp+620h+var_5E8], 0Fh
0x18002f5b9  mov     byte ptr [rbp+620h+var_600], r8b
0x18002f5bd  jnz     loc_18002F808
0x18002f5c3  mov     r12b, [r14+0Bh]
0x18002f5c7  test    r12b, r12b
0x18002f5ca  jnz     short loc_18002F5D9
0x18002f5cc  lea     rsi, [r14+0Ch]
0x18002f5d0  cmp     [rsi], r12b
0x18002f5d3  jz      loc_18002F740
0x18002f5d9  mov     rax, rdx
0x18002f5dc  cmp     rdx, r9
0x18002f5df  jnb     short loc_18002F60C
0x18002f5e1  cmp     byte ptr [rax], 2Eh ; '.'
0x18002f5e4  jnz     short loc_18002F5EF
0x18002f5e6  mov     r11, rax
0x18002f5e9  mov     [rbp+620h+var_698], rax
0x18002f5ed  jmp     short loc_18002F5FC
0x18002f5ef  cmp     [rax], r13b
0x18002f5f2  jnz     short loc_18002F5FC
0x18002f5f4  mov     r10, rax
0x18002f5f7  mov     qword ptr [rsp+720h+var_6D0], rax
0x18002f5fc  inc     rax
0x18002f5ff  cmp     rax, r9
0x18002f602  jb      short loc_18002F5E1
0x18002f604  cmp     r10, r11
0x18002f607  mov     rax, r10
0x18002f60a  jb      short loc_18002F60F
0x18002f60c  mov     rax, r11
0x18002f60f  mov     [rsp+720h+var_6B0], rax
0x18002f614  test    r12b, r12b
0x18002f617  jz      short loc_18002F62C
0x18002f619  cmp     r11, r9
0x18002f61c  jnz     short loc_18002F62C
0x18002f61e  inc     ecx
0x18002f620  mov     [rsp+720h+var_6E8], ecx
0x18002f624  mov     r15b, 1
0x18002f627  mov     byte ptr [rsp+720h+var_6F0+2], r15b
0x18002f62c  lea     rsi, [r14+0Ch]
0x18002f630  cmp     byte ptr [rsi], 0
0x18002f633  jz      loc_18002F740
0x18002f639  mov     rax, [rbp+620h+arg_20]
0x18002f640  test    rax, rax
0x18002f643  jz      short loc_18002F65B
0x18002f645  mov     rcx, [rax+8]
0x18002f649  mov     [rbp+620h+var_6A0], rcx
0x18002f64d  mov     rax, [rcx]
0x18002f650  mov     rax, [rax+8]
0x18002f654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f659  jmp     short loc_18002F667
0x18002f65b  mov     cl, 1
0x18002f65d  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002f663  mov     [rbp+620h+var_6A0], rax
0x18002f667  lea     rcx, [rsp+720h+var_6A8]
0x18002f66c  call    ??$use_facet@V?$numpunct@D@std@@@std@@YAAEBV?$numpunct@D@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<char>>(std::locale const &)
0x18002f671  mov     rcx, rax
0x18002f674  mov     rax, [rax]
0x18002f677  lea     rdx, [rbp+620h+var_5E0]
0x18002f67b  mov     rax, [rax+28h]
0x18002f67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f684  lea     rdx, [rbp+620h+var_5E0]
0x18002f688  lea     rcx, [rbp+620h+var_600]
0x18002f68c  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002f691  lea     rcx, [rbp+620h+var_5E0]
0x18002f695  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002f69a  nop
0x18002f69b  mov     rcx, [rbp+620h+var_6A0]
0x18002f69f  test    rcx, rcx
0x18002f6a2  jz      short loc_18002F6C8
0x18002f6a4  mov     rax, [rcx]
0x18002f6a7  mov     rax, [rax+10h]
0x18002f6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6b0  mov     rcx, rax
0x18002f6b3  test    rax, rax
0x18002f6b6  jz      short loc_18002F6C8
0x18002f6b8  mov     rax, [rax]
0x18002f6bb  mov     edx, 1
0x18002f6c0  mov     rax, [rax]
0x18002f6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6c8  lea     rax, [rbp+620h+var_600]
0x18002f6cc  cmp     [rbp+620h+var_5E8], 0Fh
0x18002f6d1  cmova   rax, qword ptr [rbp+620h+var_600]
0x18002f6d6  mov     r10, [rbp+620h+var_5F0]
0x18002f6da  mov     rdx, [rsp+720h+var_6D8]
0x18002f6df  xor     r8d, r8d
0x18002f6e2  test    r10, r10
0x18002f6e5  jz      short loc_18002F71C
0x18002f6e7  mov     r9, [rsp+720h+var_6B0]
0x18002f6ec  sub     r9, rdx
0x18002f6ef  movsx   r11, byte ptr [rax]
0x18002f6f3  cmp     r9, r11
0x18002f6f6  jbe     short loc_18002F71C
0x18002f6f8  add     r10, rax
0x18002f6fb  movsx   rcx, r11b
0x18002f6ff  sub     r9, rcx
0x18002f702  inc     r8d
0x18002f705  lea     rcx, [rax+1]
0x18002f709  cmp     rcx, r10
0x18002f70c  cmovz   rcx, rax
0x18002f710  mov     rax, rcx
0x18002f713  movsx   r11, byte ptr [rcx]
0x18002f717  cmp     r9, r11
0x18002f71a  ja      short loc_18002F6FB
0x18002f71c  mov     dword ptr [rsp+720h+var_6E0+4], r8d
0x18002f721  mov     ecx, [rsp+720h+var_6E8]
0x18002f725  add     ecx, r8d
0x18002f728  mov     [rsp+720h+var_6E8], ecx
0x18002f72c  mov     r9, qword ptr [rsp+720h+var_6D0+8]
0x18002f731  mov     r15b, byte ptr [rsp+720h+var_6F0+2]
0x18002f736  mov     r10, qword ptr [rsp+720h+var_6D0]
0x18002f73b  mov     r8d, [rsp+720h+var_6E4]
0x18002f740  sub     edi, 1
0x18002f743  jz      loc_18002F7D5
0x18002f749  sub     edi, 1
0x18002f74c  jz      loc_18002F7FA
0x18002f752  cmp     edi, 1
0x18002f755  jnz     short loc_18002F7D5
0x18002f757  cmp     byte ptr [r14+0Bh], 0
0x18002f75c  jz      loc_18002F804
0x18002f762  mov     al, [r14+8]
0x18002f766  sub     al, 47h ; 'G'
0x18002f768  test    al, 0DFh
0x18002f76a  jnz     loc_18002F804
  ... truncated ...
```
