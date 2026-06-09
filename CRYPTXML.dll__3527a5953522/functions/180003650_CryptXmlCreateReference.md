# CryptXmlCreateReference

- ea: `0x180003650`
- end: `0x180003fa6`
- name: `CryptXmlCreateReference`
- size: `2390`
- prototype: `HRESULT __stdcall(HCRYPTXML hCryptXml, DWORD dwFlags, LPCWSTR wszId, LPCWSTR wszURI, LPCWSTR wszType, const CRYPT_XML_ALGORITHM *pDigestMethod, ULONG cTransform, const CRYPT_XML_ALGORITHM *rgTransform, HCRYPTXML *phReference)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003650`
- `0x1800049c0`
- `0x180004f60`
- `0x180006da0`
- `0x1800070d0`
- `0x180008ffc`
- `0x180009180`
- `0x18000f200`
- `0x1800110e0`
- `0x180014ce0`
- `0x1800160e4`
- `0x180017224`
- `0x180018625`
- `0x180018640`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f2e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003823`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000387e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003d66`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003823`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000387e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003d66`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003905`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003945`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800039b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800039d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800039fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003af9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003905`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003945`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800039b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800039d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800039fc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180003af9`

## string_xrefs

- `0x180003721`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003760`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x1800038b3`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x18000391c`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x18000397c`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003a64`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003b74`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003bd9`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003c95`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003ce0`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003dec`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003e45`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003ebe`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003ee6`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003f45`: `onecore\ds\security\cryptoapi\xml\lib\reference.cpp`
- `0x180003e7d`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlCreateReference(
        HCRYPTXML hCryptXml,
        DWORD dwFlags,
        LPCWSTR wszId,
        LPCWSTR wszURI,
        LPCWSTR wszType,
        const CRYPT_XML_ALGORITHM *pDigestMethod,
        ULONG cTransform,
        const CRYPT_XML_ALGORITHM *rgTransform,
        HCRYPTXML *phReference)
{
  const char *v11; // rax
  HRESULT v13; // edi
  const char *v14; // rax
  _QWORD *i; // rbx
  void (__fastcall *v16)(_QWORD *); // rax
  unsigned int k; // edi
  __int64 v18; // rax
  unsigned int j; // edi
  DWORD v20; // r13d
  const char *v21; // r8
  int v22; // r9d
  void (__fastcall *v23)(_QWORD *); // rax
  const WCHAR *v24; // r14
  unsigned int v25; // eax
  unsigned int v26; // esi
  char v27; // al
  const char *v28; // rdx
  bool v29; // zf
  unsigned int v30; // r15d
  int v31; // eax
  LPCWSTR v32; // rcx
  unsigned int v33; // r14d
  unsigned int v34; // r12d
  ULONG v35; // eax
  ULONG cbData; // edx
  ULONG v37; // r12d
  __int64 v38; // r14
  const CRYPT_XML_ALGORITHM *v39; // r13
  __int64 v40; // rsi
  __int64 v41; // rdi
  const WCHAR *v42; // rcx
  HANDLE *v43; // r12
  int v44; // eax
  __int64 v45; // r14
  const char *v46; // r8
  char v47; // al
  const char *v48; // rdx
  bool v49; // zf
  const char *v50; // r8
  char v51; // al
  const char *v52; // rdx
  bool v53; // zf
  HANDLE v54; // rcx
  const char *v55; // rax
  const char *v56; // rax
  LPCWSTR v57; // r13
  __int64 m; // rdi
  _DWORD *v59; // rdx
  const char *v60; // rax
  char v61; // al
  const char *v62; // rdx
  bool v63; // zf
  const char *v64; // r8
  char v65; // cl
  const char *v66; // rdx
  bool v67; // zf
  const char *v68; // rax
  const char *v69; // rax
  const char *v70; // r8
  char v71; // al
  const char *v72; // rdx
  bool v73; // zf
  DWORD v74; // [rsp+40h] [rbp-C0h]
  ULONG v75; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v76; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpString; // [rsp+50h] [rbp-B0h]
  __int64 v78; // [rsp+58h] [rbp-A8h] BYREF
  HCRYPTXML *v79; // [rsp+60h] [rbp-A0h]
  LPCWSTR v80; // [rsp+68h] [rbp-98h]
  LPCWSTR v81; // [rsp+70h] [rbp-90h]
  CRYPT_XML_ALGORITHM *pXmlAlgorithm; // [rsp+78h] [rbp-88h]
  const CRYPT_XML_ALGORITHM *v83; // [rsp+80h] [rbp-80h]
  HANDLE *v84; // [rsp+88h] [rbp-78h]
  const WCHAR *v85; // [rsp+90h] [rbp-70h]
  unsigned int v86; // [rsp+98h] [rbp-68h]
  int v87; // [rsp+9Ch] [rbp-64h]
  __int64 v88; // [rsp+A0h] [rbp-60h]
  __int64 v89; // [rsp+A8h] [rbp-58h]
  __int64 v90; // [rsp+B0h] [rbp-50h]
  int v91; // [rsp+B8h] [rbp-48h]
  __int64 v92; // [rsp+BCh] [rbp-44h]
  __int64 v93; // [rsp+C4h] [rbp-3Ch]
  __int64 v94; // [rsp+CCh] [rbp-34h]
  __int64 v95; // [rsp+D4h] [rbp-2Ch]
  int v96; // [rsp+DCh] [rbp-24h]
  const WCHAR *v97; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v98; // [rsp+E8h] [rbp-18h]
  const WCHAR *v99; // [rsp+F0h] [rbp-10h]
  unsigned int v100; // [rsp+F8h] [rbp-8h]
  const WCHAR *v101; // [rsp+100h] [rbp+0h]
  int v102; // [rsp+108h] [rbp+8h]
  LPCWSTR wszAlgorithm; // [rsp+110h] [rbp+10h]
  unsigned int v104; // [rsp+118h] [rbp+18h]
  CRYPT_XML_CHARSET dwCharset; // [rsp+120h] [rbp+20h]
  ULONG v106; // [rsp+124h] [rbp+24h]
  BYTE *pbData; // [rsp+128h] [rbp+28h]
  ULONG v108; // [rsp+13Ch] [rbp+3Ch]
  _QWORD v109[82]; // [rsp+140h] [rbp+40h]

  v80 = wszId;
  v84 = (HANDLE *)hCryptXml;
  v81 = wszType;
  pXmlAlgorithm = (CRYPT_XML_ALGORITHM *)pDigestMethod;
  v83 = rgTransform;
  v79 = phReference;
  lpString = wszURI;
  memset_0(&v97, 0, 0x2E8u);
  v78 = 0;
  v75 = 0;
  if ( hCryptXml && phReference && (!cTransform || rgTransform) && pDigestMethod )
  {
    *phReference = 0;
    if ( cTransform > 0x10 )
    {
      v11 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885374, v11, 323);
      return -2146885374;
    }
    if ( ((*(_DWORD *)hCryptXml - 1145324610) & 0xFFFFFFFD) != 0 )
    {
      v13 = -2146885370;
      v14 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885370, v14, 331);
      return v13;
    }
    for ( i = hCryptXml; ; i = (_QWORD *)i[10] )
    {
      if ( !i )
      {
        v13 = -2146885370;
        v69 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885370, v69, 343);
        return v13;
      }
      if ( *(_DWORD *)i == 1145324609 )
        break;
    }
    v16 = (void (__fastcall *)(_QWORD *))i[15];
    if ( v16 )
      v16(i);
    if ( (*((_DWORD *)i + 15) & 0x10000000) != 0 )
      dwFlags |= 0x10000000u;
    if ( !dword_180022FC8 )
      LoadRegExtensions();
    v74 = dwFlags;
    if ( (dwFlags & 0x10000000) != 0 )
    {
LABEL_27:
      for ( j = 0; j < 0x11; ++j )
      {
        if ( LODWORD(qword_180022180[9 * j + 3]) == 1
          && CompareStringW(0, 1u, pDigestMethod->wszAlgorithm, -1, (PCNZWCH)qword_180022180[9 * j + 1], -1) == 2 )
        {
          goto LABEL_32;
        }
      }
      v64 = "";
      while ( 1 )
      {
        v65 = *(v64 - 1);
        v66 = v64--;
        v67 = v65 == 92;
        if ( v65 == 92 )
          break;
        if ( v64 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
        {
          v67 = v65 == 92;
          break;
        }
      }
      if ( v67 )
        v64 = v66;
      v13 = -2146885372;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %S", -2146885372, v64, 1408, pDigestMethod->wszAlgorithm);
      v68 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885372, v68, 368);
      goto LABEL_36;
    }
    for ( k = 0; ; ++k )
    {
      if ( k >= dword_180022FC0 )
        goto LABEL_27;
      v18 = *((_QWORD *)qword_180022FD8 + k);
      if ( *(_DWORD *)(v18 + 24) == 1
        && CompareStringW(0, 1u, pDigestMethod->wszAlgorithm, -1, *(PCNZWCH *)(v18 + 8), -1) == 2 )
      {
        break;
      }
    }
LABEL_32:
    v20 = dwFlags & 1;
    v76 = v20;
    if ( (dwFlags & 1) != 0 )
    {
      if ( *(_DWORD *)hCryptXml != 1145324610 )
      {
        v13 = -2147024809;
        v21 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
        v22 = 377;
LABEL_35:
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v21, v22);
        goto LABEL_36;
      }
      v24 = lpString;
      if ( lstrlenW(lpString) < 2 || *lpString != 35 )
      {
        v13 = -2147024809;
        v21 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
        v22 = 384;
        goto LABEL_35;
      }
    }
    else
    {
      v24 = lpString;
    }
    v25 = lstrlenW(v80);
    v98 = v25;
    v26 = v25;
    if ( v25 )
    {
      v97 = v80;
      v13 = I_CryptXmlCheckUniqueId((__int64)i, v80, v25, 0);
      if ( v13 < 0 )
      {
        v21 = "";
        while ( 1 )
        {
          v27 = *(v21 - 1);
          v28 = v21--;
          v29 = v27 == 92;
          if ( v27 == 92 )
            break;
          if ( v21 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
          {
            v29 = v27 == 92;
            break;
          }
        }
        if ( v29 )
          v21 = v28;
        v22 = 402;
        goto LABEL_35;
      }
    }
    if ( v24 )
    {
      v99 = v24;
      v30 = lstrlenW(v24);
      v100 = v30;
    }
    else
    {
      v30 = v100;
    }
    v31 = lstrlenW(v81);
    v32 = v101;
    v33 = v31;
    v102 = v31;
    if ( v31 )
      v32 = v81;
    v101 = v32;
    wszAlgorithm = pDigestMethod->wszAlgorithm;
    v34 = lstrlenW(wszAlgorithm);
    v104 = v34;
    v35 = cTransform;
    v108 = cTransform;
    cbData = pXmlAlgorithm->Encoded.cbData;
    pbData = pXmlAlgorithm->Encoded.pbData;
    dwCharset = pXmlAlgorithm->Encoded.dwCharset;
    v106 = cbData;
    if ( !cbData )
    {
      dwCharset = CRYPT_XML_CHARSET_UTF8;
      v13 = I_CryptXmlEncodeAlgorithmProxy(pXmlAlgorithm, (__int64)&v75);
      if ( v13 < 0 )
      {
        v21 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
        v22 = 441;
        goto LABEL_35;
      }
      pbData = 0;
      v106 = v75;
      v35 = cTransform;
    }
    if ( v26 > 0x100 || v30 > 0x2000 || v33 > 0x2000 || v34 > 0x2000 )
    {
      v13 = -2146885375;
      v21 = "";
      while ( 1 )
      {
        v61 = *(v21 - 1);
        v62 = v21--;
        v63 = v61 == 92;
        if ( v61 == 92 )
          break;
        if ( v21 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
        {
          v63 = v61 == 92;
          break;
        }
      }
      if ( v63 )
        v21 = v62;
      v22 = 455;
      goto LABEL_35;
    }
    v37 = 0;
    if ( v35 )
    {
      v38 = 0;
      v39 = v83;
      do
      {
        v40 = 5 * v38;
        v41 = v38;
        v42 = v39[v38].wszAlgorithm;
        v109[5 * v38] = v42;
        LODWORD(v109[5 * v38 + 1]) = lstrlenW(v42);
        ++v37;
        ++v38;
        v109[v40 + 3] = v39[v41].Encoded.pbData;
        HIDWORD(v109[v40 + 2]) = v39[v41].Encoded.cbData;
      }
      while ( v37 < cTransform );
      v30 = v100;
      v26 = v98;
      v20 = v76;
    }
    v43 = v84;
    v44 = I_CryptXmlHandleAllocReference(v84[6], 1, v74, (__int64)&v97, 0, &v78);
    v45 = v78;
    v13 = v44;
    if ( v44 < 0 )
    {
      v46 = "";
      while ( 1 )
      {
        v47 = *(v46 - 1);
        v48 = v46--;
        v49 = v47 == 92;
        if ( v47 == 92 )
          break;
        if ( v46 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
        {
          v49 = v47 == 92;
          break;
        }
      }
      if ( v49 )
        v46 = v48;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v46, 481);
      goto LABEL_103;
    }
    if ( *(_DWORD *)v43 == 1145324610 )
    {
      v13 = I_CryptXmlSignatureAddReference(v43, *(_QWORD *)(v78 + 136));
      if ( v13 < 0 )
      {
        v50 = "";
        while ( 1 )
        {
          v51 = *(v50 - 1);
          v52 = v50--;
          v53 = v51 == 92;
          if ( v51 == 92 )
            break;
          if ( v50 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
          {
            v53 = v51 == 92;
            break;
          }
        }
        if ( v53 )
          v50 = v52;
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v50, 493);
        goto LABEL_103;
      }
      if ( v20 )
      {
        v54 = v43[6];
        v87 = 0;
        v85 = v99 + 1;
        v86 = v30 - 1;
        v89 = 0;
        v92 = 0;
        v93 = 0;
        v94 = 0;
        v95 = 0;
        v96 = 0;
        v88 = 0;
        v90 = 0;
        v91 = 0;
        v13 = I_CryptXmlHandleAllocObject(v54);
        if ( v13 < 0 )
        {
          v55 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v55, 515);
          goto LABEL_103;
        }
        v13 = I_CryptXmlSignatureAddObject(v43, MEMORY[0x88]);
        if ( v13 < 0 )
        {
          v56 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v56, 525);
          goto LABEL_103;
        }
      }
      else
      {
        v57 = lpString;
        if ( lpString && *lpString == 35 )
        {
          for ( m = 0; ; m = (unsigned int)(m + 1) )
          {
            v59 = v43[18];
            if ( (unsigned int)m >= v59[40] )
              break;
            if ( CompareStringW(0, 0, *(PCNZWCH *)(*(_QWORD *)(*((_QWORD *)v59 + 21) + 8 * m) + 16LL), -1, v57 + 1, -1) == 2 )
            {
              _mm_lfence();
              *(_QWORD *)(v45 + 144) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v43[18] + 21) + 8 * m) + 8LL);
              break;
            }
          }
        }
      }
    }
    else if ( *(_DWORD *)v43 == 1145324612 )
    {
      v13 = I_CryptXmlObjectAddReference(v43, *(_QWORD *)(v78 + 136));
      if ( v13 < 0 )
      {
        v60 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v13, v60, 564);
LABEL_103:
        if ( v45 )
          I_CryptXmlRelease(v45);
LABEL_36:
        v23 = (void (__fastcall *)(_QWORD *))i[16];
        if ( v23 )
          v23(i);
        return v13;
      }
    }
    if ( v26 )
      I_CryptXmlCheckUniqueId((__int64)i, v97, v26, 1);
    *v79 = (HCRYPTXML)v45;
    v13 = 0;
    goto LABEL_103;
  }
  v70 = "";
  while ( 1 )
  {
    v71 = *(v70 - 1);
    v72 = v70--;
    v73 = v71 == 92;
    if ( v71 == 92 )
      break;
    if ( v70 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\reference.cpp" )
    {
      v73 = v71 == 92;
      break;
    }
  }
  if ( v73 )
    v70 = v72;
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024809, v70, 310);
  return -2147024809;
}

```

## disassembly

```asm
0x180003650  push    rbp
0x180003652  push    rbx
0x180003653  push    rsi
0x180003654  push    rdi
0x180003655  push    r12
0x180003657  push    r13
0x180003659  push    r14
0x18000365b  push    r15
0x18000365d  lea     rbp, [rsp-2E8h]
0x180003665  sub     rsp, 3E8h
0x18000366c  mov     rax, cs:__security_cookie
0x180003673  xor     rax, rsp
0x180003676  mov     [rbp+320h+var_50], rax
0x18000367d  mov     rax, [rbp+320h+wszType]
0x180003684  mov     esi, edx
0x180003686  mov     r12, [rbp+320h+pDigestMethod]
0x18000368d  mov     r14, rcx
0x180003690  mov     rdi, [rbp+320h+rgTransform]
0x180003697  xor     edx, edx; Val
0x180003699  mov     rbx, [rbp+320h+phReference]
0x1800036a0  mov     [rsp+420h+var_3B8], r8
0x1800036a5  mov     r8d, 2E8h; Size
0x1800036ab  mov     [rbp+320h+var_398], rcx
0x1800036af  lea     rcx, [rbp+320h+var_340]; void *
0x1800036b3  mov     [rsp+420h+var_3B0], rax
0x1800036b8  mov     [rsp+420h+pXmlAlgorithm], r12
0x1800036bd  mov     [rbp+320h+var_3A0], rdi
0x1800036c1  mov     [rsp+420h+var_3C0], rbx
0x1800036c6  mov     [rsp+420h+lpString], r9
0x1800036cb  call    memset_0
0x1800036d0  xor     ecx, ecx
0x1800036d2  mov     [rsp+420h+var_3C8], rcx
0x1800036d7  mov     r13d, ecx
0x1800036da  mov     [rsp+420h+var_3F0], rcx
0x1800036df  mov     [rsp+420h+lpMem], rcx
0x1800036e4  mov     dword ptr [rsp+420h+var_3DC], ecx
0x1800036e8  test    r14, r14
0x1800036eb  jz      loc_180003F3E
0x1800036f1  test    rbx, rbx
0x1800036f4  jz      loc_180003F3E
0x1800036fa  mov     r15d, [rbp+320h+cTransform]
0x180003701  test    r15d, r15d
0x180003704  jz      short loc_18000370F
0x180003706  test    rdi, rdi
0x180003709  jz      loc_180003F3E
0x18000370f  test    r12, r12
0x180003712  jz      loc_180003F3E
0x180003718  mov     [rbx], rcx
0x18000371b  cmp     r15d, 10h
0x18000371f  jbe     short loc_180003751
0x180003721  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180003728  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000372d  mov     r8, rax
0x180003730  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180003737  mov     edx, 80092102h
0x18000373c  mov     r9d, 143h
0x180003742  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180003747  mov     eax, 80092102h
0x18000374c  jmp     loc_180003F82
0x180003751  mov     eax, [r14]
0x180003754  sub     eax, 44444442h
0x180003759  test    eax, 0FFFFFFFDh
0x18000375e  jz      short loc_18000378F
0x180003760  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180003767  mov     edi, 80092106h
0x18000376c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180003771  mov     r8, rax
0x180003774  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000377b  mov     edx, edi
0x18000377d  mov     r9d, 14Bh
0x180003783  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180003788  mov     eax, edi
0x18000378a  jmp     loc_180003F82
0x18000378f  mov     rbx, r14
0x180003792  test    rbx, rbx
0x180003795  jz      loc_180003EE6
0x18000379b  cmp     dword ptr [rbx], 44444441h
0x1800037a1  jz      short loc_1800037A9
0x1800037a3  mov     rbx, [rbx+50h]
0x1800037a7  jmp     short loc_180003792
0x1800037a9  mov     rax, [rbx+78h]
0x1800037ad  test    rax, rax
0x1800037b0  jz      short loc_1800037BC
0x1800037b2  mov     rcx, rbx
0x1800037b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ba  xor     ecx, ecx
0x1800037bc  test    dword ptr [rbx+3Ch], 10000000h
0x1800037c3  jz      short loc_1800037C9
0x1800037c5  bts     esi, 1Ch
0x1800037c9  cmp     cs:dword_180022FC8, r13d
0x1800037d0  jnz     short loc_1800037D9
0x1800037d2  call    _LoadRegExtensions
0x1800037d7  xor     ecx, ecx
0x1800037d9  mov     [rsp+420h+var_3E0], esi
0x1800037dd  bt      esi, 1Ch
0x1800037e1  jb      short loc_18000383A
0x1800037e3  mov     edi, ecx
0x1800037e5  cmp     edi, cs:dword_180022FC0
0x1800037eb  jnb     short loc_180003838
0x1800037ed  mov     rax, cs:qword_180022FD8
0x1800037f4  mov     ecx, edi
0x1800037f6  mov     rax, [rax+rcx*8]
0x1800037fa  cmp     dword ptr [rax+18h], 1
0x1800037fe  jnz     short loc_180003834
0x180003800  mov     rax, [rax+8]
0x180003804  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000380a  mov     r8, [r12+8]; lpString1
0x18000380f  mov     edx, 1; dwCmpFlags
0x180003814  mov     [rsp+420h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000381c  xor     ecx, ecx; Locale
0x18000381e  mov     [rsp+420h+lpString2], rax; lpString2
0x180003823  call    cs:__imp_CompareStringW
0x18000382a  nop     dword ptr [rax+rax+00h]
0x18000382f  cmp     eax, 2
0x180003832  jz      short loc_180003893
0x180003834  inc     edi
0x180003836  jmp     short loc_1800037E5
0x180003838  xor     ecx, ecx
0x18000383a  mov     edi, ecx
0x18000383c  lea     r15, qword_180022180
0x180003843  cmp     edi, 11h
0x180003846  jnb     loc_180003E71
0x18000384c  mov     eax, edi
0x18000384e  lea     rcx, [rax+rax*8]
0x180003852  cmp     dword ptr [r15+rcx*8+18h], 1
0x180003858  jnz     short loc_18000388F
0x18000385a  mov     rax, [r15+rcx*8+8]
0x18000385f  mov     r9d, 0FFFFFFFFh; cchCount1
0x180003865  mov     r8, [r12+8]; lpString1
0x18000386a  xor     ecx, ecx; Locale
0x18000386c  mov     [rsp+420h+cchCount2], 0FFFFFFFFh; cchCount2
0x180003874  mov     edx, 1; dwCmpFlags
0x180003879  mov     [rsp+420h+lpString2], rax; lpString2
0x18000387e  call    cs:__imp_CompareStringW
0x180003885  nop     dword ptr [rax+rax+00h]
0x18000388a  cmp     eax, 2
0x18000388d  jz      short loc_180003893
0x18000388f  inc     edi
0x180003891  jmp     short loc_180003843
0x180003893  mov     r13d, esi
0x180003896  mov     edi, 23h ; '#'
0x18000389b  and     r13d, 1
0x18000389f  mov     dword ptr [rsp+420h+var_3DC+4], r13d
0x1800038a4  jz      loc_180003938
0x1800038aa  cmp     dword ptr [r14], 44444442h
0x1800038b1  jz      short loc_1800038FD
0x1800038b3  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800038ba  mov     edi, 80070057h
0x1800038bf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800038c4  mov     r8, rax
0x1800038c7  mov     r9d, 179h
0x1800038cd  mov     edx, edi
0x1800038cf  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800038d6  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800038db  mov     r13, [rsp+420h+lpMem]
0x1800038e0  mov     rax, [rbx+80h]
0x1800038e7  test    rax, rax
0x1800038ea  jz      loc_180003F0E
0x1800038f0  mov     rcx, rbx
0x1800038f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f8  jmp     loc_180003F0E
0x1800038fd  mov     r14, [rsp+420h+lpString]
0x180003902  mov     rcx, r14; lpString
0x180003905  call    cs:__imp_lstrlenW
0x18000390c  nop     dword ptr [rax+rax+00h]
0x180003911  cmp     eax, 2
0x180003914  jl      short loc_18000391C
0x180003916  cmp     di, [r14]
0x18000391a  jz      short loc_18000393D
0x18000391c  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180003923  mov     edi, 80070057h
0x180003928  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000392d  mov     r8, rax
0x180003930  mov     r9d, 180h
0x180003936  jmp     short loc_1800038CD
0x180003938  mov     r14, [rsp+420h+lpString]
0x18000393d  mov     rdi, [rsp+420h+var_3B8]
0x180003942  mov     rcx, rdi; lpString
0x180003945  call    cs:__imp_lstrlenW
0x18000394c  nop     dword ptr [rax+rax+00h]
0x180003951  mov     [rbp+320h+var_338], eax
0x180003954  mov     esi, eax
0x180003956  test    eax, eax
0x180003958  jz      short loc_1800039A8
0x18000395a  xor     r9d, r9d
0x18000395d  mov     [rbp+320h+var_340], rdi
0x180003961  mov     r8d, eax
0x180003964  mov     rdx, rdi
0x180003967  mov     rcx, rbx
0x18000396a  call    I_CryptXmlCheckUniqueId
0x18000396f  mov     edi, eax
0x180003971  test    eax, eax
0x180003973  jns     short loc_1800039A8
0x180003975  lea     r8, aOnecoreDsSecur_14+33h; ""
0x18000397c  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180003983  movzx   eax, byte ptr [r8-1]
0x180003988  mov     rdx, r8
0x18000398b  dec     r8
0x18000398e  cmp     al, 5Ch ; '\'
0x180003990  jz      short loc_180003999
0x180003992  cmp     r8, rcx
0x180003995  ja      short loc_180003983
0x180003997  cmp     al, 5Ch ; '\'
0x180003999  cmovz   r8, rdx
0x18000399d  mov     r9d, 192h
0x1800039a3  jmp     loc_1800038CD
0x1800039a8  test    r14, r14
0x1800039ab  jz      short loc_1800039C8
0x1800039ad  mov     rcx, r14; lpString
0x1800039b0  mov     [rbp+320h+var_330], r14
0x1800039b4  call    cs:__imp_lstrlenW
0x1800039bb  nop     dword ptr [rax+rax+00h]
0x1800039c0  mov     r15d, eax
0x1800039c3  mov     [rbp+320h+var_328], eax
0x1800039c6  jmp     short loc_1800039CC
0x1800039c8  mov     r15d, [rbp+320h+var_328]
0x1800039cc  mov     rcx, [rsp+420h+var_3B0]; lpString
0x1800039d1  call    cs:__imp_lstrlenW
0x1800039d8  nop     dword ptr [rax+rax+00h]
0x1800039dd  mov     rcx, [rbp+320h+var_320]
0x1800039e1  test    eax, eax
0x1800039e3  mov     r14d, eax
0x1800039e6  mov     [rbp+320h+var_318], eax
0x1800039e9  cmovnz  rcx, [rsp+420h+var_3B0]
0x1800039ef  mov     [rbp+320h+var_320], rcx
0x1800039f3  mov     rcx, [r12+8]; lpString
0x1800039f8  mov     [rbp+320h+var_310], rcx
0x1800039fc  call    cs:__imp_lstrlenW
0x180003a03  nop     dword ptr [rax+rax+00h]
0x180003a08  mov     r10, [rsp+420h+pXmlAlgorithm]
0x180003a0d  mov     r12d, eax
0x180003a10  mov     [rbp+320h+var_308], eax
0x180003a13  mov     eax, [rbp+320h+cTransform]
0x180003a19  mov     [rbp+320h+var_2E4], eax
0x180003a1c  mov     rcx, [r10+18h]
0x180003a20  mov     edx, [r10+14h]
0x180003a24  mov     [rbp+320h+var_2F8], rcx
0x180003a28  mov     ecx, [r10+10h]
0x180003a2c  mov     [rbp+320h+var_300], ecx
0x180003a2f  mov     [rbp+320h+var_2FC], edx
0x180003a32  test    edx, edx
0x180003a34  jnz     short loc_180003A94
0x180003a36  mov     edx, [rsp+420h+var_3E0]
0x180003a3a  lea     rax, [rsp+420h+var_3DC]
0x180003a3f  lea     r9, [rsp+420h+lpMem]
0x180003a44  mov     [rsp+420h+lpString2], rax; __int64
0x180003a49  mov     r8d, 1
0x180003a4f  mov     [rbp+320h+var_300], 1
0x180003a56  mov     rcx, r10; pXmlAlgorithm
0x180003a59  call    I_CryptXmlEncodeAlgorithmProxy
0x180003a5e  mov     edi, eax
0x180003a60  test    eax, eax
0x180003a62  jns     short loc_180003A7E
0x180003a64  lea     rcx, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180003a6b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180003a70  mov     r8, rax
0x180003a73  mov     r9d, 1B9h
0x180003a79  jmp     loc_1800038CD
0x180003a7e  mov     rax, [rsp+420h+lpMem]
0x180003a83  mov     [rbp+320h+var_2F8], rax
0x180003a87  mov     eax, dword ptr [rsp+420h+var_3DC]
0x180003a8b  mov     [rbp+320h+var_2FC], eax
0x180003a8e  mov     eax, [rbp+320h+cTransform]
0x180003a94  cmp     esi, 100h
0x180003a9a  ja      loc_180003E39
0x180003aa0  cmp     r15d, 2000h
0x180003aa7  ja      loc_180003E39
0x180003aad  cmp     r14d, 2000h
0x180003ab4  ja      loc_180003E39
0x180003aba  cmp     r12d, 2000h
0x180003ac1  ja      loc_180003E39
0x180003ac7  xor     r12d, r12d
0x180003aca  test    eax, eax
0x180003acc  jz      short loc_180003B33
0x180003ace  mov     r15d, [rbp+320h+cTransform]
0x180003ad5  xor     r14d, r14d
0x180003ad8  mov     r13, [rbp+320h+var_3A0]
0x180003adc  lea     rax, [r14+r14*4]
0x180003ae0  mov     rdi, r14
0x180003ae3  lea     rsi, ds:0[rax*8]
0x180003aeb  shl     rdi, 5
0x180003aef  mov     rcx, [rdi+r13+8]; lpString
0x180003af4  mov     [rbp+rsi+320h+var_2E0], rcx
0x180003af9  call    cs:__imp_lstrlenW
0x180003b00  nop     dword ptr [rax+rax+00h]
0x180003b05  mov     [rbp+rsi+320h+var_2D8], eax
0x180003b09  inc     r12d
0x180003b0c  mov     rax, [rdi+r13+18h]
0x180003b11  inc     r14
0x180003b14  mov     [rbp+rsi+320h+var_2C8], rax
0x180003b19  mov     eax, [rdi+r13+14h]
0x180003b1e  mov     [rbp+rsi+320h+var_2CC], eax
0x180003b22  cmp     r12d, r15d
0x180003b25  jb      short loc_180003ADC
0x180003b27  mov     r15d, [rbp+320h+var_328]
0x180003b2b  mov     esi, [rbp+320h+var_338]
0x180003b2e  mov     r13d, dword ptr [rsp+420h+var_3DC+4]
0x180003b33  mov     r12, [rbp+320h+var_398]
0x180003b37  lea     rax, [rsp+420h+var_3C8]
0x180003b3c  mov     r8d, [rsp+420h+var_3E0]
  ... truncated ...
```
