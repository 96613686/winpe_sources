# mkl_serv_free

- ea: `0x18003eb20`
- end: `0x18003fa70`
- name: `mkl_serv_free`
- size: `3920`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca80`
- `0x18000d570`
- `0x18003df30`

## callees

- `0x18003eb20`
- `0x180054070`
- `0x180054080`
- `0x180055ce0`
- `0x180055e50`
- `0x180056180`
- `0x180060de0`
- `0x180061160`
- `0x180077140`
- `0x1800775d0`
- `0x1800777c0`
- `0x180077840`
- `0x180077950`
- `0x1832ce3b0`
- `0x1832dbf30`
- `0x1832dbf90`
- `0x1832dbfe0`
- `0x1832dc0b0`
- `0x1832dc0c0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003f8a4`
- `KERNEL32!GetProcAddress` at `0x18003f8bb`
- `KERNEL32!GetProcAddress` at `0x18003f8d2`
- `KERNEL32!GetProcAddress` at `0x18003f8a4`
- `KERNEL32!GetProcAddress` at `0x18003f8bb`
- `KERNEL32!GetProcAddress` at `0x18003f8d2`
- `KERNEL32!TlsAlloc` at `0x18003f5a8`
- `KERNEL32!TlsAlloc` at `0x18003f612`
- `KERNEL32!TlsAlloc` at `0x18003f5a8`
- `KERNEL32!TlsAlloc` at `0x18003f612`
- `KERNEL32!TlsGetValue` at `0x18003eb8e`
- `KERNEL32!TlsGetValue` at `0x18003eb8e`
- `KERNEL32!TlsSetValue` at `0x18003f57d`
- `KERNEL32!TlsSetValue` at `0x18003f57d`
- `KERNEL32!LoadLibraryA` at `0x18003f77e`
- `KERNEL32!LoadLibraryA` at `0x18003f88c`
- `KERNEL32!LoadLibraryA` at `0x18003f77e`
- `KERNEL32!LoadLibraryA` at `0x18003f88c`

## pseudocode

```c
void __fastcall mkl_serv_free(__int64 a1)
{
  int Value; // esi
  volatile signed __int32 *v3; // rdi
  signed __int32 i; // eax
  signed __int32 v5; // ebx
  signed int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rbp
  void *v14; // rcx
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // rdx
  int device_count; // ebp
  int v19; // ebx
  unsigned __int64 v20; // rax
  int v21; // edx
  int v22; // ebp
  char v23; // bl
  _QWORD *v24; // rdx
  __int64 v25; // rax
  unsigned __int64 v26; // r11
  __int64 v27; // r8
  int v28; // edi
  char v29; // r13
  size_t v30; // rax
  size_t v31; // r8
  unsigned __int64 v32; // rdx
  unsigned __int64 k; // rax
  int v34; // r15d
  __int64 v35; // r14
  __int64 v36; // rdx
  __int64 v37; // r15
  unsigned __int64 v38; // rdi
  int v39; // edx
  __int64 v40; // r8
  unsigned __int64 v41; // rdi
  unsigned __int64 v42; // r13
  unsigned __int64 v43; // rax
  unsigned __int64 j; // rdx
  __int64 v45; // rdx
  char *v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rbp
  char v49; // al
  HMODULE LibraryA; // rsi
  __int64 v51; // rbp
  __int64 v52; // rax
  __int64 v53; // rbp
  char v54; // al
  FARPROC ProcAddress; // rax
  int v56; // eax
  int v57; // eax
  _OWORD v58[3]; // [rsp+0h] [rbp-598h]
  _QWORD *v59; // [rsp+30h] [rbp-568h] BYREF
  _QWORD *v60; // [rsp+38h] [rbp-560h] BYREF
  size_t Size[2]; // [rsp+40h] [rbp-558h] BYREF
  char v62[16]; // [rsp+50h] [rbp-548h] BYREF
  CHAR v64[688]; // [rsp+70h] [rbp-528h] BYREF
  CHAR v65[256]; // [rsp+320h] [rbp-278h] BYREF
  __int128 v66; // [rsp+420h] [rbp-178h]
  CHAR LibFileName[256]; // [rsp+430h] [rbp-168h] BYREF
  int v68; // [rsp+530h] [rbp-68h]
  char String[8]; // [rsp+540h] [rbp-58h] BYREF

  if ( !a1 )
    return;
  if ( dword_1836E1210 == -1 )
  {
    mkl_serv_lock(&unk_1836E8CFC);
    if ( dword_1836E1210 != -1 )
    {
LABEL_168:
      mkl_serv_unlock(&unk_1836E8CFC);
      goto LABEL_3;
    }
    mkl_serv_lock(&unk_1836E8D00);
    if ( dword_1836E1214 == -1 )
    {
      dword_1836E1218 = (int)mkl_serv_getenv("MKL_DISABLE_FAST_MM", v62, 32) > 0;
      if ( (int)mkl_serv_getenv("MKL_FAST_MEMORY_LIMIT", v62, 32) > 0 )
      {
        v57 = atol_0(v62);
        if ( v57 < 0 )
          qword_1836E1200 = -1;
        else
          qword_1836E1200 = (__int64)v57 << 20;
      }
      dword_1836E1214 = 1;
    }
    mkl_serv_unlock(&unk_1836E8D00);
    v45 = 0x708000000LL;
    while ( (v45 & _intel_mkl_feature_indicator_x) != v45 )
    {
      if ( _intel_mkl_feature_indicator_x )
        goto LABEL_193;
      _intel_mkl_features_init_x();
    }
    v46 = off_1836E1208;
    v47 = 256;
    v68 = _mm_cvtsi128_si32((__m128i)0LL);
    do
    {
      *(_OWORD *)&LibFileName[v47 - 16] = 0;
      *(_OWORD *)&v65[v47 + 240] = 0;
      *(_OWORD *)&v65[v47 + 224] = 0;
      *(_OWORD *)&v65[v47 + 208] = 0;
      v47 -= 64;
    }
    while ( v47 );
    v48 = 0;
    if ( mkl_serv_strnlen_s(v46, 260) )
    {
      while ( 1 )
      {
        v49 = v46[v48];
        if ( v49 == 47 || v49 == 92 )
          break;
        if ( ++v48 >= (unsigned __int64)mkl_serv_strnlen_s(v46, 260) )
          goto LABEL_178;
      }
      LibraryA = 0;
    }
    else
    {
LABEL_178:
      mkl_serv_strncpy_s(LibFileName, 260, byte_1836E8A40, 260);
      mkl_serv_strncat_s(LibFileName, 260, v46, 260);
      LibraryA = LoadLibraryA(LibFileName);
      if ( LibraryA )
      {
LABEL_188:
        if ( LibraryA )
        {
          qword_1836E8C68 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                      LibraryA,
                                                                                      "hbw_posix_memalign_psize");
          qword_1836E8C70 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(LibraryA, "hbw_malloc");
          ProcAddress = GetProcAddress(LibraryA, "hbw_free");
          qword_1836E8C78 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
          if ( qword_1836E8C68 )
          {
            if ( qword_1836E8C70 && ProcAddress )
            {
              v56 = 1;
              goto LABEL_194;
            }
          }
        }
LABEL_193:
        v56 = 0;
LABEL_194:
        dword_1836E8CF0 = v56;
        if ( i_malloc == malloc_0 && i_free == free_0 && i_realloc == realloc_0 && calloc_0 == i_calloc )
        {
          qword_1836E8C80 = (__int64 (__fastcall *)(_QWORD))sub_18003BEE0;
          qword_1836E8C88 = (__int64)sub_18003BAF0;
          qword_1836E8C90 = (__int64 (__fastcall *)(_QWORD))sub_18003C000;
          qword_1836E8C98 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))sub_18003BEE0;
          qword_1836E8CA0 = (__int64 (__fastcall *)(_QWORD))sub_18003C000;
        }
        else
        {
          qword_1836E8C80 = (__int64 (__fastcall *)(_QWORD))i_malloc;
          qword_1836E8C88 = (__int64)i_realloc;
          qword_1836E8C90 = (__int64 (__fastcall *)(_QWORD))i_free;
          qword_1836E8C98 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))i_malloc;
          qword_1836E8CA0 = (__int64 (__fastcall *)(_QWORD))i_free;
        }
        dword_1836E1210 = 1;
        goto LABEL_168;
      }
    }
    v51 = mkl_serv_strnlen_s(byte_1836E8A40, 260);
    if ( v51 != mkl_serv_strnlen_s(byte_1836E8B60, 260) || strncmp_0(byte_1836E8A40, byte_1836E8B60, 0x104u) )
    {
      v52 = 256;
      LODWORD(v66) = _mm_cvtsi128_si32((__m128i)0LL);
      do
      {
        *(_OWORD *)&v64[v52 + 672] = 0;
        *(_OWORD *)&v64[v52 + 656] = 0;
        *(_OWORD *)&v64[v52 + 640] = 0;
        *(_OWORD *)&v64[v52 + 624] = 0;
        v52 -= 64;
      }
      while ( v52 );
      v53 = 0;
      if ( mkl_serv_strnlen_s(v46, 260) )
      {
        while ( 1 )
        {
          v54 = v46[v53];
          if ( v54 == 47 || v54 == 92 )
            break;
          if ( ++v53 >= (unsigned __int64)mkl_serv_strnlen_s(v46, 260) )
            goto LABEL_187;
        }
        LibraryA = 0;
      }
      else
      {
LABEL_187:
        mkl_serv_strncpy_s(v65, 260, byte_1836E8B60, 260);
        mkl_serv_strncat_s(v65, 260, v46, 260);
        LibraryA = LoadLibraryA(v65);
      }
    }
    goto LABEL_188;
  }
LABEL_3:
  if ( !*(_QWORD *)(a1 - 24) )
    return;
  if ( (dword_1836E8CBC & 1) == 0 )
  {
    mkl_serv_lock(&unk_1836E8CB8);
    if ( (dword_1836E8CBC & 1) == 0 )
    {
      dwTlsIndex = TlsAlloc();
      if ( dwTlsIndex != -1 )
      {
        qword_1836E8CB0 = (__int64)sub_180040370;
        dword_1836E8CBC |= 1u;
      }
      mkl_serv_core_register_cleanup(sub_180061240, &dwTlsIndex);
    }
    mkl_serv_unlock(&unk_1836E8CB8);
  }
  if ( (dword_1836E8CBC & 1) != 0 )
    Value = (unsigned int)TlsGetValue(dwTlsIndex);
  else
    Value = 0;
  if ( Value > 0 && Value <= 1024 )
  {
    v3 = (volatile signed __int32 *)&qword_1836D1000[8 * (__int64)Value + 56];
    for ( i = _InterlockedCompareExchange(v3, 1, 0); i; i = _InterlockedCompareExchange(v3, 1, 0) )
      _mm_pause();
LABEL_16:
    v5 = Value;
    goto LABEL_17;
  }
  _InterlockedExchangeAdd(dword_1836D11C0, 2u);
  while ( (dword_1836D11C0[0] & 1) != 0 )
    _mm_pause();
  if ( Value )
    goto LABEL_16;
  v5 = _InterlockedIncrement(&dword_1836D1008);
  if ( (dword_1836E8CBC & 1) == 0 )
  {
    mkl_serv_lock(&unk_1836E8CB8);
    if ( (dword_1836E8CBC & 1) == 0 )
    {
      dwTlsIndex = TlsAlloc();
      if ( dwTlsIndex != -1 )
      {
        qword_1836E8CB0 = (__int64)sub_180040370;
        dword_1836E8CBC |= 1u;
      }
      mkl_serv_core_register_cleanup(sub_180061240, &dwTlsIndex);
    }
    mkl_serv_unlock(&unk_1836E8CB8);
  }
  if ( (dword_1836E8CBC & 1) != 0 )
    TlsSetValue(dwTlsIndex, (LPVOID)v5);
LABEL_17:
  v6 = v5 - 1;
  if ( v5 - 1 >= dword_1836D1008 )
    goto LABEL_88;
  if ( v6 >= 1024 )
  {
    _BitScanReverse((unsigned int *)&v34, v6);
    v35 = 1LL << v34;
    if ( qword_1836D0FC8[v34] )
      goto LABEL_120;
    mkl_serv_lock(&unk_1836E8D0C);
    if ( qword_1836D0FC8[v34] )
    {
LABEL_122:
      mkl_serv_unlock(&unk_1836E8D0C);
      if ( !qword_1836D0FC8[v34] )
      {
        v9 = 0;
        goto LABEL_21;
      }
LABEL_120:
      v36 = (__int64)(v5 - (int)v35 - 1) << 6;
      v37 = qword_1836D0FC8[v34];
      *(_DWORD *)(v36 + v37) = Value;
      v9 = (__int64 *)(v37 + v36 + 8);
      goto LABEL_21;
    }
    v38 = ((v35 << 6) + 0x1FFF) & 0xFFFFFFFFFFFFF000uLL;
    if ( (char *)qword_1836E8C80 == (char *)sub_18003BEE0 )
    {
      v59 = 0;
      LODWORD(Size[1]) = 0;
      LOBYTE(v60) = 0;
      Size[0] = v38 + 32;
      if ( dword_1836E8CF0
        && (qword_1836E1200 == -1 || qword_1836E1200 && (mkl_serv_lock(&unk_1836E8CF4), Size[0] < qword_1836E1200)) )
      {
        LODWORD(Size[1]) = 1;
        LOBYTE(v60) = 1;
        if ( (unsigned int)qword_1836E8C68(&v59, 0x200000, Size[0], 2) )
        {
          v59 = (_QWORD *)qword_1836E8C70(Size[0]);
          if ( !v59 )
          {
            v59 = malloc_0(Size[0]);
            LOBYTE(v60) = 0;
            LODWORD(Size[1]) = 0;
          }
        }
      }
      else
      {
        v59 = malloc_0(Size[0]);
      }
      if ( dword_1836E8CF0 && qword_1836E1200 != -1 && qword_1836E1200 )
      {
        if ( (_BYTE)v60 )
          qword_1836E1200 = qword_1836E1200 - v38 - 32;
        mkl_serv_unlock(&unk_1836E8CF4);
      }
      if ( !v59 )
        goto LABEL_152;
      v39 = Size[1];
      v40 = (__int64)(v59 + 4);
      *v59 = v59;
      *(_QWORD *)(v40 - 16) = Size[0];
      *(_QWORD *)(v40 - 8) = 4096;
      *(_DWORD *)(v40 - 24) = v39;
    }
    else
    {
      v40 = qword_1836E8C80(((v35 << 6) + 0x1FFF) & 0xFFFFFFFFFFFFF000uLL);
    }
    if ( v40 )
    {
      v41 = (v40 + 4096) & 0xFFFFFFFFFFFFF000uLL;
      *(_QWORD *)(v41 - 8) = v40;
      if ( v41 )
      {
        v42 = (unsigned __int64)(v35 << 6) >> 2;
        if ( v42 )
        {
          if ( v42 < 4 )
          {
            v43 = 0;
          }
          else
          {
            v43 = (unsigned __int64)(v35 << 6) >> 2;
            for ( j = 0; j < v42; j += 4LL )
              *(_OWORD *)(v41 + 4 * j) = 0;
          }
          for ( ; v43 < v42; ++v43 )
            *(_DWORD *)(v41 + 4 * v43) = 0;
        }
      }
      goto LABEL_150;
    }
LABEL_152:
    v41 = 0;
LABEL_150:
    qword_1836D0FC8[v34] = v41;
    goto LABEL_122;
  }
  v7 = qword_1836D1010[0];
  if ( qword_1836D1010[0] )
  {
LABEL_20:
    v8 = (v5 - 1LL) << 6;
    *(_DWORD *)(v7 + v8) = Value;
    v9 = (__int64 *)(v8 + v7 + 8);
    goto LABEL_21;
  }
  mkl_serv_lock(&unk_1836E8D0C);
  if ( qword_1836D1010[0] )
    goto LABEL_92;
  if ( (char *)qword_1836E8C80 == (char *)sub_18003BEE0 )
  {
    Size[0] = 0;
    v28 = 0;
    v29 = 0;
    if ( dword_1836E8CF0
      && (qword_1836E1200 == -1
       || qword_1836E1200 && (mkl_serv_lock(&unk_1836E8CF4), (unsigned __int64)qword_1836E1200 > 0x11020)) )
    {
      v28 = 1;
      v29 = 1;
      if ( (unsigned int)qword_1836E8C68(Size, 0x200000, 69664, 2) )
      {
        Size[0] = qword_1836E8C70(69664);
        if ( !Size[0] )
        {
          Size[0] = (size_t)malloc_0(0x11020u);
          v29 = 0;
          v28 = 0;
        }
      }
    }
    else
    {
      Size[0] = (size_t)malloc_0(0x11020u);
    }
    if ( dword_1836E8CF0 && qword_1836E1200 != -1 && qword_1836E1200 )
    {
      if ( v29 )
        qword_1836E1200 -= 69664;
      mkl_serv_unlock(&unk_1836E8CF4);
    }
    v30 = Size[0];
    if ( !Size[0] )
      goto LABEL_118;
    v31 = Size[0] + 32;
    *(_QWORD *)Size[0] = Size[0];
    *(_QWORD *)(v30 + 16) = 69664;
    *(_QWORD *)(v30 + 24) = 4096;
    *(_DWORD *)(v30 + 8) = v28;
  }
  else
  {
    v31 = qword_1836E8C80(69632);
  }
  if ( v31 )
  {
    v32 = (v31 + 4096) & 0xFFFFFFFFFFFFF000uLL;
    *(_QWORD *)(v32 - 8) = v31;
    if ( v32 )
    {
      for ( k = 0; k < 0x4000; k += 4LL )
        *(_OWORD *)(v32 + 4 * k) = 0;
    }
    qword_1836D1010[0] = (v31 + 4096) & 0xFFFFFFFFFFFFF000uLL;
    goto LABEL_92;
  }
LABEL_118:
  qword_1836D1010[0] = 0;
LABEL_92:
  mkl_serv_unlock(&unk_1836E8D0C);
  v7 = qword_1836D1010[0];
  if ( qword_1836D1010[0] )
    goto LABEL_20;
  v9 = 0;
LABEL_21:
  if ( v9 )
  {
    if ( *v9 )
      goto LABEL_23;
    if ( (char *)qword_1836E8C80 == (char *)sub_18003BEE0 )
    {
      v60 = 0;
      v22 = 0;
      v23 = 0;
      if ( dword_1836E8CF0
        && (qword_1836E1200 == -1
         || qword_1836E1200 && (mkl_serv_lock(&unk_1836E8CF4), (unsigned __int64)qword_1836E1200 > 0x100)) )
      {
        v22 = 1;
        v23 = 1;
        if ( (unsigned int)qword_1836E8C68(&v60, 0x200000, 256, 2) )
        {
          v60 = (_QWORD *)qword_1836E8C70(256);
          if ( !v60 )
          {
            v60 = malloc_0(0x100u);
            v23 = 0;
            v22 = 0;
          }
        }
      }
      else
      {
        v60 = malloc_0(0x100u);
      }
      if ( dword_1836E8CF0 && qword_1836E1200 != -1 && qword_1836E1200 )
      {
        if ( v23 )
          qword_1836E1200 -= 256;
        mkl_serv_unlock(&unk_1836E8CF4);
      }
      v24 = v60;
      if ( !v60 )
      {
LABEL_23:
        v10 = *v9;
        if ( *v9 )
        {
          *(_QWORD *)(v10 + 208) -= *(_QWORD *)(a1 - 16);
          --*(_DWORD *)(v10 + 204);
        }
        v11 = *((int *)v9 - 2);
        if ( v11 > 0 && v11 <= 1024 )
        {
          dword_1836D11C0[16 * v11] = 0;
          goto LABEL_29;
        }
        goto LABEL_28;
      }
      v25 = (__int64)(v60 + 4);
      *v60 = v60;
      v24[2] = 256;
      v24[3] = 4096;
      *((_DWORD *)v24 + 2) = v22;
    }
    else
    {
      v25 = qword_1836E8C80(224);
    }
    if ( v25 )
    {
      v26 = 224;
      do
      {
        *(_OWORD *)&v64[v26 - 16] = xmmword_1833EE8F0[v26 / 0x10];
        *(_OWORD *)&v62[v26] = xmmword_1833EE8E0[v26 / 0x10];
        *(_OWORD *)&Size[v26 / 8] = xmmword_1833EE8D0[v26 / 0x10];
        *(_OWORD *)&(&v59)[v26 / 8] = *(_OWORD *)&aMklVerbose[v26 + 8];
        v58[v26 / 0x10 + 2] = *(_OWORD *)&qword_1833EE8B0[v26 / 8];
        v58[v26 / 0x10 + 1] = xmmword_1833EE8A0[v26 / 0x10];
        v58[v26 / 0x10] = xmmword_1833EE890[v26 / 0x10];
        v26 -= 112LL;
      }
      while ( v26 );
      v27 = 224;
      do
      {
        *(_QWORD *)(v25 + v27 - 8) = *(_QWORD *)&v64[v27 - 8];
        *(_QWORD *)(v25 + v27 - 16) = *(_QWORD *)&v64[v27 - 16];
        *(_QWORD *)(v25 + v27 - 24) = *(_QWORD *)&v62[v27 + 8];
        *(_QWORD *)(v25 + v27 - 32) = *(_QWORD *)&v62[v27];
        v27 -= 32;
      }
      while ( v27 );
      *v9 = v25;
    }
    goto LABEL_23;
  }
LABEL_88:
  if ( Value <= 0 || Value > 1024 )
  {
LABEL_28:
    _InterlockedExchangeAdd(dword_1836D11C0, 0xFFFFFFFE);
    goto LABEL_29;
  }
  dword_1836D11C0[16 * (__int64)Value] = 0;
LABEL_29:
  v12 = -*(_QWORD *)(a1 - 16);
  if ( dword_1836E121C == 1 )
  {
    mkl_serv_lock(&unk_1836E8D04);
    if ( dword_1836E121C == 1 )
    {
      v20 = v12 + qword_1836E8CC0;
      v21 = dword_1836E8CC8 - 1;
      qword_1836E8CC0 = v20;
      --dword_1836E8CC8;
      if ( v20 > qword_1836E8CD0 )
      {
        qword_1836E8CD0 = v20;
        dword_1836E8CD8 = v21;
      }
    }
    mkl_serv_unlock(&unk_1836E8D04);
  }
  if ( *(_DWORD *)(a1 - 8) == 1 )
  {
    if ( dword_1836E1220 == 3 )
    {
      *(_QWORD *)String = 0;
      mkl_serv_getenv("MKL_MIC_REGISTER_MEMORY", String, 7);
      mkl_serv_lock(&unk_1836E8D08);
      if ( dword_1836E1220 == 3 )
        dword_1836E1220 = atoi_0(String) != 0;
      mkl_serv_unlock(&unk_1836E8D08);
    }
    if ( dword_1836E1220 == 1 && !(unsigned int)mkl_aa_fw_enter(v64, "mkl_free", 1) )
    {
      device_count = mkl_ueaa_get_device_count();
      v19 = 1;
      if ( device_count > 0 )
      {
        do
          mkl_ueaa_unregister(a1, (unsigned int)v19++);
        while ( v19 <= device_count );
      }
      mkl_aa_fw_leave(v64);
    }
  }
  if ( (char *)qword_1836E8C90 != (char *)sub_18003C000 )
  {
    qword_1836E8C90(*(_QWORD *)(a1 - 24));
    return;
  }
  v13 = *(_QWORD *)(a1 - 24);
  v14 = *(void **)(v13 - 32);
  if ( !v14 )
    return;
  v15 = dword_1836E8CF0;
  if ( !dword_1836E8CF0 )
    goto LABEL_43;
  v16 = qword_1836E1200;
  if ( qword_1836E1200 != -1 )
  {
    if ( qword_1836E1200 )
    {
      mkl_serv_lock(&unk_1836E8CF4);
      v16 = qword_1836E1200;
      v15 = dword_1836E8CF0;
      if ( !qword_1836E1200 )
        goto LABEL_38;
      goto LABEL_37;
    }
LABEL_43:
    free_0(v14);
    return;
  }
LABEL_37:
  if ( *(_DWORD *)(v13 - 24) != 1 )
  {
LABEL_38:
    if ( v15 && v16 != -1 )
    {
      if ( v16 )
        mkl_serv_unlock(&unk_1836E8CF4);
    }
    v14 = *(void **)(v13 - 32);
    goto LABEL_43;
  }
  v17 = -*(_QWORD *)(v13 - 16);
  if ( v15 && v16 != -1 )
  {
    qword_1836E1200 = v16 + *(_QWORD *)(v13 - 16);
    mkl_serv_unlock(&unk_1836E8CF4);
  }
  qword_1836E8C78(*(_QWORD *)(v13 - 32), v17);
}

```

## disassembly

```asm
0x18003eb20  push    rbx
0x18003eb21  push    rsi
0x18003eb22  push    rdi
0x18003eb23  push    r12
0x18003eb25  push    r13
0x18003eb27  push    r14
0x18003eb29  push    r15
0x18003eb2b  push    rbp
0x18003eb2c  sub     rsp, 548h
0x18003eb33  mov     r12, rcx
0x18003eb36  mov     rax, cs:__security_cookie
0x18003eb3d  xor     rax, rsp
0x18003eb40  mov     [rsp+588h+var_50], rax
0x18003eb48  test    r12, r12
0x18003eb4b  jz      loc_18003ED5B
0x18003eb51  mov     eax, cs:dword_1836E1210
0x18003eb57  cmp     eax, 0FFFFFFFFh
0x18003eb5a  jz      loc_18003F65C
0x18003eb60  cmp     qword ptr [r12-18h], 0
0x18003eb66  jz      loc_18003ED5B
0x18003eb6c  mov     eax, cs:dword_1836E8CBC
0x18003eb72  test    al, 1
0x18003eb74  jz      loc_18003F5F2
0x18003eb7a  mov     eax, cs:dword_1836E8CBC
0x18003eb80  test    al, 1
0x18003eb82  jnz     short loc_18003EB88
0x18003eb84  xor     esi, esi
0x18003eb86  jmp     short loc_18003EB97
0x18003eb88  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18003eb8e  call    cs:__imp_TlsGetValue
0x18003eb94  mov     rsi, rax
0x18003eb97  mov     ebp, esi
0x18003eb99  test    ebp, ebp
0x18003eb9b  jle     short loc_18003EBD9
0x18003eb9d  cmp     ebp, 400h
0x18003eba3  jg      short loc_18003EBD9
0x18003eba5  movsxd  rbx, esi
0x18003eba8  lea     rdx, qword_1836D1000
0x18003ebaf  shl     rbx, 6
0x18003ebb3  mov     ecx, 1
0x18003ebb8  xor     eax, eax
0x18003ebba  lea     rdi, [rdx+rbx+1C0h]
0x18003ebc2  lock cmpxchg [rdi], ecx
0x18003ebc6  test    eax, eax
0x18003ebc8  jz      short loc_18003EC07
0x18003ebca  pause
0x18003ebcc  mov     ecx, 1
0x18003ebd1  xor     eax, eax
0x18003ebd3  lock cmpxchg [rdi], ecx
0x18003ebd7  jmp     short loc_18003EBC6
0x18003ebd9  lea     rdx, dword_1836D11C0
0x18003ebe0  mov     eax, 2
0x18003ebe5  lock xadd [rdx], eax
0x18003ebe9  mov     eax, cs:dword_1836D11C0
0x18003ebef  test    al, 1
0x18003ebf1  jz      short loc_18003EBFF
0x18003ebf3  pause
0x18003ebf5  mov     eax, cs:dword_1836D11C0
0x18003ebfb  test    al, 1
0x18003ebfd  jnz     short loc_18003EBF3
0x18003ebff  test    ebp, ebp
0x18003ec01  jz      loc_18003F545
0x18003ec07  mov     ebx, ebp
0x18003ec09  lea     eax, [rbx-1]
0x18003ec0c  cmp     eax, cs:dword_1836D1008
0x18003ec12  jge     loc_18003F0EE
0x18003ec18  cmp     eax, 400h
0x18003ec1d  jge     loc_18003F2D3
0x18003ec23  mov     rax, cs:qword_1836D1010
0x18003ec2a  test    rax, rax
0x18003ec2d  jz      loc_18003F120
0x18003ec33  movsxd  rbx, ebx
0x18003ec36  dec     rbx
0x18003ec39  shl     rbx, 6
0x18003ec3d  mov     [rax+rbx], ebp
0x18003ec40  lea     rdi, [rbx+rax+8]
0x18003ec45  test    rdi, rdi
0x18003ec48  jz      loc_18003F0EE
0x18003ec4e  cmp     qword ptr [rdi], 0
0x18003ec52  jz      loc_18003EEEE
0x18003ec58  mov     rdx, [rdi]
0x18003ec5b  test    rdx, rdx
0x18003ec5e  jz      short loc_18003EC72
0x18003ec60  mov     rax, [r12-10h]
0x18003ec65  sub     [rdx+0D0h], rax
0x18003ec6c  dec     dword ptr [rdx+0CCh]
0x18003ec72  movsxd  rdx, dword ptr [rdi-8]
0x18003ec76  test    rdx, rdx
0x18003ec79  jle     short loc_18003EC9C
0x18003ec7b  cmp     rdx, 400h
0x18003ec82  jg      short loc_18003EC9C
0x18003ec84  shl     rdx, 6
0x18003ec88  lea     rax, cs:180000000h
0x18003ec8f  mov     rva dword_1836D11C0[rax+rdx], 0
0x18003ec9a  jmp     short loc_18003ECAC
0x18003ec9c  lea     rdx, dword_1836D11C0
0x18003eca3  mov     eax, 0FFFFFFFEh
0x18003eca8  lock xadd [rdx], eax
0x18003ecac  mov     rbx, [r12-10h]
0x18003ecb1  neg     rbx
0x18003ecb4  cmp     cs:dword_1836E121C, 1
0x18003ecbb  jz      loc_18003EE91
0x18003ecc1  cmp     dword ptr [r12-8], 1
0x18003ecc7  jz      loc_18003EDB2
0x18003eccd  lea     rax, sub_18003C000
0x18003ecd4  mov     rdx, cs:qword_1836E8C90
0x18003ecdb  cmp     rdx, rax
0x18003ecde  jnz     short loc_18003ED54
0x18003ece0  mov     rbp, [r12-18h]
0x18003ece5  mov     rcx, [rbp-20h]
0x18003ece9  test    rcx, rcx
0x18003ecec  jz      short loc_18003ED5B
0x18003ecee  mov     eax, cs:dword_1836E8CF0
0x18003ecf4  test    eax, eax
0x18003ecf6  jz      short loc_18003ED4D
0x18003ecf8  mov     rbx, cs:qword_1836E1200
0x18003ecff  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003ed03  jz      short loc_18003ED28
0x18003ed05  test    rbx, rbx
0x18003ed08  jz      short loc_18003ED4D
0x18003ed0a  lea     rcx, unk_1836E8CF4
0x18003ed11  call    mkl_serv_lock
0x18003ed16  mov     rbx, cs:qword_1836E1200
0x18003ed1d  test    rbx, rbx
0x18003ed20  mov     eax, cs:dword_1836E8CF0
0x18003ed26  jbe     short loc_18003ED2E
0x18003ed28  cmp     dword ptr [rbp-18h], 1
0x18003ed2c  jz      short loc_18003ED7F
0x18003ed2e  test    eax, eax
0x18003ed30  jz      short loc_18003ED49
0x18003ed32  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003ed36  jz      short loc_18003ED49
0x18003ed38  test    rbx, rbx
0x18003ed3b  jz      short loc_18003ED49
0x18003ed3d  lea     rcx, unk_1836E8CF4
0x18003ed44  call    mkl_serv_unlock
0x18003ed49  mov     rcx, [rbp-20h]; Block
0x18003ed4d  call    free_0
0x18003ed52  jmp     short loc_18003ED5B
0x18003ed54  mov     rcx, [r12-18h]
0x18003ed59  call    rdx ; qword_1836E8C90
0x18003ed5b  mov     rcx, [rsp+588h+var_50]
0x18003ed63  xor     rcx, rsp; StackCookie
0x18003ed66  call    __security_check_cookie
0x18003ed6b  add     rsp, 548h
0x18003ed72  pop     rbp
0x18003ed73  pop     r15
0x18003ed75  pop     r14
0x18003ed77  pop     r13
0x18003ed79  pop     r12
0x18003ed7b  pop     rdi
0x18003ed7c  pop     rsi
0x18003ed7d  pop     rbx
0x18003ed7e  retn
0x18003ed7f  mov     rdx, [rbp-10h]
0x18003ed83  neg     rdx
0x18003ed86  test    eax, eax
0x18003ed88  jz      short loc_18003EDA6
0x18003ed8a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003ed8e  jz      short loc_18003EDA6
0x18003ed90  lea     rcx, unk_1836E8CF4
0x18003ed97  sub     rbx, rdx
0x18003ed9a  mov     cs:qword_1836E1200, rbx
0x18003eda1  call    mkl_serv_unlock
0x18003eda6  mov     rcx, [rbp-20h]
0x18003edaa  call    cs:qword_1836E8C78
0x18003edb0  jmp     short loc_18003ED5B
0x18003edb2  mov     eax, cs:dword_1836E1220
0x18003edb8  cmp     eax, 3
0x18003edbb  jz      short loc_18003EE1A
0x18003edbd  mov     eax, cs:dword_1836E1220
0x18003edc3  cmp     eax, 1
0x18003edc6  jnz     loc_18003ECCD
0x18003edcc  lea     rdx, aMklFree; "mkl_free"
0x18003edd3  lea     rcx, [rsp+588h+var_528]
0x18003edd8  mov     r8d, 1
0x18003edde  call    mkl_aa_fw_enter
0x18003ede3  test    eax, eax
0x18003ede5  jnz     loc_18003ECCD
0x18003edeb  call    mkl_ueaa_get_device_count
0x18003edf0  mov     ebp, eax
0x18003edf2  mov     ebx, 1
0x18003edf7  test    ebp, ebp
0x18003edf9  jle     short loc_18003EE0B
0x18003edfb  mov     rcx, r12
0x18003edfe  mov     edx, ebx
0x18003ee00  call    mkl_ueaa_unregister
0x18003ee05  inc     ebx
0x18003ee07  cmp     ebx, ebp
0x18003ee09  jle     short loc_18003EDFB
0x18003ee0b  lea     rcx, [rsp+588h+var_528]
0x18003ee10  call    mkl_aa_fw_leave
0x18003ee15  jmp     loc_18003ECCD
0x18003ee1a  mov     qword ptr [rsp+588h+String], 0
0x18003ee26  lea     rcx, aMklMicRegister; "MKL_MIC_REGISTER_MEMORY"
0x18003ee2d  lea     rdx, [rsp+588h+String]
0x18003ee35  mov     r8d, 7
0x18003ee3b  call    mkl_serv_getenv
0x18003ee40  lea     rcx, unk_1836E8D08
0x18003ee47  call    mkl_serv_lock
0x18003ee4c  mov     eax, cs:dword_1836E1220
0x18003ee52  cmp     eax, 3
0x18003ee55  jz      short loc_18003EE68
0x18003ee57  lea     rcx, unk_1836E8D08
0x18003ee5e  call    mkl_serv_unlock
0x18003ee63  jmp     loc_18003EDBD
0x18003ee68  lea     rcx, [rsp+588h+String]; String
0x18003ee70  call    atoi_0
0x18003ee75  test    eax, eax
0x18003ee77  jz      short loc_18003EE85
0x18003ee79  mov     cs:dword_1836E1220, 1
0x18003ee83  jmp     short loc_18003EE57
0x18003ee85  mov     cs:dword_1836E1220, 0
0x18003ee8f  jmp     short loc_18003EE57
0x18003ee91  lea     rcx, unk_1836E8D04
0x18003ee98  call    mkl_serv_lock
0x18003ee9d  cmp     cs:dword_1836E121C, 1
0x18003eea4  jz      short loc_18003EEB7
0x18003eea6  lea     rcx, unk_1836E8D04
0x18003eead  call    mkl_serv_unlock
0x18003eeb2  jmp     loc_18003ECC1
0x18003eeb7  mov     rax, cs:qword_1836E8CC0
0x18003eebe  add     rax, rbx
0x18003eec1  mov     edx, cs:dword_1836E8CC8
0x18003eec7  dec     edx
0x18003eec9  mov     cs:qword_1836E8CC0, rax
0x18003eed0  mov     cs:dword_1836E8CC8, edx
0x18003eed6  cmp     rax, cs:qword_1836E8CD0
0x18003eedd  jbe     short loc_18003EEA6
0x18003eedf  mov     cs:qword_1836E8CD0, rax
0x18003eee6  mov     cs:dword_1836E8CD8, edx
0x18003eeec  jmp     short loc_18003EEA6
0x18003eeee  lea     rax, sub_18003BEE0
0x18003eef5  mov     rdx, cs:qword_1836E8C80
0x18003eefc  cmp     rdx, rax
0x18003eeff  jnz     loc_18003EFF9
0x18003ef05  mov     qword ptr [rsp+588h+var_568+8], 0
0x18003ef0e  xor     ebp, ebp
0x18003ef10  xor     bl, bl
0x18003ef12  cmp     cs:dword_1836E8CF0, 0
0x18003ef19  jz      short loc_18003EF88
0x18003ef1b  mov     rax, cs:qword_1836E1200
0x18003ef22  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ef26  jz      short loc_18003EF46
0x18003ef28  test    rax, rax
0x18003ef2b  jz      short loc_18003EF88
0x18003ef2d  lea     rcx, unk_1836E8CF4
0x18003ef34  call    mkl_serv_lock
0x18003ef39  cmp     cs:qword_1836E1200, 100h
0x18003ef44  jbe     short loc_18003EF88
0x18003ef46  mov     edx, 200000h
0x18003ef4b  lea     rcx, [rsp+588h+var_568+8]
0x18003ef50  mov     r8d, 100h
0x18003ef56  mov     r9d, 2
0x18003ef5c  mov     ebp, 1
0x18003ef61  mov     bl, 1
0x18003ef63  call    cs:qword_1836E8C68
0x18003ef69  test    eax, eax
0x18003ef6b  jz      short loc_18003EF97
0x18003ef6d  mov     ecx, 100h
0x18003ef72  call    cs:qword_1836E8C70
0x18003ef78  mov     qword ptr [rsp+588h+var_568+8], rax
0x18003ef7d  test    rax, rax
0x18003ef80  jz      loc_18003F0D6
0x18003ef86  jmp     short loc_18003EF97
0x18003ef88  mov     ecx, 100h; Size
0x18003ef8d  call    malloc_0
0x18003ef92  mov     qword ptr [rsp+588h+var_568+8], rax
0x18003ef97  cmp     cs:dword_1836E8CF0, 0
0x18003ef9e  jz      short loc_18003EFCF
0x18003efa0  mov     rax, cs:qword_1836E1200
0x18003efa7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003efab  jz      short loc_18003EFCF
0x18003efad  test    rax, rax
0x18003efb0  jz      short loc_18003EFCF
0x18003efb2  test    bl, bl
0x18003efb4  jz      short loc_18003EFC3
0x18003efb6  add     rax, 0FFFFFFFFFFFFFF00h
0x18003efbc  mov     cs:qword_1836E1200, rax
0x18003efc3  lea     rcx, unk_1836E8CF4
0x18003efca  call    mkl_serv_unlock
0x18003efcf  mov     rdx, qword ptr [rsp+588h+var_568+8]
0x18003efd4  test    rdx, rdx
0x18003efd7  jz      loc_18003EC58
0x18003efdd  lea     rax, [rdx+20h]
0x18003efe1  mov     [rdx], rdx
0x18003efe4  mov     qword ptr [rax-10h], 100h
0x18003efec  mov     qword ptr [rax-8], 1000h
0x18003eff4  mov     [rax-18h], ebp
0x18003eff7  jmp     short loc_18003F000
0x18003eff9  mov     ecx, 0E0h
0x18003effe  call    rdx ; qword_1836E8C80
0x18003f000  test    rax, rax
0x18003f003  jz      loc_18003EC58
0x18003f009  mov     r11d, 0E0h
0x18003f00f  lea     rdx, cs:180000000h
0x18003f016  mov     rbx, rdx
0x18003f019  mov     rbp, rdx
0x18003f01c  mov     rsi, rdx
0x18003f01f  mov     r8, rdx
  ... truncated ...
```
