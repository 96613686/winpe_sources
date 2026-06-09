# CryptXmlDigestReference

- ea: `0x1800057a0`
- end: `0x180006149`
- name: `CryptXmlDigestReference`
- size: `2473`
- prototype: `HRESULT __stdcall(HCRYPTXML hReference, DWORD dwFlags, CRYPT_XML_DATA_PROVIDER *pDataProviderIn)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800094a0`
- `0x18000b3b0`

## callees

- `0x1800057a0`
- `0x1800070d0`
- `0x18000f200`
- `0x180010da0`
- `0x180014ce0`
- `0x180018601`
- `0x180018625`
- `0x180018640`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005e3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005e54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005e54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005939`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005939`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800059d5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005a86`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005c3c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800059d5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005a86`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005c3c`

## string_xrefs

- `0x180005833`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x1800058a1`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005a0e`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005ad1`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005af4`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005d3e`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005def`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005e6d`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005ec7`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005f3d`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005f5e`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180005fb1`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x1800060be`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x1800060ee`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x18000610d`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x18000607b`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180005daf`: `http://www.w3.org/TR/2001/REC-xml-c14n-20010315`
- `0x180005cef`: `onecore\ds\security\cryptoapi\xml\lib\engine.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlDigestReference(
        HCRYPTXML hReference,
        DWORD dwFlags,
        CRYPT_XML_DATA_PROVIDER *pDataProviderIn)
{
  struct _CRYPT_XML_CRYPTOGRAPHIC_INTERFACE *v5; // r15
  void *v6; // rsi
  __int128 v7; // xmm1
  HRESULT TransformChainEngine; // ebx
  const char *v9; // rax
  void (*v10)(void); // rax
  _QWORD *i; // r14
  const char *v12; // r8
  int v13; // r9d
  void (__fastcall *v14)(HCRYPTXML); // rax
  HANDLE v15; // rax
  __int64 v17; // rsi
  unsigned int j; // ebx
  __int64 v19; // r15
  const char *v20; // r8
  char v21; // al
  const char *v22; // rdx
  bool v23; // zf
  unsigned int k; // ebx
  __int64 (__fastcall *fpCryptXmlCreateDigest)(__int64, char *, __int64 *); // rax
  const char *v26; // rax
  int v27; // r9d
  __int64 v28; // rax
  __int64 v29; // rsi
  unsigned int v30; // ebx
  __int64 v31; // rax
  struct _CRYPT_XML_TRANSFORM_CHAIN_CONFIG *v32; // r14
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  unsigned int m; // edx
  PCRYPT_XML_TRANSFORM_INFO v36; // r8
  PCNZWCH *v37; // r9
  PCNZWCH v38; // rcx
  int v39; // ebx
  __int64 n; // rsi
  PCRYPT_XML_TRANSFORM_INFO v41; // r8
  int cchCount2; // eax
  const WCHAR *wszAlgorithm; // r8
  __int64 v44; // r14
  __int64 v45; // rsi
  __int128 v46; // xmm1
  const char *v47; // rax
  int v48; // r9d
  void (__fastcall *v49)(__int64); // rax
  __int64 v50; // rcx
  const char *v51; // r8
  char v52; // al
  const char *v53; // rdx
  bool v54; // zf
  unsigned int v55; // r14d
  _WORD *v56; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v58; // rcx
  __int64 (__fastcall *v59)(__int64, void *, _QWORD, int *); // rax
  char v60; // al
  const char *v61; // rdx
  bool v62; // zf
  char v63; // al
  const char *v64; // rdx
  bool v65; // zf
  const char *v66; // r8
  char v67; // al
  const char *v68; // rdx
  bool v69; // zf
  int v70; // ebx
  __int64 v71; // rax
  unsigned int v72; // ecx
  const char *v73; // r8
  char v74; // cl
  const char *v75; // rdx
  bool v76; // zf
  const char *v77; // rax
  const char *v78; // rax
  ULONG cbBufferSize; // [rsp+38h] [rbp-D0h]
  int v80; // [rsp+3Ch] [rbp-CCh] BYREF
  __int64 v81; // [rsp+40h] [rbp-C8h]
  LPVOID v82; // [rsp+48h] [rbp-C0h]
  unsigned int v83; // [rsp+50h] [rbp-B8h]
  __int128 v84; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v85; // [rsp+68h] [rbp-A0h]
  __int64 v86; // [rsp+78h] [rbp-90h] BYREF
  __int64 v87; // [rsp+80h] [rbp-88h]
  __int128 v88; // [rsp+88h] [rbp-80h] BYREF
  __int128 v89; // [rsp+98h] [rbp-70h]
  PCNZWCH *v90; // [rsp+A8h] [rbp-60h]
  _QWORD v91[16]; // [rsp+B8h] [rbp-50h] BYREF

  LODWORD(v81) = dwFlags;
  v86 = 0;
  v80 = 0;
  v84 = 0;
  v85 = 0;
  if ( hReference && pDataProviderIn && pDataProviderIn->pfnRead )
  {
    v23 = *(_DWORD *)hReference == 1145324611;
    v5 = 0;
    v6 = 0;
    v7 = *(_OWORD *)&pDataProviderIn->pfnRead;
    v84 = *(_OWORD *)&pDataProviderIn->pvCallbackState;
    v85 = v7;
    if ( !v23 )
    {
      TransformChainEngine = -2146885370;
      v9 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885370, v9, 695);
      goto LABEL_15;
    }
    cbBufferSize = pDataProviderIn->cbBufferSize;
    v10 = (void (*)(void))*((_QWORD *)hReference + 15);
    if ( v10 )
      v10();
    for ( i = hReference; ; i = (_QWORD *)i[10] )
    {
      if ( !i )
      {
        TransformChainEngine = -2146885370;
        v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
        v13 = 706;
        goto LABEL_14;
      }
      if ( *(_DWORD *)i == 1145324609 )
        break;
    }
    if ( (*((_DWORD *)hReference + 18) & 4) != 0 )
    {
      TransformChainEngine = -2146885369;
      v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
      v13 = 713;
LABEL_14:
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", TransformChainEngine, v12, v13);
      goto LABEL_15;
    }
    v17 = *((_QWORD *)hReference + 17);
    if ( !dword_180022FC8 )
      LoadRegExtensions();
    for ( j = 0; ; ++j )
    {
      if ( j >= dword_180022FC0 )
      {
        for ( k = 0; k < 0x11; ++k )
        {
          if ( CompareStringW(0, 1u, *(PCNZWCH *)(v17 + 48), -1, off_180022188[9 * k], -1) == 2 )
          {
            v5 = &g_CryptXmlCNG;
            goto LABEL_44;
          }
        }
        v73 = "";
        v5 = 0;
        while ( 1 )
        {
          v74 = *(v73 - 1);
          v75 = v73--;
          v76 = v74 == 92;
          if ( v74 == 92 )
            break;
          if ( v73 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
          {
            v76 = v74 == 92;
            break;
          }
        }
        if ( v76 )
          v73 = v75;
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %S", -2146885372, v73, 1712, *(const wchar_t **)(v17 + 48));
        *((_DWORD *)hReference + 17) |= 4u;
        TransformChainEngine = -2146885372;
        v77 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885372, v77, 725);
        v6 = 0;
        goto LABEL_15;
      }
      v19 = 8LL * j;
      if ( CompareStringW(
             0,
             1u,
             *(PCNZWCH *)(v17 + 48),
             -1,
             *(PCNZWCH *)(*(_QWORD *)((char *)qword_180022FD8 + v19) + 8LL),
             -1) == 2 )
        break;
    }
    _mm_lfence();
    v5 = (struct _CRYPT_XML_CRYPTOGRAPHIC_INTERFACE *)(*(_QWORD *)((char *)qword_180022FD8 + v19) + 88LL);
    if ( !v5 )
    {
LABEL_32:
      TransformChainEngine = -2146885372;
      v20 = "";
      while ( 1 )
      {
        v21 = *(v20 - 1);
        v22 = v20--;
        v23 = v21 == 92;
        if ( v21 == 92 )
          break;
        if ( v20 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
        {
          v23 = v21 == 92;
          break;
        }
      }
      if ( v23 )
        v20 = v22;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885372, v20, 733);
      v6 = 0;
      goto LABEL_15;
    }
LABEL_44:
    fpCryptXmlCreateDigest = (__int64 (__fastcall *)(__int64, char *, __int64 *))v5->fpCryptXmlCreateDigest;
    if ( !fpCryptXmlCreateDigest )
      goto LABEL_32;
    TransformChainEngine = fpCryptXmlCreateDigest(*((_QWORD *)hReference + 17) + 40LL, (char *)hReference + 152, &v86);
    if ( TransformChainEngine < 0 )
    {
      v26 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
      v27 = 748;
      goto LABEL_96;
    }
    if ( *((_DWORD *)hReference + 38) > 0x80u )
    {
      TransformChainEngine = -2146885372;
      v26 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
      v27 = 755;
      goto LABEL_96;
    }
    if ( (v81 & 1) != 0 )
      goto LABEL_101;
    v28 = *((_QWORD *)hReference + 17);
    if ( *(_DWORD *)(v28 + 88) )
    {
      v84 = 0;
      v85 = 0;
      v29 = *(_QWORD *)(v28 + 96);
      v30 = *(_DWORD *)(v28 + 88);
      v31 = i[17];
      v87 = v29;
      LODWORD(v81) = v30;
      v32 = *(struct _CRYPT_XML_TRANSFORM_CHAIN_CONFIG **)(v31 + 16);
      memset_0(v91, 0, sizeof(v91));
      v33 = *(_OWORD *)&pDataProviderIn->pfnRead;
      v88 = 0;
      v89 = 0;
      v34 = *(_OWORD *)&pDataProviderIn->pvCallbackState;
      v85 = v33;
      v84 = v34;
      if ( v30 )
      {
        if ( !v32 )
          v32 = &g_CHAIN_CONFIG;
        if ( v30 > 0x10 )
        {
          TransformChainEngine = -2146885374;
LABEL_78:
          v47 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\engine.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", TransformChainEngine, v47, v48);
          v49 = (void (__fastcall *)(__int64))*((_QWORD *)&v89 + 1);
          if ( *((_QWORD *)&v89 + 1) )
          {
            v50 = v88;
            goto LABEL_82;
          }
          v49 = (void (__fastcall *)(__int64))*((_QWORD *)&v85 + 1);
          if ( *((_QWORD *)&v85 + 1) )
          {
            v50 = v84;
LABEL_82:
            v49(v50);
          }
          v51 = "";
          v84 = 0;
          v85 = 0;
          while ( 1 )
          {
            v52 = *(v51 - 1);
            v53 = v51--;
            v54 = v52 == 92;
            if ( v52 == 92 )
              break;
            if ( v51 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
            {
              v54 = v52 == 92;
              break;
            }
          }
          if ( v54 )
            v51 = v53;
          v27 = 777;
LABEL_97:
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", TransformChainEngine, v51, v27);
          v6 = 0;
          goto LABEL_15;
        }
        for ( m = 0; ; ++m )
        {
          v83 = m;
          if ( m >= v30 )
            break;
          v36 = 0;
          v37 = (PCNZWCH *)(v29 + 32LL * m + 8);
          v90 = v37;
          v38 = *v37;
          if ( *v37 )
          {
            v39 = 0;
            if ( *v38 )
            {
              do
              {
                if ( v38[v39] == 63 )
                  break;
                ++v39;
              }
              while ( v38[v39] );
            }
            for ( n = 0; (unsigned int)n < v32->cTransformInfo; n = (unsigned int)(n + 1) )
            {
              v41 = v32->rgpTransformInfo[n];
              cchCount2 = -1;
              v23 = (v41->dwFlags & 4) == 0;
              wszAlgorithm = v41->wszAlgorithm;
              if ( !v23 )
                cchCount2 = v39;
              if ( CompareStringW(0, 1u, wszAlgorithm, -1, *v37, cchCount2) == 2 )
              {
                v36 = v32->rgpTransformInfo[n];
                goto LABEL_70;
              }
              v37 = v90;
            }
            v36 = 0;
LABEL_70:
            m = v83;
            v29 = v87;
            v30 = v81;
          }
          v91[m] = v36;
          if ( !v36 )
          {
            TransformChainEngine = -2146885371;
            goto LABEL_78;
          }
        }
        v44 = v87;
        v45 = 0;
        while ( (unsigned int)v45 < v30 )
        {
          TransformChainEngine = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(v91[v45] + 24LL))(
                                   v44 + 32LL * (unsigned int)v45,
                                   &v84,
                                   &v88);
          if ( TransformChainEngine < 0 )
            goto LABEL_78;
          v30 = v81;
          v45 = (unsigned int)(v45 + 1);
          v46 = v89;
          v84 = v88;
          v88 = 0;
          v89 = 0;
          v85 = v46;
        }
      }
      v55 = cbBufferSize;
      if ( cbBufferSize < DWORD2(v84) )
        v55 = DWORD2(v84);
      goto LABEL_102;
    }
    v56 = *(_WORD **)(v28 + 24);
    if ( !v56 || *v56 != 35 )
    {
LABEL_101:
      v55 = cbBufferSize;
      goto LABEL_102;
    }
    *(_QWORD *)&v88 = 32;
    v89 = 0u;
    *((_QWORD *)&v88 + 1) = L"http://www.w3.org/TR/2001/REC-xml-c14n-20010315";
    v84 = 0;
    v85 = 0;
    TransformChainEngine = I_CreateTransformChainEngine(
                             0,
                             1,
                             (unsigned int)&v88,
                             (_DWORD)pDataProviderIn,
                             (__int64)&v84);
    if ( TransformChainEngine < 0 )
    {
      v26 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
      v27 = 814;
LABEL_96:
      v51 = v26;
      goto LABEL_97;
    }
    v55 = cbBufferSize;
    if ( cbBufferSize < DWORD2(v84) )
      v55 = DWORD2(v84);
LABEL_102:
    if ( v55 < 0x400 )
      v55 = 1024;
    ProcessHeap = GetProcessHeap();
    v82 = HeapAlloc(ProcessHeap, 8u, v55);
    v6 = v82;
    if ( !v82 )
    {
      TransformChainEngine = -2147024882;
      v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
      v13 = 834;
      goto LABEL_14;
    }
    *((_DWORD *)hReference + 18) &= ~8u;
    v58 = v84;
    v59 = (__int64 (__fastcall *)(__int64, void *, _QWORD, int *))v85;
    *((_DWORD *)hReference + 17) &= ~1u;
    *((_DWORD *)hReference + 18) |= 4u;
    v80 = 0;
    TransformChainEngine = v59(v58, v6, v55, &v80);
    if ( TransformChainEngine < 0 )
    {
      v12 = "";
      while ( 1 )
      {
        v60 = *(v12 - 1);
        v61 = v12--;
        v62 = v60 == 92;
        if ( v60 == 92 )
          break;
        if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
        {
          v62 = v60 == 92;
          break;
        }
      }
      if ( v62 )
        v12 = v61;
      v13 = 855;
      goto LABEL_14;
    }
    while ( v80 )
    {
      TransformChainEngine = ((__int64 (__fastcall *)(__int64, void *))v5->fpCryptXmlDigestData)(v86, v6);
      if ( TransformChainEngine < 0 )
      {
        v12 = "";
        while ( 1 )
        {
          v63 = *(v12 - 1);
          v64 = v12--;
          v65 = v63 == 92;
          if ( v63 == 92 )
            break;
          if ( v12 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
          {
            v65 = v63 == 92;
            break;
          }
        }
        if ( v65 )
          v12 = v64;
        v13 = 876;
        goto LABEL_14;
      }
      v80 = 0;
      TransformChainEngine = ((__int64 (__fastcall *)(_QWORD, void *, _QWORD, int *))v85)(v84, v6, v55, &v80);
      if ( TransformChainEngine < 0 )
      {
        v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
        v13 = 889;
        goto LABEL_14;
      }
    }
    TransformChainEngine = ((__int64 (__fastcall *)(__int64, char *, _QWORD))v5->fpCryptXmlFinalizeDigest)(
                             v86,
                             (char *)hReference + 156,
                             *((unsigned int *)hReference + 38));
    if ( TransformChainEngine >= 0 )
    {
      *((_DWORD *)hReference + 18) &= ~4u;
      *((_DWORD *)hReference + 17) &= ~2u;
      v70 = *((_DWORD *)hReference + 18);
      v71 = *((_QWORD *)hReference + 17);
      if ( v70 < 0 )
      {
        *(_QWORD *)(v71 + 80) = (char *)hReference + 156;
        TransformChainEngine = 0;
        v6 = v82;
        *(_DWORD *)(*((_QWORD *)hReference + 17) + 72LL) = *((_DWORD *)hReference + 38);
        *((_DWORD *)hReference + 18) |= 8u;
      }
      else
      {
        v72 = *((_DWORD *)hReference + 38);
        if ( *(_DWORD *)(v71 + 72) == v72 && !memcmp_0(*(const void **)(v71 + 80), (char *)hReference + 156, v72) )
        {
          v6 = v82;
          *((_DWORD *)hReference + 18) = v70 | 8;
          TransformChainEngine = 0;
        }
        else
        {
          *((_DWORD *)hReference + 17) |= 2u;
          TransformChainEngine = 0;
          v6 = v82;
        }
      }
    }
    else
    {
      v66 = "";
      while ( 1 )
      {
        v67 = *(v66 - 1);
        v68 = v66--;
        v69 = v67 == 92;
        if ( v67 == 92 )
          break;
        if ( v66 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
        {
          v69 = v67 == 92;
          break;
        }
      }
      if ( v69 )
        v66 = v68;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", TransformChainEngine, v66, 901);
      v6 = v82;
    }
LABEL_15:
    v14 = (void (__fastcall *)(HCRYPTXML))*((_QWORD *)hReference + 16);
    if ( v14 )
      v14(hReference);
  }
  else
  {
    v78 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
    TransformChainEngine = -2147024809;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v78, 686);
    v5 = 0;
    v6 = 0;
    if ( hReference )
      goto LABEL_15;
  }
  if ( v86 && v5 )
    ((void (*)(void))v5->fpCryptXmlCloseDigest)();
  if ( v6 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 8u, v6);
  }
  if ( *((_QWORD *)&v85 + 1) )
    (*((void (__fastcall **)(_QWORD))&v85 + 1))(v84);
  return TransformChainEngine;
}

```

## disassembly

```asm
0x1800057a0  mov     r11, rsp
0x1800057a3  push    rbp
0x1800057a4  push    rbx
0x1800057a5  lea     rbp, [r11-78h]
0x1800057a9  sub     rsp, 168h
0x1800057b0  mov     rax, cs:__security_cookie
0x1800057b7  xor     rax, rsp
0x1800057ba  mov     [rbp+70h+var_40], rax
0x1800057be  mov     [r11+10h], rsi
0x1800057c2  xorps   xmm0, xmm0
0x1800057c5  mov     [r11-18h], rdi
0x1800057c9  mov     rdi, rcx
0x1800057cc  mov     [r11-20h], r12
0x1800057d0  xor     r12d, r12d
0x1800057d3  mov     [r11-28h], r13
0x1800057d7  mov     r13, r8
0x1800057da  mov     [r11-38h], r15
0x1800057de  mov     dword ptr [rsp+170h+var_138], edx
0x1800057e2  mov     [rsp+170h+var_100], r12
0x1800057e7  mov     [rsp+170h+var_13C], r12d
0x1800057ec  movups  [rsp+170h+var_128+8], xmm0
0x1800057f1  movups  [rsp+170h+var_118+8], xmm0
0x1800057f6  test    rcx, rcx
0x1800057f9  jz      loc_18000610D
0x1800057ff  test    r8, r8
0x180005802  jz      loc_18000610D
0x180005808  cmp     [r8+10h], r12
0x18000580c  jz      loc_18000610D
0x180005812  cmp     dword ptr [rcx], 44444443h
0x180005818  mov     r15d, r12d
0x18000581b  movups  xmm0, xmmword ptr [r8]
0x18000581f  mov     esi, r12d
0x180005822  movups  xmm1, xmmword ptr [r8+10h]
0x180005827  movups  [rsp+170h+var_128+8], xmm0
0x18000582c  movups  [rsp+170h+var_118+8], xmm1
0x180005831  jz      short loc_18000585D
0x180005833  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000583a  mov     ebx, 80092106h
0x18000583f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180005844  mov     r8, rax
0x180005847  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000584e  mov     edx, ebx
0x180005850  mov     r9d, 2B7h
0x180005856  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000585b  jmp     short loc_1800058D1
0x18000585d  mov     eax, [r8+8]
0x180005861  mov     [rsp+170h+var_140], eax
0x180005865  mov     rax, [rcx+78h]
0x180005869  mov     [rsp+170h+var_28], r14
0x180005871  test    rax, rax
0x180005874  jz      short loc_18000587B
0x180005876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587b  mov     r14, rdi
0x18000587e  test    r14, r14
0x180005881  jz      loc_1800060EE
0x180005887  cmp     dword ptr [r14], 44444441h
0x18000588e  jz      short loc_180005896
0x180005890  mov     r14, [r14+50h]
0x180005894  jmp     short loc_18000587E
0x180005896  mov     eax, [rdi+48h]
0x180005899  test    al, 4
0x18000589b  jz      loc_18000597A
0x1800058a1  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800058a8  mov     ebx, 80092107h
0x1800058ad  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800058b2  mov     r8, rax
0x1800058b5  mov     r9d, 2C9h
0x1800058bb  mov     edx, ebx
0x1800058bd  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800058c4  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800058c9  mov     r14, [rsp+170h+var_28]
0x1800058d1  mov     rax, [rdi+80h]
0x1800058d8  test    rax, rax
0x1800058db  jz      short loc_1800058E5
0x1800058dd  mov     rcx, rdi
0x1800058e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e5  mov     rcx, [rsp+170h+var_100]
0x1800058ea  mov     r13, [rsp+170h+var_20]
0x1800058f2  mov     r12, [rsp+170h+var_18]
0x1800058fa  mov     rdi, [rsp+160h]
0x180005902  test    rcx, rcx
0x180005905  jz      short loc_180005915
0x180005907  test    r15, r15
0x18000590a  jz      short loc_180005915
0x18000590c  mov     rax, [r15+28h]
0x180005910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005915  mov     r15, [rsp+170h+var_30]
0x18000591d  test    rsi, rsi
0x180005920  jz      short loc_180005945
0x180005922  call    cs:__imp_GetProcessHeap
0x180005929  nop     dword ptr [rax+rax+00h]
0x18000592e  mov     r8, rsi; lpMem
0x180005931  mov     edx, 8; dwFlags
0x180005936  mov     rcx, rax; hHeap
0x180005939  call    cs:__imp_HeapFree
0x180005940  nop     dword ptr [rax+rax+00h]
0x180005945  mov     rax, [rsp+170h+var_108]
0x18000594a  mov     rsi, [rsp+170h+arg_8]
0x180005952  test    rax, rax
0x180005955  jz      short loc_180005961
0x180005957  mov     rcx, qword ptr [rsp+170h+var_128+8]
0x18000595c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005961  mov     eax, ebx
0x180005963  mov     rcx, [rbp+70h+var_40]
0x180005967  xor     rcx, rsp; StackCookie
0x18000596a  call    __security_check_cookie
0x18000596f  add     rsp, 168h
0x180005976  pop     rbx
0x180005977  pop     rbp
0x180005978  retn
0x18000597a  cmp     cs:dword_180022FC8, r12d
0x180005981  mov     rsi, [rdi+88h]
0x180005988  jnz     short loc_18000598F
0x18000598a  call    _LoadRegExtensions
0x18000598f  mov     ebx, r12d
0x180005992  cmp     ebx, cs:dword_180022FC0
0x180005998  jnb     loc_180005A4B
0x18000599e  mov     r8, [rsi+30h]; lpString1
0x1800059a2  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800059a8  mov     eax, ebx
0x1800059aa  mov     edx, 1; dwCmpFlags
0x1800059af  mov     [rsp+170h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800059b7  xor     ecx, ecx; Locale
0x1800059b9  lea     r15, ds:0[rax*8]
0x1800059c1  mov     rax, cs:qword_180022FD8
0x1800059c8  mov     rax, [r15+rax]
0x1800059cc  mov     rax, [rax+8]
0x1800059d0  mov     [rsp+170h+lpString2], rax; lpString2
0x1800059d5  call    cs:__imp_CompareStringW
0x1800059dc  nop     dword ptr [rax+rax+00h]
0x1800059e1  cmp     eax, 2
0x1800059e4  jz      short loc_1800059EA
0x1800059e6  inc     ebx
0x1800059e8  jmp     short loc_180005992
0x1800059ea  lfence
0x1800059ed  mov     rax, cs:qword_180022FD8
0x1800059f4  mov     r15, [r15+rax]
0x1800059f8  add     r15, 58h ; 'X'
0x1800059fc  jnz     loc_180005AA2
0x180005a02  mov     ebx, 80092104h
0x180005a07  lea     r8, aOnecoreDsSecur_14+33h; ""
0x180005a0e  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180005a15  movzx   eax, byte ptr [r8-1]
0x180005a1a  mov     rdx, r8
0x180005a1d  dec     r8
0x180005a20  cmp     al, 5Ch ; '\'
0x180005a22  jz      short loc_180005A2B
0x180005a24  cmp     r8, rcx
0x180005a27  ja      short loc_180005A15
0x180005a29  cmp     al, 5Ch ; '\'
0x180005a2b  cmovz   r8, rdx
0x180005a2f  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180005a36  mov     edx, ebx
0x180005a38  mov     r9d, 2DDh
0x180005a3e  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180005a43  mov     rsi, r12
0x180005a46  jmp     loc_1800058C9
0x180005a4b  mov     ebx, r12d
0x180005a4e  lea     r15, off_180022188; "http://www.w3.org/2000/09/xmldsig#sha1"
0x180005a55  cmp     ebx, 11h
0x180005a58  jnb     loc_18000606D
0x180005a5e  mov     r8, [rsi+30h]; lpString1
0x180005a62  mov     r9d, 0FFFFFFFFh; cchCount1
0x180005a68  mov     eax, ebx
0x180005a6a  mov     edx, 1; dwCmpFlags
0x180005a6f  mov     [rsp+170h+cchCount2], 0FFFFFFFFh; cchCount2
0x180005a77  xor     ecx, ecx; Locale
0x180005a79  lea     rax, [rax+rax*8]
0x180005a7d  mov     rax, [r15+rax*8]
0x180005a81  mov     [rsp+170h+lpString2], rax; lpString2
0x180005a86  call    cs:__imp_CompareStringW
0x180005a8d  nop     dword ptr [rax+rax+00h]
0x180005a92  cmp     eax, 2
0x180005a95  jz      short loc_180005A9B
0x180005a97  inc     ebx
0x180005a99  jmp     short loc_180005A55
0x180005a9b  lea     r15, ?g_CryptXmlCNG@@3U_CRYPT_XML_CRYPTOGRAPHIC_INTERFACE@@A; "H"
0x180005aa2  mov     rax, [r15+10h]
0x180005aa6  test    rax, rax
0x180005aa9  jz      loc_180005A02
0x180005aaf  mov     rcx, [rdi+88h]
0x180005ab6  lea     r8, [rsp+170h+var_100]
0x180005abb  add     rcx, 28h ; '('
0x180005abf  lea     rdx, [rdi+98h]
0x180005ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005acb  mov     ebx, eax
0x180005acd  test    eax, eax
0x180005acf  jns     short loc_180005AE8
0x180005ad1  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180005ad8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180005add  mov     r9d, 2ECh
0x180005ae3  jmp     loc_180005E01
0x180005ae8  cmp     dword ptr [rdi+98h], 80h
0x180005af2  jbe     short loc_180005B10
0x180005af4  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180005afb  mov     ebx, 80092104h
0x180005b00  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180005b05  mov     r9d, 2F3h
0x180005b0b  jmp     loc_180005E01
0x180005b10  mov     eax, dword ptr [rsp+170h+var_138]
0x180005b14  test    al, 1
0x180005b16  jnz     loc_180005E2C
0x180005b1c  mov     rax, [rdi+88h]
0x180005b23  cmp     [rax+58h], r12d
0x180005b27  jbe     loc_180005D89
0x180005b2d  xorps   xmm0, xmm0
0x180005b30  lea     rcx, [rbp+70h+var_C0]; void *
0x180005b34  movups  [rsp+170h+var_128+8], xmm0
0x180005b39  xor     edx, edx; Val
0x180005b3b  mov     r8d, 80h; Size
0x180005b41  movups  [rsp+170h+var_118+8], xmm0
0x180005b46  mov     rsi, [rax+60h]
0x180005b4a  mov     ebx, [rax+58h]
0x180005b4d  mov     rax, [r14+88h]
0x180005b54  mov     [rsp+170h+var_F8], rsi
0x180005b59  mov     dword ptr [rsp+170h+var_138], ebx
0x180005b5d  mov     r14, [rax+10h]
0x180005b61  call    memset_0
0x180005b66  xorps   xmm0, xmm0
0x180005b69  movups  xmm1, xmmword ptr [r13+10h]
0x180005b6e  movups  [rbp+70h+var_F0], xmm0
0x180005b72  movups  [rbp+70h+var_E0], xmm0
0x180005b76  movups  xmm0, xmmword ptr [r13+0]
0x180005b7b  movups  [rsp+170h+var_118+8], xmm1
0x180005b80  movups  [rsp+170h+var_128+8], xmm0
0x180005b85  test    ebx, ebx
0x180005b87  jz      loc_180005D6F
0x180005b8d  test    r14, r14
0x180005b90  jnz     short loc_180005B99
0x180005b92  lea     r14, ?g_CHAIN_CONFIG@@3U_CRYPT_XML_TRANSFORM_CHAIN_CONFIG@@A; _CRYPT_XML_TRANSFORM_CHAIN_CONFIG g_CHAIN_CONFIG
0x180005b99  cmp     ebx, 10h
0x180005b9c  jbe     short loc_180005BAE
0x180005b9e  mov     ebx, 80092102h
0x180005ba3  mov     r9d, 97h
0x180005ba9  jmp     loc_180005CEF
0x180005bae  xor     edx, edx
0x180005bb0  mov     dword ptr [rsp+170h+var_128], edx
0x180005bb4  cmp     edx, ebx
0x180005bb6  jnb     loc_180005C8F
0x180005bbc  mov     r9d, edx
0x180005bbf  xor     r8d, r8d
0x180005bc2  shl     r9, 5
0x180005bc6  add     r9, 8
0x180005bca  add     r9, rsi
0x180005bcd  mov     [rbp+70h+var_D0], r9
0x180005bd1  mov     rcx, [r9]
0x180005bd4  test    rcx, rcx
0x180005bd7  jz      loc_180005C6F
0x180005bdd  xor     ebx, ebx
0x180005bdf  cmp     [rcx], bx
0x180005be2  jz      short loc_180005BFA
0x180005be4  movsxd  rax, ebx
0x180005be7  cmp     word ptr [rcx+rax*2], 3Fh ; '?'
0x180005bec  jz      short loc_180005BFA
0x180005bee  inc     ebx
0x180005bf0  movsxd  rax, ebx
0x180005bf3  cmp     [rcx+rax*2], r8w
0x180005bf8  jnz     short loc_180005BE4
0x180005bfa  xor     esi, esi
0x180005bfc  cmp     esi, [r14+4]
0x180005c00  jnb     short loc_180005C5F
0x180005c02  mov     rax, [r14+8]
0x180005c06  lea     r13, ds:0[rsi*8]
0x180005c0e  mov     edx, 1; dwCmpFlags
0x180005c13  mov     r8, [rax+r13]
0x180005c17  mov     eax, 0FFFFFFFFh
0x180005c1c  test    byte ptr [r8+14h], 4
0x180005c21  mov     r8, [r8+8]; lpString1
0x180005c25  cmovnz  eax, ebx
0x180005c28  xor     ecx, ecx; Locale
0x180005c2a  mov     [rsp+170h+cchCount2], eax; cchCount2
0x180005c2e  mov     rax, [r9]
0x180005c31  mov     r9d, 0FFFFFFFFh; cchCount1
0x180005c37  mov     [rsp+170h+lpString2], rax; lpString2
0x180005c3c  call    cs:__imp_CompareStringW
0x180005c43  nop     dword ptr [rax+rax+00h]
0x180005c48  cmp     eax, 2
0x180005c4b  jz      short loc_180005C55
0x180005c4d  mov     r9, [rbp+70h+var_D0]
0x180005c51  inc     esi
0x180005c53  jmp     short loc_180005BFC
0x180005c55  mov     rax, [r14+8]
0x180005c59  mov     r8, [rax+r13]
0x180005c5d  jmp     short loc_180005C62
0x180005c5f  mov     r8, r12
0x180005c62  mov     edx, dword ptr [rsp+170h+var_128]
0x180005c66  mov     rsi, [rsp+170h+var_F8]
0x180005c6b  mov     ebx, dword ptr [rsp+170h+var_138]
0x180005c6f  mov     eax, edx
0x180005c71  mov     [rbp+rax*8+70h+var_C0], r8
0x180005c76  test    r8, r8
0x180005c79  jz      short loc_180005C82
0x180005c7b  inc     edx
0x180005c7d  jmp     loc_180005BB0
0x180005c82  mov     ebx, 80092105h
0x180005c87  mov     r9d, 0A9h
0x180005c8d  jmp     short loc_180005CEF
0x180005c8f  mov     r14, [rsp+170h+var_F8]
0x180005c94  xor     esi, esi
0x180005c96  cmp     esi, ebx
  ... truncated ...
```
