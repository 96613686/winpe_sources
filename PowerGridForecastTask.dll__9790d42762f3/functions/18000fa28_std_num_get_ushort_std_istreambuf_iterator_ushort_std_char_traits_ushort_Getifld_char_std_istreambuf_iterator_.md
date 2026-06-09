# std::num_get<ushort,std::istreambuf_iterator<ushort,std::char_traits<ushort>>>::_Getifld(char *,std::istreambuf_iterator<ushort,std::char_traits<ushort>> &,std::istreambuf_iterator<ushort,std::char_traits<ushort>> &,int,std::locale const &)

- ea: `0x18000fa28`
- end: `0x18000fe5e`
- name: `?_Getifld@?$num_get@GV?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@GU?$char_traits@G@std@@@2@1HAEBVlocale@2@@Z`
- size: `1078`
- prototype: `__int64 __fastcall(__int64, char *, __int64 *, __int64, __int16, __int64 *)`
- caller_count: `8`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180016770`
- `0x1800168c0`
- `0x180016a10`
- `0x180016b40`
- `0x180016f70`
- `0x1800170a0`
- `0x1800171d0`
- `0x180017300`

## callees

- `0x180009acc`
- `0x18000af0c`
- `0x18000b754`
- `0x18000fa28`
- `0x180011cac`
- `0x18001c5d8`
- `0x180026609`
- `0x180034120`
- `0x1800350e0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall std::num_get<unsigned short,std::istreambuf_iterator<unsigned short>>::_Getifld(
        __int64 a1,
        char *a2,
        __int64 *a3,
        __int64 a4,
        __int16 a5,
        __int64 *a6)
{
  char *v8; // r13
  struct std::_Facet_base *v9; // rdi
  unsigned __int8 v10; // di
  struct std::_Facet_base *v11; // rax
  char *v12; // r14
  _WORD *v13; // rax
  __int64 *v14; // rcx
  _WORD *v15; // rax
  int v16; // ecx
  unsigned int v17; // esi
  _WORD *v18; // rax
  _WORD *v19; // rax
  _WORD *v20; // rax
  __int64 v21; // r15
  unsigned __int64 v22; // r12
  __int64 v23; // rdi
  void **v24; // r15
  __int16 v25; // cx
  char *v26; // rax
  unsigned __int64 v27; // rax
  char v28; // cl
  void **v29; // rax
  void **v30; // rax
  void **v31; // rax
  void **v32; // rax
  char v33; // al
  void **v34; // rcx
  void *v35; // rdx
  unsigned __int64 v36; // r8
  char v37; // r9
  void **v38; // rax
  void **v40; // rax
  char v41; // [rsp+38h] [rbp-A9h]
  char v42; // [rsp+39h] [rbp-A8h]
  int v43; // [rsp+3Ch] [rbp-A5h]
  __int16 v44; // [rsp+40h] [rbp-A1h]
  unsigned __int64 v45; // [rsp+48h] [rbp-99h]
  __int64 v48; // [rsp+68h] [rbp-79h]
  void *v49[3]; // [rsp+70h] [rbp-71h] BYREF
  __int64 v50; // [rsp+88h] [rbp-59h]
  void *v51[3]; // [rsp+90h] [rbp-51h] BYREF
  unsigned __int64 v52; // [rsp+A8h] [rbp-39h]
  _WORD v53[26]; // [rsp+B0h] [rbp-31h] BYREF
  char v54; // [rsp+E4h] [rbp+3h] BYREF

  HIBYTE(v48) = -1;
  v8 = a2;
  v9 = std::use_facet<std::numpunct<unsigned short>>(a6);
  (*(void (__fastcall **)(struct std::_Facet_base *, void **))(*(_QWORD *)v9 + 40LL))(v9, v51);
  if ( v51[2] )
  {
    v44 = (*(__int64 (__fastcall **)(struct std::_Facet_base *))(*(_QWORD *)v9 + 32LL))(v9);
    v10 = 0;
  }
  else
  {
    v10 = 0;
    v44 = 0;
  }
  v11 = std::use_facet<std::ctype<unsigned short>>(a6);
  (*(void (__fastcall **)(struct std::_Facet_base *, const char *, char *, _WORD *))(*(_QWORD *)v11 + 88LL))(
    v11,
    "0123456789ABCDEFabcdef-+Xx",
    "",
    v53);
  v12 = v8;
  if ( !(unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4) )
  {
    v13 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3);
    v14 = a3;
    if ( *v13 == v53[23] )
    {
      *v8 = 43;
    }
    else
    {
      v15 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3);
      if ( *v15 != v53[22] )
        goto LABEL_10;
      *v8 = 45;
      v14 = a3;
    }
    v12 = v8 + 1;
    std::istreambuf_iterator<unsigned short>::_Inc(v14);
  }
LABEL_10:
  v16 = a5 & 0xE00;
  v45 = 10;
  v17 = v16 != 0 ? 0xA : 0;
  if ( v16 == 2048 )
    v17 = 16;
  if ( v16 == 1024 )
    v17 = 8;
  v43 = v17;
  v41 = 0;
  v42 = 0;
  if ( (unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4)
    || (v18 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3), *v18 != v53[0]) )
  {
    if ( !v17 )
      goto LABEL_29;
  }
  else
  {
    std::istreambuf_iterator<unsigned short>::_Inc(a3);
    if ( !(unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4) )
    {
      v19 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3);
      if ( *v19 == v53[25] || (v20 = (_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3), *v20 == v53[24]) )
      {
        if ( (v17 & 0xFFFFFFEF) == 0 )
        {
          v17 = 16;
          v43 = 16;
          v41 = 0;
          std::istreambuf_iterator<unsigned short>::_Inc(a3);
          goto LABEL_26;
        }
      }
    }
    v10 = 1;
    v41 = 1;
    if ( !v17 )
    {
      v17 = 8;
      v43 = 8;
      goto LABEL_26;
    }
  }
  if ( v17 == 10 )
    goto LABEL_29;
  v43 = v17;
LABEL_26:
  v21 = 22;
  if ( v17 == 8 )
    v21 = 8;
  v45 = v21;
LABEL_29:
  v22 = 15;
  v50 = 15;
  LOWORD(v49[0]) = v10;
  v49[2] = (void *)1;
  v23 = 0;
  v24 = (void **)v49[0];
  if ( (unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4) )
    goto LABEL_58;
  while ( 1 )
  {
    v25 = *(_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3);
    v26 = (char *)v53;
    do
    {
      if ( *(_WORD *)v26 == v25 )
        break;
      v26 += 2;
    }
    while ( v26 != &v54 );
    v27 = (v26 - (char *)v53) >> 1;
    if ( v27 >= v45 )
      break;
    v28 = `std::num_get<unsigned short,std::istreambuf_iterator<unsigned short>>::_Getifld'::`2'::_Src[v27];
    *v12 = v28;
    if ( (v42 || v28 != 48) && v12 < v8 + 31 )
    {
      ++v12;
      v42 = 1;
    }
    v41 = 1;
    v29 = v49;
    if ( v22 >= 0x10 )
      v29 = v24;
    if ( *((_BYTE *)v29 + v23) == 127 )
      goto LABEL_51;
    v30 = v49;
    if ( v22 >= 0x10 )
      v30 = v24;
    ++*((_BYTE *)v30 + v23);
LABEL_50:
    v24 = (void **)v49[0];
    v22 = v50;
LABEL_51:
    std::istreambuf_iterator<unsigned short>::_Inc(a3);
    if ( (unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a3, a4) )
      goto LABEL_52;
  }
  v31 = v49;
  if ( v22 >= 0x10 )
    v31 = v24;
  if ( *((_BYTE *)v31 + v23) && v44 && *(_WORD *)std::istreambuf_iterator<unsigned short>::operator*(a3) == v44 )
  {
    std::string::append(v49, 1);
    ++v23;
    goto LABEL_50;
  }
LABEL_52:
  v17 = v43;
  v8 = a2;
  if ( !v23 )
    goto LABEL_58;
  v32 = v49;
  if ( v22 >= 0x10 )
    v32 = v24;
  if ( *((char *)v32 + v23) <= 0 )
  {
    v33 = 0;
  }
  else
  {
    ++v23;
LABEL_58:
    v33 = v41;
  }
  v34 = v51;
  v35 = v51[0];
  v36 = v52;
  if ( v52 >= 0x10 )
    v34 = (void **)v51[0];
  if ( v33 )
  {
    while ( v23 )
    {
      v37 = *(_BYTE *)v34;
      if ( *(_BYTE *)v34 == 127 )
        break;
      if ( --v23 )
      {
        v38 = v49;
        if ( v22 >= 0x10 )
          v38 = v24;
        if ( v37 != *((_BYTE *)v38 + v23) )
          goto LABEL_68;
      }
      else
      {
        v40 = v49;
        if ( v22 >= 0x10 )
          v40 = v24;
        if ( v37 < *(char *)v40 )
          goto LABEL_68;
      }
      if ( *((char *)v34 + 1) > 0 )
        v34 = (void **)((char *)v34 + 1);
    }
    if ( !v42 )
      *v12++ = 48;
  }
  else
  {
LABEL_68:
    v12 = v8;
  }
  *v12 = 0;
  if ( v22 >= 0x10 )
  {
    operator delete(v24);
    v36 = v52;
    v35 = v51[0];
  }
  if ( v36 >= 0x10 )
    operator delete(v35);
  return v17;
}

```

## disassembly

```asm
0x18000fa28  mov     rax, rsp
0x18000fa2b  push    rbp
0x18000fa2c  push    rsi
0x18000fa2d  push    rdi
0x18000fa2e  push    r12
0x18000fa30  push    r13
0x18000fa32  push    r14
0x18000fa34  push    r15
0x18000fa36  lea     rbp, [rax-4Fh]
0x18000fa3a  sub     rsp, 0F0h
0x18000fa41  mov     [rbp+47h+var_C0], 0FFFFFFFFFFFFFFFEh
0x18000fa49  mov     [rax+8], rbx
0x18000fa4d  mov     rax, cs:__security_cookie
0x18000fa54  xor     rax, rsp
0x18000fa57  mov     [rbp+47h+var_40], rax
0x18000fa5b  mov     r12, r9
0x18000fa5e  mov     [rsp+120h+var_D8], r9
0x18000fa63  mov     rbx, r8
0x18000fa66  mov     r13, rdx
0x18000fa69  mov     [rsp+58h], rdx
0x18000fa6e  mov     rsi, [rbp+47h+arg_28]
0x18000fa72  xor     r14d, r14d
0x18000fa75  mov     rcx, rsi
0x18000fa78  call    ??$use_facet@V?$numpunct@G@std@@@std@@YAAEBV?$numpunct@G@0@AEBVlocale@0@@Z
0x18000fa7d  mov     rdi, rax
0x18000fa80  mov     rcx, [rax]
0x18000fa83  mov     rax, [rcx+28h]
0x18000fa87  lea     rdx, [rbp+47h+var_98]
0x18000fa8b  mov     rcx, rdi
0x18000fa8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa93  nop
0x18000fa94  cmp     [rbp+47h+var_88], r14
0x18000fa98  jnz     short loc_18000FAA2
0x18000fa9a  xor     edi, edi
0x18000fa9c  mov     dword ptr [rsp+120h+var_E8], edi
0x18000faa0  jmp     short loc_18000FAB8
0x18000faa2  mov     rax, [rdi]
0x18000faa5  mov     rcx, rdi
0x18000faa8  mov     rax, [rax+20h]
0x18000faac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fab1  mov     word ptr [rsp+120h+var_E8], ax
0x18000fab6  xor     edi, edi
0x18000fab8  mov     rcx, rsi
0x18000fabb  call    ??$use_facet@V?$ctype@G@std@@@std@@YAAEBV?$ctype@G@0@AEBVlocale@0@@Z
0x18000fac0  mov     r10, rax
0x18000fac3  mov     rcx, [rax]
0x18000fac6  mov     rax, [rcx+58h]
0x18000faca  lea     r9, [rbp+47h+var_78]
0x18000face  lea     r8, ?_Src@?1??_Getifld@?$num_get@GV?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@GU?$char_traits@G@std@@@3@1HAEBVlocale@3@@Z@4QBDB+1Ah
0x18000fad5  lea     rdx, ?_Src@?1??_Getifld@?$num_get@GV?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@GU?$char_traits@G@std@@@3@1HAEBVlocale@3@@Z@4QBDB
0x18000fadc  mov     rcx, r10
0x18000fadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fae4  mov     r14, r13
0x18000fae7  mov     rdx, r12
0x18000faea  mov     rcx, rbx
0x18000faed  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18000faf2  test    al, al
0x18000faf4  jnz     short loc_18000FB30
0x18000faf6  mov     rcx, rbx
0x18000faf9  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000fafe  movzx   ecx, [rbp+47h+var_4A]
0x18000fb02  cmp     [rax], cx
0x18000fb05  mov     rcx, rbx
0x18000fb08  jnz     short loc_18000FB11
0x18000fb0a  mov     byte ptr [r13+0], 2Bh ; '+'
0x18000fb0f  jmp     short loc_18000FB27
0x18000fb11  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000fb16  movzx   ecx, [rbp+47h+var_4C]
0x18000fb1a  cmp     [rax], cx
0x18000fb1d  jnz     short loc_18000FB30
0x18000fb1f  mov     byte ptr [r13+0], 2Dh ; '-'
0x18000fb24  mov     rcx, rbx
0x18000fb27  lea     r14, [r13+1]
0x18000fb2b  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x18000fb30  mov     ecx, dword ptr [rbp+47h+arg_20]
0x18000fb33  and     ecx, 0E00h
0x18000fb39  mov     eax, ecx
0x18000fb3b  neg     eax
0x18000fb3d  sbb     esi, esi
0x18000fb3f  mov     r15d, 0Ah
0x18000fb45  mov     [rsp+120h+var_E0], r15
0x18000fb4a  and     esi, r15d
0x18000fb4d  lea     eax, [r15+6]
0x18000fb51  cmp     ecx, 800h
0x18000fb57  cmovz   esi, eax
0x18000fb5a  lea     eax, [r15-2]
0x18000fb5e  cmp     ecx, 400h
0x18000fb64  cmovz   esi, eax
0x18000fb67  mov     [rsp+34h], esi
0x18000fb6b  mov     byte ptr [rsp+120h+var_F0], dil
0x18000fb70  mov     byte ptr [rsp+120h+var_F0+1], dil
0x18000fb75  mov     rdx, r12
0x18000fb78  mov     rcx, rbx
0x18000fb7b  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18000fb80  test    al, al
0x18000fb82  jnz     loc_18000FC09
0x18000fb88  mov     rcx, rbx
0x18000fb8b  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000fb90  movzx   ecx, [rbp+47h+var_78]
0x18000fb94  cmp     [rax], cx
0x18000fb97  jnz     short loc_18000FC09
0x18000fb99  mov     rcx, rbx
0x18000fb9c  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x18000fba1  mov     rdx, r12
0x18000fba4  mov     rcx, rbx
0x18000fba7  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18000fbac  test    al, al
0x18000fbae  jnz     short loc_18000FBF2
0x18000fbb0  mov     rcx, rbx
0x18000fbb3  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000fbb8  movzx   ecx, [rbp+47h+var_46]
0x18000fbbc  cmp     [rax], cx
0x18000fbbf  jz      short loc_18000FBD2
0x18000fbc1  mov     rcx, rbx
0x18000fbc4  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000fbc9  movzx   ecx, [rbp+47h+var_48]
0x18000fbcd  cmp     [rax], cx
0x18000fbd0  jnz     short loc_18000FBF2
0x18000fbd2  test    esi, 0FFFFFFEFh
0x18000fbd8  jnz     short loc_18000FBF2
0x18000fbda  mov     esi, 10h
0x18000fbdf  mov     [rsp+34h], esi
0x18000fbe3  mov     byte ptr [rsp+120h+var_F0], dil
0x18000fbe8  mov     rcx, rbx
0x18000fbeb  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x18000fbf0  jmp     short loc_18000FC16
0x18000fbf2  mov     dil, 1
0x18000fbf5  mov     byte ptr [rsp+120h+var_F0], dil
0x18000fbfa  test    esi, esi
0x18000fbfc  jnz     short loc_18000FC0D
0x18000fbfe  lea     eax, [rsi+8]
0x18000fc01  mov     esi, eax
0x18000fc03  mov     [rsp+34h], eax
0x18000fc07  jmp     short loc_18000FC1B
0x18000fc09  test    esi, esi
0x18000fc0b  jz      short loc_18000FC2C
0x18000fc0d  cmp     esi, r15d
0x18000fc10  jz      short loc_18000FC2C
0x18000fc12  mov     [rsp+34h], esi
0x18000fc16  mov     eax, 8
0x18000fc1b  mov     r15d, 16h
0x18000fc21  cmp     esi, eax
0x18000fc23  cmovz   r15, rax
0x18000fc27  mov     [rsp+120h+var_E0], r15
0x18000fc2c  mov     r12d, 0Fh
0x18000fc32  mov     [rbp+47h+var_A0], r12
0x18000fc36  mov     byte ptr [rbp+47h+var_B8], dil
0x18000fc3a  mov     [rbp+47h+var_A8], 1
0x18000fc42  xor     r15d, r15d
0x18000fc45  mov     byte ptr [rbp+47h+var_B8+1], r15b
0x18000fc49  mov     edi, r15d
0x18000fc4c  lea     rax, [r13+1Fh]
0x18000fc50  mov     [rsp+120h+var_D0], rax
0x18000fc55  mov     rdx, [rsp+120h+var_D8]
0x18000fc5a  mov     rcx, rbx
0x18000fc5d  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18000fc62  mov     r15, [rbp+47h+var_B8]
0x18000fc66  test    al, al
0x18000fc68  jnz     loc_18000FD7E
0x18000fc6e  mov     r13, [rsp+120h+var_E0]
0x18000fc73  mov     esi, dword ptr [rsp+120h+var_E8]
0x18000fc77  mov     rcx, rbx
0x18000fc7a  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000fc7f  movzx   ecx, word ptr [rax]
0x18000fc82  lea     rax, [rbp+47h+var_78]
0x18000fc86  cmp     [rax], cx
0x18000fc89  jz      short loc_18000FC98
0x18000fc8b  add     rax, 2
0x18000fc8f  lea     rdx, [rbp+47h+var_44]
0x18000fc93  cmp     rax, rdx
0x18000fc96  jnz     short loc_18000FC86
0x18000fc98  lea     rcx, [rbp+47h+var_78]
0x18000fc9c  sub     rax, rcx
0x18000fc9f  sar     rax, 1
0x18000fca2  cmp     rax, r13
0x18000fca5  jnb     short loc_18000FCF7
0x18000fca7  lea     rcx, ?_Src@?1??_Getifld@?$num_get@GV?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBAHPEADAEAV?$istreambuf_iterator@GU?$char_traits@G@std@@@3@1HAEBVlocale@3@@Z@4QBDB
0x18000fcae  mov     cl, [rax+rcx]
0x18000fcb1  mov     [r14], cl
0x18000fcb4  cmp     byte ptr [rsp+120h+var_F0+1], 0
0x18000fcb9  jnz     short loc_18000FCC0
0x18000fcbb  cmp     cl, 30h ; '0'
0x18000fcbe  jz      short loc_18000FCCF
0x18000fcc0  cmp     r14, [rsp+120h+var_D0]
0x18000fcc5  jnb     short loc_18000FCCF
0x18000fcc7  inc     r14
0x18000fcca  mov     byte ptr [rsp+120h+var_F0+1], 1
0x18000fccf  mov     byte ptr [rsp+120h+var_F0], 1
0x18000fcd4  lea     rax, [rbp+47h+var_B8]
0x18000fcd8  cmp     r12, 10h
0x18000fcdc  cmovnb  rax, r15
0x18000fce0  cmp     byte ptr [rax+rdi], 7Fh
0x18000fce4  jz      short loc_18000FD37
0x18000fce6  lea     rax, [rbp+47h+var_B8]
0x18000fcea  cmp     r12, 10h
0x18000fcee  cmovnb  rax, r15
0x18000fcf2  inc     byte ptr [rax+rdi]
0x18000fcf5  jmp     short loc_18000FD2F
0x18000fcf7  lea     rax, [rbp+47h+var_B8]
0x18000fcfb  cmp     r12, 10h
0x18000fcff  cmovnb  rax, r15
0x18000fd03  xor     ecx, ecx
0x18000fd05  cmp     [rax+rdi], cl
0x18000fd08  jz      short loc_18000FD54
0x18000fd0a  test    si, si
0x18000fd0d  jz      short loc_18000FD54
0x18000fd0f  mov     rcx, rbx
0x18000fd12  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18000fd17  cmp     [rax], si
0x18000fd1a  jnz     short loc_18000FD54
0x18000fd1c  xor     r8d, r8d
0x18000fd1f  lea     edx, [r8+1]
0x18000fd23  lea     rcx, [rbp+47h+var_B8]
0x18000fd27  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z
0x18000fd2c  inc     rdi
0x18000fd2f  mov     r15, [rbp+47h+var_B8]
0x18000fd33  mov     r12, [rbp+47h+var_A0]
0x18000fd37  mov     rcx, rbx
0x18000fd3a  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x18000fd3f  mov     rdx, [rsp+120h+var_D8]
0x18000fd44  mov     rcx, rbx
0x18000fd47  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18000fd4c  test    al, al
0x18000fd4e  jz      loc_18000FC77
0x18000fd54  xor     ebx, ebx
0x18000fd56  test    rdi, rdi
0x18000fd59  mov     esi, [rsp+34h]
0x18000fd5d  mov     r13, [rsp+58h]
0x18000fd62  jz      short loc_18000FD80
0x18000fd64  lea     rax, [rbp+47h+var_B8]
0x18000fd68  cmp     r12, 10h
0x18000fd6c  cmovnb  rax, r15
0x18000fd70  cmp     [rax+rdi], bl
0x18000fd73  jle     short loc_18000FD7A
0x18000fd75  inc     rdi
0x18000fd78  jmp     short loc_18000FD80
0x18000fd7a  mov     al, bl
0x18000fd7c  jmp     short loc_18000FD84
0x18000fd7e  xor     ebx, ebx
0x18000fd80  mov     al, byte ptr [rsp+120h+var_F0]
0x18000fd84  lea     rcx, [rbp+47h+var_98]
0x18000fd88  mov     rdx, [rbp+47h+var_98]
0x18000fd8c  mov     r8, [rbp+47h+var_80]
0x18000fd90  mov     r10d, 10h
0x18000fd96  cmp     r8, r10
0x18000fd99  cmovnb  rcx, rdx
0x18000fd9d  test    al, al
0x18000fd9f  jz      short loc_18000FDCE
0x18000fda1  test    rdi, rdi
0x18000fda4  jz      loc_18000FE4B
0x18000fdaa  mov     r9b, [rcx]
0x18000fdad  cmp     r9b, 7Fh
0x18000fdb1  jz      loc_18000FE4B
0x18000fdb7  sub     rdi, 1
0x18000fdbb  jz      short loc_18000FE25
0x18000fdbd  lea     rax, [rbp+47h+var_B8]
0x18000fdc1  cmp     r12, r10
0x18000fdc4  cmovnb  rax, r15
0x18000fdc8  cmp     r9b, [rax+rdi]
0x18000fdcc  jz      short loc_18000FE3A
0x18000fdce  mov     r14, r13
0x18000fdd1  mov     [r14], bl
0x18000fdd4  cmp     r12, r10
0x18000fdd7  jb      short loc_18000FDEF
0x18000fdd9  mov     rcx, r15; void *
0x18000fddc  call    ??3@YAXPEAX@Z_0
0x18000fde1  mov     r8, [rbp+47h+var_80]
0x18000fde5  mov     rdx, [rbp+47h+var_98]
0x18000fde9  mov     r10d, 10h
0x18000fdef  cmp     r8, r10
0x18000fdf2  jb      short loc_18000FDFC
0x18000fdf4  mov     rcx, rdx; void *
0x18000fdf7  call    ??3@YAXPEAX@Z_0
0x18000fdfc  mov     eax, esi
0x18000fdfe  mov     rcx, [rbp+47h+var_40]
0x18000fe02  xor     rcx, rsp; StackCookie
0x18000fe05  call    __security_check_cookie
0x18000fe0a  mov     rbx, [rsp+120h+arg_0]
0x18000fe12  add     rsp, 0F0h
0x18000fe19  pop     r15
0x18000fe1b  pop     r14
0x18000fe1d  pop     r13
0x18000fe1f  pop     r12
0x18000fe21  pop     rdi
0x18000fe22  pop     rsi
0x18000fe23  pop     rbp
0x18000fe24  retn
0x18000fe25  test    rdi, rdi
0x18000fe28  jnz     short loc_18000FE3A
0x18000fe2a  lea     rax, [rbp+47h+var_B8]
0x18000fe2e  cmp     r12, r10
0x18000fe31  cmovnb  rax, r15
0x18000fe35  cmp     r9b, [rax]
0x18000fe38  jl      short loc_18000FDCE
0x18000fe3a  cmp     [rcx+1], bl
0x18000fe3d  jle     loc_18000FDA1
0x18000fe43  inc     rcx
0x18000fe46  jmp     loc_18000FDA1
0x18000fe4b  cmp     byte ptr [rsp+120h+var_F0+1], bl
0x18000fe4f  jnz     short loc_18000FDD1
  ... truncated ...
```
