# std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,long double,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)

- ea: `0x18002d25c`
- end: `0x18002d8df`
- name: `??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@OAEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
- size: `1667`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002ff18`

## callees

- `0x180005020`
- `0x18002a334`
- `0x18002afd4`
- `0x18002b100`
- `0x18002b2ac`
- `0x18002d25c`
- `0x180033a7c`
- `0x1800342a8`
- `0x180034450`
- `0x180034bdc`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002d584`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002d584`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x18002d377`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x18002d377`

## pseudocode

```c
_QWORD *__fastcall std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>(
        _QWORD *a1,
        __int64 a2,
        long double a3,
        __int64 a4,
        __int64 a5)
{
  char v7; // di
  char v8; // r13
  int v9; // edx
  char v10; // r15
  int v11; // esi
  int v12; // r12d
  int v13; // ecx
  char *v14; // r9
  char *v15; // rdx
  int v16; // ecx
  bool v17; // al
  char v18; // di
  char *v19; // r10
  char *v20; // r11
  int v21; // r8d
  char v22; // r12
  _BYTE *v23; // r15
  char *v24; // rax
  char *v25; // rax
  struct std::locale::_Locimp *v26; // rdi
  __int64 v27; // rax
  void (__fastcall ***v28)(_QWORD, __int64); // rax
  char *v29; // rax
  int v30; // r8d
  unsigned __int64 v31; // r9
  unsigned __int64 v32; // r11
  char *v33; // r10
  int v34; // esi
  int v35; // esi
  int v36; // eax
  int v37; // ecx
  bool v38; // al
  int v40; // esi
  int v41; // edi
  char v42; // al
  int v43; // edi
  __int64 v44; // rax
  _QWORD *v45; // rbx
  char v46; // [rsp+39h] [rbp-CFh] BYREF
  char v47; // [rsp+3Ah] [rbp-CEh] BYREF
  bool v48; // [rsp+3Bh] [rbp-CDh] BYREF
  int v49; // [rsp+3Ch] [rbp-CCh] BYREF
  int v50; // [rsp+40h] [rbp-C8h] BYREF
  int v51; // [rsp+44h] [rbp-C4h] BYREF
  int v52; // [rsp+48h] [rbp-C0h]
  __int128 v53; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-A0h] BYREF
  char *v55; // [rsp+70h] [rbp-98h] BYREF
  char *v56; // [rsp+78h] [rbp-90h] BYREF
  __int128 v57; // [rsp+88h] [rbp-80h] BYREF
  char *v58; // [rsp+98h] [rbp-70h] BYREF
  _DWORD v59[4]; // [rsp+A0h] [rbp-68h] BYREF
  char *v60; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD *v61; // [rsp+B8h] [rbp-50h]
  _QWORD v62[16]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v63; // [rsp+148h] [rbp+40h] BYREF
  __int64 v64; // [rsp+158h] [rbp+50h]
  unsigned __int64 v65; // [rsp+160h] [rbp+58h]
  _BYTE v66[32]; // [rsp+168h] [rbp+60h] BYREF
  char v67; // [rsp+188h] [rbp+80h] BYREF
  _BYTE v68[1384]; // [rsp+189h] [rbp+81h] BYREF
  _BYTE v69[7]; // [rsp+6F1h] [rbp+5E9h] BYREF

  v61 = a1;
  v46 = *(_BYTE *)(a4 + 10);
  if ( !v46 )
    v46 = 2;
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
  v57 = 0;
  v12 = v9;
  if ( v9 > 1074 )
    v12 = 1074;
  v59[0] = v12;
  v13 = v9 - 1074;
  if ( v9 <= 1074 )
    v13 = 0;
  v52 = v13;
  v48 = _ldsign(a3) != 0;
  if ( v12 == -1 )
  {
    if ( v10 )
      std::_Floating_to_chars<0,double>(&v53, &v67, v69);
    else
      std::_Floating_to_chars<1,double>(&v53, &v67, v69);
  }
  else
  {
    std::_Floating_to_chars<2,double>(&v53, &v67, v69);
  }
  v57 = v53;
  v14 = (char *)v53;
  v15 = &v67;
  v55 = &v67;
  v16 = v53 - (unsigned int)&v67;
  v50 = v16;
  if ( v48 )
  {
    v15 = v68;
    v55 = v68;
  }
  else if ( v46 != 2 )
  {
    v50 = ++v16;
  }
  if ( v7 )
  {
    if ( v15 != (char *)v53 )
    {
      do
      {
        if ( (unsigned __int8)(*v15 - 97) <= 0x19u )
          *v15 -= 32;
        ++v15;
      }
      while ( v15 != v14 );
      v14 = (char *)v57;
      v15 = v55;
      v16 = v50;
    }
    v8 -= 32;
  }
  v17 = ((*(_QWORD *)&a3 >> 52) & 0x7FF) == 2047;
  v18 = 0;
  v47 = 0;
  v19 = v14;
  v56 = v14;
  v20 = v14;
  v60 = v14;
  v58 = v14;
  v21 = 0;
  v51 = 0;
  LODWORD(v54) = 0;
  v63 = 0;
  v64 = 0;
  v65 = 15;
  LOBYTE(v63) = 0;
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
          v60 = v24;
        }
        else if ( *v24 == v8 )
        {
          v19 = v24;
          v56 = v24;
        }
        ++v24;
      }
      while ( v24 < v14 );
      v25 = v19;
      if ( v19 >= v20 )
LABEL_58:
        v25 = v20;
      v58 = v25;
      if ( v22 && v20 == v14 )
      {
        v50 = ++v16;
        v18 = 1;
        v47 = 1;
      }
      v23 = (_BYTE *)(a4 + 12);
      if ( *(_BYTE *)(a4 + 12) )
      {
        if ( a5 )
        {
          v26 = *(struct std::locale::_Locimp **)(a5 + 8);
          *((_QWORD *)&v53 + 1) = v26;
          (*(void (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v26 + 8LL))(v26);
        }
        else
        {
          v26 = std::locale::_Init(1);
          *((_QWORD *)&v53 + 1) = v26;
        }
        v27 = std::use_facet<std::numpunct<unsigned short>>(&v53);
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v27 + 40LL))(v27, v66);
        std::string::operator=(&v63, v66);
        std::string::~string(v66);
        if ( v26 )
        {
          v28 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v26 + 16LL))(v26);
          if ( v28 )
            (**v28)(v28, 1);
        }
        v29 = (char *)&v63;
        if ( v65 > 0xF )
          v29 = (char *)v63;
        v15 = v55;
        v30 = 0;
        if ( v64 )
        {
          v31 = v58 - v55;
          v32 = *v29;
          if ( v58 - v55 > v32 )
          {
            v33 = &v29[v64];
            do
            {
              v31 -= (char)v32;
              ++v30;
              if ( v29 + 1 != v33 )
                ++v29;
              v32 = *v29;
            }
            while ( v31 > v32 );
          }
        }
        LODWORD(v54) = v30;
        v16 = v30 + v50;
        v50 += v30;
        v14 = (char *)v57;
        v18 = v47;
        v19 = v56;
        v21 = v51;
      }
    }
    v34 = v11 - 1;
    if ( v34 )
    {
      v35 = v34 - 1;
      if ( !v35 )
      {
        v21 = v52;
LABEL_101:
        v51 = v21;
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
          v21 = v59[0] + v52 - v36;
          v51 = v21;
          if ( v19 == v14 && COERCE_DOUBLE(*(_QWORD *)&a3 & _xmm) < 1.0 && a3 != 0.0 )
          {
            while ( v15 < v14 )
            {
              if ( *v15 == 48 )
              {
                v51 = ++v21;
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
    v21 = v52;
    if ( v52 && !*(_BYTE *)(a4 + 11) && !*v23 )
    {
      do
        v56 = --v19;
      while ( *v19 != v8 );
    }
    goto LABEL_101;
  }
LABEL_103:
  v37 = v21 + v16;
  v50 = v37;
  v38 = *(_BYTE *)(a4 + 13) && !*(_BYTE *)(a4 + 9) && !v17;
  LOBYTE(v49) = v38;
  v62[0] = &v46;
  v62[1] = &v48;
  v62[2] = &v49;
  v62[3] = &v50;
  v62[4] = a4;
  v62[5] = &a5;
  v62[6] = &v55;
  v62[7] = &v58;
  v62[8] = &v63;
  v62[9] = &v54;
  v62[10] = &v60;
  v62[11] = &v57;
  v62[12] = &v47;
  v62[13] = &v56;
  v62[14] = &v51;
  if ( v38 )
  {
    `std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
      v62,
      v61,
      a2);
    std::string::~string(&v63);
    return v61;
  }
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
        v43 = *(_DWORD *)a4;
        break;
      case 2:
        v40 = *(_DWORD *)a4 - v37;
        goto LABEL_120;
      case 3:
        v40 = (*(_DWORD *)a4 - v37) / 2;
        v43 = *(_DWORD *)a4 - v40;
        break;
      default:
        goto LABEL_120;
    }
    v41 = v43 - v37;
  }
LABEL_120:
  *(_QWORD *)&v53 = a4 + 16;
  *((_QWORD *)&v53 + 1) = *(unsigned __int8 *)(a4 + 14);
  while ( v40 > 0 )
  {
    a2 = *(_QWORD *)(std::ranges::_Copy_fn::operator()<std::basic_string_view<unsigned short> const &,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
                       v59,
                       &v53,
                       a2)
                   + 8);
    --v40;
  }
  v44 = *(_QWORD *)`std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,long double>'::`2'::_lambda_1_::operator()(
                     v62,
                     v59,
                     a2);
  while ( v41 > 0 )
  {
    v44 = *(_QWORD *)(std::ranges::_Copy_fn::operator()<std::basic_string_view<unsigned short> const &,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>>(
                        v59,
                        &v53,
                        v44)
                    + 8);
    --v41;
  }
  v45 = v61;
  *v61 = v44;
  std::string::~string(&v63);
  return v45;
}

```

## disassembly

```asm
0x18002d25c  mov     rax, rsp
0x18002d25f  mov     [rax+10h], rbx
0x18002d263  push    rbp
0x18002d264  push    rsi
0x18002d265  push    rdi
0x18002d266  push    r12
0x18002d268  push    r13
0x18002d26a  push    r14
0x18002d26c  push    r15
0x18002d26e  lea     rbp, [rax-648h]
0x18002d275  sub     rsp, 710h
0x18002d27c  movaps  xmmword ptr [rax-48h], xmm6
0x18002d280  mov     rax, cs:__security_cookie
0x18002d287  xor     rax, rsp
0x18002d28a  mov     [rbp+640h+var_50], rax
0x18002d291  mov     r14, r9
0x18002d294  movaps  xmm6, xmm2
0x18002d297  mov     rbx, rdx
0x18002d29a  mov     [rbp+640h+var_690], rcx
0x18002d29e  mov     al, [r9+0Ah]
0x18002d2a2  mov     byte ptr [rsp+740h+var_710+1], al
0x18002d2a6  mov     r9d, 2
0x18002d2ac  test    al, al
0x18002d2ae  jnz     short loc_18002D2B5
0x18002d2b0  mov     byte ptr [rsp+740h+var_710+1], r9b
0x18002d2b5  xor     dil, dil
0x18002d2b8  mov     r13b, 65h ; 'e'
0x18002d2bb  mov     edx, [r14+4]
0x18002d2bf  xor     r15b, r15b
0x18002d2c2  movsx   ecx, byte ptr [r14+8]
0x18002d2c7  mov     esi, 4
0x18002d2cc  lea     r8d, [rsi-3]
0x18002d2d0  sub     ecx, 41h ; 'A'
0x18002d2d3  jz      short loc_18002D341
0x18002d2d5  sub     ecx, esi
0x18002d2d7  jz      short loc_18002D32E
0x18002d2d9  sub     ecx, r8d
0x18002d2dc  jz      short loc_18002D31B
0x18002d2de  sub     ecx, r8d
0x18002d2e1  jz      short loc_18002D2FF
0x18002d2e3  sub     ecx, 1Ah
0x18002d2e6  jz      short loc_18002D344
0x18002d2e8  sub     ecx, esi
0x18002d2ea  jz      short loc_18002D331
0x18002d2ec  sub     ecx, r8d
0x18002d2ef  jz      short loc_18002D31E
0x18002d2f1  cmp     ecx, r8d
0x18002d2f4  jz      short loc_18002D302
0x18002d2f6  lea     esi, [r8+2]
0x18002d2fa  mov     r15b, r8b
0x18002d2fd  jmp     short loc_18002D347
0x18002d2ff  mov     dil, r8b
0x18002d302  cmp     edx, 0FFFFFFFFh
0x18002d305  jnz     short loc_18002D30E
0x18002d307  mov     edx, 6
0x18002d30c  jmp     short loc_18002D314
0x18002d30e  test    edx, edx
0x18002d310  cmovz   edx, r8d
0x18002d314  mov     esi, 3
0x18002d319  jmp     short loc_18002D347
0x18002d31b  mov     dil, r8b
0x18002d31e  mov     eax, 6
0x18002d323  cmp     edx, 0FFFFFFFFh
0x18002d326  cmovz   edx, eax
0x18002d329  mov     esi, r9d
0x18002d32c  jmp     short loc_18002D347
0x18002d32e  mov     dil, r8b
0x18002d331  mov     eax, 6
0x18002d336  cmp     edx, 0FFFFFFFFh
0x18002d339  cmovz   edx, eax
0x18002d33c  mov     esi, r8d
0x18002d33f  jmp     short loc_18002D347
0x18002d341  mov     dil, r8b
0x18002d344  mov     r13b, 70h ; 'p'
0x18002d347  xorps   xmm0, xmm0
0x18002d34a  movups  [rbp+640h+var_6C0], xmm0
0x18002d34e  mov     r12d, edx
0x18002d351  mov     r8d, 432h
0x18002d357  cmp     edx, r8d
0x18002d35a  cmovg   r12d, r8d
0x18002d35e  mov     [rbp+640h+var_6A8], r12d
0x18002d362  lea     ecx, [rdx-432h]
0x18002d368  xor     eax, eax
0x18002d36a  cmp     edx, r8d
0x18002d36d  cmovle  ecx, eax
0x18002d370  mov     [rsp+740h+var_700], ecx
0x18002d374  movaps  xmm0, xmm6; X
0x18002d377  call    cs:__imp__ldsign
0x18002d37d  mov     edx, eax
0x18002d37f  test    eax, eax
0x18002d381  setnz   byte ptr [rsp+740h+var_710+3]
0x18002d386  ucomisd xmm6, xmm6
0x18002d38a  setp    al
0x18002d38d  cmp     al, 1
0x18002d38f  jnz     short loc_18002D3C9
0x18002d391  lea     rax, [rbp+640h+var_5C0]
0x18002d398  lea     rcx, [rbp+640h+var_5BF]
0x18002d39f  test    edx, edx
0x18002d3a1  cmovz   rcx, rax
0x18002d3a5  mov     qword ptr [rbp+640h+var_6C0], rcx
0x18002d3a9  mov     eax, dword ptr cs:aNan; "nan"
0x18002d3af  mov     [rcx], ax
0x18002d3b2  mov     al, byte ptr cs:aNan+2; "n"
0x18002d3b8  mov     [rcx+2], al
0x18002d3bb  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18002d3bf  add     r9, 3
0x18002d3c3  mov     qword ptr [rbp+640h+var_6C0], r9
0x18002d3c7  jmp     short loc_18002D418
0x18002d3c9  movaps  xmm3, xmm6
0x18002d3cc  lea     r8, [rbp+640h+var_57]
0x18002d3d3  lea     rdx, [rbp+640h+var_5C0]
0x18002d3da  lea     rcx, [rsp+740h+var_6F8+8]
0x18002d3df  cmp     r12d, 0FFFFFFFFh
0x18002d3e3  jnz     short loc_18002D3FC
0x18002d3e5  test    r15b, r15b
0x18002d3e8  jz      short loc_18002D3F1
0x18002d3ea  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18002d3ef  jmp     short loc_18002D40A
0x18002d3f1  mov     [rsp+740h+var_720], esi
0x18002d3f5  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x18002d3fa  jmp     short loc_18002D40A
0x18002d3fc  mov     dword ptr [rsp+740h+var_718], r12d
0x18002d401  mov     [rsp+740h+var_720], esi
0x18002d405  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x18002d40a  movaps  xmm0, [rsp+740h+var_6F8+8]
0x18002d40f  movaps  [rbp+640h+var_6C0], xmm0
0x18002d413  movq    r9, xmm0
0x18002d418  lea     rdx, [rbp+640h+var_5C0]
0x18002d41f  mov     [rsp+740h+var_6D8], rdx
0x18002d424  mov     ecx, r9d
0x18002d427  sub     ecx, edx
0x18002d429  mov     [rsp+740h+var_708], ecx
0x18002d42d  cmp     byte ptr [rsp+740h+var_710+3], 0
0x18002d432  jz      short loc_18002D442
0x18002d434  lea     rdx, [rbp+640h+var_5BF]
0x18002d43b  mov     [rsp+740h+var_6D8], rdx
0x18002d440  jmp     short loc_18002D44F
0x18002d442  cmp     byte ptr [rsp+740h+var_710+1], 2
0x18002d447  jz      short loc_18002D44F
0x18002d449  inc     ecx
0x18002d44b  mov     [rsp+740h+var_708], ecx
0x18002d44f  test    dil, dil
0x18002d452  jz      short loc_18002D480
0x18002d454  cmp     rdx, r9
0x18002d457  jz      short loc_18002D47C
0x18002d459  mov     cl, [rdx]
0x18002d45b  lea     eax, [rcx-61h]
0x18002d45e  cmp     al, 19h
0x18002d460  ja      short loc_18002D467
0x18002d462  sub     cl, 20h ; ' '
0x18002d465  mov     [rdx], cl
0x18002d467  inc     rdx
0x18002d46a  cmp     rdx, r9
0x18002d46d  jnz     short loc_18002D459
0x18002d46f  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18002d473  mov     rdx, [rsp+740h+var_6D8]
0x18002d478  mov     ecx, [rsp+740h+var_708]
0x18002d47c  add     r13b, 0E0h
0x18002d480  movq    rax, xmm6
0x18002d485  shr     rax, 34h
0x18002d489  mov     r8d, 7FFh
0x18002d48f  and     eax, r8d
0x18002d492  cmp     eax, r8d
0x18002d495  setnz   al
0x18002d498  xor     al, 1
0x18002d49a  mov     byte ptr [rsp+740h+var_710], al
0x18002d49e  mov     dil, 0
0x18002d4a1  mov     byte ptr [rsp+740h+var_710+2], dil
0x18002d4a6  mov     r10, r9
0x18002d4a9  mov     [rsp+740h+var_6D0], r9
0x18002d4ae  mov     r11, r9
0x18002d4b1  mov     [rbp+640h+var_698], r9
0x18002d4b5  mov     [rbp+640h+var_6B0], r9
0x18002d4b9  mov     r8d, 0
0x18002d4bf  mov     [rsp+740h+var_704], r8d
0x18002d4c4  mov     dword ptr [rsp+740h+var_6E0], r8d
0x18002d4c9  xorps   xmm0, xmm0
0x18002d4cc  movups  [rbp+640h+var_600], xmm0
0x18002d4d0  mov     [rbp+640h+var_5F0], r8
0x18002d4d4  mov     [rbp+640h+var_5E8], 0Fh
0x18002d4dc  mov     byte ptr [rbp+640h+var_600], dil
0x18002d4e0  jnz     loc_18002D72F
0x18002d4e6  mov     r12b, [r14+0Bh]
0x18002d4ea  test    r12b, r12b
0x18002d4ed  jnz     short loc_18002D4FC
0x18002d4ef  lea     r15, [r14+0Ch]
0x18002d4f3  cmp     [r15], r12b
0x18002d4f6  jz      loc_18002D665
0x18002d4fc  mov     rax, rdx
0x18002d4ff  cmp     rdx, r9
0x18002d502  jnb     short loc_18002D52F
0x18002d504  cmp     byte ptr [rax], 2Eh ; '.'
0x18002d507  jnz     short loc_18002D512
0x18002d509  mov     r11, rax
0x18002d50c  mov     [rbp+640h+var_698], rax
0x18002d510  jmp     short loc_18002D51F
0x18002d512  cmp     [rax], r13b
0x18002d515  jnz     short loc_18002D51F
0x18002d517  mov     r10, rax
0x18002d51a  mov     [rsp+740h+var_6D0], rax
0x18002d51f  inc     rax
0x18002d522  cmp     rax, r9
0x18002d525  jb      short loc_18002D504
0x18002d527  cmp     r10, r11
0x18002d52a  mov     rax, r10
0x18002d52d  jb      short loc_18002D532
0x18002d52f  mov     rax, r11
0x18002d532  mov     [rbp+640h+var_6B0], rax
0x18002d536  test    r12b, r12b
0x18002d539  jz      short loc_18002D54E
0x18002d53b  cmp     r11, r9
0x18002d53e  jnz     short loc_18002D54E
0x18002d540  inc     ecx
0x18002d542  mov     [rsp+740h+var_708], ecx
0x18002d546  mov     dil, 1
0x18002d549  mov     byte ptr [rsp+740h+var_710+2], dil
0x18002d54e  lea     r15, [r14+0Ch]
0x18002d552  cmp     byte ptr [r15], 0
0x18002d556  jz      loc_18002D665
0x18002d55c  mov     rax, [rbp+640h+arg_20]
0x18002d563  test    rax, rax
0x18002d566  jz      short loc_18002D582
0x18002d568  mov     rdi, [rax+8]
0x18002d56c  mov     qword ptr [rsp+740h+var_6E8], rdi
0x18002d571  mov     rax, [rdi]
0x18002d574  mov     rcx, rdi
0x18002d577  mov     rax, [rax+8]
0x18002d57b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d580  jmp     short loc_18002D592
0x18002d582  mov     cl, 1
0x18002d584  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002d58a  mov     rdi, rax
0x18002d58d  mov     qword ptr [rsp+740h+var_6E8], rax
0x18002d592  lea     rcx, [rsp+740h+var_6F8+8]
0x18002d597  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x18002d59c  mov     rcx, rax
0x18002d59f  mov     rax, [rax]
0x18002d5a2  lea     rdx, [rbp+640h+var_5E0]
0x18002d5a6  mov     rax, [rax+28h]
0x18002d5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5af  lea     rdx, [rbp+640h+var_5E0]
0x18002d5b3  lea     rcx, [rbp+640h+var_600]
0x18002d5b7  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002d5bc  lea     rcx, [rbp+640h+var_5E0]
0x18002d5c0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002d5c5  nop
0x18002d5c6  test    rdi, rdi
0x18002d5c9  jz      short loc_18002D5F2
0x18002d5cb  mov     rax, [rdi]
0x18002d5ce  mov     rcx, rdi
0x18002d5d1  mov     rax, [rax+10h]
0x18002d5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5da  mov     rcx, rax
0x18002d5dd  test    rax, rax
0x18002d5e0  jz      short loc_18002D5F2
0x18002d5e2  mov     rax, [rax]
0x18002d5e5  mov     edx, 1
0x18002d5ea  mov     rax, [rax]
0x18002d5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5f2  lea     rax, [rbp+640h+var_600]
0x18002d5f6  cmp     [rbp+640h+var_5E8], 0Fh
0x18002d5fb  cmova   rax, qword ptr [rbp+640h+var_600]
0x18002d600  mov     r10, [rbp+640h+var_5F0]
0x18002d604  mov     rdx, [rsp+740h+var_6D8]
0x18002d609  xor     r8d, r8d
0x18002d60c  test    r10, r10
0x18002d60f  jz      short loc_18002D642
0x18002d611  mov     r9, [rbp+640h+var_6B0]
0x18002d615  sub     r9, rdx
0x18002d618  movsx   r11, byte ptr [rax]
0x18002d61c  cmp     r9, r11
0x18002d61f  jbe     short loc_18002D642
0x18002d621  add     r10, rax
0x18002d624  movsx   rcx, r11b
0x18002d628  sub     r9, rcx
0x18002d62b  inc     r8d
0x18002d62e  lea     rcx, [rax+1]
0x18002d632  cmp     rcx, r10
0x18002d635  cmovnz  rax, rcx
0x18002d639  movsx   r11, byte ptr [rax]
0x18002d63d  cmp     r9, r11
0x18002d640  ja      short loc_18002D624
0x18002d642  mov     dword ptr [rsp+740h+var_6E0], r8d
0x18002d647  mov     ecx, [rsp+740h+var_708]
0x18002d64b  add     ecx, r8d
0x18002d64e  mov     [rsp+740h+var_708], ecx
0x18002d652  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18002d656  mov     dil, byte ptr [rsp+740h+var_710+2]
0x18002d65b  mov     r10, [rsp+740h+var_6D0]
0x18002d660  mov     r8d, [rsp+740h+var_704]
0x18002d665  sub     esi, 1
0x18002d668  jz      loc_18002D6FB
0x18002d66e  sub     esi, 1
0x18002d671  jz      loc_18002D721
0x18002d677  cmp     esi, 1
0x18002d67a  jnz     short loc_18002D6FB
0x18002d67c  cmp     byte ptr [r14+0Bh], 0
0x18002d681  jz      loc_18002D72B
0x18002d687  mov     al, [r14+8]
0x18002d68b  sub     al, 47h ; 'G'
  ... truncated ...
```
