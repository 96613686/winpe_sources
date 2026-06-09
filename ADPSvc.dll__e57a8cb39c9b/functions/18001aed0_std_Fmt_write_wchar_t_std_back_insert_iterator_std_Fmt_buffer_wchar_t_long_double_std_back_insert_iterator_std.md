# std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,long double>(std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,long double,std::_Basic_format_specs<wchar_t> const &,std::_Lazy_locale)

- ea: `0x18001aed0`
- end: `0x18001b553`
- name: `??$_Fmt_write@_WV?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@O@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@0@V10@OAEBU?$_Basic_format_specs@_W@0@V_Lazy_locale@0@@Z`
- size: `1667`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, long double, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001cf28`

## callees

- `0x180002250`
- `0x180013830`
- `0x180018970`
- `0x180018c48`
- `0x180018d74`
- `0x180018f20`
- `0x18001aed0`
- `0x180020724`
- `0x180020b94`
- `0x180020fac`
- `0x1800ca010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18001b1f8`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18001b1f8`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x18001afeb`
- `api-ms-win-crt-private-l1-1-0!_o__ldsign` at `0x18001afeb`

## pseudocode

```c
__int16 **__fastcall std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,long double>(
        __int16 **a1,
        __int16 *a2,
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
  __int16 *v44; // rax
  __int16 **v45; // rbx
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
  __int16 *v59[2]; // [rsp+A0h] [rbp-68h] BYREF
  char *v60; // [rsp+B0h] [rbp-58h] BYREF
  __int16 **v61; // [rsp+B8h] [rbp-50h]
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
  LODWORD(v59[0]) = v12;
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
        v27 = std::use_facet<std::numpunct<wchar_t>>(&v53);
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
          v21 = LODWORD(v59[0]) + v52 - v36;
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
    `std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,double>'::`2'::_lambda_1_::operator()(
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
    a2 = std::ranges::_Copy_fn::operator()<std::wstring_view const &,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>>(
           v59,
           (__int64)&v53,
           (__int64)a2)[1];
    --v40;
  }
  v44 = *(__int16 **)`std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,double>'::`2'::_lambda_1_::operator()(
                       v62,
                       v59,
                       a2);
  while ( v41 > 0 )
  {
    v44 = std::ranges::_Copy_fn::operator()<std::wstring_view const &,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>>(
            v59,
            (__int64)&v53,
            (__int64)v44)[1];
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
0x18001aed0  mov     rax, rsp
0x18001aed3  mov     [rax+10h], rbx
0x18001aed7  push    rbp
0x18001aed8  push    rsi
0x18001aed9  push    rdi
0x18001aeda  push    r12
0x18001aedc  push    r13
0x18001aede  push    r14
0x18001aee0  push    r15
0x18001aee2  lea     rbp, [rax-648h]
0x18001aee9  sub     rsp, 710h
0x18001aef0  movaps  xmmword ptr [rax-48h], xmm6
0x18001aef4  mov     rax, cs:__security_cookie
0x18001aefb  xor     rax, rsp
0x18001aefe  mov     [rbp+640h+var_50], rax
0x18001af05  mov     r14, r9
0x18001af08  movaps  xmm6, xmm2
0x18001af0b  mov     rbx, rdx
0x18001af0e  mov     [rbp+640h+var_690], rcx
0x18001af12  mov     al, [r9+0Ah]
0x18001af16  mov     byte ptr [rsp+740h+var_710+1], al
0x18001af1a  mov     r9d, 2
0x18001af20  test    al, al
0x18001af22  jnz     short loc_18001AF29
0x18001af24  mov     byte ptr [rsp+740h+var_710+1], r9b
0x18001af29  xor     dil, dil
0x18001af2c  mov     r13b, 65h ; 'e'
0x18001af2f  mov     edx, [r14+4]
0x18001af33  xor     r15b, r15b
0x18001af36  movsx   ecx, byte ptr [r14+8]
0x18001af3b  mov     esi, 4
0x18001af40  lea     r8d, [rsi-3]
0x18001af44  sub     ecx, 41h ; 'A'
0x18001af47  jz      short loc_18001AFB5
0x18001af49  sub     ecx, esi
0x18001af4b  jz      short loc_18001AFA2
0x18001af4d  sub     ecx, r8d
0x18001af50  jz      short loc_18001AF8F
0x18001af52  sub     ecx, r8d
0x18001af55  jz      short loc_18001AF73
0x18001af57  sub     ecx, 1Ah
0x18001af5a  jz      short loc_18001AFB8
0x18001af5c  sub     ecx, esi
0x18001af5e  jz      short loc_18001AFA5
0x18001af60  sub     ecx, r8d
0x18001af63  jz      short loc_18001AF92
0x18001af65  cmp     ecx, r8d
0x18001af68  jz      short loc_18001AF76
0x18001af6a  lea     esi, [r8+2]
0x18001af6e  mov     r15b, r8b
0x18001af71  jmp     short loc_18001AFBB
0x18001af73  mov     dil, r8b
0x18001af76  cmp     edx, 0FFFFFFFFh
0x18001af79  jnz     short loc_18001AF82
0x18001af7b  mov     edx, 6
0x18001af80  jmp     short loc_18001AF88
0x18001af82  test    edx, edx
0x18001af84  cmovz   edx, r8d
0x18001af88  mov     esi, 3
0x18001af8d  jmp     short loc_18001AFBB
0x18001af8f  mov     dil, r8b
0x18001af92  mov     eax, 6
0x18001af97  cmp     edx, 0FFFFFFFFh
0x18001af9a  cmovz   edx, eax
0x18001af9d  mov     esi, r9d
0x18001afa0  jmp     short loc_18001AFBB
0x18001afa2  mov     dil, r8b
0x18001afa5  mov     eax, 6
0x18001afaa  cmp     edx, 0FFFFFFFFh
0x18001afad  cmovz   edx, eax
0x18001afb0  mov     esi, r8d
0x18001afb3  jmp     short loc_18001AFBB
0x18001afb5  mov     dil, r8b
0x18001afb8  mov     r13b, 70h ; 'p'
0x18001afbb  xorps   xmm0, xmm0
0x18001afbe  movups  [rbp+640h+var_6C0], xmm0
0x18001afc2  mov     r12d, edx
0x18001afc5  mov     r8d, 432h
0x18001afcb  cmp     edx, r8d
0x18001afce  cmovg   r12d, r8d
0x18001afd2  mov     [rbp+640h+var_6A8], r12d
0x18001afd6  lea     ecx, [rdx-432h]
0x18001afdc  xor     eax, eax
0x18001afde  cmp     edx, r8d
0x18001afe1  cmovle  ecx, eax
0x18001afe4  mov     [rsp+740h+var_700], ecx
0x18001afe8  movaps  xmm0, xmm6; X
0x18001afeb  call    cs:__imp__ldsign
0x18001aff1  mov     edx, eax
0x18001aff3  test    eax, eax
0x18001aff5  setnz   byte ptr [rsp+740h+var_710+3]
0x18001affa  ucomisd xmm6, xmm6
0x18001affe  setp    al
0x18001b001  cmp     al, 1
0x18001b003  jnz     short loc_18001B03D
0x18001b005  lea     rax, [rbp+640h+var_5C0]
0x18001b00c  lea     rcx, [rbp+640h+var_5BF]
0x18001b013  test    edx, edx
0x18001b015  cmovz   rcx, rax
0x18001b019  mov     qword ptr [rbp+640h+var_6C0], rcx
0x18001b01d  mov     eax, dword ptr cs:aNan; "nan"
0x18001b023  mov     [rcx], ax
0x18001b026  mov     al, byte ptr cs:aNan+2; "n"
0x18001b02c  mov     [rcx+2], al
0x18001b02f  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18001b033  add     r9, 3
0x18001b037  mov     qword ptr [rbp+640h+var_6C0], r9
0x18001b03b  jmp     short loc_18001B08C
0x18001b03d  movaps  xmm3, xmm6
0x18001b040  lea     r8, [rbp+640h+var_57]
0x18001b047  lea     rdx, [rbp+640h+var_5C0]
0x18001b04e  lea     rcx, [rsp+740h+var_6F8+8]
0x18001b053  cmp     r12d, 0FFFFFFFFh
0x18001b057  jnz     short loc_18001B070
0x18001b059  test    r15b, r15b
0x18001b05c  jz      short loc_18001B065
0x18001b05e  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18001b063  jmp     short loc_18001B07E
0x18001b065  mov     [rsp+740h+var_720], esi
0x18001b069  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x18001b06e  jmp     short loc_18001B07E
0x18001b070  mov     dword ptr [rsp+740h+var_718], r12d
0x18001b075  mov     [rsp+740h+var_720], esi
0x18001b079  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x18001b07e  movaps  xmm0, [rsp+740h+var_6F8+8]
0x18001b083  movaps  [rbp+640h+var_6C0], xmm0
0x18001b087  movq    r9, xmm0
0x18001b08c  lea     rdx, [rbp+640h+var_5C0]
0x18001b093  mov     [rsp+740h+var_6D8], rdx
0x18001b098  mov     ecx, r9d
0x18001b09b  sub     ecx, edx
0x18001b09d  mov     [rsp+740h+var_708], ecx
0x18001b0a1  cmp     byte ptr [rsp+740h+var_710+3], 0
0x18001b0a6  jz      short loc_18001B0B6
0x18001b0a8  lea     rdx, [rbp+640h+var_5BF]
0x18001b0af  mov     [rsp+740h+var_6D8], rdx
0x18001b0b4  jmp     short loc_18001B0C3
0x18001b0b6  cmp     byte ptr [rsp+740h+var_710+1], 2
0x18001b0bb  jz      short loc_18001B0C3
0x18001b0bd  inc     ecx
0x18001b0bf  mov     [rsp+740h+var_708], ecx
0x18001b0c3  test    dil, dil
0x18001b0c6  jz      short loc_18001B0F4
0x18001b0c8  cmp     rdx, r9
0x18001b0cb  jz      short loc_18001B0F0
0x18001b0cd  mov     cl, [rdx]
0x18001b0cf  lea     eax, [rcx-61h]
0x18001b0d2  cmp     al, 19h
0x18001b0d4  ja      short loc_18001B0DB
0x18001b0d6  sub     cl, 20h ; ' '
0x18001b0d9  mov     [rdx], cl
0x18001b0db  inc     rdx
0x18001b0de  cmp     rdx, r9
0x18001b0e1  jnz     short loc_18001B0CD
0x18001b0e3  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18001b0e7  mov     rdx, [rsp+740h+var_6D8]
0x18001b0ec  mov     ecx, [rsp+740h+var_708]
0x18001b0f0  add     r13b, 0E0h
0x18001b0f4  movq    rax, xmm6
0x18001b0f9  shr     rax, 34h
0x18001b0fd  mov     r8d, 7FFh
0x18001b103  and     eax, r8d
0x18001b106  cmp     eax, r8d
0x18001b109  setnz   al
0x18001b10c  xor     al, 1
0x18001b10e  mov     byte ptr [rsp+740h+var_710], al
0x18001b112  mov     dil, 0
0x18001b115  mov     byte ptr [rsp+740h+var_710+2], dil
0x18001b11a  mov     r10, r9
0x18001b11d  mov     [rsp+740h+var_6D0], r9
0x18001b122  mov     r11, r9
0x18001b125  mov     [rbp+640h+var_698], r9
0x18001b129  mov     [rbp+640h+var_6B0], r9
0x18001b12d  mov     r8d, 0
0x18001b133  mov     [rsp+740h+var_704], r8d
0x18001b138  mov     dword ptr [rsp+740h+var_6E0], r8d
0x18001b13d  xorps   xmm0, xmm0
0x18001b140  movups  [rbp+640h+var_600], xmm0
0x18001b144  mov     [rbp+640h+var_5F0], r8
0x18001b148  mov     [rbp+640h+var_5E8], 0Fh
0x18001b150  mov     byte ptr [rbp+640h+var_600], dil
0x18001b154  jnz     loc_18001B3A3
0x18001b15a  mov     r12b, [r14+0Bh]
0x18001b15e  test    r12b, r12b
0x18001b161  jnz     short loc_18001B170
0x18001b163  lea     r15, [r14+0Ch]
0x18001b167  cmp     [r15], r12b
0x18001b16a  jz      loc_18001B2D9
0x18001b170  mov     rax, rdx
0x18001b173  cmp     rdx, r9
0x18001b176  jnb     short loc_18001B1A3
0x18001b178  cmp     byte ptr [rax], 2Eh ; '.'
0x18001b17b  jnz     short loc_18001B186
0x18001b17d  mov     r11, rax
0x18001b180  mov     [rbp+640h+var_698], rax
0x18001b184  jmp     short loc_18001B193
0x18001b186  cmp     [rax], r13b
0x18001b189  jnz     short loc_18001B193
0x18001b18b  mov     r10, rax
0x18001b18e  mov     [rsp+740h+var_6D0], rax
0x18001b193  inc     rax
0x18001b196  cmp     rax, r9
0x18001b199  jb      short loc_18001B178
0x18001b19b  cmp     r10, r11
0x18001b19e  mov     rax, r10
0x18001b1a1  jb      short loc_18001B1A6
0x18001b1a3  mov     rax, r11
0x18001b1a6  mov     [rbp+640h+var_6B0], rax
0x18001b1aa  test    r12b, r12b
0x18001b1ad  jz      short loc_18001B1C2
0x18001b1af  cmp     r11, r9
0x18001b1b2  jnz     short loc_18001B1C2
0x18001b1b4  inc     ecx
0x18001b1b6  mov     [rsp+740h+var_708], ecx
0x18001b1ba  mov     dil, 1
0x18001b1bd  mov     byte ptr [rsp+740h+var_710+2], dil
0x18001b1c2  lea     r15, [r14+0Ch]
0x18001b1c6  cmp     byte ptr [r15], 0
0x18001b1ca  jz      loc_18001B2D9
0x18001b1d0  mov     rax, [rbp+640h+arg_20]
0x18001b1d7  test    rax, rax
0x18001b1da  jz      short loc_18001B1F6
0x18001b1dc  mov     rdi, [rax+8]
0x18001b1e0  mov     qword ptr [rsp+740h+var_6E8], rdi
0x18001b1e5  mov     rax, [rdi]
0x18001b1e8  mov     rcx, rdi
0x18001b1eb  mov     rax, [rax+8]
0x18001b1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1f4  jmp     short loc_18001B206
0x18001b1f6  mov     cl, 1
0x18001b1f8  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18001b1fe  mov     rdi, rax
0x18001b201  mov     qword ptr [rsp+740h+var_6E8], rax
0x18001b206  lea     rcx, [rsp+740h+var_6F8+8]
0x18001b20b  call    ??$use_facet@V?$numpunct@_W@std@@@std@@YAAEBV?$numpunct@_W@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<wchar_t>>(std::locale const &)
0x18001b210  mov     rcx, rax
0x18001b213  mov     rax, [rax]
0x18001b216  lea     rdx, [rbp+640h+var_5E0]
0x18001b21a  mov     rax, [rax+28h]
0x18001b21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b223  lea     rdx, [rbp+640h+var_5E0]
0x18001b227  lea     rcx, [rbp+640h+var_600]
0x18001b22b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18001b230  lea     rcx, [rbp+640h+var_5E0]
0x18001b234  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001b239  nop
0x18001b23a  test    rdi, rdi
0x18001b23d  jz      short loc_18001B266
0x18001b23f  mov     rax, [rdi]
0x18001b242  mov     rcx, rdi
0x18001b245  mov     rax, [rax+10h]
0x18001b249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b24e  mov     rcx, rax
0x18001b251  test    rax, rax
0x18001b254  jz      short loc_18001B266
0x18001b256  mov     rax, [rax]
0x18001b259  mov     edx, 1
0x18001b25e  mov     rax, [rax]
0x18001b261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b266  lea     rax, [rbp+640h+var_600]
0x18001b26a  cmp     [rbp+640h+var_5E8], 0Fh
0x18001b26f  cmova   rax, qword ptr [rbp+640h+var_600]
0x18001b274  mov     r10, [rbp+640h+var_5F0]
0x18001b278  mov     rdx, [rsp+740h+var_6D8]
0x18001b27d  xor     r8d, r8d
0x18001b280  test    r10, r10
0x18001b283  jz      short loc_18001B2B6
0x18001b285  mov     r9, [rbp+640h+var_6B0]
0x18001b289  sub     r9, rdx
0x18001b28c  movsx   r11, byte ptr [rax]
0x18001b290  cmp     r9, r11
0x18001b293  jbe     short loc_18001B2B6
0x18001b295  add     r10, rax
0x18001b298  movsx   rcx, r11b
0x18001b29c  sub     r9, rcx
0x18001b29f  inc     r8d
0x18001b2a2  lea     rcx, [rax+1]
0x18001b2a6  cmp     rcx, r10
0x18001b2a9  cmovnz  rax, rcx
0x18001b2ad  movsx   r11, byte ptr [rax]
0x18001b2b1  cmp     r9, r11
0x18001b2b4  ja      short loc_18001B298
0x18001b2b6  mov     dword ptr [rsp+740h+var_6E0], r8d
0x18001b2bb  mov     ecx, [rsp+740h+var_708]
0x18001b2bf  add     ecx, r8d
0x18001b2c2  mov     [rsp+740h+var_708], ecx
0x18001b2c6  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18001b2ca  mov     dil, byte ptr [rsp+740h+var_710+2]
0x18001b2cf  mov     r10, [rsp+740h+var_6D0]
0x18001b2d4  mov     r8d, [rsp+740h+var_704]
0x18001b2d9  sub     esi, 1
0x18001b2dc  jz      loc_18001B36F
0x18001b2e2  sub     esi, 1
0x18001b2e5  jz      loc_18001B395
0x18001b2eb  cmp     esi, 1
0x18001b2ee  jnz     short loc_18001B36F
0x18001b2f0  cmp     byte ptr [r14+0Bh], 0
0x18001b2f5  jz      loc_18001B39F
0x18001b2fb  mov     al, [r14+8]
0x18001b2ff  sub     al, 47h ; 'G'
  ... truncated ...
```
