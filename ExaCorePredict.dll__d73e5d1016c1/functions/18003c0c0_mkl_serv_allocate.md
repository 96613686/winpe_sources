# mkl_serv_allocate

- ea: `0x18003c0c0`
- end: `0x18003cec0`
- name: `mkl_serv_allocate`
- size: `3584`
- prototype: ``
- caller_count: `71`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x1800088d0`
- `0x18000a8b0`
- `0x18000ae40`
- `0x18004c3c0`
- `0x18004db60`
- `0x18004fcd0`
- `0x180051460`
- `0x1800592b0`
- `0x18005ec30`
- `0x18006a480`
- `0x18006f9f0`
- `0x18007a4c0`
- `0x18007c7d0`
- `0x18007e820`
- `0x18007fbb0`
- `0x1800810b0`
- `0x180081f80`
- `0x1800914d0`
- `0x1800928b0`
- `0x180093960`
- `0x180095ec0`
- `0x1800976c0`
- `0x180098f90`
- `0x18009a930`
- `0x18009d5d0`
- `0x18009f320`
- `0x1800e4860`
- `0x180107090`
- `0x180114710`
- `0x180117c90`
- `0x18011b780`
- `0x18034d450`
- `0x180353e00`
- `0x18035b470`
- `0x1803bec70`
- `0x1803e4330`
- `0x1805d5d80`
- `0x1806f3440`
- `0x18081e600`
- `0x1808cbe30`
- `0x1808cc020`
- `0x180af3b30`
- `0x180af3d00`
- `0x180bfae70`
- `0x180c07160`
- `0x180c1f6b0`
- `0x180c39db0`
- `0x180c56a00`
- `0x180cc0230`
- `0x180cc0420`

## callees

- `0x18003c0c0`
- `0x18003cec0`
- `0x18003d720`
- `0x180054070`
- `0x180054080`
- `0x180055ce0`
- `0x180055e50`
- `0x180056180`
- `0x180077140`
- `0x1800775d0`
- `0x1800777c0`
- `0x1832ce3b0`
- `0x1832dbf30`
- `0x1832dbf90`
- `0x1832dbfe0`
- `0x1832dc0c0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003ccfb`
- `KERNEL32!GetProcAddress` at `0x18003cd12`
- `KERNEL32!GetProcAddress` at `0x18003cd29`
- `KERNEL32!GetProcAddress` at `0x18003ccfb`
- `KERNEL32!GetProcAddress` at `0x18003cd12`
- `KERNEL32!GetProcAddress` at `0x18003cd29`
- `KERNEL32!TlsAlloc` at `0x18003c9cb`
- `KERNEL32!TlsAlloc` at `0x18003c9cb`
- `KERNEL32!TlsGetValue` at `0x18003c1a0`
- `KERNEL32!TlsGetValue` at `0x18003c1a0`
- `KERNEL32!LoadLibraryA` at `0x18003cbea`
- `KERNEL32!LoadLibraryA` at `0x18003cce3`
- `KERNEL32!LoadLibraryA` at `0x18003cbea`
- `KERNEL32!LoadLibraryA` at `0x18003cce3`

## pseudocode

```c
__int64 __fastcall mkl_serv_allocate(unsigned __int64 a1, unsigned int a2)
{
  unsigned int v5; // eax
  _QWORD *v6; // rax
  _QWORD *v7; // r13
  __int64 v8; // r12
  __int64 v9; // r15
  __int64 v10; // r9
  unsigned __int64 v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // rbp
  __int64 v14; // r8
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // r15
  __int64 v19; // rcx
  __int64 v20; // r14
  __int64 v21; // rdi
  int v22; // eax
  __int64 v23; // rdi
  int v24; // edi
  unsigned __int64 v25; // r14
  _QWORD *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r15
  __int64 v29; // rbp
  __int64 v30; // rdx
  unsigned __int64 v31; // rax
  int v32; // edx
  unsigned __int64 v33; // rax
  int v34; // edx
  int v35; // ebp
  unsigned __int64 v36; // r14
  _QWORD *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r15
  unsigned __int64 v41; // rax
  int v42; // edx
  __int64 v43; // rdx
  __int64 v44; // r15
  __int64 v45; // rbp
  int v46; // eax
  char *v47; // rsi
  __int64 v48; // rax
  __int64 v49; // rbp
  char v50; // al
  HMODULE LibraryA; // rbp
  __int64 v52; // rdi
  __int64 v53; // rax
  __int64 v54; // rbp
  char v55; // al
  FARPROC ProcAddress; // rax
  int v57; // eax
  int v58; // eax
  __int128 v59; // [rsp+10h] [rbp-2C8h]
  _QWORD *v60; // [rsp+20h] [rbp-2B8h] BYREF
  _QWORD *v61; // [rsp+28h] [rbp-2B0h] BYREF
  char v62[16]; // [rsp+30h] [rbp-2A8h] BYREF
  CHAR v64[256]; // [rsp+50h] [rbp-288h] BYREF
  __int128 v65; // [rsp+150h] [rbp-188h]
  CHAR LibFileName[256]; // [rsp+160h] [rbp-178h] BYREF
  int v67; // [rsp+260h] [rbp-78h]
  char String[36]; // [rsp+264h] [rbp-74h] BYREF

  if ( !a1 )
    return 0;
  if ( dword_1836E1210 == -1 )
  {
    mkl_serv_lock(&unk_1836E8CFC);
    if ( dword_1836E1210 != -1 )
    {
LABEL_152:
      mkl_serv_unlock(&unk_1836E8CFC);
      goto LABEL_4;
    }
    mkl_serv_lock(&unk_1836E8D00);
    if ( dword_1836E1214 == -1 )
    {
      dword_1836E1218 = (int)mkl_serv_getenv("MKL_DISABLE_FAST_MM", v62, 32) > 0;
      if ( (int)mkl_serv_getenv("MKL_FAST_MEMORY_LIMIT", v62, 32) > 0 )
      {
        v58 = atol_0(v62);
        if ( v58 < 0 )
          qword_1836E1200 = -1;
        else
          qword_1836E1200 = (__int64)v58 << 20;
      }
      dword_1836E1214 = 1;
    }
    mkl_serv_unlock(&unk_1836E8D00);
    while ( (_intel_mkl_feature_indicator_x & 0x708000000LL) != 0x708000000LL )
    {
      if ( _intel_mkl_feature_indicator_x )
        goto LABEL_177;
      _intel_mkl_features_init_x();
    }
    v47 = off_1836E1208;
    v48 = 256;
    v67 = _mm_cvtsi128_si32((__m128i)0LL);
    do
    {
      *(_OWORD *)&LibFileName[v48 - 16] = 0;
      *(_OWORD *)&v64[v48 + 240] = 0;
      *(_OWORD *)&v64[v48 + 224] = 0;
      *(_OWORD *)&v64[v48 + 208] = 0;
      v48 -= 64;
    }
    while ( v48 );
    v49 = 0;
    if ( mkl_serv_strnlen_s(v47, 260) )
    {
      while ( 1 )
      {
        v50 = v47[v49];
        if ( v50 == 47 || v50 == 92 )
          break;
        if ( ++v49 >= (unsigned __int64)mkl_serv_strnlen_s(v47, 260) )
          goto LABEL_162;
      }
      LibraryA = 0;
    }
    else
    {
LABEL_162:
      mkl_serv_strncpy_s(LibFileName, 260, byte_1836E8A40, 260);
      mkl_serv_strncat_s(LibFileName, 260, v47, 260);
      LibraryA = LoadLibraryA(LibFileName);
      if ( LibraryA )
      {
LABEL_172:
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
              v57 = 1;
              goto LABEL_178;
            }
          }
        }
LABEL_177:
        v57 = 0;
LABEL_178:
        dword_1836E8CF0 = v57;
        if ( i_malloc == malloc_0 && i_free == free_0 && i_realloc == realloc_0 && calloc_0 == i_calloc )
        {
          qword_1836E8C80 = (__int64)sub_18003BEE0;
          qword_1836E8C88 = (__int64)sub_18003BAF0;
          qword_1836E8C90 = (__int64)sub_18003C000;
          qword_1836E8C98 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))sub_18003BEE0;
          qword_1836E8CA0 = (__int64 (__fastcall *)(_QWORD))sub_18003C000;
        }
        else
        {
          qword_1836E8C80 = (__int64)i_malloc;
          qword_1836E8C88 = (__int64)i_realloc;
          qword_1836E8C90 = (__int64)i_free;
          qword_1836E8C98 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))i_malloc;
          qword_1836E8CA0 = (__int64 (__fastcall *)(_QWORD))i_free;
        }
        dword_1836E1210 = 1;
        goto LABEL_152;
      }
    }
    v52 = mkl_serv_strnlen_s(byte_1836E8A40, 260);
    if ( v52 != mkl_serv_strnlen_s(byte_1836E8B60, 260) || strncmp_0(byte_1836E8A40, byte_1836E8B60, 0x104u) )
    {
      v53 = 256;
      LODWORD(v65) = _mm_cvtsi128_si32((__m128i)0LL);
      do
      {
        *(_OWORD *)&v64[v53 - 16] = 0;
        *(_OWORD *)&v62[v53] = 0;
        *(_OWORD *)&(&v60)[(unsigned __int64)v53 / 8] = 0;
        *(__int128 *)((char *)&v59 + v53) = 0;
        v53 -= 64;
      }
      while ( v53 );
      v54 = 0;
      if ( mkl_serv_strnlen_s(v47, 260) )
      {
        while ( 1 )
        {
          v55 = v47[v54];
          if ( v55 == 47 || v55 == 92 )
            break;
          if ( ++v54 >= (unsigned __int64)mkl_serv_strnlen_s(v47, 260) )
            goto LABEL_171;
        }
        LibraryA = 0;
      }
      else
      {
LABEL_171:
        mkl_serv_strncpy_s(v64, 260, byte_1836E8B60, 260);
        mkl_serv_strncat_s(v64, 260, v47, 260);
        LibraryA = LoadLibraryA(v64);
      }
    }
    goto LABEL_172;
  }
LABEL_4:
  if ( dword_1836E1214 == -1 )
  {
    mkl_serv_lock(&unk_1836E8D00);
    if ( dword_1836E1214 == -1 )
    {
      dword_1836E1218 = (int)mkl_serv_getenv("MKL_DISABLE_FAST_MM", String, 32) > 0;
      if ( (int)mkl_serv_getenv("MKL_FAST_MEMORY_LIMIT", String, 32) > 0 )
      {
        v46 = atol_0(String);
        if ( v46 < 0 )
          qword_1836E1200 = -1;
        else
          qword_1836E1200 = (__int64)v46 << 20;
      }
      dword_1836E1214 = 1;
    }
    mkl_serv_unlock(&unk_1836E8D00);
  }
  if ( dword_1836E1218 > 0 || a1 > 0x8000000 )
    return mkl_serv_malloc(a1, a2);
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
  v5 = (dword_1836E8CBC & 1) != 0 ? (unsigned int)TlsGetValue(dwTlsIndex) : 0;
  v6 = (_QWORD *)sub_18003D720(v5, 1, 0);
  v7 = v6;
  if ( !v6 )
    return mkl_serv_malloc(a1, a2);
  v8 = *v6;
  if ( !*v6 )
  {
    v45 = *((int *)v6 - 2);
    if ( v45 > 0 && v45 <= 1024 )
    {
      dword_1836D11C0[16 * v45] = 0;
      return mkl_serv_malloc(a1, a2);
    }
LABEL_136:
    _InterlockedExchangeAdd(dword_1836D11C0, 0xFFFFFFFE);
    return mkl_serv_malloc(a1, a2);
  }
  if ( (int)a2 < 64 )
  {
    v9 = 64;
  }
  else
  {
    v9 = a2;
    if ( (a2 & (a2 - 1)) != 0 )
      v9 = 64;
  }
  v10 = -1;
  v11 = a1 + v9;
  v12 = *(int *)(v8 + 200);
  v13 = -1;
  v14 = 0;
  if ( v12 > 0 )
  {
    do
    {
      if ( !*(_QWORD *)(v8 + 8 * v14 + 160) )
      {
        v15 = *(_QWORD *)(v8 + 8 * v14 + 120);
        if ( v15 == v11 )
        {
          *(_QWORD *)(v8 + 8 * v14 + 80) = a1;
          v43 = *(_QWORD *)(v8 + 8 * v14);
          v17 = v43 - ((unsigned int)v43 & ((_DWORD)v9 - 1));
          v44 = v17 + v9;
          *(_QWORD *)(v8 + 8 * v14 + 160) = 1;
          if ( v17 != v43 )
            v17 = v44;
          *(_QWORD *)(v8 + 8 * v14 + 40) = v17;
          goto LABEL_34;
        }
        if ( v15 <= v11 )
        {
          if ( v13 == -1 )
            v13 = (int)v14;
        }
        else if ( v10 == -1 )
        {
          v10 = (int)v14;
        }
        else if ( v15 < *(_QWORD *)(v8 + 8 * v10 + 120) )
        {
          v10 = (int)v14;
        }
      }
      ++v14;
    }
    while ( v14 < v12 );
    if ( v10 >= 0 )
    {
      *(_QWORD *)(v8 + 8 * v10 + 80) = a1;
      v16 = *(_QWORD *)(v8 + 8 * v10);
      v17 = v16 - ((unsigned int)v16 & ((_DWORD)v9 - 1));
      v18 = v17 + v9;
      *(_QWORD *)(v8 + 8 * v10 + 160) = 1;
      if ( v17 != v16 )
        v17 = v18;
      *(_QWORD *)(v8 + 8 * v10 + 40) = v17;
      goto LABEL_34;
    }
    if ( v12 < 5 )
      goto LABEL_100;
    if ( v13 >= 0 )
    {
      v20 = *(_QWORD *)(v8 + 8 * v13);
      if ( v20 )
      {
        v21 = -*(_QWORD *)(v8 + 8 * v13 + 120);
        if ( dword_1836E121C == 1 )
        {
          mkl_serv_lock(&unk_1836E8D04);
          if ( dword_1836E121C == 1 )
          {
            v33 = v21 + qword_1836E8CC0;
            v34 = dword_1836E8CC8 - 1;
            qword_1836E8CC0 = v33;
            --dword_1836E8CC8;
            if ( v33 > qword_1836E8CD0 )
            {
              qword_1836E8CD0 = v33;
              dword_1836E8CD8 = v34;
            }
          }
          mkl_serv_unlock(&unk_1836E8D04);
          v20 = *(_QWORD *)(v8 + 8 * v13);
        }
        if ( (char *)qword_1836E8CA0 == (char *)sub_18003C000 )
        {
          if ( *(_QWORD *)(v20 - 32) )
          {
            v22 = dword_1836E8CF0;
            if ( !dword_1836E8CF0 )
              goto LABEL_55;
            v23 = qword_1836E1200;
            if ( qword_1836E1200 == -1 )
              goto LABEL_50;
            if ( qword_1836E1200 )
            {
              mkl_serv_lock(&unk_1836E8CF4);
              v23 = qword_1836E1200;
              v22 = dword_1836E8CF0;
              if ( !qword_1836E1200 )
                goto LABEL_51;
LABEL_50:
              if ( *(_DWORD *)(v20 - 24) != 1 )
              {
LABEL_51:
                if ( v22 && v23 != -1 && v23 )
                  mkl_serv_unlock(&unk_1836E8CF4);
                goto LABEL_55;
              }
              v30 = -*(_QWORD *)(v20 - 16);
              if ( v22 && v23 != -1 )
              {
                qword_1836E1200 = v23 + *(_QWORD *)(v20 - 16);
                mkl_serv_unlock(&unk_1836E8CF4);
              }
              qword_1836E8C78(*(_QWORD *)(v20 - 32), v30);
            }
            else
            {
LABEL_55:
              free_0(*(void **)(v20 - 32));
            }
          }
        }
        else
        {
          qword_1836E8CA0(v20);
        }
        *(_QWORD *)(v8 + 8 * v13 + 40) = 0;
        *(_QWORD *)(v8 + 8 * v13) = 0;
        *(_QWORD *)(v8 + 8 * v13 + 120) = 0;
        *(_QWORD *)(v8 + 8 * v13 + 80) = 0;
      }
      if ( (char *)qword_1836E8C98 == (char *)sub_18003BEE0 )
      {
        v61 = 0;
        v24 = 0;
        LOBYTE(v60) = 0;
        v25 = a1 + v9 + 32;
        if ( dword_1836E8CF0
          && (qword_1836E1200 == -1 || qword_1836E1200 && (mkl_serv_lock(&unk_1836E8CF4), v25 < qword_1836E1200)) )
        {
          LOBYTE(v60) = 1;
          v24 = 1;
          if ( (unsigned int)qword_1836E8C68(&v61, 0x200000, a1 + v9 + 32, 2) )
          {
            v61 = (_QWORD *)qword_1836E8C70(a1 + v9 + 32);
            if ( !v61 )
            {
              v61 = malloc_0(a1 + v9 + 32);
              v24 = 0;
              LOBYTE(v60) = 0;
            }
          }
        }
        else
        {
          v61 = malloc_0(a1 + v9 + 32);
        }
        if ( dword_1836E8CF0 && qword_1836E1200 != -1 && qword_1836E1200 )
        {
          if ( (_BYTE)v60 )
            qword_1836E1200 = qword_1836E1200 - v11 - 32;
          mkl_serv_unlock(&unk_1836E8CF4);
        }
        v26 = v61;
        if ( v61 )
        {
          v27 = (__int64)(v61 + 4);
          *v61 = v61;
          v26[2] = v25;
          v26[3] = 4096;
          *((_DWORD *)v26 + 2) = v24;
        }
        else
        {
          v27 = 0;
        }
      }
      else
      {
        v27 = qword_1836E8C98(a1 + v9, qword_1836E8C98, v14);
      }
      *(_QWORD *)(v8 + 8 * v13) = v27;
      *(_QWORD *)(v8 + 8 * v13 + 80) = a1;
      *(_QWORD *)(v8 + 8 * v13 + 120) = v11;
      *(_QWORD *)(v8 + 8 * v13 + 160) = 1;
      if ( v27 )
      {
        if ( dword_1836E121C == 1 )
        {
          mkl_serv_lock(&unk_1836E8D04);
          if ( dword_1836E121C == 1 )
          {
            v31 = v11 + qword_1836E8CC0;
            v32 = dword_1836E8CC8 + 1;
            qword_1836E8CC0 = v31;
            ++dword_1836E8CC8;
            if ( v31 > qword_1836E8CD0 )
            {
              qword_1836E8CD0 = v31;
              dword_1836E8CD8 = v32;
            }
          }
          mkl_serv_unlock(&unk_1836E8D04);
          v27 = *(_QWORD *)(v8 + 8 * v13);
        }
        v17 = v27 - ((unsigned int)v27 & ((_DWORD)v9 - 1));
        v28 = v17 + v9;
        if ( v17 != v27 )
          v17 = v28;
        *(_QWORD *)(v8 + 8 * v13 + 40) = v17;
      }
      else
      {
        v17 = *(_QWORD *)(v8 + 8 * v13 + 40);
      }
      goto LABEL_34;
    }
    v29 = *((int *)v7 - 2);
    if ( v29 > 0 && v29 <= 1024 )
    {
      dword_1836D11C0[16 * v29] = 0;
      return mkl_serv_malloc(a1, a2);
    }
    goto LABEL_136;
  }
LABEL_100:
  if ( (char *)qword_1836E8C98 == (char *)sub_18003BEE0 )
  {
    v60 = 0;
    v35 = 0;
    LOBYTE(v61) = 0;
    v36 = a1 + v9 + 32;
    if ( dword_1836E8CF0
      && (qword_1836E1200 == -1 || qword_1836E1200 && (mkl_serv_lock(&unk_1836E8CF4), v36 < qword_1836E1200)) )
    {
      LOBYTE(v61) = 1;
      v35 = 1;
      if ( (unsigned int)qword_1836E8C68(&v60, 0x200000, a1 + v9 + 32, 2) )
      {
        v60 = (_QWORD *)qword_1836E8C70(a1 + v9 + 32);
        if ( !v60 )
        {
          v60 = malloc_0(a1 + v9 + 32);
          v35 = 0;
          LOBYTE(v61) = 0;
        }
      }
    }
    else
    {
      v60 = malloc_0(a1 + v9 + 32);
    }
    if ( dword_1836E8CF0 && qword_1836E1200 != -1 && qword_1836E1200 )
    {
      if ( (_BYTE)v61 )
        qword_1836E1200 = qword_1836E1200 - v11 - 32;
      mkl_serv_unlock(&unk_1836E8CF4);
    }
    v37 = v60;
    if ( v60 )
    {
      v38 = (__int64)(v60 + 4);
      *v60 = v60;
      v37[2] = v36;
      v37[3] = 4096;
      *((_DWORD *)v37 + 2) = v35;
    }
    else
    {
      v38 = 0;
    }
  }
  else
  {
    v38 = qword_1836E8C98(a1 + v9, qword_1836E8C98, v14);
  }
  *(_QWORD *)(v8 + 8 * v12) = v38;
  *(_QWORD *)(v8 + 8 * v12 + 80) = a1;
  *(_QWORD *)(v8 + 8 * v12 + 120) = v11;
  *(_QWORD *)(v8 + 8 * v12 + 160) = 1;
  if ( v38 )
  {
    ++*(_DWORD *)(v8 + 200);
    if ( dword_1836E121C == 1 )
    {
      mkl_serv_lock(&unk_1836E8D04);
      if ( dword_1836E121C == 1 )
      {
        v41 = v11 + qword_1836E8CC0;
        v42 = dword_1836E8CC8 + 1;
        qword_1836E8CC0 = v41;
        ++dword_1836E8CC8;
        if ( v41 > qword_1836E8CD0 )
        {
          qword_1836E8CD0 = v41;
          dword_1836E8CD8 = v42;
        }
      }
      mkl_serv_unlock(&unk_1836E8D04);
    }
    v39 = *(_QWORD *)(v8 + 8 * v12);
    v17 = v39 - ((unsigned int)v39 & ((_DWORD)v9 - 1));
    v40 = v17 + v9;
    if ( v17 != v39 )
      v17 = v40;
    *(_QWORD *)(v8 + 8 * v12 + 40) = v17;
  }
  else
  {
    v17 = *(_QWORD *)(v8 + 8 * v12 + 40);
  }
LABEL_34:
  v19 = *((int *)v7 - 2);
  if ( v19 <= 0 || v19 > 1024 )
    _InterlockedExchangeAdd(dword_1836D11C0, 0xFFFFFFFE);
  else
    dword_1836D11C0[16 * v19] = 0;
  return v17;
}

```

## disassembly

```asm
0x18003c0c0  push    rbx
0x18003c0c1  push    rsi
0x18003c0c2  push    rdi
0x18003c0c3  push    r12
0x18003c0c5  push    r13
0x18003c0c7  push    r14
0x18003c0c9  push    r15
0x18003c0cb  push    rbp
0x18003c0cc  sub     rsp, 298h
0x18003c0d3  mov     rbx, rcx
0x18003c0d6  mov     rax, cs:__security_cookie
0x18003c0dd  mov     r14d, edx
0x18003c0e0  xor     rax, rsp
0x18003c0e3  mov     [rsp+2D8h+var_50], rax
0x18003c0eb  cmp     rbx, 1
0x18003c0ef  jnb     short loc_18003C117
0x18003c0f1  mov     rcx, [rsp+2D8h+var_50]
0x18003c0f9  xor     rcx, rsp; StackCookie
0x18003c0fc  call    __security_check_cookie
0x18003c101  xor     eax, eax
0x18003c103  add     rsp, 298h
0x18003c10a  pop     rbp
0x18003c10b  pop     r15
0x18003c10d  pop     r14
0x18003c10f  pop     r13
0x18003c111  pop     r12
0x18003c113  pop     rdi
0x18003c114  pop     rsi
0x18003c115  pop     rbx
0x18003c116  retn
0x18003c117  mov     eax, cs:dword_1836E1210
0x18003c11d  cmp     eax, 0FFFFFFFFh
0x18003c120  jz      loc_18003CAC8
0x18003c126  cmp     cs:dword_1836E1214, 0FFFFFFFFh
0x18003c12d  jz      loc_18003CA15
0x18003c133  cmp     cs:dword_1836E1218, 0
0x18003c13a  jle     short loc_18003C171
0x18003c13c  mov     rcx, rbx
0x18003c13f  mov     edx, r14d
0x18003c142  call    mkl_serv_malloc
0x18003c147  mov     rbx, rax
0x18003c14a  mov     rcx, [rsp+2D8h+var_50]
0x18003c152  xor     rcx, rsp; StackCookie
0x18003c155  call    __security_check_cookie
0x18003c15a  mov     rax, rbx
0x18003c15d  add     rsp, 298h
0x18003c164  pop     rbp
0x18003c165  pop     r15
0x18003c167  pop     r14
0x18003c169  pop     r13
0x18003c16b  pop     r12
0x18003c16d  pop     rdi
0x18003c16e  pop     rsi
0x18003c16f  pop     rbx
0x18003c170  retn
0x18003c171  cmp     rbx, 8000000h
0x18003c178  ja      loc_18003C2F4
0x18003c17e  mov     eax, cs:dword_1836E8CBC
0x18003c184  test    al, 1
0x18003c186  jz      loc_18003C9AB
0x18003c18c  mov     eax, cs:dword_1836E8CBC
0x18003c192  test    al, 1
0x18003c194  jnz     short loc_18003C19A
0x18003c196  xor     eax, eax
0x18003c198  jmp     short loc_18003C1A6
0x18003c19a  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18003c1a0  call    cs:__imp_TlsGetValue
0x18003c1a6  mov     ecx, eax
0x18003c1a8  mov     edx, 1
0x18003c1ad  xor     r8d, r8d
0x18003c1b0  call    sub_18003D720
0x18003c1b5  mov     r13, rax
0x18003c1b8  test    r13, r13
0x18003c1bb  jz      loc_18003C976
0x18003c1c1  mov     r12, [r13+0]
0x18003c1c5  test    r12, r12
0x18003c1c8  jz      loc_18003C907
0x18003c1ce  cmp     r14d, 40h ; '@'
0x18003c1d2  jl      short loc_18003C1E9
0x18003c1d4  mov     r15d, r14d
0x18003c1d7  lea     eax, [r14-1]
0x18003c1db  mov     ebp, 40h ; '@'
0x18003c1e0  test    eax, r14d
0x18003c1e3  cmovnz  r15, rbp
0x18003c1e7  jmp     short loc_18003C1EF
0x18003c1e9  mov     r15d, 40h ; '@'
0x18003c1ef  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18003c1f6  lea     rsi, [rbx+r15]
0x18003c1fa  movsxd  rdi, dword ptr [r12+0C8h]
0x18003c202  mov     rbp, r9
0x18003c205  xor     r8d, r8d
0x18003c208  test    rdi, rdi
0x18003c20b  jle     loc_18003C6E9
0x18003c211  cmp     qword ptr [r12+r8*8+0A0h], 0
0x18003c21a  jnz     short loc_18003C250
0x18003c21c  mov     rax, [r12+r8*8+78h]
0x18003c221  cmp     rax, rsi
0x18003c224  jz      loc_18003C8D0
0x18003c22a  jbe     short loc_18003C245
0x18003c22c  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18003c230  jz      short loc_18003C240
0x18003c232  cmp     rax, [r12+r9*8+78h]
0x18003c237  movsxd  r10, r8d
0x18003c23a  cmovb   r9, r10
0x18003c23e  jmp     short loc_18003C250
0x18003c240  movsxd  r9, r8d
0x18003c243  jmp     short loc_18003C250
0x18003c245  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18003c249  movsxd  rax, r8d
0x18003c24c  cmovz   rbp, rax
0x18003c250  inc     r8
0x18003c253  cmp     r8, rdi
0x18003c256  jl      short loc_18003C211
0x18003c258  test    r9, r9
0x18003c25b  jl      loc_18003C329
0x18003c261  mov     [r12+r9*8+50h], rbx
0x18003c266  mov     ebx, r15d
0x18003c269  dec     ebx
0x18003c26b  mov     rdx, [r12+r9*8]
0x18003c26f  and     rbx, rdx
0x18003c272  neg     rbx
0x18003c275  add     rbx, rdx
0x18003c278  add     r15, rbx
0x18003c27b  cmp     rbx, rdx
0x18003c27e  mov     qword ptr [r12+r9*8+0A0h], 1
0x18003c28a  cmovnz  rbx, r15
0x18003c28e  mov     [r12+r9*8+28h], rbx
0x18003c293  movsxd  rcx, dword ptr [r13-8]
0x18003c297  test    rcx, rcx
0x18003c29a  jle     short loc_18003C2BD
0x18003c29c  cmp     rcx, 400h
0x18003c2a3  jg      short loc_18003C2BD
0x18003c2a5  shl     rcx, 6
0x18003c2a9  lea     rdx, cs:180000000h
0x18003c2b0  mov     rva dword_1836D11C0[rdx+rcx], 0
0x18003c2bb  jmp     short loc_18003C2CD
0x18003c2bd  lea     rdx, dword_1836D11C0
0x18003c2c4  mov     eax, 0FFFFFFFEh
0x18003c2c9  lock xadd [rdx], eax
0x18003c2cd  mov     rcx, [rsp+2D8h+var_50]
0x18003c2d5  xor     rcx, rsp; StackCookie
0x18003c2d8  call    __security_check_cookie
0x18003c2dd  mov     rax, rbx
0x18003c2e0  add     rsp, 298h
0x18003c2e7  pop     rbp
0x18003c2e8  pop     r15
0x18003c2ea  pop     r14
0x18003c2ec  pop     r13
0x18003c2ee  pop     r12
0x18003c2f0  pop     rdi
0x18003c2f1  pop     rsi
0x18003c2f2  pop     rbx
0x18003c2f3  retn
0x18003c2f4  mov     rcx, rbx
0x18003c2f7  mov     edx, r14d
0x18003c2fa  call    mkl_serv_malloc
0x18003c2ff  mov     rbx, rax
0x18003c302  mov     rcx, [rsp+2D8h+var_50]
0x18003c30a  xor     rcx, rsp; StackCookie
0x18003c30d  call    __security_check_cookie
0x18003c312  mov     rax, rbx
0x18003c315  add     rsp, 298h
0x18003c31c  pop     rbp
0x18003c31d  pop     r15
0x18003c31f  pop     r14
0x18003c321  pop     r13
0x18003c323  pop     r12
0x18003c325  pop     rdi
0x18003c326  pop     rsi
0x18003c327  pop     rbx
0x18003c328  retn
0x18003c329  cmp     rdi, 5
0x18003c32d  jl      loc_18003C6E9
0x18003c333  test    rbp, rbp
0x18003c336  jl      loc_18003C569
0x18003c33c  mov     r14, [r12+rbp*8]
0x18003c340  test    r14, r14
0x18003c343  jz      loc_18003C3FD
0x18003c349  mov     rdi, [r12+rbp*8+78h]
0x18003c34e  neg     rdi
0x18003c351  cmp     cs:dword_1836E121C, 1
0x18003c358  jz      loc_18003C688
0x18003c35e  lea     rax, sub_18003C000
0x18003c365  mov     rdx, cs:qword_1836E8CA0
0x18003c36c  cmp     rdx, rax
0x18003c36f  jnz     short loc_18003C3E3
0x18003c371  cmp     qword ptr [r14-20h], 0
0x18003c376  jz      short loc_18003C3E8
0x18003c378  mov     eax, cs:dword_1836E8CF0
0x18003c37e  test    eax, eax
0x18003c380  jz      short loc_18003C3D8
0x18003c382  mov     rdi, cs:qword_1836E1200
0x18003c389  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003c38d  jz      short loc_18003C3B2
0x18003c38f  test    rdi, rdi
0x18003c392  jz      short loc_18003C3D8
0x18003c394  lea     rcx, unk_1836E8CF4
0x18003c39b  call    mkl_serv_lock
0x18003c3a0  mov     rdi, cs:qword_1836E1200
0x18003c3a7  test    rdi, rdi
0x18003c3aa  mov     eax, cs:dword_1836E8CF0
0x18003c3b0  jbe     short loc_18003C3BD
0x18003c3b2  cmp     dword ptr [r14-18h], 1
0x18003c3b7  jz      loc_18003C5D8
0x18003c3bd  test    eax, eax
0x18003c3bf  jz      short loc_18003C3D8
0x18003c3c1  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003c3c5  jz      short loc_18003C3D8
0x18003c3c7  test    rdi, rdi
0x18003c3ca  jz      short loc_18003C3D8
0x18003c3cc  lea     rcx, unk_1836E8CF4
0x18003c3d3  call    mkl_serv_unlock
0x18003c3d8  mov     rcx, [r14-20h]; Block
0x18003c3dc  call    free_0
0x18003c3e1  jmp     short loc_18003C3E8
0x18003c3e3  mov     rcx, r14
0x18003c3e6  call    rdx ; qword_1836E8CA0
0x18003c3e8  xor     eax, eax
0x18003c3ea  mov     [r12+rbp*8+28h], rax
0x18003c3ef  mov     [r12+rbp*8], rax
0x18003c3f3  mov     [r12+rbp*8+78h], rax
0x18003c3f8  mov     [r12+rbp*8+50h], rax
0x18003c3fd  lea     rax, sub_18003BEE0
0x18003c404  mov     rdx, cs:qword_1836E8C98
0x18003c40b  cmp     rdx, rax
0x18003c40e  jnz     loc_18003C509
0x18003c414  mov     qword ptr [rsp+2D8h+var_2B8+8], 0
0x18003c41d  xor     edi, edi
0x18003c41f  mov     byte ptr [rsp+2D8h+var_2B8], 0
0x18003c424  lea     r14, [rbx+r15+20h]
0x18003c429  cmp     cs:dword_1836E8CF0, 0
0x18003c430  jz      short loc_18003C499
0x18003c432  mov     rax, cs:qword_1836E1200
0x18003c439  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c43d  jz      short loc_18003C459
0x18003c43f  test    rax, rax
0x18003c442  jz      short loc_18003C499
0x18003c444  lea     rcx, unk_1836E8CF4
0x18003c44b  call    mkl_serv_lock
0x18003c450  cmp     r14, cs:qword_1836E1200
0x18003c457  jnb     short loc_18003C499
0x18003c459  mov     byte ptr [rsp+2D8h+var_2B8], 1
0x18003c45e  lea     rcx, [rsp+2D8h+var_2B8+8]
0x18003c463  mov     edx, 200000h
0x18003c468  mov     r8, r14
0x18003c46b  mov     r9d, 2
0x18003c471  mov     edi, 1
0x18003c476  call    cs:qword_1836E8C68
0x18003c47c  test    eax, eax
0x18003c47e  jz      short loc_18003C4A6
0x18003c480  mov     rcx, r14
0x18003c483  call    cs:qword_1836E8C70
0x18003c489  mov     qword ptr [rsp+2D8h+var_2B8+8], rax
0x18003c48e  test    rax, rax
0x18003c491  jz      loc_18003C60E
0x18003c497  jmp     short loc_18003C4A6
0x18003c499  mov     rcx, r14; Size
0x18003c49c  call    malloc_0
0x18003c4a1  mov     qword ptr [rsp+2D8h+var_2B8+8], rax
0x18003c4a6  cmp     cs:dword_1836E8CF0, 0
0x18003c4ad  jz      short loc_18003C4E3
0x18003c4af  mov     rdx, cs:qword_1836E1200
0x18003c4b6  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18003c4ba  jz      short loc_18003C4E3
0x18003c4bc  test    rdx, rdx
0x18003c4bf  jz      short loc_18003C4E3
0x18003c4c1  mov     al, byte ptr [rsp+2D8h+var_2B8]
0x18003c4c5  test    al, al
0x18003c4c7  jz      short loc_18003C4D7
0x18003c4c9  sub     rdx, rsi
0x18003c4cc  add     rdx, 0FFFFFFFFFFFFFFE0h
0x18003c4d0  mov     cs:qword_1836E1200, rdx
0x18003c4d7  lea     rcx, unk_1836E8CF4
0x18003c4de  call    mkl_serv_unlock
0x18003c4e3  mov     rax, qword ptr [rsp+2D8h+var_2B8+8]
0x18003c4e8  test    rax, rax
0x18003c4eb  jz      short loc_18003C505
0x18003c4ed  lea     rdx, [rax+20h]
0x18003c4f1  mov     [rax], rax
0x18003c4f4  mov     [rdx-10h], r14
0x18003c4f8  mov     qword ptr [rdx-8], 1000h
0x18003c500  mov     [rdx-18h], edi
0x18003c503  jmp     short loc_18003C511
0x18003c505  xor     edx, edx
0x18003c507  jmp     short loc_18003C511
0x18003c509  mov     rcx, rsi
0x18003c50c  call    rdx ; qword_1836E8C98
0x18003c50e  mov     rdx, rax
0x18003c511  mov     [r12+rbp*8], rdx
0x18003c515  test    rdx, rdx
0x18003c518  mov     [r12+rbp*8+50h], rbx
0x18003c51d  mov     [r12+rbp*8+78h], rsi
0x18003c522  mov     qword ptr [r12+rbp*8+0A0h], 1
0x18003c52e  jz      short loc_18003C55F
0x18003c530  cmp     cs:dword_1836E121C, 1
0x18003c537  jz      loc_18003C627
0x18003c53d  mov     ebx, r15d
0x18003c540  dec     ebx
0x18003c542  and     rbx, rdx
0x18003c545  neg     rbx
  ... truncated ...
```
