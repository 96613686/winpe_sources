# mkl_serv_deallocate

- ea: `0x18003df30`
- end: `0x18003eb20`
- name: `mkl_serv_deallocate`
- size: `3056`
- prototype: ``
- caller_count: `53`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

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
- `0x180c56d80`
- `0x180cc07b0`
- `0x180feb890`
- `0x1811f1b90`
- `0x1811f1de0`
- `0x1811f2030`
- `0x1811f6260`
- `0x1811f6d40`
- `0x1811f89e0`
- `0x1811f9ac0`
- `0x1811fb0f0`
- `0x1811fed70`
- `0x1812009a0`
- `0x181201470`
- `0x1812025a0`

## callees

- `0x18003d720`
- `0x18003df30`
- `0x18003eb20`
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
- `0x1832dbfe0`
- `0x1832dc0c0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003e958`
- `KERNEL32!GetProcAddress` at `0x18003e96f`
- `KERNEL32!GetProcAddress` at `0x18003e986`
- `KERNEL32!GetProcAddress` at `0x18003e958`
- `KERNEL32!GetProcAddress` at `0x18003e96f`
- `KERNEL32!GetProcAddress` at `0x18003e986`
- `KERNEL32!TlsAlloc` at `0x18003e623`
- `KERNEL32!TlsAlloc` at `0x18003e623`
- `KERNEL32!TlsGetValue` at `0x18003dfc8`
- `KERNEL32!TlsGetValue` at `0x18003dfc8`
- `KERNEL32!LoadLibraryA` at `0x18003e846`
- `KERNEL32!LoadLibraryA` at `0x18003e940`
- `KERNEL32!LoadLibraryA` at `0x18003e846`
- `KERNEL32!LoadLibraryA` at `0x18003e940`

## pseudocode

```c
void __fastcall mkl_serv_deallocate(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rsi
  __int64 v3; // r12
  unsigned int Value; // eax
  _QWORD *v6; // rax
  _QWORD *v7; // r15
  __int64 v8; // rbp
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // r10
  unsigned __int64 v12; // r9
  __int64 v13; // rbp
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r11
  unsigned __int64 v17; // r11
  unsigned __int64 v18; // r13
  __int64 v19; // r9
  unsigned __int64 v20; // rsi
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // rax
  __int64 v24; // rbp
  __int64 v25; // r10
  __int64 v26; // rcx
  _QWORD *v27; // rbp
  __int64 v28; // rdx
  int v29; // r8d
  __int64 v30; // rdx
  __int64 v31; // rdi
  __int64 v32; // r14
  char v33; // r13
  int v34; // r15d
  __int64 v35; // rdx
  __int64 v36; // rbx
  __int64 v37; // rsi
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdi
  __int64 v41; // rdx
  void (__fastcall *v42)(_QWORD); // rdx
  bool v43; // zf
  __int64 v44; // rdi
  void *v45; // rcx
  int v46; // eax
  __int64 v47; // r8
  int v48; // edx
  __int64 v49; // rax
  __int64 v50; // rdx
  unsigned __int64 v51; // rax
  int v52; // edx
  int v53; // eax
  int v54; // eax
  __int64 v55; // rdx
  char *v56; // r13
  __int64 v57; // rax
  __int64 v58; // rbp
  char v59; // al
  HMODULE LibraryA; // rbp
  __int64 v61; // r14
  __int64 v62; // rax
  __int64 v63; // rbp
  char v64; // al
  FARPROC ProcAddress; // rax
  int v66; // eax
  int v67; // eax
  __int64 v68; // [rsp+20h] [rbp-2A8h]
  __int64 v69; // [rsp+28h] [rbp-2A0h]
  char v70[16]; // [rsp+30h] [rbp-298h] BYREF
  _OWORD v71[2]; // [rsp+40h] [rbp-288h]
  CHAR v72[256]; // [rsp+60h] [rbp-268h] BYREF
  __int128 v73; // [rsp+160h] [rbp-168h]
  CHAR LibFileName[256]; // [rsp+170h] [rbp-158h] BYREF
  int v75; // [rsp+270h] [rbp-58h]
  char String[36]; // [rsp+274h] [rbp-54h] BYREF

  if ( !a1 )
    return;
  if ( dword_1836E1210 != -1 )
    goto LABEL_3;
  mkl_serv_lock(&unk_1836E8CFC);
  if ( dword_1836E1210 == -1 )
  {
    mkl_serv_lock(&unk_1836E8D00);
    if ( dword_1836E1214 == -1 )
    {
      dword_1836E1218 = (int)mkl_serv_getenv("MKL_DISABLE_FAST_MM", &v70[8], 32) > 0;
      if ( (int)mkl_serv_getenv("MKL_FAST_MEMORY_LIMIT", &v70[8], 32) > 0 )
      {
        v67 = atol_0(&v70[8]);
        if ( v67 < 0 )
          qword_1836E1200 = -1;
        else
          qword_1836E1200 = (__int64)v67 << 20;
      }
      dword_1836E1214 = 1;
    }
    mkl_serv_unlock(&unk_1836E8D00);
    v55 = 0x708000000LL;
    while ( (v55 & _intel_mkl_feature_indicator_x) != v55 )
    {
      if ( _intel_mkl_feature_indicator_x )
        goto LABEL_149;
      _intel_mkl_features_init_x();
    }
    v56 = off_1836E1208;
    v57 = 256;
    v75 = _mm_cvtsi128_si32((__m128i)0LL);
    do
    {
      *(_OWORD *)&LibFileName[v57 - 16] = 0;
      *(_OWORD *)&v72[v57 + 240] = 0;
      *(_OWORD *)&v72[v57 + 224] = 0;
      *(_OWORD *)&v72[v57 + 208] = 0;
      v57 -= 64;
    }
    while ( v57 );
    v58 = 0;
    if ( mkl_serv_strnlen_s(v56, 260) )
    {
      while ( 1 )
      {
        v59 = v56[v58];
        if ( v59 == 47 || v59 == 92 )
          break;
        if ( ++v58 >= (unsigned __int64)mkl_serv_strnlen_s(v56, 260) )
          goto LABEL_134;
      }
      LibraryA = 0;
    }
    else
    {
LABEL_134:
      mkl_serv_strncpy_s(LibFileName, 260, byte_1836E8A40, 260);
      mkl_serv_strncat_s(LibFileName, 260, v56, 260);
      LibraryA = LoadLibraryA(LibFileName);
      if ( LibraryA )
      {
LABEL_144:
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
              v66 = 1;
              goto LABEL_150;
            }
          }
        }
LABEL_149:
        v66 = 0;
LABEL_150:
        dword_1836E8CF0 = v66;
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
        goto LABEL_124;
      }
    }
    v61 = mkl_serv_strnlen_s(byte_1836E8A40, 260);
    if ( v61 != mkl_serv_strnlen_s(byte_1836E8B60, 260) || strncmp_0(byte_1836E8A40, byte_1836E8B60, 0x104u) )
    {
      v62 = 16;
      LODWORD(v73) = _mm_cvtsi128_si32((__m128i)0LL);
      do
      {
        v71[v62 + 1] = 0;
        v71[v62] = 0;
        *(_OWORD *)&v70[v62 * 16] = 0;
        *(_OWORD *)((char *)&v68 + v62 * 16) = 0;
        v62 -= 4;
      }
      while ( v62 * 16 );
      v63 = 0;
      if ( mkl_serv_strnlen_s(v56, 260) )
      {
        while ( 1 )
        {
          v64 = v56[v63];
          if ( v64 == 47 || v64 == 92 )
            break;
          if ( ++v63 >= (unsigned __int64)mkl_serv_strnlen_s(v56, 260) )
            goto LABEL_143;
        }
        LibraryA = 0;
      }
      else
      {
LABEL_143:
        mkl_serv_strncpy_s(v72, 260, byte_1836E8B60, 260);
        mkl_serv_strncat_s(v72, 260, v56, 260);
        LibraryA = LoadLibraryA(v72);
      }
    }
    goto LABEL_144;
  }
LABEL_124:
  mkl_serv_unlock(&unk_1836E8CFC);
LABEL_3:
  if ( dword_1836E1214 == -1 )
  {
    mkl_serv_lock(&unk_1836E8D00);
    if ( dword_1836E1214 == -1 )
    {
      dword_1836E1218 = (int)mkl_serv_getenv("MKL_DISABLE_FAST_MM", String, 32) > 0;
      if ( (int)mkl_serv_getenv("MKL_FAST_MEMORY_LIMIT", String, 32) > 0 )
      {
        v54 = atol_0(String);
        if ( v54 < 0 )
          qword_1836E1200 = -1;
        else
          qword_1836E1200 = (__int64)v54 << 20;
      }
      dword_1836E1214 = 1;
    }
    mkl_serv_unlock(&unk_1836E8D00);
  }
  if ( dword_1836E1218 > 0 )
  {
    mkl_serv_free(a1);
    return;
  }
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
  v6 = (_QWORD *)sub_18003D720(Value, 1, 0);
  v7 = v6;
  if ( v6 )
  {
    v8 = *v6;
    if ( *v6 )
    {
      v9 = 0;
      v10 = *(int *)(v8 + 200);
      if ( v10 > 0 )
      {
        while ( a1 != *(_QWORD *)(v8 + 8 * v9 + 40) )
        {
          if ( ++v9 >= v10 )
            goto LABEL_16;
        }
        *(_QWORD *)(v8 + 8 * v9 + 160) = 0;
        v53 = *((_DWORD *)v7 - 2);
        if ( v53 <= 0 || v53 > 1024 )
          _InterlockedExchangeAdd(dword_1836D11C0, 0xFFFFFFFE);
        else
          dword_1836D11C0[16 * (__int64)v53] = 0;
        return;
      }
    }
LABEL_16:
    v11 = qword_1836D1010[0];
    if ( qword_1836D1010[0] )
    {
      v12 = 0;
      v13 = 0;
      while ( 1 )
      {
        if ( v12 >= dword_1836D1008 )
        {
          v27 = 0;
          goto LABEL_36;
        }
        v14 = *(_QWORD *)(v13 + qword_1836D1010[0] + 8);
        if ( v14 )
        {
          v15 = 0;
          v16 = *(int *)(v14 + 200);
          if ( v16 > 0 )
            break;
        }
LABEL_23:
        ++v12;
        v13 += qword_1836D1000[0] + 8;
        if ( v12 >= 0x400 )
          goto LABEL_24;
      }
      while ( a1 != *(_QWORD *)(v14 + 8 * v15 + 40) )
      {
        if ( ++v15 >= v16 )
          goto LABEL_23;
      }
      *(_QWORD *)(v14 + 8 * v15 + 160) = 0;
      v27 = (_QWORD *)(v13 + v11 + 8);
    }
    else
    {
LABEL_24:
      v68 = v1;
      v17 = 1;
      v69 = v2;
      v18 = 1024;
      *(_QWORD *)v70 = v3;
      v19 = qword_1836D1000[0] + 8;
      while ( 1 )
      {
        v20 = 2 * v18;
        if ( qword_1836D1010[v17] )
        {
          v21 = v18 * v19;
          if ( v18 < v20 )
            break;
        }
LABEL_34:
        ++v17;
        v18 = v20;
        if ( v17 >= 0x36 )
          goto LABEL_35;
      }
      v22 = v19 * v18;
      while ( v18 < dword_1836D1008 )
      {
        v23 = qword_1836D1010[v17] - v22;
        v24 = *(_QWORD *)(v23 + v21 + 8);
        if ( v24 )
        {
          v25 = 0;
          v26 = *(int *)(v24 + 200);
          if ( v26 > 0 )
          {
            while ( a1 != *(_QWORD *)(v24 + 8 * v25 + 40) )
            {
              if ( ++v25 >= v26 )
                goto LABEL_33;
            }
            v2 = v69;
            v1 = v68;
            v3 = *(_QWORD *)v70;
            *(_QWORD *)(v24 + 8 * v25 + 160) = 0;
            v27 = (_QWORD *)(v21 + v23 + 8);
            goto LABEL_36;
          }
        }
LABEL_33:
        ++v18;
        v21 += qword_1836D1000[0] + 8;
        if ( v18 >= v20 )
          goto LABEL_34;
      }
LABEL_35:
      v1 = v68;
      v27 = 0;
      v2 = v69;
      v3 = *(_QWORD *)v70;
    }
LABEL_36:
    v28 = *((int *)v7 - 2);
    if ( v28 <= 0 || v28 > 1024 )
      _InterlockedExchangeAdd(dword_1836D11C0, 0xFFFFFFFE);
    else
      dword_1836D11C0[16 * v28] = 0;
    if ( !v27 )
    {
      mkl_serv_free(a1);
      return;
    }
    if ( *(_DWORD *)(*v27 + 216LL) )
    {
      while ( _InterlockedCompareExchange(dword_1836D11C0, 1, 0) )
        _mm_pause();
      v29 = 0;
      v30 = 0;
      do
      {
        while ( _InterlockedCompareExchange((volatile signed __int32 *)&qword_1836D1000[v30 + 64], 1, 0) )
          _mm_pause();
        ++v29;
        v30 += 8;
      }
      while ( v29 < 1024 );
      v31 = *v27;
      v32 = 0;
      v33 = 1;
      v34 = 0;
      v35 = *(int *)(*v27 + 200LL);
      if ( v35 > 0 )
      {
        v68 = v1;
        v36 = 0;
        v69 = v2;
        *(_QWORD *)v70 = v3;
        do
        {
          v37 = *(_QWORD *)(v31 + 8 * v36);
          if ( v37 )
          {
            if ( !*(_QWORD *)(v31 + 8 * v36 + 160) )
            {
              ++v34;
              v32 += *(_QWORD *)(v31 + 8 * v36 + 120);
              if ( (char *)qword_1836E8CA0 == (char *)sub_18003C000 )
              {
                if ( *(_QWORD *)(v37 - 32) )
                {
                  v38 = (unsigned int)dword_1836E8CF0;
                  if ( !dword_1836E8CF0 )
                    goto LABEL_66;
                  v39 = qword_1836E1200;
                  if ( qword_1836E1200 == -1 )
                    goto LABEL_61;
                  if ( !qword_1836E1200 )
                    goto LABEL_66;
                  mkl_serv_lock(&unk_1836E8CF4);
                  v39 = qword_1836E1200;
                  v38 = (unsigned int)dword_1836E8CF0;
                  if ( qword_1836E1200 )
                  {
LABEL_61:
                    if ( *(_DWORD *)(v37 - 24) != 1 )
                    {
                      if ( (_DWORD)v38 && v39 != -1 )
                        goto LABEL_64;
                      goto LABEL_66;
                    }
                    if ( (_DWORD)v38 && v39 != -1 )
                    {
                      qword_1836E1200 = v39 + *(_QWORD *)(v37 - 16);
                      mkl_serv_unlock(&unk_1836E8CF4);
                    }
                    qword_1836E8C78(*(_QWORD *)(v37 - 32), v38);
                  }
                  else
                  {
                    if ( !dword_1836E8CF0 )
                      goto LABEL_66;
LABEL_64:
                    if ( v39 )
                      mkl_serv_unlock(&unk_1836E8CF4);
LABEL_66:
                    free_0(*(void **)(v37 - 32));
                  }
                }
              }
              else
              {
                qword_1836E8CA0(*(_QWORD *)(v31 + 8 * v36));
              }
              *(_QWORD *)(v31 + 8 * v36 + 40) = 0;
              *(_QWORD *)(v31 + 8 * v36) = 0;
              *(_QWORD *)(v31 + 8 * v36 + 120) = 0;
              *(_QWORD *)(v31 + 8 * v36 + 80) = 0;
              v35 = *(int *)(v31 + 200);
              goto LABEL_69;
            }
            v33 = 0;
          }
LABEL_69:
          ++v36;
        }
        while ( v36 < v35 );
      }
      if ( dword_1836E121C == 1 )
      {
        mkl_serv_lock(&unk_1836E8D04);
        if ( dword_1836E121C == 1 )
        {
          v51 = qword_1836E8CC0 - v32;
          v52 = dword_1836E8CC8 - v34;
          qword_1836E8CC0 = v51;
          dword_1836E8CC8 -= v34;
          if ( v51 > qword_1836E8CD0 )
          {
            qword_1836E8CD0 = v51;
            dword_1836E8CD8 = v52;
          }
        }
        mkl_serv_unlock(&unk_1836E8D04);
      }
      if ( !v33 )
      {
LABEL_87:
        v48 = 0;
        v49 = 0;
        do
        {
          ++v48;
          dword_1836D1200[v49] = 0;
          v49 += 16;
        }
        while ( v48 < 1024 );
        _InterlockedExchangeAdd(dword_1836D11C0, 0xFFFFFFFF);
        return;
      }
      *(_DWORD *)(v31 + 200) = 0;
      v40 = *v27;
      mkl_serv_lock(&unk_1836E8D10);
      v41 = *(_QWORD *)(v40 + 208);
      dword_1836E8CE8 += *(_DWORD *)(v40 + 204);
      qword_1836E8CE0 += v41;
      mkl_serv_unlock(&unk_1836E8D10);
      v42 = (void (__fastcall *)(_QWORD))qword_1836E8C90;
      v43 = qword_1836E8C90 == (_QWORD)sub_18003C000;
      *(_QWORD *)(v40 + 208) = 0;
      *(_DWORD *)(v40 + 204) = 0;
      if ( !v43 )
      {
        v42(*v27);
        goto LABEL_86;
      }
      v44 = *v27;
      v45 = *(void **)(*v27 - 32LL);
      if ( !v45 )
      {
LABEL_86:
        *v27 = 0;
        goto LABEL_87;
      }
      v46 = dword_1836E8CF0;
      if ( dword_1836E8CF0 )
      {
        v47 = qword_1836E1200;
        if ( qword_1836E1200 == -1 )
          goto LABEL_78;
        if ( qword_1836E1200 )
        {
          mkl_serv_lock(&unk_1836E8CF4);
          v47 = qword_1836E1200;
          v46 = dword_1836E8CF0;
          if ( !qword_1836E1200 )
          {
LABEL_79:
            if ( v46 && v47 != -1 && v47 )
              mkl_serv_unlock(&unk_1836E8CF4);
            v45 = *(void **)(v44 - 32);
            goto LABEL_84;
          }
LABEL_78:
          if ( *(_DWORD *)(v44 - 24) == 1 )
          {
            v50 = -*(_QWORD *)(v44 - 16);
            if ( v46 && v47 != -1 )
            {
              qword_1836E1200 = v47 + *(_QWORD *)(v44 - 16);
              mkl_serv_unlock(&unk_1836E8CF4);
            }
            qword_1836E8C78(*(_QWORD *)(v44 - 32), v50);
            goto LABEL_86;
          }
          goto LABEL_79;
        }
      }
LABEL_84:
      free_0(v45);
      goto LABEL_86;
    }
  }
}

```

## disassembly

```asm
0x18003df30  push    rdi
0x18003df31  push    r13
0x18003df33  push    r14
0x18003df35  push    r15
0x18003df37  push    rbp
0x18003df38  sub     rsp, 2A0h
0x18003df3f  mov     rdi, rcx
0x18003df42  mov     rax, cs:__security_cookie
0x18003df49  xor     rax, rsp
0x18003df4c  mov     [rsp+2C8h+var_30], rax
0x18003df54  test    rdi, rdi
0x18003df57  jz      short loc_18003DF86
0x18003df59  mov     eax, cs:dword_1836E1210
0x18003df5f  cmp     eax, 0FFFFFFFFh
0x18003df62  jz      loc_18003E722
0x18003df68  cmp     cs:dword_1836E1214, 0FFFFFFFFh
0x18003df6f  jz      loc_18003E66E
0x18003df75  cmp     cs:dword_1836E1218, 0
0x18003df7c  jle     short loc_18003DFA6
0x18003df7e  mov     rcx, rdi
0x18003df81  call    mkl_serv_free
0x18003df86  mov     rcx, [rsp+2C8h+var_30]
0x18003df8e  xor     rcx, rsp; StackCookie
0x18003df91  call    __security_check_cookie
0x18003df96  add     rsp, 2A0h
0x18003df9d  pop     rbp
0x18003df9e  pop     r15
0x18003dfa0  pop     r14
0x18003dfa2  pop     r13
0x18003dfa4  pop     rdi
0x18003dfa5  retn
0x18003dfa6  mov     eax, cs:dword_1836E8CBC
0x18003dfac  test    al, 1
0x18003dfae  jz      loc_18003E603
0x18003dfb4  mov     eax, cs:dword_1836E8CBC
0x18003dfba  test    al, 1
0x18003dfbc  jnz     short loc_18003DFC2
0x18003dfbe  xor     eax, eax
0x18003dfc0  jmp     short loc_18003DFCE
0x18003dfc2  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18003dfc8  call    cs:__imp_TlsGetValue
0x18003dfce  mov     ecx, eax
0x18003dfd0  mov     edx, 1
0x18003dfd5  xor     r8d, r8d
0x18003dfd8  call    sub_18003D720
0x18003dfdd  mov     r15, rax
0x18003dfe0  test    r15, r15
0x18003dfe3  jz      short loc_18003DF86
0x18003dfe5  mov     rbp, [r15]
0x18003dfe8  test    rbp, rbp
0x18003dfeb  jz      short loc_18003E00E
0x18003dfed  xor     edx, edx
0x18003dfef  movsxd  rax, dword ptr [rbp+0C8h]
0x18003dff6  test    rax, rax
0x18003dff9  jle     short loc_18003E00E
0x18003dffb  cmp     rdi, [rbp+rdx*8+28h]
0x18003e000  jz      loc_18003E59D
0x18003e006  inc     rdx
0x18003e009  cmp     rdx, rax
0x18003e00c  jl      short loc_18003DFFB
0x18003e00e  mov     r10, cs:qword_1836D1010
0x18003e015  test    r10, r10
0x18003e018  movsxd  r8, cs:dword_1836D1008
0x18003e01f  mov     r14, cs:qword_1836D1000
0x18003e026  jz      short loc_18003E072
0x18003e028  xor     r9d, r9d
0x18003e02b  xor     ebp, ebp
0x18003e02d  cmp     r9, r8
0x18003e030  jnb     loc_18003E596
0x18003e036  mov     rdx, [rbp+r10+8]
0x18003e03b  test    rdx, rdx
0x18003e03e  jz      short loc_18003E061
0x18003e040  xor     eax, eax
0x18003e042  movsxd  r11, dword ptr [rdx+0C8h]
0x18003e049  test    r11, r11
0x18003e04c  jle     short loc_18003E061
0x18003e04e  cmp     rdi, [rdx+rax*8+28h]
0x18003e053  jz      loc_18003E580
0x18003e059  inc     rax
0x18003e05c  cmp     rax, r11
0x18003e05f  jl      short loc_18003E04E
0x18003e061  inc     r9
0x18003e064  lea     rbp, [rbp+r14+8]
0x18003e069  cmp     r9, 400h
0x18003e070  jb      short loc_18003E02D
0x18003e072  mov     qword ptr [rsp+2C8h+var_2A8], rbx
0x18003e077  mov     r11d, 1
0x18003e07d  mov     qword ptr [rsp+2C8h+var_2A8+8], rsi
0x18003e082  mov     r13d, 400h
0x18003e088  mov     qword ptr [rsp+2C8h+var_298], r12
0x18003e08d  lea     r9, [r14+8]
0x18003e091  lea     r12, cs:180000000h
0x18003e098  cmp     rva qword_1836D1010[r12+r11*8], 0
0x18003e0a1  lea     rsi, [r13+r13+0]
0x18003e0a6  jz      short loc_18003E107
0x18003e0a8  mov     rdx, r9
0x18003e0ab  imul    rdx, r13
0x18003e0af  cmp     r13, rsi
0x18003e0b2  jnb     short loc_18003E107
0x18003e0b4  mov     rbx, r13
0x18003e0b7  imul    rbx, r9
0x18003e0bb  cmp     r13, r8
0x18003e0be  jnb     short loc_18003E117
0x18003e0c0  mov     rax, rva qword_1836D1010[r12+r11*8]
0x18003e0c8  sub     rax, rbx
0x18003e0cb  mov     rbp, [rax+rdx+8]
0x18003e0d0  test    rbp, rbp
0x18003e0d3  jz      short loc_18003E0F7
0x18003e0d5  xor     r10d, r10d
0x18003e0d8  movsxd  rcx, dword ptr [rbp+0C8h]
0x18003e0df  test    rcx, rcx
0x18003e0e2  jle     short loc_18003E0F7
0x18003e0e4  cmp     rdi, [rbp+r10*8+28h]
0x18003e0e9  jz      loc_18003E55B
0x18003e0ef  inc     r10
0x18003e0f2  cmp     r10, rcx
0x18003e0f5  jl      short loc_18003E0E4
0x18003e0f7  nop     dword ptr [rax]
0x18003e0fa  inc     r13
0x18003e0fd  lea     rdx, [rdx+r14+8]
0x18003e102  cmp     r13, rsi
0x18003e105  jb      short loc_18003E0BB
0x18003e107  nop     dword ptr [rax+00h]
0x18003e10b  inc     r11
0x18003e10e  mov     r13, rsi
0x18003e111  cmp     r11, 36h ; '6'
0x18003e115  jb      short loc_18003E098
0x18003e117  mov     rbx, qword ptr [rsp+2C8h+var_2A8]
0x18003e11c  xor     ebp, ebp
0x18003e11e  mov     rsi, qword ptr [rsp+2C8h+var_2A8+8]
0x18003e123  mov     r12, qword ptr [rsp+2C8h+var_298]
0x18003e128  movsxd  rdx, dword ptr [r15-8]
0x18003e12c  test    rdx, rdx
0x18003e12f  jle     short loc_18003E152
0x18003e131  cmp     rdx, 400h
0x18003e138  jg      short loc_18003E152
0x18003e13a  shl     rdx, 6
0x18003e13e  lea     rax, cs:180000000h
0x18003e145  mov     rva dword_1836D11C0[rax+rdx], 0
0x18003e150  jmp     short loc_18003E162
0x18003e152  lea     rdx, dword_1836D11C0
0x18003e159  mov     eax, 0FFFFFFFEh
0x18003e15e  lock xadd [rdx], eax
0x18003e162  test    rbp, rbp
0x18003e165  jz      loc_18003E533
0x18003e16b  mov     rax, [rbp+0]
0x18003e16f  cmp     dword ptr [rax+0D8h], 0
0x18003e176  jz      loc_18003E446
0x18003e17c  lea     rdi, dword_1836D11C0
0x18003e183  mov     ecx, 1
0x18003e188  xor     eax, eax
0x18003e18a  lock cmpxchg [rdi], ecx
0x18003e18e  test    eax, eax
0x18003e190  jz      short loc_18003E1AA
0x18003e192  pause
0x18003e194  lea     rdi, dword_1836D11C0
0x18003e19b  mov     ecx, 1
0x18003e1a0  xor     eax, eax
0x18003e1a2  lock cmpxchg [rdi], ecx
0x18003e1a6  test    eax, eax
0x18003e1a8  jnz     short loc_18003E192
0x18003e1aa  xor     r8d, r8d
0x18003e1ad  xor     edx, edx
0x18003e1af  lea     r9, qword_1836D1000
0x18003e1b6  mov     ecx, 1
0x18003e1bb  xor     eax, eax
0x18003e1bd  lea     rdi, [r9+rdx+200h]
0x18003e1c5  lock cmpxchg [rdi], ecx
0x18003e1c9  test    eax, eax
0x18003e1cb  jz      short loc_18003E1DE
0x18003e1cd  pause
0x18003e1cf  mov     ecx, 1
0x18003e1d4  xor     eax, eax
0x18003e1d6  lock cmpxchg [rdi], ecx
0x18003e1da  test    eax, eax
0x18003e1dc  jnz     short loc_18003E1CD
0x18003e1de  inc     r8d
0x18003e1e1  add     rdx, 40h ; '@'
0x18003e1e5  cmp     r8d, 400h
0x18003e1ec  jl      short loc_18003E1AF
0x18003e1ee  mov     rdi, [rbp+0]
0x18003e1f2  xor     r14d, r14d
0x18003e1f5  mov     r13b, 1
0x18003e1f8  xor     r15d, r15d
0x18003e1fb  xor     eax, eax
0x18003e1fd  movsxd  rdx, dword ptr [rdi+0C8h]
0x18003e204  test    rdx, rdx
0x18003e207  jle     loc_18003E30F
0x18003e20d  mov     qword ptr [rsp+2C8h+var_2A8], rbx
0x18003e212  mov     rbx, rax
0x18003e215  mov     qword ptr [rsp+2C8h+var_2A8+8], rsi
0x18003e21a  mov     qword ptr [rsp+2C8h+var_298], r12
0x18003e21f  mov     rsi, [rdi+rbx*8]
0x18003e223  test    rsi, rsi
0x18003e226  jz      loc_18003E2F4
0x18003e22c  cmp     qword ptr [rdi+rbx*8+0A0h], 0
0x18003e235  jz      short loc_18003E23F
0x18003e237  xor     r13b, r13b
0x18003e23a  jmp     loc_18003E2F4
0x18003e23f  lea     rdx, sub_18003C000
0x18003e246  inc     r15d
0x18003e249  add     r14, [rdi+rbx*8+78h]
0x18003e24e  mov     r8, cs:qword_1836E8CA0
0x18003e255  cmp     r8, rdx
0x18003e258  jnz     short loc_18003E2D1
0x18003e25a  cmp     qword ptr [rsi-20h], 0
0x18003e25f  jz      short loc_18003E2D8
0x18003e261  mov     edx, cs:dword_1836E8CF0
0x18003e267  test    edx, edx
0x18003e269  jz      short loc_18003E2C6
0x18003e26b  mov     r8, cs:qword_1836E1200
0x18003e272  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003e276  jz      short loc_18003E2A1
0x18003e278  test    r8, r8
0x18003e27b  jz      short loc_18003E2C6
0x18003e27d  lea     rcx, unk_1836E8CF4
0x18003e284  call    mkl_serv_lock
0x18003e289  mov     r8, cs:qword_1836E1200
0x18003e290  test    r8, r8
0x18003e293  mov     edx, cs:dword_1836E8CF0
0x18003e299  ja      short loc_18003E2A1
0x18003e29b  test    edx, edx
0x18003e29d  jnz     short loc_18003E2B5
0x18003e29f  jmp     short loc_18003E2C6
0x18003e2a1  cmp     dword ptr [rsi-18h], 1
0x18003e2a5  jz      loc_18003E466
0x18003e2ab  test    edx, edx
0x18003e2ad  jz      short loc_18003E2C6
0x18003e2af  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003e2b3  jz      short loc_18003E2C6
0x18003e2b5  test    r8, r8
0x18003e2b8  jz      short loc_18003E2C6
0x18003e2ba  lea     rcx, unk_1836E8CF4
0x18003e2c1  call    mkl_serv_unlock
0x18003e2c6  mov     rcx, [rsi-20h]; Block
0x18003e2ca  call    free_0
0x18003e2cf  jmp     short loc_18003E2D8
0x18003e2d1  mov     rcx, [rdi+rbx*8]
0x18003e2d5  call    r8 ; qword_1836E8CA0
0x18003e2d8  xor     edx, edx
0x18003e2da  mov     [rdi+rbx*8+28h], rdx
0x18003e2df  mov     [rdi+rbx*8], rdx
0x18003e2e3  mov     [rdi+rbx*8+78h], rdx
0x18003e2e8  mov     [rdi+rbx*8+50h], rdx
0x18003e2ed  movsxd  rdx, dword ptr [rdi+0C8h]
0x18003e2f4  inc     rbx
0x18003e2f7  cmp     rbx, rdx
0x18003e2fa  jl      loc_18003E21F
0x18003e300  mov     rbx, qword ptr [rsp+2C8h+var_2A8]
0x18003e305  mov     rsi, qword ptr [rsp+2C8h+var_2A8+8]
0x18003e30a  mov     r12, qword ptr [rsp+2C8h+var_298]
0x18003e30f  cmp     cs:dword_1836E121C, 1
0x18003e316  jz      loc_18003E4D4
0x18003e31c  test    r13b, r13b
0x18003e31f  jz      loc_18003E412
0x18003e325  mov     dword ptr [rdi+0C8h], 0
0x18003e32f  lea     rcx, unk_1836E8D10
0x18003e336  mov     rdi, [rbp+0]
0x18003e33a  call    mkl_serv_lock
0x18003e33f  lea     rcx, unk_1836E8D10
0x18003e346  mov     eax, [rdi+0CCh]
0x18003e34c  mov     rdx, [rdi+0D0h]
0x18003e353  add     cs:dword_1836E8CE8, eax
0x18003e359  add     cs:qword_1836E8CE0, rdx
0x18003e360  call    mkl_serv_unlock
0x18003e365  lea     rax, sub_18003C000
0x18003e36c  mov     rdx, cs:qword_1836E8C90
0x18003e373  cmp     rdx, rax
0x18003e376  mov     qword ptr [rdi+0D0h], 0
0x18003e381  mov     dword ptr [rdi+0CCh], 0
0x18003e38b  jnz     short loc_18003E404
0x18003e38d  mov     rdi, [rbp+0]
0x18003e391  mov     rcx, [rdi-20h]
0x18003e395  test    rcx, rcx
0x18003e398  jz      short loc_18003E40A
0x18003e39a  mov     eax, cs:dword_1836E8CF0
0x18003e3a0  test    eax, eax
0x18003e3a2  jz      short loc_18003E3FD
0x18003e3a4  mov     r8, cs:qword_1836E1200
0x18003e3ab  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003e3af  jz      short loc_18003E3D4
0x18003e3b1  test    r8, r8
0x18003e3b4  jz      short loc_18003E3FD
0x18003e3b6  lea     rcx, unk_1836E8CF4
0x18003e3bd  call    mkl_serv_lock
0x18003e3c2  mov     r8, cs:qword_1836E1200
0x18003e3c9  test    r8, r8
0x18003e3cc  mov     eax, cs:dword_1836E8CF0
0x18003e3d2  jbe     short loc_18003E3DE
0x18003e3d4  cmp     dword ptr [rdi-18h], 1
0x18003e3d8  jz      loc_18003E49D
0x18003e3de  test    eax, eax
0x18003e3e0  jz      short loc_18003E3F9
0x18003e3e2  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003e3e6  jz      short loc_18003E3F9
0x18003e3e8  test    r8, r8
0x18003e3eb  jz      short loc_18003E3F9
0x18003e3ed  lea     rcx, unk_1836E8CF4
0x18003e3f4  call    mkl_serv_unlock
0x18003e3f9  mov     rcx, [rdi-20h]; Block
  ... truncated ...
```
