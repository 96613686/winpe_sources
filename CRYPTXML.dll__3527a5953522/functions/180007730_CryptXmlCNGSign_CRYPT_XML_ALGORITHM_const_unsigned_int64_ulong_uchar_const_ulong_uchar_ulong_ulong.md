# CryptXmlCNGSign(_CRYPT_XML_ALGORITHM const *,unsigned __int64,ulong,uchar const *,ulong,uchar *,ulong,ulong *)

- ea: `0x180007730`
- end: `0x180007fee`
- name: `?CryptXmlCNGSign@@YAJPEBU_CRYPT_XML_ALGORITHM@@_KKPEBEKPEAEKPEAK@Z`
- size: `2238`
- prototype: `__int64 __usercall@<rax>(const struct _CRYPT_XML_ALGORITHM *@<rcx>, unsigned __int64@<rdx>, unsigned int@<r8d>, const unsigned __int8 *@<r9>, ULONG cbInput, PBYTE pbSignature, DWORD cbSignature, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180007730`
- `0x180008078`
- `0x18000f200`
- `0x180014854`
- `0x180014ce0`
- `0x1800185f5`
- `0x180018640`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800078e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800078e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f4f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800077f4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800078c8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800077f4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800078c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078fc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007f7b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180007f7b`
- `bcrypt!BCryptGetProperty` at `0x180007b00`
- `bcrypt!BCryptGetProperty` at `0x180007c25`
- `bcrypt!BCryptGetProperty` at `0x180007b00`
- `bcrypt!BCryptGetProperty` at `0x180007c25`
- `bcrypt!BCryptFinishHash` at `0x180007dfc`
- `bcrypt!BCryptFinishHash` at `0x180007dfc`
- `bcrypt!BCryptDestroyHash` at `0x180007f64`
- `bcrypt!BCryptDestroyHash` at `0x180007f64`
- `bcrypt!BCryptHashData` at `0x180007da8`
- `bcrypt!BCryptHashData` at `0x180007da8`
- `bcrypt!BCryptCreateHash` at `0x180007d50`
- `bcrypt!BCryptCreateHash` at `0x180007d50`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800079ac`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800079ac`
- `ncrypt!NCryptIsKeyHandle` at `0x18000797f`
- `ncrypt!NCryptIsKeyHandle` at `0x18000797f`
- `ncrypt!NCryptTranslateHandle` at `0x180007a94`
- `ncrypt!NCryptTranslateHandle` at `0x180007a94`
- `ncrypt!NCryptSignHash` at `0x180007e77`
- `ncrypt!NCryptSignHash` at `0x180007e77`

## string_xrefs

- `0x180007993`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x180007a4d`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x180007f23`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x180007837`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180007917`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180007ec4`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x180007eec`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x1800079e7`: `BCryptOpenAlgorithmProvider`
- `0x180007d78`: `BCryptCreateHash`
- `0x180007a66`: `CryptXmlCAPI1Sign`

## pseudocode

```c
__int64 __fastcall CryptXmlCNGSign(
        const struct _CRYPT_XML_ALGORITHM *a1,
        NCRYPT_KEY_HANDLE a2,
        unsigned int a3,
        UCHAR *a4,
        ULONG cbInput,
        PBYTE pbSignature,
        DWORD cbSignature,
        unsigned int *a8)
{
  UCHAR *p_hMem; // rdi
  UCHAR *v12; // r15
  unsigned int i; // ebx
  const WCHAR *wszAlgorithm; // r8
  int (__fastcall *v15)(const struct _CRYPT_XML_ALGORITHM *, HLOCAL *); // rax
  const char *v16; // rax
  int v17; // r10d
  unsigned int j; // ebx
  const WCHAR *v19; // r8
  _OWORD *v20; // rax
  signed int LastError; // eax
  int v22; // ebx
  const char *v23; // rax
  unsigned __int64 v24; // rcx
  NTSTATUS v25; // ebx
  const char *v26; // r8
  char v27; // al
  const char *v28; // rcx
  bool v29; // zf
  const char *v30; // rax
  SECURITY_STATUS v31; // eax
  const char *v32; // rax
  NTSTATUS Property; // eax
  const char *v34; // rax
  unsigned __int64 v35; // rbx
  __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  void *v38; // rsp
  void *v39; // rsp
  UCHAR *v40; // rax
  const char *v41; // rax
  int v42; // r9d
  NTSTATUS v43; // ebx
  const char *v44; // r8
  char v45; // al
  const char *v46; // rcx
  bool v47; // zf
  unsigned __int64 v48; // rbx
  __int64 v49; // rcx
  unsigned __int64 v50; // rcx
  void *v51; // rsp
  void *v52; // rsp
  UCHAR *v53; // rax
  NTSTATUS v54; // eax
  const char *v55; // rax
  NTSTATUS v56; // eax
  const char *v57; // rax
  NTSTATUS v58; // eax
  const char *v59; // rax
  SECURITY_STATUS v60; // eax
  const char *v61; // rax
  const char *v62; // r8
  int v63; // r9d
  char v64; // cl
  const char *v65; // rdx
  bool v66; // zf
  _BYTE v68[32]; // [rsp+0h] [rbp-40h] BYREF
  UCHAR v69[4]; // [rsp+40h] [rbp+0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp+8h] BYREF
  UCHAR pbOutput[4]; // [rsp+50h] [rbp+10h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp+14h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp+18h] BYREF
  unsigned __int64 v74; // [rsp+60h] [rbp+20h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+68h] [rbp+28h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp+30h] BYREF
  PUCHAR pbInput; // [rsp+78h] [rbp+38h]

  v29 = dword_180022FC8 == 0;
  pbInput = a4;
  phAlgorithm = 0;
  *a8 = 0;
  p_hMem = 0;
  phHash = 0;
  v12 = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v69 = 0;
  pcbResult = 0;
  phKey = 0;
  hMem = 0;
  if ( v29 )
    LoadRegExtensions();
  if ( a1 )
  {
    hMem = 0;
    for ( i = 0; i < dword_180022FC0; ++i )
    {
      wszAlgorithm = a1->wszAlgorithm;
      v74 = 8LL * i;
      if ( CompareStringW(0, 1u, wszAlgorithm, -1, *(PCNZWCH *)(*(_QWORD *)((char *)qword_180022FD8 + v74) + 8LL), -1) == 2 )
      {
        v15 = *(int (__fastcall **)(const struct _CRYPT_XML_ALGORITHM *, HLOCAL *))(*(_QWORD *)((char *)qword_180022FD8
                                                                                              + v74)
                                                                                  + 152LL);
        if ( v15 )
        {
          if ( v15(a1, &hMem) >= 0 )
            goto LABEL_22;
          v16 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v17, v16, 1118);
          if ( hMem )
          {
            LocalFree(hMem);
            hMem = 0;
          }
        }
      }
    }
    for ( j = 0; ; ++j )
    {
      if ( j >= 0x11 )
      {
        v22 = -2146885372;
        v62 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        v63 = 1167;
        goto LABEL_88;
      }
      v19 = a1->wszAlgorithm;
      v74 = 72LL * j;
      if ( CompareStringW(0, 1u, v19, -1, (PCNZWCH)qword_180022180[v74 / 8 + 1], -1) == 2 )
        break;
    }
    v20 = LocalAlloc(0x40u, 0x48u);
    hMem = v20;
    if ( v20 )
    {
      v24 = v74;
      *v20 = *(_OWORD *)&qword_180022180[v74 / 8];
      v20[1] = *(_OWORD *)((char *)&qword_180022180[2] + v24);
      v20[2] = *(_OWORD *)((char *)&qword_180022180[4] + v24);
      v20[3] = *(_OWORD *)((char *)&qword_180022180[6] + v24);
      *((_QWORD *)v20 + 8) = *(__int64 *)((char *)&qword_180022180[8] + v24);
      goto LABEL_22;
    }
    LastError = GetLastError();
    v22 = LastError;
    if ( LastError > 0 )
      v22 = (unsigned __int16)LastError | 0x80070000;
    v23 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v22, v23, 1155);
    if ( v22 < 0 )
      goto LABEL_89;
LABEL_22:
    if ( NCryptIsKeyHandle(a2) )
    {
      phKey = a2;
    }
    else
    {
      v22 = CryptXmlCAPI1Sign(a1, a2, a3, pbInput, cbInput, pbSignature, cbSignature, a8);
      if ( v22 >= 0 )
        goto LABEL_91;
      v30 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v22, v30, 379, "CryptXmlCAPI1Sign");
      v31 = NCryptTranslateHandle(0, &phKey, a2, 0, a3, 0);
      if ( v31 < 0 )
      {
        v22 = v31 | 0x10000000;
        v32 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v22, v32, 397, "NCryptTranslateHandle");
        goto LABEL_91;
      }
    }
    v25 = BCryptOpenAlgorithmProvider(&phAlgorithm, *((LPCWSTR *)hMem + 4), 0, 0);
    if ( v25 >= 0 )
    {
      Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
      if ( Property < 0 )
      {
        v22 = Property | 0x10000000;
        v34 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v22, v34, 435, "BCryptGetProperty");
        goto LABEL_91;
      }
      v35 = *(unsigned int *)pbOutput;
      if ( !*(_DWORD *)pbOutput
        || *(unsigned int *)pbOutput > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)*(unsigned int *)pbOutput + g_ulAdditionalProbeSize + 8 < *(unsigned int *)pbOutput
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_108;
      }
      v36 = v35 + 23;
      if ( v35 + 23 <= v35 + 8 )
        v36 = 0xFFFFFFFFFFFFFF0LL;
      v37 = v36 & 0xFFFFFFFFFFFFFFF0uLL;
      v38 = alloca(v37);
      v39 = alloca(v37);
      p_hMem = v69;
      if ( v68 == (_BYTE *)-64LL || (*(_DWORD *)v69 = 1801679955, (p_hMem = (UCHAR *)&hMem) == 0) )
      {
LABEL_108:
        if ( v35 + 8 >= v35 )
        {
          v40 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          p_hMem = v40;
          if ( v40 )
          {
            *(_DWORD *)v40 = 1885431112;
            p_hMem = v40 + 8;
          }
        }
      }
      if ( !p_hMem )
      {
        v22 = -2147024888;
        v41 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
        v42 = 444;
        goto LABEL_90;
      }
      v43 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v69, 4u, &pcbResult, 0);
      if ( v43 >= 0 )
      {
        v48 = *(unsigned int *)v69;
        if ( !*(_DWORD *)v69
          || *(unsigned int *)v69 > (unsigned __int64)g_ulMaxStackAllocSize
          || (unsigned __int64)*(unsigned int *)v69 + g_ulAdditionalProbeSize + 8 < *(unsigned int *)v69
          || !(unsigned int)VerifyStackAvailable() )
        {
          goto LABEL_109;
        }
        v49 = v48 + 23;
        if ( v48 + 23 <= v48 + 8 )
          v49 = 0xFFFFFFFFFFFFFF0LL;
        v50 = v49 & 0xFFFFFFFFFFFFFFF0uLL;
        v51 = alloca(v50);
        v52 = alloca(v50);
        v12 = v69;
        if ( v68 == (_BYTE *)-64LL || (*(_DWORD *)v69 = 1801679955, (v12 = (UCHAR *)&hMem) == 0) )
        {
LABEL_109:
          if ( v48 + 8 >= v48 )
          {
            v53 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
            v12 = v53;
            if ( v53 )
            {
              *(_DWORD *)v53 = 1885431112;
              v12 = v53 + 8;
            }
          }
        }
        if ( !v12 )
        {
          v22 = -2147024888;
          v41 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
          v42 = 468;
          goto LABEL_90;
        }
        v54 = BCryptCreateHash(phAlgorithm, &phHash, p_hMem, *(ULONG *)pbOutput, 0, 0, 0);
        if ( v54 >= 0 )
        {
          v56 = BCryptHashData(phHash, pbInput, cbInput, 0);
          if ( v56 >= 0 )
          {
            v58 = BCryptFinishHash(phHash, v12, *(ULONG *)v69, 0);
            if ( v58 >= 0 )
            {
              v60 = NCryptSignHash(
                      phKey,
                      *((void **)hMem + 7),
                      v12,
                      *(DWORD *)v69,
                      pbSignature,
                      cbSignature,
                      a8,
                      *((_DWORD *)hMem + 12));
              if ( v60 >= 0 )
              {
                v22 = 0;
              }
              else
              {
                v22 = v60 | 0x10000000;
                v61 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
                WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v22, v61, 532, "NCryptSignHash");
              }
            }
            else
            {
              v22 = v58 | 0x10000000;
              v59 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
              WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v22, v59, 510, "BCryptFinishHash");
            }
          }
          else
          {
            v22 = v56 | 0x10000000;
            v57 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v22, v57, 497, "BCryptHashData");
          }
        }
        else
        {
          v22 = v54 | 0x10000000;
          v55 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v22, v55, 484, "BCryptCreateHash");
        }
      }
      else
      {
        v22 = v43 | 0x10000000;
        v44 = "";
        while ( 1 )
        {
          v45 = *(v44 - 1);
          v46 = v44--;
          v47 = v45 == 92;
          if ( v45 == 92 )
            break;
          if ( v44 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp" )
          {
            v47 = v45 == 92;
            break;
          }
        }
        if ( v47 )
          v44 = v46;
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v22, v44, 459, "BCryptGetProperty");
      }
    }
    else
    {
      v22 = v25 | 0x10000000;
      v26 = "";
      while ( 1 )
      {
        v27 = *(v26 - 1);
        v28 = v26--;
        v29 = v27 == 92;
        if ( v27 == 92 )
          break;
        if ( v26 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp" )
        {
          v29 = v27 == 92;
          break;
        }
      }
      if ( v29 )
        v26 = v28;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v22, v26, 420, "BCryptOpenAlgorithmProvider");
    }
  }
  else
  {
    v22 = -2147024809;
    v62 = "";
    while ( 1 )
    {
      v64 = *(v62 - 1);
      v65 = v62--;
      v66 = v64 == 92;
      if ( v64 == 92 )
        break;
      if ( v62 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
      {
        v66 = v64 == 92;
        break;
      }
    }
    if ( v66 )
      v62 = v65;
    v63 = 1086;
LABEL_88:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v22, v62, v63);
LABEL_89:
    v41 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
    v42 = 352;
LABEL_90:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v22, v41, v42);
  }
LABEL_91:
  if ( hMem )
    LocalFree(hMem);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v12 && *((_DWORD *)v12 - 2) == 1885431112 )
    ((void (__fastcall *)(UCHAR *))g_pfnFree)(v12 - 8);
  if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
    ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_hMem - 8);
  if ( v22 < 0 )
    return (unsigned int)-2146885364;
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180007730  push    rbp
0x180007732  push    rbx
0x180007733  push    rsi
0x180007734  push    rdi
0x180007735  push    r12
0x180007737  push    r13
0x180007739  push    r14
0x18000773b  push    r15
0x18000773d  sub     rsp, 98h
0x180007744  lea     rbp, [rsp+40h]
0x180007749  mov     rax, cs:__security_cookie
0x180007750  xor     rax, rbp
0x180007753  mov     [rbp+90h+var_50], rax
0x180007757  mov     r12, [rbp+90h+arg_38]
0x18000775e  xor     eax, eax
0x180007760  cmp     cs:dword_180022FC8, eax
0x180007766  mov     r13d, r8d
0x180007769  mov     [rbp+90h+pbInput], r9
0x18000776d  mov     rsi, rdx
0x180007770  mov     r14, rcx
0x180007773  mov     [rbp+90h+phAlgorithm], rax
0x180007777  mov     [r12], eax
0x18000777b  mov     edi, eax
0x18000777d  mov     [rbp+90h+phHash], rax
0x180007781  mov     r15d, eax
0x180007784  mov     dword ptr [rbp+90h+pbOutput], eax
0x180007787  mov     dword ptr [rbp+90h+var_90], eax
0x18000778a  mov     [rbp+90h+pcbResult], eax
0x18000778d  mov     [rbp+90h+phKey], rax
0x180007791  mov     [rbp+90h+hMem], rax
0x180007795  jnz     short loc_18000779E
0x180007797  call    _LoadRegExtensions
0x18000779c  xor     eax, eax
0x18000779e  test    r14, r14
0x1800077a1  jz      loc_180007EE0
0x1800077a7  mov     [rbp+90h+hMem], rax
0x1800077ab  mov     ebx, eax
0x1800077ad  cmp     ebx, cs:dword_180022FC0
0x1800077b3  jnb     loc_180007881
0x1800077b9  mov     r8, [r14+8]; lpString1
0x1800077bd  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800077c3  mov     eax, ebx
0x1800077c5  mov     edx, 1; dwCmpFlags
0x1800077ca  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800077d2  lea     rcx, ds:0[rax*8]
0x1800077da  mov     rax, cs:qword_180022FD8
0x1800077e1  mov     [rbp+90h+var_70], rcx
0x1800077e5  mov     rax, [rcx+rax]
0x1800077e9  xor     ecx, ecx; Locale
0x1800077eb  mov     rax, [rax+8]
0x1800077ef  mov     [rsp+0D0h+lpString2], rax; lpString2
0x1800077f4  call    cs:__imp_CompareStringW
0x1800077fb  nop     dword ptr [rax+rax+00h]
0x180007800  cmp     eax, 2
0x180007803  jnz     short loc_180007878
0x180007805  mov     rax, cs:qword_180022FD8
0x18000780c  mov     rcx, [rbp+90h+var_70]
0x180007810  mov     rcx, [rcx+rax]
0x180007814  mov     rax, [rcx+98h]
0x18000781b  test    rax, rax
0x18000781e  jz      short loc_180007878
0x180007820  lea     rdx, [rbp+90h+hMem]
0x180007824  mov     rcx, r14
0x180007827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782c  mov     r10d, eax
0x18000782f  test    eax, eax
0x180007831  jns     loc_18000797C
0x180007837  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000783e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007843  mov     r8, rax
0x180007846  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000784d  mov     edx, r10d
0x180007850  mov     r9d, 45Eh
0x180007856  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000785b  mov     rcx, [rbp+90h+hMem]; hMem
0x18000785f  test    rcx, rcx
0x180007862  jz      short loc_180007878
0x180007864  call    cs:__imp_LocalFree
0x18000786b  nop     dword ptr [rax+rax+00h]
0x180007870  xor     eax, eax
0x180007872  mov     [rbp+90h+hMem], rax
0x180007876  jmp     short loc_18000787A
0x180007878  xor     eax, eax
0x18000787a  inc     ebx
0x18000787c  jmp     loc_1800077AD
0x180007881  mov     ebx, eax
0x180007883  lea     rdx, qword_180022180
0x18000788a  cmp     ebx, 11h
0x18000788d  jnb     loc_180007EC4
0x180007893  mov     r8, [r14+8]; lpString1
0x180007897  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000789d  mov     eax, ebx
0x18000789f  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800078a7  lea     rcx, [rax+rax*8]
0x1800078ab  lea     rax, ds:0[rcx*8]
0x1800078b3  mov     [rbp+90h+var_70], rax
0x1800078b7  mov     rax, [rdx+rcx*8+8]
0x1800078bc  mov     edx, 1; dwCmpFlags
0x1800078c1  xor     ecx, ecx; Locale
0x1800078c3  mov     [rsp+0D0h+lpString2], rax; lpString2
0x1800078c8  call    cs:__imp_CompareStringW
0x1800078cf  nop     dword ptr [rax+rax+00h]
0x1800078d4  cmp     eax, 2
0x1800078d7  jz      short loc_1800078DD
0x1800078d9  inc     ebx
0x1800078db  jmp     short loc_180007883
0x1800078dd  mov     edx, 48h ; 'H'; uBytes
0x1800078e2  mov     ecx, 40h ; '@'; uFlags
0x1800078e7  call    cs:__imp_LocalAlloc
0x1800078ee  nop     dword ptr [rax+rax+00h]
0x1800078f3  mov     [rbp+90h+hMem], rax
0x1800078f7  test    rax, rax
0x1800078fa  jnz     short loc_180007944
0x1800078fc  call    cs:__imp_GetLastError
0x180007903  nop     dword ptr [rax+rax+00h]
0x180007908  mov     ebx, eax
0x18000790a  test    eax, eax
0x18000790c  jle     short loc_180007917
0x18000790e  movzx   ebx, ax
0x180007911  or      ebx, 80070000h
0x180007917  lea     rcx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000791e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007923  mov     r8, rax
0x180007926  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000792d  mov     edx, ebx
0x18000792f  mov     r9d, 483h
0x180007935  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000793a  test    ebx, ebx
0x18000793c  js      loc_180007F23
0x180007942  jmp     short loc_18000797C
0x180007944  mov     rcx, [rbp+90h+var_70]
0x180007948  lea     rdx, qword_180022180
0x18000794f  movups  xmm0, xmmword ptr [rcx+rdx]
0x180007953  movups  xmmword ptr [rax], xmm0
0x180007956  movups  xmm1, xmmword ptr [rcx+rdx+10h]
0x18000795b  movups  xmmword ptr [rax+10h], xmm1
0x18000795f  movups  xmm0, xmmword ptr [rcx+rdx+20h]
0x180007964  movups  xmmword ptr [rax+20h], xmm0
0x180007968  movups  xmm1, xmmword ptr [rcx+rdx+30h]
0x18000796d  movups  xmmword ptr [rax+30h], xmm1
0x180007971  movsd   xmm0, qword ptr [rcx+rdx+40h]
0x180007977  movsd   qword ptr [rax+40h], xmm0
0x18000797c  mov     rcx, rsi; hKey
0x18000797f  call    cs:__imp_NCryptIsKeyHandle
0x180007986  nop     dword ptr [rax+rax+00h]
0x18000798b  test    eax, eax
0x18000798d  jz      short loc_180007A0C
0x18000798f  mov     [rbp+90h+phKey], rsi
0x180007993  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000799a  mov     rdx, [rbp+90h+hMem]
0x18000799e  lea     rcx, [rbp+90h+phAlgorithm]; phAlgorithm
0x1800079a2  xor     r9d, r9d; dwFlags
0x1800079a5  xor     r8d, r8d; pszImplementation
0x1800079a8  mov     rdx, [rdx+20h]; pszAlgId
0x1800079ac  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800079b3  nop     dword ptr [rax+rax+00h]
0x1800079b8  mov     ebx, eax
0x1800079ba  test    eax, eax
0x1800079bc  jns     loc_180007ADE
0x1800079c2  bts     ebx, 1Ch
0x1800079c6  lea     r8, aOnecoreDsSecur_2+2Dh; ""
0x1800079cd  movzx   eax, byte ptr [r8-1]
0x1800079d2  mov     rcx, r8
0x1800079d5  dec     r8
0x1800079d8  cmp     al, 5Ch ; '\'
0x1800079da  jz      short loc_1800079E3
0x1800079dc  cmp     r8, r14
0x1800079df  ja      short loc_1800079CD
0x1800079e1  cmp     al, 5Ch ; '\'
0x1800079e3  cmovz   r8, rcx
0x1800079e7  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x1800079ee  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x1800079f5  mov     [rsp+0D0h+lpString2], rax
0x1800079fa  mov     r9d, 1A4h
0x180007a00  mov     edx, ebx
0x180007a02  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180007a07  jmp     loc_180007F46
0x180007a0c  mov     eax, [rbp+90h+cbSignature]
0x180007a12  mov     r8d, r13d; unsigned int
0x180007a15  mov     r9, [rbp+90h+pbInput]; unsigned __int8 *
0x180007a19  mov     rdx, rsi; unsigned __int64
0x180007a1c  mov     qword ptr [rsp+0D0h+var_98], r12; unsigned int *
0x180007a21  mov     rcx, r14; struct _CRYPT_XML_ALGORITHM *
0x180007a24  mov     [rsp+0D0h+dwFlags], eax; unsigned int
0x180007a28  mov     rax, [rbp+90h+pbSignature]
0x180007a2f  mov     qword ptr [rsp+0D0h+cchCount2], rax; unsigned __int8 *
0x180007a34  mov     eax, [rbp+90h+cbInput]
0x180007a3a  mov     dword ptr [rsp+0D0h+lpString2], eax; unsigned int
0x180007a3e  call    ?CryptXmlCAPI1Sign@@YAJPEBU_CRYPT_XML_ALGORITHM@@_KKPEBEKPEAEKPEAK@Z; CryptXmlCAPI1Sign(_CRYPT_XML_ALGORITHM const *,unsigned __int64,ulong,uchar const *,ulong,uchar *,ulong,ulong *)
0x180007a43  mov     ebx, eax
0x180007a45  test    eax, eax
0x180007a47  jns     loc_180007F46
0x180007a4d  lea     r14, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180007a54  mov     rcx, r14; char *
0x180007a57  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007a5c  mov     r8, rax
0x180007a5f  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x180007a66  lea     rax, aCryptxmlcapi1s; "CryptXmlCAPI1Sign"
0x180007a6d  mov     r9d, 17Bh
0x180007a73  mov     edx, ebx
0x180007a75  mov     [rsp+0D0h+lpString2], rax
0x180007a7a  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180007a7f  xor     r9d, r9d; hLegacyKey
0x180007a82  mov     [rsp+0D0h+cchCount2], edi; dwFlags
0x180007a86  mov     r8, rsi; hLegacyProv
0x180007a89  mov     dword ptr [rsp+0D0h+lpString2], r13d; dwLegacyKeySpec
0x180007a8e  lea     rdx, [rbp+90h+phKey]; phKey
0x180007a92  xor     ecx, ecx; phProvider
0x180007a94  call    cs:__imp_NCryptTranslateHandle
0x180007a9b  nop     dword ptr [rax+rax+00h]
0x180007aa0  mov     ebx, eax
0x180007aa2  test    eax, eax
0x180007aa4  jns     loc_18000799A
0x180007aaa  mov     rcx, r14; char *
0x180007aad  bts     ebx, 1Ch
0x180007ab1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007ab6  mov     r8, rax
0x180007ab9  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x180007ac0  lea     rax, aNcrypttranslat_0; "NCryptTranslateHandle"
0x180007ac7  mov     r9d, 18Dh
0x180007acd  mov     edx, ebx
0x180007acf  mov     [rsp+0D0h+lpString2], rax
0x180007ad4  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180007ad9  jmp     loc_180007F46
0x180007ade  mov     rcx, [rbp+90h+phAlgorithm]; hObject
0x180007ae2  lea     rax, [rbp+90h+pcbResult]
0x180007ae6  mov     [rsp+0D0h+cchCount2], edi; dwFlags
0x180007aea  lea     r8, [rbp+90h+pbOutput]; pbOutput
0x180007aee  mov     r9d, 4; cbOutput
0x180007af4  mov     [rsp+0D0h+lpString2], rax; pcbResult
0x180007af9  lea     rdx, pszProperty; "ObjectLength"
0x180007b00  call    cs:__imp_BCryptGetProperty
0x180007b07  nop     dword ptr [rax+rax+00h]
0x180007b0c  mov     ebx, eax
0x180007b0e  test    eax, eax
0x180007b10  jns     short loc_180007B46
0x180007b12  mov     rcx, r14; char *
0x180007b15  bts     ebx, 1Ch
0x180007b19  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007b1e  mov     r8, rax
0x180007b21  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x180007b28  lea     rax, aBcryptgetprope_0; "BCryptGetProperty"
0x180007b2f  mov     r9d, 1B3h
0x180007b35  mov     edx, ebx
0x180007b37  mov     [rsp+0D0h+lpString2], rax
0x180007b3c  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180007b41  jmp     loc_180007F46
0x180007b46  mov     ebx, dword ptr [rbp+90h+pbOutput]
0x180007b49  test    rbx, rbx
0x180007b4c  jz      short loc_180007BB4
0x180007b4e  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180007b55  ja      short loc_180007BB4
0x180007b57  mov     rcx, cs:g_ulAdditionalProbeSize
0x180007b5e  add     rcx, 8
0x180007b62  add     rcx, rbx
0x180007b65  cmp     rcx, rbx
0x180007b68  jb      short loc_180007BB4
0x180007b6a  call    VerifyStackAvailable
0x180007b6f  test    eax, eax
0x180007b71  jz      short loc_180007BB4
0x180007b73  lea     rax, [rbx+8]
0x180007b77  mov     rsi, 0FFFFFFFFFFFFFF0h
0x180007b81  lea     rcx, [rax+0Fh]
0x180007b85  cmp     rcx, rax
0x180007b88  ja      short loc_180007B8D
0x180007b8a  mov     rcx, rsi
0x180007b8d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180007b91  mov     rax, rcx
0x180007b94  call    __chkstk_0
0x180007b99  sub     rsp, rcx
0x180007b9c  lea     rdi, [rsp+0D0h+var_90]
0x180007ba1  test    rdi, rdi
0x180007ba4  jz      short loc_180007BBE
0x180007ba6  mov     dword ptr [rdi], 6B637453h
0x180007bac  add     rdi, 8
0x180007bb0  jz      short loc_180007BBE
0x180007bb2  jmp     short loc_180007BE5
0x180007bb4  mov     rsi, 0FFFFFFFFFFFFFF0h
0x180007bbe  lea     rcx, [rbx+8]
0x180007bc2  cmp     rcx, rbx
0x180007bc5  jb      short loc_180007BE5
0x180007bc7  mov     rax, cs:g_pfnAllocate
0x180007bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bd3  mov     rdi, rax
0x180007bd6  test    rax, rax
0x180007bd9  jz      short loc_180007BE5
0x180007bdb  mov     dword ptr [rax], 70616548h
0x180007be1  add     rdi, 8
0x180007be5  test    rdi, rdi
0x180007be8  jnz     short loc_180007C02
0x180007bea  mov     rcx, r14; char *
0x180007bed  mov     ebx, 80070008h
0x180007bf2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180007bf7  mov     r9d, 1BCh
0x180007bfd  jmp     loc_180007F35
0x180007c02  mov     rcx, [rbp+90h+phAlgorithm]; hObject
0x180007c06  lea     rax, [rbp+90h+pcbResult]
0x180007c0a  mov     [rsp+0D0h+cchCount2], r15d; dwFlags
0x180007c0f  lea     r8, [rbp+90h+var_90]; pbOutput
0x180007c13  mov     r9d, 4; cbOutput
  ... truncated ...
```
