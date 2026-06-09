# std::_Fmt_write<ushort,std::back_insert_iterator<std::_Fmt_buffer<ushort>>,double>(std::back_insert_iterator<std::_Fmt_buffer<ushort>>,double,std::_Basic_format_specs<ushort> const &,std::_Lazy_locale)

- ea: `0x18002cbd0`
- end: `0x18002d253`
- name: `??$_Fmt_write@GV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@std@@N@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@G@std@@@0@V10@NAEBU?$_Basic_format_specs@G@0@V_Lazy_locale@0@@Z`
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
- `0x18002cbd0`
- `0x180033a7c`
- `0x1800342a8`
- `0x180034450`
- `0x180034bdc`
- `0x18005e010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002cef8`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18002cef8`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18002cceb`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18002cceb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::_Fmt_write<unsigned short,std::back_insert_iterator<std::_Fmt_buffer<unsigned short>>,double>(
        _QWORD *a1,
        __int64 a2,
        double a3,
        __int64 a4,
        __int64 a5)
{
  char v7; // di
  char v8; // r13
  __int64 v9; // rdx
  char v10; // r15
  int v11; // esi
  int v12; // r12d
  __int64 v13; // rcx
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
  v57 = 0;
  v12 = v9;
  if ( (int)v9 > 1074 )
    v12 = 1074;
  v59[0] = v12;
  v13 = (unsigned int)(v9 - 1074);
  if ( (int)v9 <= 1074 )
    v13 = 0;
  v52 = v13;
  v48 = (unsigned int)_o__dsign(v13, v9, 1074, 2) != 0;
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
0x18002cbd0  mov     rax, rsp
0x18002cbd3  mov     [rax+10h], rbx
0x18002cbd7  push    rbp
0x18002cbd8  push    rsi
0x18002cbd9  push    rdi
0x18002cbda  push    r12
0x18002cbdc  push    r13
0x18002cbde  push    r14
0x18002cbe0  push    r15
0x18002cbe2  lea     rbp, [rax-648h]
0x18002cbe9  sub     rsp, 710h
0x18002cbf0  movaps  xmmword ptr [rax-48h], xmm6
0x18002cbf4  mov     rax, cs:__security_cookie
0x18002cbfb  xor     rax, rsp
0x18002cbfe  mov     [rbp+640h+var_50], rax
0x18002cc05  mov     r14, r9
0x18002cc08  movaps  xmm6, xmm2
0x18002cc0b  mov     rbx, rdx
0x18002cc0e  mov     [rbp+640h+var_690], rcx
0x18002cc12  mov     al, [r9+0Ah]
0x18002cc16  mov     byte ptr [rsp+740h+var_710+1], al
0x18002cc1a  mov     r9d, 2
0x18002cc20  test    al, al
0x18002cc22  jnz     short loc_18002CC29
0x18002cc24  mov     byte ptr [rsp+740h+var_710+1], r9b
0x18002cc29  xor     dil, dil
0x18002cc2c  mov     r13b, 65h ; 'e'
0x18002cc2f  mov     edx, [r14+4]
0x18002cc33  xor     r15b, r15b
0x18002cc36  movsx   ecx, byte ptr [r14+8]
0x18002cc3b  mov     esi, 4
0x18002cc40  lea     r8d, [rsi-3]
0x18002cc44  sub     ecx, 41h ; 'A'
0x18002cc47  jz      short loc_18002CCB5
0x18002cc49  sub     ecx, esi
0x18002cc4b  jz      short loc_18002CCA2
0x18002cc4d  sub     ecx, r8d
0x18002cc50  jz      short loc_18002CC8F
0x18002cc52  sub     ecx, r8d
0x18002cc55  jz      short loc_18002CC73
0x18002cc57  sub     ecx, 1Ah
0x18002cc5a  jz      short loc_18002CCB8
0x18002cc5c  sub     ecx, esi
0x18002cc5e  jz      short loc_18002CCA5
0x18002cc60  sub     ecx, r8d
0x18002cc63  jz      short loc_18002CC92
0x18002cc65  cmp     ecx, r8d
0x18002cc68  jz      short loc_18002CC76
0x18002cc6a  lea     esi, [r8+2]
0x18002cc6e  mov     r15b, r8b
0x18002cc71  jmp     short loc_18002CCBB
0x18002cc73  mov     dil, r8b
0x18002cc76  cmp     edx, 0FFFFFFFFh
0x18002cc79  jnz     short loc_18002CC82
0x18002cc7b  mov     edx, 6
0x18002cc80  jmp     short loc_18002CC88
0x18002cc82  test    edx, edx
0x18002cc84  cmovz   edx, r8d
0x18002cc88  mov     esi, 3
0x18002cc8d  jmp     short loc_18002CCBB
0x18002cc8f  mov     dil, r8b
0x18002cc92  mov     eax, 6
0x18002cc97  cmp     edx, 0FFFFFFFFh
0x18002cc9a  cmovz   edx, eax
0x18002cc9d  mov     esi, r9d
0x18002cca0  jmp     short loc_18002CCBB
0x18002cca2  mov     dil, r8b
0x18002cca5  mov     eax, 6
0x18002ccaa  cmp     edx, 0FFFFFFFFh
0x18002ccad  cmovz   edx, eax
0x18002ccb0  mov     esi, r8d
0x18002ccb3  jmp     short loc_18002CCBB
0x18002ccb5  mov     dil, r8b
0x18002ccb8  mov     r13b, 70h ; 'p'
0x18002ccbb  xorps   xmm0, xmm0
0x18002ccbe  movups  [rbp+640h+var_6C0], xmm0
0x18002ccc2  mov     r12d, edx
0x18002ccc5  mov     r8d, 432h
0x18002cccb  cmp     edx, r8d
0x18002ccce  cmovg   r12d, r8d
0x18002ccd2  mov     [rbp+640h+var_6A8], r12d
0x18002ccd6  lea     ecx, [rdx-432h]
0x18002ccdc  xor     eax, eax
0x18002ccde  cmp     edx, r8d
0x18002cce1  cmovle  ecx, eax
0x18002cce4  mov     [rsp+740h+var_700], ecx
0x18002cce8  movaps  xmm0, xmm6
0x18002cceb  call    cs:__imp__o__dsign
0x18002ccf1  mov     edx, eax
0x18002ccf3  test    eax, eax
0x18002ccf5  setnz   byte ptr [rsp+740h+var_710+3]
0x18002ccfa  ucomisd xmm6, xmm6
0x18002ccfe  setp    al
0x18002cd01  cmp     al, 1
0x18002cd03  jnz     short loc_18002CD3D
0x18002cd05  lea     rax, [rbp+640h+var_5C0]
0x18002cd0c  lea     rcx, [rbp+640h+var_5BF]
0x18002cd13  test    edx, edx
0x18002cd15  cmovz   rcx, rax
0x18002cd19  mov     qword ptr [rbp+640h+var_6C0], rcx
0x18002cd1d  mov     eax, dword ptr cs:aNan; "nan"
0x18002cd23  mov     [rcx], ax
0x18002cd26  mov     al, byte ptr cs:aNan+2; "n"
0x18002cd2c  mov     [rcx+2], al
0x18002cd2f  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18002cd33  add     r9, 3
0x18002cd37  mov     qword ptr [rbp+640h+var_6C0], r9
0x18002cd3b  jmp     short loc_18002CD8C
0x18002cd3d  movaps  xmm3, xmm6
0x18002cd40  lea     r8, [rbp+640h+var_57]
0x18002cd47  lea     rdx, [rbp+640h+var_5C0]
0x18002cd4e  lea     rcx, [rsp+740h+var_6F8+8]
0x18002cd53  cmp     r12d, 0FFFFFFFFh
0x18002cd57  jnz     short loc_18002CD70
0x18002cd59  test    r15b, r15b
0x18002cd5c  jz      short loc_18002CD65
0x18002cd5e  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18002cd63  jmp     short loc_18002CD7E
0x18002cd65  mov     [rsp+740h+var_720], esi
0x18002cd69  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x18002cd6e  jmp     short loc_18002CD7E
0x18002cd70  mov     dword ptr [rsp+740h+var_718], r12d
0x18002cd75  mov     [rsp+740h+var_720], esi
0x18002cd79  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x18002cd7e  movaps  xmm0, [rsp+740h+var_6F8+8]
0x18002cd83  movaps  [rbp+640h+var_6C0], xmm0
0x18002cd87  movq    r9, xmm0
0x18002cd8c  lea     rdx, [rbp+640h+var_5C0]
0x18002cd93  mov     [rsp+740h+var_6D8], rdx
0x18002cd98  mov     ecx, r9d
0x18002cd9b  sub     ecx, edx
0x18002cd9d  mov     [rsp+740h+var_708], ecx
0x18002cda1  cmp     byte ptr [rsp+740h+var_710+3], 0
0x18002cda6  jz      short loc_18002CDB6
0x18002cda8  lea     rdx, [rbp+640h+var_5BF]
0x18002cdaf  mov     [rsp+740h+var_6D8], rdx
0x18002cdb4  jmp     short loc_18002CDC3
0x18002cdb6  cmp     byte ptr [rsp+740h+var_710+1], 2
0x18002cdbb  jz      short loc_18002CDC3
0x18002cdbd  inc     ecx
0x18002cdbf  mov     [rsp+740h+var_708], ecx
0x18002cdc3  test    dil, dil
0x18002cdc6  jz      short loc_18002CDF4
0x18002cdc8  cmp     rdx, r9
0x18002cdcb  jz      short loc_18002CDF0
0x18002cdcd  mov     cl, [rdx]
0x18002cdcf  lea     eax, [rcx-61h]
0x18002cdd2  cmp     al, 19h
0x18002cdd4  ja      short loc_18002CDDB
0x18002cdd6  sub     cl, 20h ; ' '
0x18002cdd9  mov     [rdx], cl
0x18002cddb  inc     rdx
0x18002cdde  cmp     rdx, r9
0x18002cde1  jnz     short loc_18002CDCD
0x18002cde3  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18002cde7  mov     rdx, [rsp+740h+var_6D8]
0x18002cdec  mov     ecx, [rsp+740h+var_708]
0x18002cdf0  add     r13b, 0E0h
0x18002cdf4  movq    rax, xmm6
0x18002cdf9  shr     rax, 34h
0x18002cdfd  mov     r8d, 7FFh
0x18002ce03  and     eax, r8d
0x18002ce06  cmp     eax, r8d
0x18002ce09  setnz   al
0x18002ce0c  xor     al, 1
0x18002ce0e  mov     byte ptr [rsp+740h+var_710], al
0x18002ce12  mov     dil, 0
0x18002ce15  mov     byte ptr [rsp+740h+var_710+2], dil
0x18002ce1a  mov     r10, r9
0x18002ce1d  mov     [rsp+740h+var_6D0], r9
0x18002ce22  mov     r11, r9
0x18002ce25  mov     [rbp+640h+var_698], r9
0x18002ce29  mov     [rbp+640h+var_6B0], r9
0x18002ce2d  mov     r8d, 0
0x18002ce33  mov     [rsp+740h+var_704], r8d
0x18002ce38  mov     dword ptr [rsp+740h+var_6E0], r8d
0x18002ce3d  xorps   xmm0, xmm0
0x18002ce40  movups  [rbp+640h+var_600], xmm0
0x18002ce44  mov     [rbp+640h+var_5F0], r8
0x18002ce48  mov     [rbp+640h+var_5E8], 0Fh
0x18002ce50  mov     byte ptr [rbp+640h+var_600], dil
0x18002ce54  jnz     loc_18002D0A3
0x18002ce5a  mov     r12b, [r14+0Bh]
0x18002ce5e  test    r12b, r12b
0x18002ce61  jnz     short loc_18002CE70
0x18002ce63  lea     r15, [r14+0Ch]
0x18002ce67  cmp     [r15], r12b
0x18002ce6a  jz      loc_18002CFD9
0x18002ce70  mov     rax, rdx
0x18002ce73  cmp     rdx, r9
0x18002ce76  jnb     short loc_18002CEA3
0x18002ce78  cmp     byte ptr [rax], 2Eh ; '.'
0x18002ce7b  jnz     short loc_18002CE86
0x18002ce7d  mov     r11, rax
0x18002ce80  mov     [rbp+640h+var_698], rax
0x18002ce84  jmp     short loc_18002CE93
0x18002ce86  cmp     [rax], r13b
0x18002ce89  jnz     short loc_18002CE93
0x18002ce8b  mov     r10, rax
0x18002ce8e  mov     [rsp+740h+var_6D0], rax
0x18002ce93  inc     rax
0x18002ce96  cmp     rax, r9
0x18002ce99  jb      short loc_18002CE78
0x18002ce9b  cmp     r10, r11
0x18002ce9e  mov     rax, r10
0x18002cea1  jb      short loc_18002CEA6
0x18002cea3  mov     rax, r11
0x18002cea6  mov     [rbp+640h+var_6B0], rax
0x18002ceaa  test    r12b, r12b
0x18002cead  jz      short loc_18002CEC2
0x18002ceaf  cmp     r11, r9
0x18002ceb2  jnz     short loc_18002CEC2
0x18002ceb4  inc     ecx
0x18002ceb6  mov     [rsp+740h+var_708], ecx
0x18002ceba  mov     dil, 1
0x18002cebd  mov     byte ptr [rsp+740h+var_710+2], dil
0x18002cec2  lea     r15, [r14+0Ch]
0x18002cec6  cmp     byte ptr [r15], 0
0x18002ceca  jz      loc_18002CFD9
0x18002ced0  mov     rax, [rbp+640h+arg_20]
0x18002ced7  test    rax, rax
0x18002ceda  jz      short loc_18002CEF6
0x18002cedc  mov     rdi, [rax+8]
0x18002cee0  mov     qword ptr [rsp+740h+var_6E8], rdi
0x18002cee5  mov     rax, [rdi]
0x18002cee8  mov     rcx, rdi
0x18002ceeb  mov     rax, [rax+8]
0x18002ceef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cef4  jmp     short loc_18002CF06
0x18002cef6  mov     cl, 1
0x18002cef8  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18002cefe  mov     rdi, rax
0x18002cf01  mov     qword ptr [rsp+740h+var_6E8], rax
0x18002cf06  lea     rcx, [rsp+740h+var_6F8+8]
0x18002cf0b  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<ushort>>(std::locale const &)
0x18002cf10  mov     rcx, rax
0x18002cf13  mov     rax, [rax]
0x18002cf16  lea     rdx, [rbp+640h+var_5E0]
0x18002cf1a  mov     rax, [rax+28h]
0x18002cf1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf23  lea     rdx, [rbp+640h+var_5E0]
0x18002cf27  lea     rcx, [rbp+640h+var_600]
0x18002cf2b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18002cf30  lea     rcx, [rbp+640h+var_5E0]
0x18002cf34  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002cf39  nop
0x18002cf3a  test    rdi, rdi
0x18002cf3d  jz      short loc_18002CF66
0x18002cf3f  mov     rax, [rdi]
0x18002cf42  mov     rcx, rdi
0x18002cf45  mov     rax, [rax+10h]
0x18002cf49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf4e  mov     rcx, rax
0x18002cf51  test    rax, rax
0x18002cf54  jz      short loc_18002CF66
0x18002cf56  mov     rax, [rax]
0x18002cf59  mov     edx, 1
0x18002cf5e  mov     rax, [rax]
0x18002cf61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf66  lea     rax, [rbp+640h+var_600]
0x18002cf6a  cmp     [rbp+640h+var_5E8], 0Fh
0x18002cf6f  cmova   rax, qword ptr [rbp+640h+var_600]
0x18002cf74  mov     r10, [rbp+640h+var_5F0]
0x18002cf78  mov     rdx, [rsp+740h+var_6D8]
0x18002cf7d  xor     r8d, r8d
0x18002cf80  test    r10, r10
0x18002cf83  jz      short loc_18002CFB6
0x18002cf85  mov     r9, [rbp+640h+var_6B0]
0x18002cf89  sub     r9, rdx
0x18002cf8c  movsx   r11, byte ptr [rax]
0x18002cf90  cmp     r9, r11
0x18002cf93  jbe     short loc_18002CFB6
0x18002cf95  add     r10, rax
0x18002cf98  movsx   rcx, r11b
0x18002cf9c  sub     r9, rcx
0x18002cf9f  inc     r8d
0x18002cfa2  lea     rcx, [rax+1]
0x18002cfa6  cmp     rcx, r10
0x18002cfa9  cmovnz  rax, rcx
0x18002cfad  movsx   r11, byte ptr [rax]
0x18002cfb1  cmp     r9, r11
0x18002cfb4  ja      short loc_18002CF98
0x18002cfb6  mov     dword ptr [rsp+740h+var_6E0], r8d
0x18002cfbb  mov     ecx, [rsp+740h+var_708]
0x18002cfbf  add     ecx, r8d
0x18002cfc2  mov     [rsp+740h+var_708], ecx
0x18002cfc6  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18002cfca  mov     dil, byte ptr [rsp+740h+var_710+2]
0x18002cfcf  mov     r10, [rsp+740h+var_6D0]
0x18002cfd4  mov     r8d, [rsp+740h+var_704]
0x18002cfd9  sub     esi, 1
0x18002cfdc  jz      loc_18002D06F
0x18002cfe2  sub     esi, 1
0x18002cfe5  jz      loc_18002D095
0x18002cfeb  cmp     esi, 1
0x18002cfee  jnz     short loc_18002D06F
0x18002cff0  cmp     byte ptr [r14+0Bh], 0
0x18002cff5  jz      loc_18002D09F
0x18002cffb  mov     al, [r14+8]
0x18002cfff  sub     al, 47h ; 'G'
  ... truncated ...
```
