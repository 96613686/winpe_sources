# CryptXmlCNGVerifySignature(_CRYPT_XML_ALGORITHM const *,void *,uchar const *,ulong,uchar const *,ulong)

- ea: `0x180004f90`
- end: `0x180005790`
- name: `?CryptXmlCNGVerifySignature@@YAJPEBU_CRYPT_XML_ALGORITHM@@PEAXPEBEK2K@Z`
- size: `2048`
- prototype: `int(const struct _CRYPT_XML_ALGORITHM *, void *, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004f90`
- `0x1800070d0`
- `0x180008078`
- `0x18000f200`
- `0x180014ce0`
- `0x1800185f5`
- `0x180018640`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005137`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005137`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056f2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000504b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005117`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000504b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000514c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000514c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000571e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000571e`
- `bcrypt!BCryptGetProperty` at `0x18000524f`
- `bcrypt!BCryptGetProperty` at `0x18000537f`
- `bcrypt!BCryptGetProperty` at `0x18000524f`
- `bcrypt!BCryptGetProperty` at `0x18000537f`
- `bcrypt!BCryptFinishHash` at `0x18000558f`
- `bcrypt!BCryptFinishHash` at `0x18000558f`
- `bcrypt!BCryptDestroyHash` at `0x180005707`
- `bcrypt!BCryptDestroyHash` at `0x180005707`
- `bcrypt!BCryptHashData` at `0x18000551e`
- `bcrypt!BCryptHashData` at `0x18000551e`
- `bcrypt!BCryptCreateHash` at `0x1800054ad`
- `bcrypt!BCryptCreateHash` at `0x1800054ad`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800051df`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800051df`
- `bcrypt!BCryptVerifySignature` at `0x180005609`
- `bcrypt!BCryptVerifySignature` at `0x180005609`

## string_xrefs

- `0x1800051f1`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x180005261`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x18000533d`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x18000539c`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x180005470`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x1800054ca`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x18000553b`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x1800055a1`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x18000561b`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x1800056b4`: `onecore\ds\security\cryptoapi\xml\lib\cng.cpp`
- `0x180004fef`: `onecore\ds\security\cryptoapi\xml\lib\crypto.cpp`
- `0x18000520b`: `BCryptOpenAlgorithmProvider`
- `0x1800054eb`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall CryptXmlCNGVerifySignature(
        const struct _CRYPT_XML_ALGORITHM *a1,
        void *a2,
        UCHAR *a3,
        ULONG a4,
        UCHAR *pbSignature,
        ULONG cbSignature)
{
  UCHAR *p_hMem; // rsi
  UCHAR *v9; // rdi
  unsigned int i; // r14d
  __int64 v11; // r12
  int (__fastcall *v12)(const struct _CRYPT_XML_ALGORITHM *, HLOCAL *); // rax
  const char *v13; // rax
  int v14; // r10d
  unsigned int j; // r14d
  __int64 v16; // r12
  _OWORD *v17; // rax
  signed int LastError; // eax
  int v19; // ebx
  const char *v20; // rax
  NTSTATUS v21; // eax
  const char *v22; // rax
  NTSTATUS Property; // eax
  const char *v24; // rax
  unsigned __int64 v25; // rbx
  __int64 v26; // rcx
  unsigned __int64 v27; // rcx
  void *v28; // rsp
  void *v29; // rsp
  UCHAR *v30; // rax
  const char *v31; // r8
  int v32; // r9d
  NTSTATUS v33; // ebx
  const char *v34; // r8
  char v35; // al
  const char *v36; // rdx
  bool v37; // zf
  unsigned __int64 v38; // rbx
  __int64 v39; // rcx
  unsigned __int64 v40; // rcx
  void *v41; // rsp
  void *v42; // rsp
  UCHAR *v43; // rax
  NTSTATUS v44; // ebx
  const char *v45; // r8
  char v46; // al
  const char *v47; // rdx
  bool v48; // zf
  NTSTATUS v49; // ebx
  const char *v50; // r8
  char v51; // al
  const char *v52; // rdx
  bool v53; // zf
  NTSTATUS v54; // eax
  const char *v55; // rax
  NTSTATUS v56; // eax
  const char *v57; // rax
  const char *v58; // r8
  int v59; // r9d
  char v60; // al
  const char *v61; // rcx
  bool v62; // zf
  char v63; // al
  const char *v64; // rdx
  bool v65; // zf
  _BYTE v67[32]; // [rsp+0h] [rbp-40h] BYREF
  UCHAR v68[4]; // [rsp+40h] [rbp+0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp+8h] BYREF
  UCHAR pbOutput[4]; // [rsp+50h] [rbp+10h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp+14h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp+18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp+20h] BYREF
  PUCHAR pbInput; // [rsp+68h] [rbp+28h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+70h] [rbp+30h]

  pbInput = a3;
  hKey = a2;
  phAlgorithm = 0;
  p_hMem = 0;
  phHash = 0;
  v9 = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v68 = 0;
  pcbResult = 0;
  hMem = 0;
  if ( !dword_180022FC8 )
    LoadRegExtensions();
  if ( a1 )
  {
    hMem = 0;
    for ( i = 0; i < dword_180022FC0; ++i )
    {
      v11 = 8LL * i;
      if ( CompareStringW(
             0,
             1u,
             a1->wszAlgorithm,
             -1,
             *(PCNZWCH *)(*(_QWORD *)((char *)qword_180022FD8 + v11) + 8LL),
             -1) == 2 )
      {
        v12 = *(int (__fastcall **)(const struct _CRYPT_XML_ALGORITHM *, HLOCAL *))(*(_QWORD *)((char *)qword_180022FD8
                                                                                              + v11)
                                                                                  + 152LL);
        if ( v12 )
        {
          if ( v12(a1, &hMem) >= 0 )
            goto LABEL_22;
          v13 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v14, v13, 1118);
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
        v19 = -2146885372;
        v58 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
        v59 = 1167;
        goto LABEL_89;
      }
      v16 = 9LL * j;
      if ( CompareStringW(0, 1u, a1->wszAlgorithm, -1, (PCNZWCH)qword_180022180[v16 + 1], -1) == 2 )
        break;
    }
    v17 = LocalAlloc(0x40u, 0x48u);
    hMem = v17;
    if ( v17 )
    {
      *v17 = *(_OWORD *)&qword_180022180[v16];
      v17[1] = *(_OWORD *)&qword_180022180[v16 + 2];
      v17[2] = *(_OWORD *)&qword_180022180[v16 + 4];
      v17[3] = *(_OWORD *)&qword_180022180[v16 + 6];
      *((_QWORD *)v17 + 8) = qword_180022180[v16 + 8];
      goto LABEL_22;
    }
    LastError = GetLastError();
    v19 = LastError;
    if ( LastError > 0 )
      v19 = (unsigned __int16)LastError | 0x80070000;
    v20 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v19, v20, 1155);
    if ( v19 < 0 )
      goto LABEL_90;
LABEL_22:
    v21 = BCryptOpenAlgorithmProvider(&phAlgorithm, *((LPCWSTR *)hMem + 4), L"Microsoft Primitive Provider", 0);
    if ( v21 < 0 )
    {
      v19 = v21 | 0x10000000;
      v22 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v19, v22, 627, "BCryptOpenAlgorithmProvider");
      goto LABEL_98;
    }
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
    {
      v19 = Property | 0x10000000;
      v24 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v19, v24, 642, "BCryptGetProperty");
      goto LABEL_98;
    }
    v25 = *(unsigned int *)pbOutput;
    if ( !*(_DWORD *)pbOutput
      || *(unsigned int *)pbOutput > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)*(unsigned int *)pbOutput + g_ulAdditionalProbeSize + 8 < *(unsigned int *)pbOutput
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_115;
    }
    v26 = v25 + 23;
    if ( v25 + 23 <= v25 + 8 )
      v26 = 0xFFFFFFFFFFFFFF0LL;
    v27 = v26 & 0xFFFFFFFFFFFFFFF0uLL;
    v28 = alloca(v27);
    v29 = alloca(v27);
    p_hMem = v68;
    if ( v67 == (_BYTE *)-64LL || (*(_DWORD *)v68 = 1801679955, (p_hMem = (UCHAR *)&hMem) == 0) )
    {
LABEL_115:
      if ( v25 + 8 >= v25 )
      {
        v30 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_hMem = v30;
        if ( v30 )
        {
          *(_DWORD *)v30 = 1885431112;
          p_hMem = v30 + 8;
        }
      }
    }
    if ( !p_hMem )
    {
      v19 = -2147024888;
      v31 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
      v32 = 651;
      goto LABEL_97;
    }
    v33 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v68, 4u, &pcbResult, 0);
    if ( v33 >= 0 )
    {
      v38 = *(unsigned int *)v68;
      if ( !*(_DWORD *)v68
        || *(unsigned int *)v68 > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)*(unsigned int *)v68 + g_ulAdditionalProbeSize + 8 < *(unsigned int *)v68
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_116;
      }
      v39 = v38 + 23;
      if ( v38 + 23 <= v38 + 8 )
        v39 = 0xFFFFFFFFFFFFFF0LL;
      v40 = v39 & 0xFFFFFFFFFFFFFFF0uLL;
      v41 = alloca(v40);
      v42 = alloca(v40);
      v9 = v68;
      if ( v67 == (_BYTE *)-64LL || (*(_DWORD *)v68 = 1801679955, (v9 = (UCHAR *)&hMem) == 0) )
      {
LABEL_116:
        if ( v38 + 8 >= v38 )
        {
          v43 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          v9 = v43;
          if ( v43 )
          {
            *(_DWORD *)v43 = 1885431112;
            v9 = v43 + 8;
          }
        }
      }
      if ( !v9 )
      {
        v19 = -2147024888;
        v31 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
        v32 = 675;
        goto LABEL_97;
      }
      v44 = BCryptCreateHash(phAlgorithm, &phHash, p_hMem, *(ULONG *)pbOutput, 0, 0, 0);
      if ( v44 >= 0 )
      {
        v49 = BCryptHashData(phHash, pbInput, a4, 0);
        if ( v49 >= 0 )
        {
          v54 = BCryptFinishHash(phHash, v9, *(ULONG *)v68, 0);
          if ( v54 >= 0 )
          {
            v56 = BCryptVerifySignature(
                    hKey,
                    *((void **)hMem + 7),
                    v9,
                    *(ULONG *)v68,
                    pbSignature,
                    cbSignature,
                    *((_DWORD *)hMem + 13));
            if ( v56 >= 0 )
            {
              v19 = 0;
            }
            else
            {
              v19 = v56 | 0x10000000;
              v57 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
              WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v19, v57, 738, "BCryptVerifySignature");
            }
          }
          else
          {
            v19 = v54 | 0x10000000;
            v55 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp");
            WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v19, v55, 717, "BCryptFinishHash");
          }
        }
        else
        {
          v19 = v49 | 0x10000000;
          v50 = "";
          while ( 1 )
          {
            v51 = *(v50 - 1);
            v52 = v50--;
            v53 = v51 == 92;
            if ( v51 == 92 )
              break;
            if ( v50 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp" )
            {
              v53 = v51 == 92;
              break;
            }
          }
          if ( v53 )
            v50 = v52;
          WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v19, v50, 704, "BCryptHashData");
        }
      }
      else
      {
        v19 = v44 | 0x10000000;
        v45 = "";
        while ( 1 )
        {
          v46 = *(v45 - 1);
          v47 = v45--;
          v48 = v46 == 92;
          if ( v46 == 92 )
            break;
          if ( v45 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp" )
          {
            v48 = v46 == 92;
            break;
          }
        }
        if ( v48 )
          v45 = v47;
        WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v19, v45, 691, "BCryptCreateHash");
      }
    }
    else
    {
      v19 = v33 | 0x10000000;
      v34 = "";
      while ( 1 )
      {
        v35 = *(v34 - 1);
        v36 = v34--;
        v37 = v35 == 92;
        if ( v35 == 92 )
          break;
        if ( v34 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp" )
        {
          v37 = v35 == 92;
          break;
        }
      }
      if ( v37 )
        v34 = v36;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u : %s", v19, v34, 666, "BCryptGetProperty");
    }
  }
  else
  {
    v19 = -2147024809;
    v58 = "";
    while ( 1 )
    {
      v60 = *(v58 - 1);
      v61 = v58--;
      v62 = v60 == 92;
      if ( v60 == 92 )
        break;
      if ( v58 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\crypto.cpp" )
      {
        v62 = v60 == 92;
        break;
      }
    }
    if ( v62 )
      v58 = v61;
    v59 = 1086;
LABEL_89:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v19, v58, v59);
LABEL_90:
    v31 = "";
    while ( 1 )
    {
      v63 = *(v31 - 1);
      v64 = v31--;
      v65 = v63 == 92;
      if ( v63 == 92 )
        break;
      if ( v31 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\cng.cpp" )
      {
        v65 = v63 == 92;
        break;
      }
    }
    if ( v65 )
      v31 = v64;
    v32 = 610;
LABEL_97:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v19, v31, v32);
  }
LABEL_98:
  if ( hMem )
    LocalFree(hMem);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v9 && *((_DWORD *)v9 - 2) == 1885431112 )
    ((void (__fastcall *)(UCHAR *))g_pfnFree)(v9 - 8);
  if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
    ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_hMem - 8);
  if ( v19 < 0 )
    return (unsigned int)-2146885363;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180004f90  push    rbp
0x180004f92  push    rbx
0x180004f93  push    rsi
0x180004f94  push    rdi
0x180004f95  push    r12
0x180004f97  push    r13
0x180004f99  push    r14
0x180004f9b  push    r15
0x180004f9d  sub     rsp, 98h
0x180004fa4  lea     rbp, [rsp+40h]
0x180004fa9  mov     rax, cs:__security_cookie
0x180004fb0  xor     rax, rbp
0x180004fb3  mov     [rbp+90h+var_50], rax
0x180004fb7  xor     eax, eax
0x180004fb9  mov     [rbp+90h+pbInput], r8
0x180004fbd  cmp     cs:dword_180022FC8, eax
0x180004fc3  mov     r13d, r9d
0x180004fc6  mov     [rbp+90h+hKey], rdx
0x180004fca  mov     rbx, rcx
0x180004fcd  mov     [rbp+90h+phAlgorithm], rax
0x180004fd1  mov     esi, eax
0x180004fd3  mov     [rbp+90h+phHash], rax
0x180004fd7  mov     edi, eax
0x180004fd9  mov     dword ptr [rbp+90h+pbOutput], eax
0x180004fdc  mov     dword ptr [rbp+90h+var_90], eax
0x180004fdf  mov     [rbp+90h+pcbResult], eax
0x180004fe2  mov     [rbp+90h+hMem], rax
0x180004fe6  jnz     short loc_180004FEF
0x180004fe8  call    _LoadRegExtensions
0x180004fed  xor     eax, eax
0x180004fef  lea     r15, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180004ff6  test    rbx, rbx
0x180004ff9  jz      loc_180005673
0x180004fff  mov     [rbp+90h+hMem], rax
0x180005003  mov     r14d, eax
0x180005006  cmp     r14d, cs:dword_180022FC0
0x18000500d  jnb     loc_1800050D1
0x180005013  mov     r8, [rbx+8]; lpString1
0x180005017  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000501d  mov     eax, r14d
0x180005020  mov     edx, 1; dwCmpFlags
0x180005025  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000502d  xor     ecx, ecx; Locale
0x18000502f  lea     r12, ds:0[rax*8]
0x180005037  mov     rax, cs:qword_180022FD8
0x18000503e  mov     rax, [r12+rax]
0x180005042  mov     rax, [rax+8]
0x180005046  mov     [rsp+0D0h+lpString2], rax; lpString2
0x18000504b  call    cs:__imp_CompareStringW
0x180005052  nop     dword ptr [rax+rax+00h]
0x180005057  cmp     eax, 2
0x18000505a  jnz     short loc_1800050C7
0x18000505c  mov     rax, cs:qword_180022FD8
0x180005063  mov     rcx, [r12+rax]
0x180005067  mov     rax, [rcx+98h]
0x18000506e  test    rax, rax
0x180005071  jz      short loc_1800050C7
0x180005073  lea     rdx, [rbp+90h+hMem]
0x180005077  mov     rcx, rbx
0x18000507a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000507f  mov     r10d, eax
0x180005082  test    eax, eax
0x180005084  jns     loc_1800051C9
0x18000508a  mov     rcx, r15; char *
0x18000508d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180005092  mov     r8, rax
0x180005095  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000509c  mov     edx, r10d
0x18000509f  mov     r9d, 45Eh
0x1800050a5  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800050aa  mov     rcx, [rbp+90h+hMem]; hMem
0x1800050ae  test    rcx, rcx
0x1800050b1  jz      short loc_1800050C7
0x1800050b3  call    cs:__imp_LocalFree
0x1800050ba  nop     dword ptr [rax+rax+00h]
0x1800050bf  xor     eax, eax
0x1800050c1  mov     [rbp+90h+hMem], rax
0x1800050c5  jmp     short loc_1800050C9
0x1800050c7  xor     eax, eax
0x1800050c9  inc     r14d
0x1800050cc  jmp     loc_180005006
0x1800050d1  mov     r14d, eax
0x1800050d4  lea     rdx, qword_180022180
0x1800050db  cmp     r14d, 11h
0x1800050df  jnb     loc_18000565B
0x1800050e5  mov     r8, [rbx+8]; lpString1
0x1800050e9  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800050ef  mov     eax, r14d
0x1800050f2  mov     [rsp+0D0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800050fa  lea     rcx, [rax+rax*8]
0x1800050fe  lea     r12, ds:0[rcx*8]
0x180005106  xor     ecx, ecx; Locale
0x180005108  mov     rax, [r12+rdx+8]
0x18000510d  mov     edx, 1; dwCmpFlags
0x180005112  mov     [rsp+0D0h+lpString2], rax; lpString2
0x180005117  call    cs:__imp_CompareStringW
0x18000511e  nop     dword ptr [rax+rax+00h]
0x180005123  cmp     eax, 2
0x180005126  jz      short loc_18000512D
0x180005128  inc     r14d
0x18000512b  jmp     short loc_1800050D4
0x18000512d  mov     edx, 48h ; 'H'; uBytes
0x180005132  mov     ecx, 40h ; '@'; uFlags
0x180005137  call    cs:__imp_LocalAlloc
0x18000513e  nop     dword ptr [rax+rax+00h]
0x180005143  mov     [rbp+90h+hMem], rax
0x180005147  test    rax, rax
0x18000514a  jnz     short loc_180005190
0x18000514c  call    cs:__imp_GetLastError
0x180005153  nop     dword ptr [rax+rax+00h]
0x180005158  mov     ebx, eax
0x18000515a  test    eax, eax
0x18000515c  jle     short loc_180005167
0x18000515e  movzx   ebx, ax
0x180005161  or      ebx, 80070000h
0x180005167  mov     rcx, r15; char *
0x18000516a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000516f  mov     r8, rax
0x180005172  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180005179  mov     edx, ebx
0x18000517b  mov     r9d, 483h
0x180005181  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180005186  test    ebx, ebx
0x180005188  js      loc_1800056AD
0x18000518e  jmp     short loc_1800051C9
0x180005190  lea     rcx, qword_180022180
0x180005197  movups  xmm0, xmmword ptr [r12+rcx]
0x18000519c  movups  xmmword ptr [rax], xmm0
0x18000519f  movups  xmm1, xmmword ptr [r12+rcx+10h]
0x1800051a5  movups  xmmword ptr [rax+10h], xmm1
0x1800051a9  movups  xmm0, xmmword ptr [r12+rcx+20h]
0x1800051af  movups  xmmword ptr [rax+20h], xmm0
0x1800051b3  movups  xmm1, xmmword ptr [r12+rcx+30h]
0x1800051b9  movups  xmmword ptr [rax+30h], xmm1
0x1800051bd  movsd   xmm0, qword ptr [r12+rcx+40h]
0x1800051c4  movsd   qword ptr [rax+40h], xmm0
0x1800051c9  mov     rdx, [rbp+90h+hMem]
0x1800051cd  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800051d4  xor     r9d, r9d; dwFlags
0x1800051d7  lea     rcx, [rbp+90h+phAlgorithm]; phAlgorithm
0x1800051db  mov     rdx, [rdx+20h]; pszAlgId
0x1800051df  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800051e6  nop     dword ptr [rax+rax+00h]
0x1800051eb  mov     ebx, eax
0x1800051ed  test    eax, eax
0x1800051ef  jns     short loc_180005229
0x1800051f1  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800051f8  bts     ebx, 1Ch
0x1800051fc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180005201  mov     r8, rax
0x180005204  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x18000520b  lea     rax, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider"
0x180005212  mov     r9d, 273h
0x180005218  mov     edx, ebx
0x18000521a  mov     [rsp+0D0h+lpString2], rax
0x18000521f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180005224  jmp     loc_1800056E9
0x180005229  mov     rcx, [rbp+90h+phAlgorithm]; hObject
0x18000522d  lea     rax, [rbp+90h+pcbResult]
0x180005231  xor     r15d, r15d
0x180005234  lea     r8, [rbp+90h+pbOutput]; pbOutput
0x180005238  mov     [rsp+0D0h+cchCount2], r15d; dwFlags
0x18000523d  lea     rdx, pszProperty; "ObjectLength"
0x180005244  mov     r9d, 4; cbOutput
0x18000524a  mov     [rsp+0D0h+lpString2], rax; pcbResult
0x18000524f  call    cs:__imp_BCryptGetProperty
0x180005256  nop     dword ptr [rax+rax+00h]
0x18000525b  mov     ebx, eax
0x18000525d  test    eax, eax
0x18000525f  jns     short loc_180005299
0x180005261  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180005268  bts     ebx, 1Ch
0x18000526c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180005271  mov     r8, rax
0x180005274  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x18000527b  lea     rax, aBcryptgetprope_0; "BCryptGetProperty"
0x180005282  mov     r9d, 282h
0x180005288  mov     edx, ebx
0x18000528a  mov     [rsp+0D0h+lpString2], rax
0x18000528f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180005294  jmp     loc_1800056E9
0x180005299  mov     ebx, dword ptr [rbp+90h+pbOutput]
0x18000529c  test    rbx, rbx
0x18000529f  jz      short loc_180005307
0x1800052a1  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800052a8  ja      short loc_180005307
0x1800052aa  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800052b1  add     rcx, 8
0x1800052b5  add     rcx, rbx
0x1800052b8  cmp     rcx, rbx
0x1800052bb  jb      short loc_180005307
0x1800052bd  call    VerifyStackAvailable
0x1800052c2  test    eax, eax
0x1800052c4  jz      short loc_180005307
0x1800052c6  lea     rax, [rbx+8]
0x1800052ca  mov     r14, 0FFFFFFFFFFFFFF0h
0x1800052d4  lea     rcx, [rax+0Fh]
0x1800052d8  cmp     rcx, rax
0x1800052db  ja      short loc_1800052E0
0x1800052dd  mov     rcx, r14
0x1800052e0  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800052e4  mov     rax, rcx
0x1800052e7  call    __chkstk_0
0x1800052ec  sub     rsp, rcx
0x1800052ef  lea     rsi, [rsp+0D0h+var_90]
0x1800052f4  test    rsi, rsi
0x1800052f7  jz      short loc_180005311
0x1800052f9  mov     dword ptr [rsi], 6B637453h
0x1800052ff  add     rsi, 8
0x180005303  jz      short loc_180005311
0x180005305  jmp     short loc_180005338
0x180005307  mov     r14, 0FFFFFFFFFFFFFF0h
0x180005311  lea     rcx, [rbx+8]
0x180005315  cmp     rcx, rbx
0x180005318  jb      short loc_180005338
0x18000531a  mov     rax, cs:g_pfnAllocate
0x180005321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005326  mov     rsi, rax
0x180005329  test    rax, rax
0x18000532c  jz      short loc_180005338
0x18000532e  mov     dword ptr [rax], 70616548h
0x180005334  add     rsi, 8
0x180005338  test    rsi, rsi
0x18000533b  jnz     short loc_18000535C
0x18000533d  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180005344  mov     ebx, 80070008h
0x180005349  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000534e  mov     r8, rax
0x180005351  mov     r9d, 28Bh
0x180005357  jmp     loc_1800056DB
0x18000535c  mov     rcx, [rbp+90h+phAlgorithm]; hObject
0x180005360  lea     rax, [rbp+90h+pcbResult]
0x180005364  mov     [rsp+0D0h+cchCount2], r15d; dwFlags
0x180005369  lea     r8, [rbp+90h+var_90]; pbOutput
0x18000536d  mov     r9d, 4; cbOutput
0x180005373  mov     [rsp+0D0h+lpString2], rax; pcbResult
0x180005378  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000537f  call    cs:__imp_BCryptGetProperty
0x180005386  nop     dword ptr [rax+rax+00h]
0x18000538b  mov     ebx, eax
0x18000538d  test    eax, eax
0x18000538f  jns     short loc_1800053E2
0x180005391  bts     ebx, 1Ch
0x180005395  lea     r8, aOnecoreDsSecur_2+2Dh; ""
0x18000539c  lea     rcx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800053a3  movzx   eax, byte ptr [r8-1]
0x1800053a8  mov     rdx, r8
0x1800053ab  dec     r8
0x1800053ae  cmp     al, 5Ch ; '\'
0x1800053b0  jz      short loc_1800053B9
0x1800053b2  cmp     r8, rcx
0x1800053b5  ja      short loc_1800053A3
0x1800053b7  cmp     al, 5Ch ; '\'
0x1800053b9  cmovz   r8, rdx
0x1800053bd  lea     rax, aBcryptgetprope_0; "BCryptGetProperty"
0x1800053c4  mov     edx, ebx
0x1800053c6  mov     [rsp+0D0h+lpString2], rax
0x1800053cb  mov     r9d, 29Ah
0x1800053d1  lea     rcx, aError0x08xSUS; "ERROR  : (0x%08x) %s:%u : %s"
0x1800053d8  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800053dd  jmp     loc_1800056E9
0x1800053e2  mov     ebx, dword ptr [rbp+90h+var_90]
0x1800053e5  test    rbx, rbx
0x1800053e8  jz      short loc_180005444
0x1800053ea  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800053f1  ja      short loc_180005444
0x1800053f3  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800053fa  add     rcx, 8
0x1800053fe  add     rcx, rbx
0x180005401  cmp     rcx, rbx
0x180005404  jb      short loc_180005444
0x180005406  call    VerifyStackAvailable
0x18000540b  test    eax, eax
0x18000540d  jz      short loc_180005444
0x18000540f  lea     rax, [rbx+8]
0x180005413  lea     rcx, [rax+0Fh]
0x180005417  cmp     rcx, rax
0x18000541a  ja      short loc_18000541F
0x18000541c  mov     rcx, r14
0x18000541f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180005423  mov     rax, rcx
0x180005426  call    __chkstk_0
0x18000542b  sub     rsp, rcx
0x18000542e  lea     rdi, [rsp+0D0h+var_90]
0x180005433  test    rdi, rdi
0x180005436  jz      short loc_180005444
0x180005438  mov     dword ptr [rdi], 6B637453h
0x18000543e  add     rdi, 8
0x180005442  jnz     short loc_18000546B
0x180005444  lea     rcx, [rbx+8]
0x180005448  cmp     rcx, rbx
0x18000544b  jb      short loc_18000546B
0x18000544d  mov     rax, cs:g_pfnAllocate
0x180005454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005459  mov     rdi, rax
0x18000545c  test    rax, rax
0x18000545f  jz      short loc_18000546B
0x180005461  mov     dword ptr [rax], 70616548h
0x180005467  add     rdi, 8
0x18000546b  test    rdi, rdi
  ... truncated ...
```
