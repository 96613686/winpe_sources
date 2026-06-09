# std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,double>(std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,double,std::_Basic_format_specs<wchar_t> const &,std::_Lazy_locale)

- ea: `0x18001a844`
- end: `0x18001aec7`
- name: `??$_Fmt_write@_WV?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@N@std@@YA?AV?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@0@V10@NAEBU?$_Basic_format_specs@_W@0@V_Lazy_locale@0@@Z`
- size: `1667`
- prototype: `__int16 **__fastcall(__int16 **, __int16 *, double, __int64, __int64)`
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
- `0x18001a844`
- `0x180020724`
- `0x180020b94`
- `0x180020fac`
- `0x1800ca010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18001ab6c`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18001ab6c`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18001a95f`
- `api-ms-win-crt-private-l1-1-0!_o__dsign` at `0x18001a95f`

## pseudocode

```c
__int16 **__fastcall std::_Fmt_write<wchar_t,std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,double>(
        __int16 **a1,
        __int16 *a2,
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
  LODWORD(v59[0]) = v12;
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
0x18001a844  mov     rax, rsp
0x18001a847  mov     [rax+10h], rbx
0x18001a84b  push    rbp
0x18001a84c  push    rsi
0x18001a84d  push    rdi
0x18001a84e  push    r12
0x18001a850  push    r13
0x18001a852  push    r14
0x18001a854  push    r15
0x18001a856  lea     rbp, [rax-648h]
0x18001a85d  sub     rsp, 710h
0x18001a864  movaps  xmmword ptr [rax-48h], xmm6
0x18001a868  mov     rax, cs:__security_cookie
0x18001a86f  xor     rax, rsp
0x18001a872  mov     [rbp+640h+var_50], rax
0x18001a879  mov     r14, r9
0x18001a87c  movaps  xmm6, xmm2
0x18001a87f  mov     rbx, rdx
0x18001a882  mov     [rbp+640h+var_690], rcx
0x18001a886  mov     al, [r9+0Ah]
0x18001a88a  mov     byte ptr [rsp+740h+var_710+1], al
0x18001a88e  mov     r9d, 2
0x18001a894  test    al, al
0x18001a896  jnz     short loc_18001A89D
0x18001a898  mov     byte ptr [rsp+740h+var_710+1], r9b
0x18001a89d  xor     dil, dil
0x18001a8a0  mov     r13b, 65h ; 'e'
0x18001a8a3  mov     edx, [r14+4]
0x18001a8a7  xor     r15b, r15b
0x18001a8aa  movsx   ecx, byte ptr [r14+8]
0x18001a8af  mov     esi, 4
0x18001a8b4  lea     r8d, [rsi-3]
0x18001a8b8  sub     ecx, 41h ; 'A'
0x18001a8bb  jz      short loc_18001A929
0x18001a8bd  sub     ecx, esi
0x18001a8bf  jz      short loc_18001A916
0x18001a8c1  sub     ecx, r8d
0x18001a8c4  jz      short loc_18001A903
0x18001a8c6  sub     ecx, r8d
0x18001a8c9  jz      short loc_18001A8E7
0x18001a8cb  sub     ecx, 1Ah
0x18001a8ce  jz      short loc_18001A92C
0x18001a8d0  sub     ecx, esi
0x18001a8d2  jz      short loc_18001A919
0x18001a8d4  sub     ecx, r8d
0x18001a8d7  jz      short loc_18001A906
0x18001a8d9  cmp     ecx, r8d
0x18001a8dc  jz      short loc_18001A8EA
0x18001a8de  lea     esi, [r8+2]
0x18001a8e2  mov     r15b, r8b
0x18001a8e5  jmp     short loc_18001A92F
0x18001a8e7  mov     dil, r8b
0x18001a8ea  cmp     edx, 0FFFFFFFFh
0x18001a8ed  jnz     short loc_18001A8F6
0x18001a8ef  mov     edx, 6
0x18001a8f4  jmp     short loc_18001A8FC
0x18001a8f6  test    edx, edx
0x18001a8f8  cmovz   edx, r8d
0x18001a8fc  mov     esi, 3
0x18001a901  jmp     short loc_18001A92F
0x18001a903  mov     dil, r8b
0x18001a906  mov     eax, 6
0x18001a90b  cmp     edx, 0FFFFFFFFh
0x18001a90e  cmovz   edx, eax
0x18001a911  mov     esi, r9d
0x18001a914  jmp     short loc_18001A92F
0x18001a916  mov     dil, r8b
0x18001a919  mov     eax, 6
0x18001a91e  cmp     edx, 0FFFFFFFFh
0x18001a921  cmovz   edx, eax
0x18001a924  mov     esi, r8d
0x18001a927  jmp     short loc_18001A92F
0x18001a929  mov     dil, r8b
0x18001a92c  mov     r13b, 70h ; 'p'
0x18001a92f  xorps   xmm0, xmm0
0x18001a932  movups  [rbp+640h+var_6C0], xmm0
0x18001a936  mov     r12d, edx
0x18001a939  mov     r8d, 432h
0x18001a93f  cmp     edx, r8d
0x18001a942  cmovg   r12d, r8d
0x18001a946  mov     [rbp+640h+var_6A8], r12d
0x18001a94a  lea     ecx, [rdx-432h]
0x18001a950  xor     eax, eax
0x18001a952  cmp     edx, r8d
0x18001a955  cmovle  ecx, eax
0x18001a958  mov     [rsp+740h+var_700], ecx
0x18001a95c  movaps  xmm0, xmm6
0x18001a95f  call    cs:__imp__o__dsign
0x18001a965  mov     edx, eax
0x18001a967  test    eax, eax
0x18001a969  setnz   byte ptr [rsp+740h+var_710+3]
0x18001a96e  ucomisd xmm6, xmm6
0x18001a972  setp    al
0x18001a975  cmp     al, 1
0x18001a977  jnz     short loc_18001A9B1
0x18001a979  lea     rax, [rbp+640h+var_5C0]
0x18001a980  lea     rcx, [rbp+640h+var_5BF]
0x18001a987  test    edx, edx
0x18001a989  cmovz   rcx, rax
0x18001a98d  mov     qword ptr [rbp+640h+var_6C0], rcx
0x18001a991  mov     eax, dword ptr cs:aNan; "nan"
0x18001a997  mov     [rcx], ax
0x18001a99a  mov     al, byte ptr cs:aNan+2; "n"
0x18001a9a0  mov     [rcx+2], al
0x18001a9a3  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18001a9a7  add     r9, 3
0x18001a9ab  mov     qword ptr [rbp+640h+var_6C0], r9
0x18001a9af  jmp     short loc_18001AA00
0x18001a9b1  movaps  xmm3, xmm6
0x18001a9b4  lea     r8, [rbp+640h+var_57]
0x18001a9bb  lea     rdx, [rbp+640h+var_5C0]
0x18001a9c2  lea     rcx, [rsp+740h+var_6F8+8]
0x18001a9c7  cmp     r12d, 0FFFFFFFFh
0x18001a9cb  jnz     short loc_18001A9E4
0x18001a9cd  test    r15b, r15b
0x18001a9d0  jz      short loc_18001A9D9
0x18001a9d2  call    ??$_Floating_to_chars@$0A@N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<0,double>(char *,char * const,double,std::chars_format,int)
0x18001a9d7  jmp     short loc_18001A9F2
0x18001a9d9  mov     [rsp+740h+var_720], esi
0x18001a9dd  call    ??$_Floating_to_chars@$00N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<1,double>(char *,char * const,double,std::chars_format,int)
0x18001a9e2  jmp     short loc_18001A9F2
0x18001a9e4  mov     dword ptr [rsp+740h+var_718], r12d
0x18001a9e9  mov     [rsp+740h+var_720], esi
0x18001a9ed  call    ??$_Floating_to_chars@$01N@std@@YA?AUto_chars_result@0@PEADQEADNW4chars_format@0@H@Z; std::_Floating_to_chars<2,double>(char *,char * const,double,std::chars_format,int)
0x18001a9f2  movaps  xmm0, [rsp+740h+var_6F8+8]
0x18001a9f7  movaps  [rbp+640h+var_6C0], xmm0
0x18001a9fb  movq    r9, xmm0
0x18001aa00  lea     rdx, [rbp+640h+var_5C0]
0x18001aa07  mov     [rsp+740h+var_6D8], rdx
0x18001aa0c  mov     ecx, r9d
0x18001aa0f  sub     ecx, edx
0x18001aa11  mov     [rsp+740h+var_708], ecx
0x18001aa15  cmp     byte ptr [rsp+740h+var_710+3], 0
0x18001aa1a  jz      short loc_18001AA2A
0x18001aa1c  lea     rdx, [rbp+640h+var_5BF]
0x18001aa23  mov     [rsp+740h+var_6D8], rdx
0x18001aa28  jmp     short loc_18001AA37
0x18001aa2a  cmp     byte ptr [rsp+740h+var_710+1], 2
0x18001aa2f  jz      short loc_18001AA37
0x18001aa31  inc     ecx
0x18001aa33  mov     [rsp+740h+var_708], ecx
0x18001aa37  test    dil, dil
0x18001aa3a  jz      short loc_18001AA68
0x18001aa3c  cmp     rdx, r9
0x18001aa3f  jz      short loc_18001AA64
0x18001aa41  mov     cl, [rdx]
0x18001aa43  lea     eax, [rcx-61h]
0x18001aa46  cmp     al, 19h
0x18001aa48  ja      short loc_18001AA4F
0x18001aa4a  sub     cl, 20h ; ' '
0x18001aa4d  mov     [rdx], cl
0x18001aa4f  inc     rdx
0x18001aa52  cmp     rdx, r9
0x18001aa55  jnz     short loc_18001AA41
0x18001aa57  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18001aa5b  mov     rdx, [rsp+740h+var_6D8]
0x18001aa60  mov     ecx, [rsp+740h+var_708]
0x18001aa64  add     r13b, 0E0h
0x18001aa68  movq    rax, xmm6
0x18001aa6d  shr     rax, 34h
0x18001aa71  mov     r8d, 7FFh
0x18001aa77  and     eax, r8d
0x18001aa7a  cmp     eax, r8d
0x18001aa7d  setnz   al
0x18001aa80  xor     al, 1
0x18001aa82  mov     byte ptr [rsp+740h+var_710], al
0x18001aa86  mov     dil, 0
0x18001aa89  mov     byte ptr [rsp+740h+var_710+2], dil
0x18001aa8e  mov     r10, r9
0x18001aa91  mov     [rsp+740h+var_6D0], r9
0x18001aa96  mov     r11, r9
0x18001aa99  mov     [rbp+640h+var_698], r9
0x18001aa9d  mov     [rbp+640h+var_6B0], r9
0x18001aaa1  mov     r8d, 0
0x18001aaa7  mov     [rsp+740h+var_704], r8d
0x18001aaac  mov     dword ptr [rsp+740h+var_6E0], r8d
0x18001aab1  xorps   xmm0, xmm0
0x18001aab4  movups  [rbp+640h+var_600], xmm0
0x18001aab8  mov     [rbp+640h+var_5F0], r8
0x18001aabc  mov     [rbp+640h+var_5E8], 0Fh
0x18001aac4  mov     byte ptr [rbp+640h+var_600], dil
0x18001aac8  jnz     loc_18001AD17
0x18001aace  mov     r12b, [r14+0Bh]
0x18001aad2  test    r12b, r12b
0x18001aad5  jnz     short loc_18001AAE4
0x18001aad7  lea     r15, [r14+0Ch]
0x18001aadb  cmp     [r15], r12b
0x18001aade  jz      loc_18001AC4D
0x18001aae4  mov     rax, rdx
0x18001aae7  cmp     rdx, r9
0x18001aaea  jnb     short loc_18001AB17
0x18001aaec  cmp     byte ptr [rax], 2Eh ; '.'
0x18001aaef  jnz     short loc_18001AAFA
0x18001aaf1  mov     r11, rax
0x18001aaf4  mov     [rbp+640h+var_698], rax
0x18001aaf8  jmp     short loc_18001AB07
0x18001aafa  cmp     [rax], r13b
0x18001aafd  jnz     short loc_18001AB07
0x18001aaff  mov     r10, rax
0x18001ab02  mov     [rsp+740h+var_6D0], rax
0x18001ab07  inc     rax
0x18001ab0a  cmp     rax, r9
0x18001ab0d  jb      short loc_18001AAEC
0x18001ab0f  cmp     r10, r11
0x18001ab12  mov     rax, r10
0x18001ab15  jb      short loc_18001AB1A
0x18001ab17  mov     rax, r11
0x18001ab1a  mov     [rbp+640h+var_6B0], rax
0x18001ab1e  test    r12b, r12b
0x18001ab21  jz      short loc_18001AB36
0x18001ab23  cmp     r11, r9
0x18001ab26  jnz     short loc_18001AB36
0x18001ab28  inc     ecx
0x18001ab2a  mov     [rsp+740h+var_708], ecx
0x18001ab2e  mov     dil, 1
0x18001ab31  mov     byte ptr [rsp+740h+var_710+2], dil
0x18001ab36  lea     r15, [r14+0Ch]
0x18001ab3a  cmp     byte ptr [r15], 0
0x18001ab3e  jz      loc_18001AC4D
0x18001ab44  mov     rax, [rbp+640h+arg_20]
0x18001ab4b  test    rax, rax
0x18001ab4e  jz      short loc_18001AB6A
0x18001ab50  mov     rdi, [rax+8]
0x18001ab54  mov     qword ptr [rsp+740h+var_6E8], rdi
0x18001ab59  mov     rax, [rdi]
0x18001ab5c  mov     rcx, rdi
0x18001ab5f  mov     rax, [rax+8]
0x18001ab63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab68  jmp     short loc_18001AB7A
0x18001ab6a  mov     cl, 1
0x18001ab6c  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18001ab72  mov     rdi, rax
0x18001ab75  mov     qword ptr [rsp+740h+var_6E8], rax
0x18001ab7a  lea     rcx, [rsp+740h+var_6F8+8]
0x18001ab7f  call    ??$use_facet@V?$numpunct@_W@std@@@std@@YAAEBV?$numpunct@_W@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<wchar_t>>(std::locale const &)
0x18001ab84  mov     rcx, rax
0x18001ab87  mov     rax, [rax]
0x18001ab8a  lea     rdx, [rbp+640h+var_5E0]
0x18001ab8e  mov     rax, [rax+28h]
0x18001ab92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab97  lea     rdx, [rbp+640h+var_5E0]
0x18001ab9b  lea     rcx, [rbp+640h+var_600]
0x18001ab9f  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18001aba4  lea     rcx, [rbp+640h+var_5E0]
0x18001aba8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001abad  nop
0x18001abae  test    rdi, rdi
0x18001abb1  jz      short loc_18001ABDA
0x18001abb3  mov     rax, [rdi]
0x18001abb6  mov     rcx, rdi
0x18001abb9  mov     rax, [rax+10h]
0x18001abbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abc2  mov     rcx, rax
0x18001abc5  test    rax, rax
0x18001abc8  jz      short loc_18001ABDA
0x18001abca  mov     rax, [rax]
0x18001abcd  mov     edx, 1
0x18001abd2  mov     rax, [rax]
0x18001abd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abda  lea     rax, [rbp+640h+var_600]
0x18001abde  cmp     [rbp+640h+var_5E8], 0Fh
0x18001abe3  cmova   rax, qword ptr [rbp+640h+var_600]
0x18001abe8  mov     r10, [rbp+640h+var_5F0]
0x18001abec  mov     rdx, [rsp+740h+var_6D8]
0x18001abf1  xor     r8d, r8d
0x18001abf4  test    r10, r10
0x18001abf7  jz      short loc_18001AC2A
0x18001abf9  mov     r9, [rbp+640h+var_6B0]
0x18001abfd  sub     r9, rdx
0x18001ac00  movsx   r11, byte ptr [rax]
0x18001ac04  cmp     r9, r11
0x18001ac07  jbe     short loc_18001AC2A
0x18001ac09  add     r10, rax
0x18001ac0c  movsx   rcx, r11b
0x18001ac10  sub     r9, rcx
0x18001ac13  inc     r8d
0x18001ac16  lea     rcx, [rax+1]
0x18001ac1a  cmp     rcx, r10
0x18001ac1d  cmovnz  rax, rcx
0x18001ac21  movsx   r11, byte ptr [rax]
0x18001ac25  cmp     r9, r11
0x18001ac28  ja      short loc_18001AC0C
0x18001ac2a  mov     dword ptr [rsp+740h+var_6E0], r8d
0x18001ac2f  mov     ecx, [rsp+740h+var_708]
0x18001ac33  add     ecx, r8d
0x18001ac36  mov     [rsp+740h+var_708], ecx
0x18001ac3a  mov     r9, qword ptr [rbp+640h+var_6C0]
0x18001ac3e  mov     dil, byte ptr [rsp+740h+var_710+2]
0x18001ac43  mov     r10, [rsp+740h+var_6D0]
0x18001ac48  mov     r8d, [rsp+740h+var_704]
0x18001ac4d  sub     esi, 1
0x18001ac50  jz      loc_18001ACE3
0x18001ac56  sub     esi, 1
0x18001ac59  jz      loc_18001AD09
0x18001ac5f  cmp     esi, 1
0x18001ac62  jnz     short loc_18001ACE3
0x18001ac64  cmp     byte ptr [r14+0Bh], 0
0x18001ac69  jz      loc_18001AD13
0x18001ac6f  mov     al, [r14+8]
0x18001ac73  sub     al, 47h ; 'G'
  ... truncated ...
```
