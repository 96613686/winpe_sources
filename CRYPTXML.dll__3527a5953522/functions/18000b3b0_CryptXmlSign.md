# CryptXmlSign

- ea: `0x18000b3b0`
- end: `0x18000c2be`
- name: `CryptXmlSign`
- size: `3854`
- prototype: `HRESULT __stdcall(HCRYPTXML hSignature, HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hKey, DWORD dwKeySpec, DWORD dwFlags, CRYPT_XML_KEYINFO_SPEC dwKeyInfoSpec, const void *pvKeyInfoSpec, const CRYPT_XML_ALGORITHM *pSignatureMethod, const CRYPT_XML_ALGORITHM *pCanonicalization)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800057a0`
- `0x180006da0`
- `0x1800070d0`
- `0x180009180`
- `0x180009310`
- `0x180009f80`
- `0x18000a310`
- `0x18000b1a0`
- `0x18000b3b0`
- `0x18000c2d0`
- `0x18000c990`
- `0x18000d1f0`
- `0x18000d500`
- `0x18000f200`
- `0x18000f7d0`
- `0x18000fe50`
- `0x180014ce0`
- `0x180014e14`
- `0x180015280`
- `0x180016820`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c25e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c28e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c1bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c25e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c28e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c275`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c1d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c275`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b555`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b5c3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b555`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b5c3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000b818`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000b818`

## string_xrefs

- `0x18000b613`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000c12c`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000b47d`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000b4bf`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000b6fd`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000b76e`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000b7a9`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000b7d0`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000b83e`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000b8d0`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000bb8e`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000bc51`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000bcc0`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000bd17`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000bdcf`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000be6e`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000be87`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000bec4`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000beed`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000bf74`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000bfa9`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000c046`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000c08b`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000c0c7`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000c0f1`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000c16a`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000c1e2`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000c1fb`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`
- `0x18000c214`: `onecore\ds\security\cryptoapi\xml\lib\signature.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlSign(
        HCRYPTXML hSignature,
        HCRYPTPROV_OR_NCRYPT_KEY_HANDLE hKey,
        DWORD dwKeySpec,
        DWORD dwFlags,
        CRYPT_XML_KEYINFO_SPEC dwKeyInfoSpec,
        const void *pvKeyInfoSpec,
        const CRYPT_XML_ALGORITHM *pSignatureMethod,
        const CRYPT_XML_ALGORITHM *pCanonicalization)
{
  _QWORD *v8; // rbx
  CRYPT_XML_ALGORITHM *v10; // r15
  const CRYPT_XML_ALGORITHM *v11; // rsi
  void (__fastcall *v12)(_QWORD *); // rax
  __int64 v13; // r12
  HRESULT CryptoInterface; // esi
  const char *v15; // rax
  const char *v16; // rax
  DWORD v17; // ebp
  unsigned int i; // edi
  __int64 v19; // rax
  __int64 v20; // r8
  unsigned int j; // edi
  __int64 v22; // rax
  int v23; // edi
  const char *v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  const char *v29; // r8
  char v30; // al
  const char *v31; // rdx
  bool v32; // zf
  int v33; // r9d
  int v34; // edx
  const char *v35; // rax
  const WCHAR **v36; // r14
  int v37; // eax
  const WCHAR *v38; // rcx
  unsigned int v39; // eax
  int v40; // r8d
  unsigned int v41; // ecx
  const WCHAR *v42; // rdx
  __int64 v43; // rsi
  const WCHAR *v44; // rax
  unsigned int v45; // ecx
  int v46; // ebp
  __int64 v47; // rdx
  __int64 v48; // rax
  const WCHAR *v49; // rcx
  unsigned int v50; // r10d
  const WCHAR *v51; // rcx
  __int64 v52; // rdx
  unsigned int k; // r11d
  __int64 v54; // rax
  __int64 v55; // r8
  __int64 v56; // r9
  unsigned int m; // r11d
  __int64 v58; // rax
  __int64 v59; // r8
  __int64 v60; // r9
  char v61; // al
  const char *v62; // rdx
  bool v63; // zf
  _OWORD *v64; // rax
  unsigned __int64 v65; // rdx
  char v66; // al
  const char *v67; // rdx
  bool v68; // zf
  __int64 v69; // r8
  int v70; // r14d
  __int64 n; // rdx
  int v72; // ecx
  char v73; // al
  const char *v74; // rdx
  bool v75; // zf
  char v76; // al
  const char *v77; // rdx
  bool v78; // zf
  __int64 ii; // rbp
  __int64 v80; // rcx
  __int64 v81; // rdx
  const WCHAR *v82; // rcx
  ULONG v83; // eax
  __int64 v84; // r8
  char v85; // al
  const char *v86; // rdx
  bool v87; // zf
  const WCHAR *HMACAlgName; // rax
  _DWORD *v89; // r14
  __int64 v90; // rbp
  char v91; // al
  const char *v92; // rdx
  bool v93; // zf
  __int64 (__fastcall *v94)(CRYPT_XML_ALGORITHM *, NCRYPT_HANDLE, _QWORD, _QWORD, _DWORD, __int64, int, __int64); // rax
  char v95; // al
  const char *v96; // rdx
  bool v97; // zf
  const char *v98; // r8
  char v99; // dl
  const char *v100; // r9
  bool v101; // zf
  void (__fastcall *v102)(_QWORD *); // rax
  HANDLE ProcessHeap; // rax
  const char *v104; // rax
  int v105; // r9d
  void *v106; // rbx
  HANDLE v107; // rax
  int v109; // [rsp+50h] [rbp-78h]
  LPVOID lpMem; // [rsp+60h] [rbp-68h] BYREF
  __int64 v111; // [rsp+68h] [rbp-60h] BYREF
  CRYPT_XML_DATA_PROVIDER pDataProviderIn; // [rsp+70h] [rbp-58h] BYREF
  __int64 dwFlagsa; // [rsp+D0h] [rbp+8h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+D8h] [rbp+10h]
  DWORD dwKeySpeca; // [rsp+E0h] [rbp+18h]

  dwKeySpeca = dwKeySpec;
  hObject = hKey;
  v8 = hSignature;
  v111 = 0;
  LODWORD(dwFlagsa) = 0;
  lpMem = 0;
  memset(&pDataProviderIn, 0, sizeof(pDataProviderIn));
  if ( !hSignature
    || (v10 = (CRYPT_XML_ALGORITHM *)pSignatureMethod) == 0
    || !pSignatureMethod->wszAlgorithm
    || (v11 = pCanonicalization) == 0
    || !pCanonicalization->wszAlgorithm )
  {
    CryptoInterface = -2147024809;
    v104 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
    v105 = 874;
    goto LABEL_194;
  }
  if ( *(_DWORD *)hSignature != 1145324610 )
  {
    CryptoInterface = -2146885370;
    v104 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
    v105 = 883;
LABEL_194:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", CryptoInterface, v104, v105);
    goto LABEL_195;
  }
  while ( 1 )
  {
    if ( !v8 )
    {
      CryptoInterface = -2146885370;
      v104 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v105 = 896;
      goto LABEL_194;
    }
    if ( *(_DWORD *)v8 == 1145324609 )
      break;
    v8 = (_QWORD *)v8[10];
  }
  v12 = (void (__fastcall *)(_QWORD *))v8[15];
  v13 = 0;
  if ( v12 )
    v12(v8);
  if ( *((int *)v8 + 18) < 0 )
  {
    if ( *(_DWORD *)(v8[17] + 24LL) != 1 )
    {
      CryptoInterface = -2146885369;
      v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885369, v16, 912);
      goto LABEL_187;
    }
    v17 = dwFlags | 0x10000000;
    if ( (*((_DWORD *)v8 + 15) & 0x10000000) == 0 )
      v17 = dwFlags;
    if ( !dword_180022FC8 )
      LoadRegExtensions();
    if ( (v17 & 0x10000000) == 0 )
    {
      for ( i = 0; i < dword_180022FC0; ++i )
      {
        v19 = *((_QWORD *)qword_180022FD8 + i);
        if ( *(_DWORD *)(v19 + 24) == 2 && CompareStringW(0, 1u, v10->wszAlgorithm, -1, *(PCNZWCH *)(v19 + 8), -1) == 2 )
          goto LABEL_34;
      }
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= 0x11 )
      {
        v98 = "";
        v23 = -2146885372;
        while ( 1 )
        {
          v99 = *(v98 - 1);
          v100 = v98--;
          v101 = v99 == 92;
          if ( v99 == 92 )
            break;
          if ( v98 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
          {
            v101 = v99 == 92;
            break;
          }
        }
        if ( v101 )
          v98 = v100;
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %S", -2146885372, v98, 1408, v10->wszAlgorithm);
        goto LABEL_184;
      }
      v22 = 9LL * j;
      if ( LODWORD(qword_180022180[v22 + 3]) == 2
        && CompareStringW(0, 1u, v10->wszAlgorithm, -1, (PCNZWCH)qword_180022180[v22 + 1], -1) == 2 )
      {
        break;
      }
    }
    if ( hObject )
    {
      v23 = IsMethodValidForKey(hObject, dwKeySpeca);
      if ( v23 < 0 )
      {
        v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v23, v24, 1399);
LABEL_184:
        CryptoInterface = v23;
        v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        v34 = v23;
        v33 = 935;
        goto LABEL_185;
      }
    }
LABEL_34:
    v25 = *(_QWORD *)(**(_QWORD **)(v8[17] + 32LL) + 8LL);
    if ( (*(_DWORD *)(v25 + 72) & 0x10000) != 0 || (*(_DWORD *)(v25 + 68) & 0x10000) != 0 )
    {
      CryptoInterface = -2146885369;
      v29 = "";
      while ( 1 )
      {
        v95 = *(v29 - 1);
        v96 = v29--;
        v97 = v95 == 92;
        if ( v95 == 92 )
          break;
        if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
        {
          v97 = v95 == 92;
          break;
        }
      }
      if ( v97 )
        v29 = v96;
      v33 = 945;
      v34 = -2146885369;
      goto LABEL_186;
    }
    v26 = *(_QWORD *)(v25 + 144);
    *(_OWORD *)(v26 + 72) = *(_OWORD *)&v10->cbSize;
    *(CRYPT_XML_BLOB *)(v26 + 88) = v10->Encoded;
    v27 = *(_QWORD *)(v25 + 144);
    *(_OWORD *)(v27 + 40) = *(_OWORD *)&v11->cbSize;
    *(CRYPT_XML_BLOB *)(v27 + 56) = v11->Encoded;
    *(_DWORD *)(v25 + 68) |= 0x10000u;
    *((_DWORD *)v8 + 17) |= 0x10000u;
    *(_DWORD *)(v25 + 72) &= ~0x10000u;
    *((_DWORD *)v8 + 18) &= ~0x10000u;
    v28 = *(_QWORD *)(v25 + 144);
    if ( !*(_DWORD *)(v28 + 92) )
    {
      *(_DWORD *)(v28 + 88) = 1;
      CryptoInterface = I_CryptXmlEncodeAlgorithmProxy(v10, (__int64)&dwFlagsa);
      if ( CryptoInterface < 0 )
      {
        v29 = "";
        while ( 1 )
        {
          v30 = *(v29 - 1);
          v31 = v29--;
          v32 = v30 == 92;
          if ( v30 == 92 )
            break;
          if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
          {
            v32 = v30 == 92;
            break;
          }
        }
        if ( v32 )
          v29 = v31;
        v33 = 980;
        v34 = CryptoInterface;
        goto LABEL_186;
      }
      *(_QWORD *)(*(_QWORD *)(v25 + 144) + 96LL) = 0;
      *(_DWORD *)(*(_QWORD *)(v25 + 144) + 92LL) = dwFlagsa;
    }
    if ( dwKeyInfoSpec == CRYPT_XML_KEYINFO_SPEC_PARAM )
    {
      v36 = (const WCHAR **)pvKeyInfoSpec;
      v37 = *((_DWORD *)pvKeyInfoSpec + 10);
      LODWORD(dwFlagsa) = *((_DWORD *)pvKeyInfoSpec + 14);
      v38 = *(const WCHAR **)pvKeyInfoSpec;
      v109 = v37;
      if ( *(_QWORD *)pvKeyInfoSpec )
      {
        if ( *v38 )
        {
          v39 = lstrlenW(v38);
          CryptoInterface = I_CryptXmlCheckUniqueId((__int64)v8, *v36, v39, 1);
          if ( CryptoInterface < 0 )
          {
            v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
            v34 = CryptoInterface;
            v33 = 1044;
            goto LABEL_185;
          }
        }
      }
      v40 = 0;
      v41 = dwFlagsa + v109;
      v42 = v36[4];
      if ( v42 && *v42 )
        ++v41;
      v43 = v41 + 1;
      v44 = v36[1];
      if ( !*((_DWORD *)v36 + 4) )
        v43 = v41;
      if ( v44 && *v44 )
        v40 = 1;
      v45 = v40 + 1;
      if ( !(_DWORD)v43 )
        v45 = v40;
      v46 = v17 & 1;
      v47 = v45 + 1;
      if ( !v46 )
        v47 = v45;
      dwFlagsa = v47 << 7;
      v48 = CryptXmlAlloc(3 * v43, (v47 << 7) + 24 * v43 + 40);
      v13 = v48;
      if ( !v48 )
      {
        CryptoInterface = -2147024882;
        v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        v34 = -2147024882;
        v33 = 1082;
        goto LABEL_185;
      }
      *(_DWORD *)v48 = 40;
      *(_QWORD *)(v48 + 8) = *v36;
      *(_QWORD *)(v48 + 24) = v48 + 40;
      v49 = v36[1];
      if ( v49 && *v49 )
      {
        *(_DWORD *)(((unsigned __int64)*(unsigned int *)(v48 + 16) << 7) + v48 + 40) = 1;
        *(_QWORD *)(((unsigned __int64)(unsigned int)(*(_DWORD *)(v48 + 16))++ << 7) + *(_QWORD *)(v48 + 24) + 8) = v36[1];
      }
      if ( (_DWORD)v43 )
      {
        v50 = 0;
        *(_DWORD *)(((unsigned __int64)*(unsigned int *)(v48 + 16) << 7) + *(_QWORD *)(v48 + 24)) = 4;
        *(_QWORD *)(((unsigned __int64)*(unsigned int *)(v48 + 16) << 7) + *(_QWORD *)(v48 + 24) + 16) = *(_QWORD *)(v48 + 24) + dwFlagsa;
        v51 = v36[4];
        if ( v51 && *v51 )
        {
          v50 = 1;
          **(_DWORD **)(((unsigned __int64)*(unsigned int *)(v48 + 16) << 7) + *(_QWORD *)(v48 + 24) + 16) = 3;
          *(_QWORD *)(*(_QWORD *)(((unsigned __int64)*(unsigned int *)(v48 + 16) << 7) + *(_QWORD *)(v48 + 24) + 16)
                    + 8LL) = v36[4];
        }
        if ( *((_DWORD *)v36 + 4) )
        {
          v52 = 24LL * v50;
          *(_DWORD *)(v52
                    + *(_QWORD *)(((unsigned __int64)*(unsigned int *)(v48 + 16) << 7) + *(_QWORD *)(v48 + 24) + 16)) = 2;
          *(_QWORD *)(*(_QWORD *)(((unsigned __int64)*(unsigned int *)(v48 + 16) << 7) + *(_QWORD *)(v48 + 24) + 16)
                    + v52
                    + 16) = v36[3];
          ++v50;
          *(_DWORD *)(*(_QWORD *)(((unsigned __int64)*(unsigned int *)(v48 + 16) << 7) + *(_QWORD *)(v48 + 24) + 16)
                    + v52
                    + 8) = *((_DWORD *)v36 + 4);
        }
        for ( k = 0;
              k < *((_DWORD *)v36 + 10);
              *(_QWORD *)(*(_QWORD *)(((unsigned __int64)*(unsigned int *)(v13 + 16) << 7) + *(_QWORD *)(v13 + 24) + 16)
                        + v56
                        + 16) = *(_QWORD *)&v36[6][4 * v55 + 4] )
        {
          v54 = v50++;
          v55 = k++;
          v55 *= 2;
          v56 = 24 * v54;
          *(_DWORD *)(v56
                    + *(_QWORD *)(((unsigned __int64)*(unsigned int *)(v13 + 16) << 7) + *(_QWORD *)(v13 + 24) + 16)) = 4;
          *(_DWORD *)(*(_QWORD *)(((unsigned __int64)*(unsigned int *)(v13 + 16) << 7) + *(_QWORD *)(v13 + 24) + 16)
                    + v56
                    + 8) = *(_DWORD *)&v36[6][4 * v55];
        }
        for ( m = 0;
              m < *((_DWORD *)v36 + 14);
              *(_QWORD *)(*(_QWORD *)(((unsigned __int64)*(unsigned int *)(v13 + 16) << 7) + *(_QWORD *)(v13 + 24) + 16)
                        + v60
                        + 16) = *(_QWORD *)&v36[8][4 * v59 + 4] )
        {
          v58 = v50++;
          v59 = m++;
          v59 *= 2;
          v60 = 24 * v58;
          *(_DWORD *)(v60
                    + *(_QWORD *)(((unsigned __int64)*(unsigned int *)(v13 + 16) << 7) + *(_QWORD *)(v13 + 24) + 16)) = 5;
          *(_DWORD *)(*(_QWORD *)(((unsigned __int64)*(unsigned int *)(v13 + 16) << 7) + *(_QWORD *)(v13 + 24) + 16)
                    + v60
                    + 8) = *(_DWORD *)&v36[8][4 * v59];
        }
        *(_DWORD *)(((unsigned __int64)(unsigned int)(*(_DWORD *)(v13 + 16))++ << 7) + *(_QWORD *)(v13 + 24) + 8) = v50;
      }
      if ( v46 )
      {
        CryptoInterface = I_CryptXmlExportPublicKey(1, hObject, dwKeySpeca, (struct _CRYPT_XML_KEY_VALUE **)&lpMem);
        if ( CryptoInterface < 0 )
        {
          v29 = "";
          while ( 1 )
          {
            v61 = *(v29 - 1);
            v62 = v29--;
            v63 = v61 == 92;
            if ( v61 == 92 )
              break;
            if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
            {
              v63 = v61 == 92;
              break;
            }
          }
          if ( v63 )
            v29 = v62;
          v33 = 1149;
          v34 = CryptoInterface;
          goto LABEL_186;
        }
        *(_DWORD *)(((unsigned __int64)*(unsigned int *)(v13 + 16) << 7) + *(_QWORD *)(v13 + 24)) = 2;
        v64 = lpMem;
        v65 = *(_QWORD *)(v13 + 24) + ((unsigned __int64)*(unsigned int *)(v13 + 16) << 7);
        *(_OWORD *)(v65 + 8) = *(_OWORD *)lpMem;
        *(_OWORD *)(v65 + 24) = v64[1];
        *(_OWORD *)(v65 + 40) = v64[2];
        *(_OWORD *)(v65 + 56) = v64[3];
        *(_OWORD *)(v65 + 72) = v64[4];
        *(_OWORD *)(v65 + 88) = v64[5];
        *(_OWORD *)(v65 + 104) = v64[6];
        *(_QWORD *)(v65 + 120) = *((_QWORD *)v64 + 14);
        ++*(_DWORD *)(v13 + 16);
      }
      CryptoInterface = I_XmlAllocAndCopyKeyInfo(*(HANDLE *)(v25 + 48));
      if ( CryptoInterface < 0 )
      {
        v29 = "";
        while ( 1 )
        {
          v66 = *(v29 - 1);
          v67 = v29--;
          v68 = v66 == 92;
          if ( v66 == 92 )
            break;
          if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
          {
            v68 = v66 == 92;
            break;
          }
        }
        if ( v68 )
          v29 = v67;
        v33 = 1166;
        v34 = CryptoInterface;
        goto LABEL_186;
      }
    }
    else if ( dwKeyInfoSpec )
    {
      if ( dwKeyInfoSpec == CRYPT_XML_KEYINFO_SPEC_ENCODED )
      {
        if ( (v17 & 1) != 0 )
        {
          CryptoInterface = -2147024809;
          v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
          v34 = -2147024809;
          v33 = 1009;
LABEL_185:
          v29 = v35;
LABEL_186:
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v34, v29, v33);
          goto LABEL_187;
        }
        CryptoInterface = I_CryptXmlDecodeKeyInfo(v8, v25, v20, pvKeyInfoSpec);
        if ( CryptoInterface < 0 )
        {
          v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
          v34 = CryptoInterface;
          v33 = 1022;
          goto LABEL_185;
        }
      }
    }
    else if ( pvKeyInfoSpec )
    {
      CryptoInterface = -2147024809;
      v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
      v34 = -2147024809;
      v33 = 999;
      goto LABEL_185;
    }
    v69 = *(_QWORD *)(v25 + 144);
    v70 = 0;
    for ( n = 0; (unsigned int)n < *(_DWORD *)(v69 + 104); n = (unsigned int)(n + 1) )
    {
      v72 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v69 + 112) + 8 * n) + 8LL) + 72LL);
      if ( (v72 & 8) == 0 )
      {
        if ( (v72 & 1) == 0 )
        {
          CryptoInterface = -2146885368;
          v29 = "";
          while ( 1 )
          {
            v73 = *(v29 - 1);
            v74 = v29--;
            v75 = v73 == 92;
            if ( v73 == 92 )
              break;
            if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
            {
              v75 = v73 == 92;
              break;
            }
          }
          if ( v75 )
            v29 = v74;
          v33 = 1188;
          v34 = -2146885368;
          goto LABEL_186;
        }
        v70 = 1;
      }
    }
    CryptoInterface = I_CryptXmlPreSignEncode((__int64)v8, 0, v70, (*(_DWORD *)(v25 + 136) >> 26) & 1);
    if ( CryptoInterface < 0 )
    {
      v29 = "";
      while ( 1 )
      {
        v76 = *(v29 - 1);
        v77 = v29--;
        v78 = v76 == 92;
        if ( v76 == 92 )
          break;
        if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
        {
          v78 = v76 == 92;
          break;
        }
      }
      if ( v78 )
        v29 = v77;
      v33 = 1207;
      v34 = CryptoInterface;
      goto LABEL_186;
    }
    if ( !v70 )
    {
LABEL_148:
      CryptoInterface = I_CryptXmlCanonicalizeSignedInfo(v8, 0);
      if ( CryptoInterface < 0 )
      {
        v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        v34 = CryptoInterface;
        v33 = 1313;
        goto LABEL_185;
      }
      if ( hObject || (HMACAlgName = (const WCHAR *)GetHMACAlgName(v10->wszAlgorithm)) == 0 )
      {
        CryptoInterface = I_CryptXmlGetCryptoInterface(v10, 0, &v111);
        if ( CryptoInterface < 0 )
        {
          v29 = "";
          while ( 1 )
          {
            v91 = *(v29 - 1);
            v92 = v29--;
            v93 = v91 == 92;
            if ( v91 == 92 )
              break;
            if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
            {
              v93 = v91 == 92;
              break;
            }
          }
          if ( v93 )
            v29 = v92;
          v33 = 1353;
          v34 = CryptoInterface;
          goto LABEL_186;
        }
        if ( !v111
          || (v94 = *(__int64 (__fastcall **)(CRYPT_XML_ALGORITHM *, NCRYPT_HANDLE, _QWORD, _QWORD, _DWORD, __int64, int, __int64))(v111 + 48)) == 0 )
        {
          CryptoInterface = -2146885372;
          v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
          v34 = -2146885372;
          v33 = 1362;
          goto LABEL_185;
        }
        v89 = (_DWORD *)(v25 + 152);
        v90 = v25 + 156;
        CryptoInterface = v94(
                            v10,
                            hObject,
                            dwKeySpeca,
                            *(_QWORD *)(*(_QWORD *)(v25 + 144) + 128LL),
                            *(_DWORD *)(*(_QWORD *)(v25 + 144) + 124LL),
                            v25 + 156,
                            2048,
                            v25 + 152);
        if ( CryptoInterface < 0 )
        {
          v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
          v34 = CryptoInterface;
          v33 = 1380;
          goto LABEL_185;
        }
      }
      else
      {
        v89 = (_DWORD *)(v25 + 152);
        v90 = v25 + 156;
        CryptoInterface = I_CryptXmlHMACSign(
                            HMACAlgName,
                            *(PUCHAR *)(*(_QWORD *)(v25 + 144) + 128LL),
                            *(_DWORD *)(*(_QWORD *)(v25 + 144) + 124LL),
                            *(PUCHAR *)(v25 + 2208),
                            *(_DWORD *)(v25 + 2216),
                            (PUCHAR)(v25 + 156),
                            2048,
                            (PUCHAR)(v25 + 152));
        if ( CryptoInterface < 0 )
        {
          v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
          v34 = CryptoInterface;
          v33 = 1336;
          goto LABEL_185;
        }
      }
      *(_QWORD *)(*(_QWORD *)(v25 + 144) + 144LL) = v90;
      *(_DWORD *)(*(_QWORD *)(v25 + 144) + 136LL) = *v89;
      CryptoInterface = I_CryptXmlPostSignEncode((__int64)v8);
      if ( CryptoInterface < 0 )
      {
        v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
        v34 = CryptoInterface;
        v33 = 1397;
        goto LABEL_185;
      }
      *(_DWORD *)(v25 + 72) |= 0x10000u;
      *((_DWORD *)v8 + 18) |= 0x10000u;
      *(_DWORD *)(v25 + 68) &= ~0x10000u;
      *((_DWORD *)v8 + 17) &= ~0x10000u;
      CryptoInterface = 0;
      goto LABEL_187;
    }
    LODWORD(dwFlagsa) = 0;
    for ( ii = 0; ; ii = (unsigned int)(ii + 1) )
    {
      v80 = *(_QWORD *)(v25 + 144);
      if ( (unsigned int)ii >= *(_DWORD *)(v80 + 104) )
        break;
      v81 = *(_QWORD *)(8 * ii + *(_QWORD *)(v80 + 112));
      if ( (*(_DWORD *)(*(_QWORD *)(v81 + 8) + 72LL) & 8) == 0 )
      {
        v82 = *(const WCHAR **)(v81 + 24);
        v83 = 0;
        v84 = *v82;
        if ( (_WORD)v84 )
        {
          if ( (_WORD)v84 == 35 )
            ++v82;
          LOBYTE(v83) = *(_DWORD *)(v81 + 88) == 0;
          LODWORD(dwFlagsa) = v83;
          CryptoInterface = I_CryptXmlResolveByIdOrElementName((__int64)v8, v82, v84, v83, (__int64)&pDataProviderIn);
          if ( CryptoInterface < 0 )
          {
            v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
            v34 = CryptoInterface;
            v33 = 1272;
            goto LABEL_185;
          }
        }
        else
        {
          CryptoInterface = I_CryptXmlResolveEmptyReference((__int64)v8, (__int64)&pDataProviderIn);
          if ( CryptoInterface < 0 )
          {
            v29 = "";
            while ( 1 )
            {
              v85 = *(v29 - 1);
              v86 = v29--;
              v87 = v85 == 92;
              if ( v85 == 92 )
                break;
              if ( v29 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp" )
              {
                v87 = v85 == 92;
                break;
              }
            }
            if ( v87 )
              v29 = v86;
            v33 = 1237;
            v34 = CryptoInterface;
            goto LABEL_186;
          }
        }
        CryptoInterface = CryptXmlDigestReference(
                            *(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v25 + 144) + 112LL) + 8 * ii) + 8LL),
                            dwFlagsa,
                            &pDataProviderIn);
        if ( CryptoInterface < 0 )
        {
          v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
          v34 = CryptoInterface;
          v33 = 1284;
          goto LABEL_185;
        }
      }
    }
    CryptoInterface = I_CryptXmlPreSignEncode((__int64)v8, 1, v70, *(_DWORD *)(v25 + 136) & 0x4000000);
    if ( CryptoInterface >= 0 )
      goto LABEL_148;
    v35 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
    v34 = CryptoInterface;
    v33 = 1301;
    goto LABEL_185;
  }
  CryptoInterface = -2146885370;
  v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\signature.cpp");
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885370, v15, 905);
LABEL_187:
  v102 = (void (__fastcall *)(_QWORD *))v8[16];
  if ( v102 )
    v102(v8);
  if ( v13 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 8u, (LPVOID)v13);
  }
LABEL_195:
  v106 = lpMem;
  if ( lpMem )
  {
    v107 = GetProcessHeap();
    HeapFree(v107, 8u, v106);
  }
  return CryptoInterface;
}

```

## disassembly

```asm
0x18000b3b0  mov     rax, rsp
0x18000b3b3  mov     [rax+18h], r8d
0x18000b3b7  mov     [rax+10h], rdx
0x18000b3bb  push    rbp
0x18000b3bc  push    rsi
0x18000b3bd  sub     rsp, 0B8h
0x18000b3c4  mov     [rax+20h], rbx
0x18000b3c8  xorps   xmm0, xmm0
0x18000b3cb  mov     [rax-18h], rdi
0x18000b3cf  mov     rbx, rcx
0x18000b3d2  xor     ecx, ecx
0x18000b3d4  mov     [rax-20h], r12
0x18000b3d8  mov     [rax-38h], r15
0x18000b3dc  mov     edi, r9d
0x18000b3df  mov     [rax-60h], rcx
0x18000b3e3  mov     ebp, ecx
0x18000b3e5  mov     [rax-70h], rcx
0x18000b3e9  mov     [rax+8], ecx
0x18000b3ec  mov     [rax-68h], rcx
0x18000b3f0  movups  xmmword ptr [rax-58h], xmm0
0x18000b3f4  movups  xmmword ptr [rax-48h], xmm0
0x18000b3f8  test    rbx, rbx
0x18000b3fb  jz      loc_18000C214
0x18000b401  mov     r15, [rsp+0C8h+pSignatureMethod]
0x18000b409  test    r15, r15
0x18000b40c  jz      loc_18000C214
0x18000b412  cmp     [r15+8], rcx
0x18000b416  jz      loc_18000C214
0x18000b41c  mov     rsi, [rsp+0C8h+pCanonicalization]
0x18000b424  test    rsi, rsi
0x18000b427  jz      loc_18000C214
0x18000b42d  cmp     [rsi+8], rcx
0x18000b431  jz      loc_18000C214
0x18000b437  cmp     dword ptr [rbx], 44444442h
0x18000b43d  jnz     loc_18000C1FB
0x18000b443  test    rbx, rbx
0x18000b446  jz      loc_18000C1E2
0x18000b44c  cmp     dword ptr [rbx], 44444441h
0x18000b452  jz      short loc_18000B45A
0x18000b454  mov     rbx, [rbx+50h]
0x18000b458  jmp     short loc_18000B443
0x18000b45a  mov     rax, [rbx+78h]
0x18000b45e  mov     r12, rcx
0x18000b461  mov     [rsp+0C8h+var_28], r13
0x18000b469  test    rax, rax
0x18000b46c  jz      short loc_18000B478
0x18000b46e  mov     rcx, rbx
0x18000b471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b476  xor     ecx, ecx
0x18000b478  cmp     [rbx+48h], ebp
0x18000b47b  jl      short loc_18000B4AA
0x18000b47d  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b484  mov     esi, 80092106h
0x18000b489  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b48e  mov     r8, rax
0x18000b491  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000b498  mov     edx, esi
0x18000b49a  mov     r9d, 389h
0x18000b4a0  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000b4a5  jmp     loc_18000C19C
0x18000b4aa  mov     rax, [rbx+88h]
0x18000b4b1  mov     [rsp+0C8h+var_30], r14
0x18000b4b9  cmp     dword ptr [rax+18h], 1
0x18000b4bd  jz      short loc_18000B4EC
0x18000b4bf  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b4c6  mov     esi, 80092107h
0x18000b4cb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b4d0  mov     r8, rax
0x18000b4d3  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000b4da  mov     edx, esi
0x18000b4dc  mov     r9d, 390h
0x18000b4e2  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000b4e7  jmp     loc_18000C194
0x18000b4ec  mov     ebp, edi
0x18000b4ee  bts     ebp, 1Ch
0x18000b4f2  test    dword ptr [rbx+3Ch], 10000000h
0x18000b4f9  cmovz   ebp, edi
0x18000b4fc  cmp     cs:dword_180022FC8, r12d
0x18000b503  jnz     short loc_18000B50C
0x18000b505  call    _LoadRegExtensions
0x18000b50a  xor     ecx, ecx
0x18000b50c  mov     r10d, 1
0x18000b512  bt      ebp, 1Ch
0x18000b516  jb      short loc_18000B576
0x18000b518  mov     edi, ecx
0x18000b51a  cmp     edi, cs:dword_180022FC0
0x18000b520  jnb     short loc_18000B574
0x18000b522  mov     rax, cs:qword_180022FD8
0x18000b529  mov     ecx, edi
0x18000b52b  mov     rax, [rax+rcx*8]
0x18000b52f  cmp     dword ptr [rax+18h], 2
0x18000b533  jnz     short loc_18000B570
0x18000b535  mov     rax, [rax+8]
0x18000b539  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000b53f  mov     r8, [r15+8]; lpString1
0x18000b543  mov     edx, r10d; dwCmpFlags
0x18000b546  mov     [rsp+0C8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000b54e  xor     ecx, ecx; Locale
0x18000b550  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18000b555  call    cs:__imp_CompareStringW
0x18000b55c  nop     dword ptr [rax+rax+00h]
0x18000b561  cmp     eax, 2
0x18000b564  jz      loc_18000B63B
0x18000b56a  mov     r10d, 1
0x18000b570  inc     edi
0x18000b572  jmp     short loc_18000B51A
0x18000b574  xor     ecx, ecx
0x18000b576  mov     edi, ecx
0x18000b578  lea     rdx, qword_180022180
0x18000b57f  cmp     edi, 11h
0x18000b582  jnb     loc_18000C11C
0x18000b588  mov     eax, edi
0x18000b58a  lea     rcx, [rax+rax*8]
0x18000b58e  lea     rax, ds:0[rcx*8]
0x18000b596  cmp     dword ptr [rax+rdx+18h], 2
0x18000b59b  mov     [rsp+0C8h+var_78], rax
0x18000b5a0  jnz     short loc_18000B5E1
0x18000b5a2  mov     rax, [rax+rdx+8]
0x18000b5a7  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000b5ad  mov     r8, [r15+8]; lpString1
0x18000b5b1  mov     edx, r10d; dwCmpFlags
0x18000b5b4  mov     [rsp+0C8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000b5bc  xor     ecx, ecx; Locale
0x18000b5be  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18000b5c3  call    cs:__imp_CompareStringW
0x18000b5ca  nop     dword ptr [rax+rax+00h]
0x18000b5cf  cmp     eax, 2
0x18000b5d2  jz      short loc_18000B5E5
0x18000b5d4  lea     rdx, qword_180022180
0x18000b5db  mov     r10d, 1
0x18000b5e1  inc     edi
0x18000b5e3  jmp     short loc_18000B57F
0x18000b5e5  mov     rcx, [rsp+0C8h+hObject]; hObject
0x18000b5ed  test    rcx, rcx
0x18000b5f0  jz      short loc_18000B63B
0x18000b5f2  mov     r8, [rsp+0C8h+var_78]
0x18000b5f7  lea     rdx, qword_180022180
0x18000b5fe  add     r8, rdx
0x18000b601  mov     edx, [rsp+0C8h+dwKeySpec]; dwKeySpec
0x18000b608  call    _IsMethodValidForKey
0x18000b60d  mov     edi, eax
0x18000b60f  test    eax, eax
0x18000b611  jns     short loc_18000B63B
0x18000b613  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b61a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b61f  mov     r8, rax
0x18000b622  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000b629  mov     edx, edi
0x18000b62b  mov     r9d, 577h
0x18000b631  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000b636  jmp     loc_18000C16A
0x18000b63b  mov     rax, [rbx+88h]
0x18000b642  mov     rcx, [rax+20h]
0x18000b646  mov     rax, [rcx]
0x18000b649  mov     rdi, [rax+8]
0x18000b64d  test    dword ptr [rdi+48h], 10000h
0x18000b654  jnz     loc_18000C0E5
0x18000b65a  test    dword ptr [rdi+44h], 10000h
0x18000b661  jnz     loc_18000C0E5
0x18000b667  movups  xmm0, xmmword ptr [r15]
0x18000b66b  mov     rax, [rdi+90h]
0x18000b672  movups  xmmword ptr [rax+48h], xmm0
0x18000b676  movups  xmm1, xmmword ptr [r15+10h]
0x18000b67b  movups  xmmword ptr [rax+58h], xmm1
0x18000b67f  mov     rax, [rdi+90h]
0x18000b686  movups  xmm0, xmmword ptr [rsi]
0x18000b689  movups  xmmword ptr [rax+28h], xmm0
0x18000b68d  movups  xmm1, xmmword ptr [rsi+10h]
0x18000b691  movups  xmmword ptr [rax+38h], xmm1
0x18000b695  or      dword ptr [rdi+44h], 10000h
0x18000b69c  or      dword ptr [rbx+44h], 10000h
0x18000b6a3  and     dword ptr [rdi+48h], 0FFFEFFFFh
0x18000b6aa  and     dword ptr [rbx+48h], 0FFFEFFFFh
0x18000b6b1  mov     rax, [rdi+90h]
0x18000b6b8  cmp     [rax+5Ch], r12d
0x18000b6bc  jnz     loc_18000B74C
0x18000b6c2  mov     dword ptr [rax+58h], 1
0x18000b6c9  lea     r9, [rsp+0C8h+var_70]
0x18000b6ce  mov     r8, [rdi+90h]
0x18000b6d5  lea     rax, [rsp+0C8h+dwFlags]
0x18000b6dd  mov     edx, ebp
0x18000b6df  mov     [rsp+0C8h+lpString2], rax; __int64
0x18000b6e4  mov     rcx, r15; pXmlAlgorithm
0x18000b6e7  mov     r8d, [r8+58h]
0x18000b6eb  call    I_CryptXmlEncodeAlgorithmProxy
0x18000b6f0  mov     esi, eax
0x18000b6f2  test    eax, eax
0x18000b6f4  jns     short loc_18000B72B
0x18000b6f6  lea     r8, aOnecoreDsSecur_11+33h; ""
0x18000b6fd  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b704  movzx   eax, byte ptr [r8-1]
0x18000b709  mov     rdx, r8
0x18000b70c  dec     r8
0x18000b70f  cmp     al, 5Ch ; '\'
0x18000b711  jz      short loc_18000B71A
0x18000b713  cmp     r8, rcx
0x18000b716  ja      short loc_18000B704
0x18000b718  cmp     al, 5Ch ; '\'
0x18000b71a  cmovz   r8, rdx
0x18000b71e  mov     r9d, 3D4h
0x18000b724  mov     edx, esi
0x18000b726  jmp     loc_18000C183
0x18000b72b  mov     rax, [rdi+90h]
0x18000b732  mov     rcx, [rsp+0C8h+var_70]
0x18000b737  mov     [rax+60h], rcx
0x18000b73b  mov     rcx, [rdi+90h]
0x18000b742  mov     eax, dword ptr [rsp+0C8h+dwFlags]
0x18000b749  mov     [rcx+5Ch], eax
0x18000b74c  mov     ecx, [rsp+0C8h+dwKeyInfoSpec]
0x18000b753  cmp     ecx, 2
0x18000b756  jz      loc_18000B7EE
0x18000b75c  test    ecx, ecx
0x18000b75e  jz      short loc_18000B7C2
0x18000b760  cmp     ecx, 1
0x18000b763  jnz     loc_18000BC7F
0x18000b769  test    cl, bpl
0x18000b76c  jz      short loc_18000B78C
0x18000b76e  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b775  mov     esi, 80070057h
0x18000b77a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b77f  mov     edx, esi
0x18000b781  mov     r9d, 3F1h
0x18000b787  jmp     loc_18000C180
0x18000b78c  mov     r9, [rsp+0C8h+pvKeyInfoSpec]
0x18000b794  mov     rdx, rdi
0x18000b797  mov     rcx, rbx
0x18000b79a  call    I_CryptXmlDecodeKeyInfo
0x18000b79f  mov     esi, eax
0x18000b7a1  test    eax, eax
0x18000b7a3  jns     loc_18000BC7F
0x18000b7a9  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b7b0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b7b5  mov     edx, esi
0x18000b7b7  mov     r9d, 3FEh
0x18000b7bd  jmp     loc_18000C180
0x18000b7c2  cmp     [rsp+0C8h+pvKeyInfoSpec], r12
0x18000b7ca  jz      loc_18000BC7F
0x18000b7d0  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b7d7  mov     esi, 80070057h
0x18000b7dc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b7e1  mov     edx, esi
0x18000b7e3  mov     r9d, 3E7h
0x18000b7e9  jmp     loc_18000C180
0x18000b7ee  mov     r14, [rsp+0C8h+pvKeyInfoSpec]
0x18000b7f6  mov     ecx, [r14+38h]
0x18000b7fa  mov     eax, [r14+28h]
0x18000b7fe  mov     dword ptr [rsp+0C8h+dwFlags], ecx
0x18000b805  mov     rcx, [r14]; lpString
0x18000b808  mov     dword ptr [rsp+0C8h+var_78], eax
0x18000b80c  test    rcx, rcx
0x18000b80f  jz      short loc_18000B857
0x18000b811  xor     eax, eax
0x18000b813  cmp     ax, [rcx]
0x18000b816  jz      short loc_18000B857
0x18000b818  call    cs:__imp_lstrlenW
0x18000b81f  nop     dword ptr [rax+rax+00h]
0x18000b824  mov     rdx, [r14]
0x18000b827  mov     r9d, 1
0x18000b82d  mov     r8d, eax
0x18000b830  mov     rcx, rbx
0x18000b833  call    I_CryptXmlCheckUniqueId
0x18000b838  mov     esi, eax
0x18000b83a  test    eax, eax
0x18000b83c  jns     short loc_18000B857
0x18000b83e  lea     rcx, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000b845  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000b84a  mov     edx, esi
0x18000b84c  mov     r9d, 414h
0x18000b852  jmp     loc_18000C180
0x18000b857  mov     ecx, dword ptr [rsp+0C8h+var_78]
0x18000b85b  xor     r8d, r8d
0x18000b85e  add     ecx, dword ptr [rsp+0C8h+dwFlags]
0x18000b865  mov     rdx, [r14+20h]
0x18000b869  test    rdx, rdx
0x18000b86c  jz      short loc_18000B877
0x18000b86e  xor     eax, eax
0x18000b870  cmp     ax, [rdx]
0x18000b873  jz      short loc_18000B877
0x18000b875  inc     ecx
0x18000b877  cmp     [r14+10h], r8d
0x18000b87b  lea     esi, [rcx+1]
0x18000b87e  mov     rax, [r14+8]
0x18000b882  cmovbe  esi, ecx
0x18000b885  test    rax, rax
0x18000b888  jz      short loc_18000B898
0x18000b88a  xor     ecx, ecx
0x18000b88c  cmp     cx, [rax]
0x18000b88f  mov     eax, 1
0x18000b894  cmovnz  r8d, eax
0x18000b898  lea     ecx, [r8+1]
0x18000b89c  test    esi, esi
0x18000b89e  cmovz   ecx, r8d
0x18000b8a2  and     ebp, 1
0x18000b8a5  lea     edx, [rcx+1]
0x18000b8a8  cmovz   edx, ecx
0x18000b8ab  lea     rcx, [rsi+rsi*2]
0x18000b8af  shl     rdx, 7
0x18000b8b3  mov     [rsp+0C8h+dwFlags], rdx
0x18000b8bb  lea     rdx, [rdx+rcx*8]
0x18000b8bf  add     rdx, 28h ; '('
  ... truncated ...
```
