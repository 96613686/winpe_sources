# CProviderEntry::ReadInfoFromRegistry(HKEY__ *,HKEY__ *,ushort const *,_GUID const *)

- ea: `0x180004da0`
- end: `0x1800054ef`
- name: `?ReadInfoFromRegistry@CProviderEntry@@QEAAJPEAUHKEY__@@0PEBGPEBU_GUID@@@Z`
- size: `1871`
- prototype: `__int64 __fastcall(CProviderEntry *this, HKEY, HKEY, const unsigned __int16 *, struct _GUID *Uuid1)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043d0`

## callees

- `0x180004da0`
- `0x18000a224`
- `0x18000a2ec`
- `0x18000bdec`
- `0x18000c068`
- `0x18000c2d0`
- `0x18000e8d6`
- `0x1800170fc`
- `0x1800171f0`
- `0x18001725c`
- `0x1800173a8`
- `0x1800173bc`
- `0x180017490`
- `0x180017554`
- `0x180017628`
- `0x1800176b0`
- `0x180017b04`
- `0x180017b28`
- `0x180017b4c`
- `0x18001a342`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000522e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000522e`
- `RPCRT4!UuidEqual` at `0x180004dde`
- `RPCRT4!UuidEqual` at `0x180004e41`
- `RPCRT4!UuidEqual` at `0x180004e5d`
- `RPCRT4!UuidEqual` at `0x180004fb6`
- `RPCRT4!UuidEqual` at `0x180004dde`
- `RPCRT4!UuidEqual` at `0x180004e41`
- `RPCRT4!UuidEqual` at `0x180004e5d`
- `RPCRT4!UuidEqual` at `0x180004fb6`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800052a6`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180005397`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800052a6`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180005397`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18000544c`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18000544c`
- `CRYPT32!CertFreeCertificateContext` at `0x1800052cc`
- `CRYPT32!CertFreeCertificateContext` at `0x180005313`
- `CRYPT32!CertFreeCertificateContext` at `0x1800053bd`
- `CRYPT32!CertFreeCertificateContext` at `0x18000547f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800054e2`
- `CRYPT32!CertFreeCertificateContext` at `0x1800052cc`
- `CRYPT32!CertFreeCertificateContext` at `0x180005313`
- `CRYPT32!CertFreeCertificateContext` at `0x1800053bd`
- `CRYPT32!CertFreeCertificateContext` at `0x18000547f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800054e2`
- `CRYPT32!CertOpenStore` at `0x180005199`
- `CRYPT32!CertOpenStore` at `0x1800051f5`
- `CRYPT32!CertOpenStore` at `0x180005199`
- `CRYPT32!CertOpenStore` at `0x1800051f5`
- `CRYPT32!CertControlStore` at `0x18000526c`
- `CRYPT32!CertControlStore` at `0x18000526c`
- `CRYPT32!CertRegisterSystemStore` at `0x1800051b9`
- `CRYPT32!CertRegisterSystemStore` at `0x1800051b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004ec6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004ec6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004f66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004f75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000516c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000517b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004f66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004f75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800050ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000516c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000517b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005064`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800050c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005142`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005064`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800050c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005142`

## string_xrefs

- `0x180004dfb`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`
- `0x180004e8a`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`
- `0x1800051c7`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`
- `0x18000520b`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`
- `0x180005247`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`
- `0x18000527a`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`
- `0x1800052f3`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`
- `0x18000545a`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`

## pseudocode

```c
__int64 __fastcall CProviderEntry::ReadInfoFromRegistry(
        CProviderEntry *this,
        HKEY a2,
        HKEY a3,
        const unsigned __int16 *a4,
        struct _GUID *Uuid1)
{
  int v10; // eax
  unsigned int v11; // r13d
  unsigned int v12; // eax
  unsigned int v13; // r8d
  unsigned int v14; // ebx
  unsigned int v15; // eax
  void *v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // rcx
  HKEY v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int ValueW; // eax
  unsigned int v24; // r8d
  int v25; // eax
  HKEY v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // r8d
  int v29; // eax
  HKEY v30; // rcx
  HCERTSTORE v31; // rax
  const char *v32; // r9
  HCERTSTORE v33; // rax
  const char *v34; // r9
  HANDLE EventW; // rax
  const char *v36; // r9
  const char *v37; // r9
  const CERT_CONTEXT *v38; // rdx
  unsigned int v39; // r15d
  unsigned int v40; // ebx
  void *v41; // rcx
  __int64 v42; // r14
  __int64 v43; // rax
  unsigned int v44; // eax
  unsigned int v45; // r8d
  int LastError; // eax
  HKEY v47; // r15
  unsigned int v48; // ebx
  const CERT_CONTEXT *v49; // rdx
  void *v50; // rcx
  __int64 v51; // r14
  PCERT_INFO pCertInfo; // r14
  DWORD cbData; // eax
  __int64 v54; // rdx
  const char *v55; // r9
  int phkResult; // [rsp+20h] [rbp-A1h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A1h]
  unsigned int phkResultb; // [rsp+20h] [rbp-A1h]
  unsigned int phkResultc; // [rsp+20h] [rbp-A1h]
  unsigned int phkResultd; // [rsp+20h] [rbp-A1h]
  unsigned int phkResulte; // [rsp+20h] [rbp-A1h]
  HKEY hKey; // [rsp+40h] [rbp-81h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-79h] BYREF
  unsigned __int64 v64; // [rsp+50h] [rbp-71h] BYREF
  HKEY v65; // [rsp+58h] [rbp-69h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-61h] BYREF
  RPC_STATUS Status; // [rsp+68h] [rbp-59h] BYREF
  struct _SecPkgContext_IssuerListInfoEx *v68; // [rsp+70h] [rbp-51h] BYREF
  _BYTE v69[24]; // [rsp+78h] [rbp-49h] BYREF
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+90h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  Status = 0;
  if ( !UuidEqual(Uuid1, (UUID *)&stru_18001E210, &Status) && (!a2 || !a3 || !a4) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp",
      (const char *)0x80070057LL,
      phkResult);
    return 2147942487LL;
  }
  *(struct _GUID *)((char *)this + 8) = *Uuid1;
  if ( UuidEqual(Uuid1, (UUID *)&stru_18001E210, &Status) || UuidEqual(Uuid1, (UUID *)&stru_180020DD0, &Status) )
    return 2147942421LL;
  v10 = StringCchCopyW((unsigned __int16 *)this + 532, 0x104u, a4);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp",
      (const char *)(unsigned int)v10,
      phkResult);
    return v11;
  }
  v65 = 0;
  v12 = RegOpenKeyExW(a3, a4, 0, 0x20019u, &v65);
  if ( v12 )
  {
    v14 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x8D, v13, (const char *)v12, phkResulta);
    goto LABEL_38;
  }
  hKey = 0;
  v15 = RegOpenKeyExW(a2, a4, 0, 0x20019u, &hKey);
  if ( v15 )
    wil::details::in1diag3::_Log_Win32(retaddr, v16, v17, (const char *)v15, phkResultb);
  LODWORD(v64) = 0;
  if ( IsProviderDisabledForPKU2U(v65, hKey, (int *)&v64) >= 0 && (_DWORD)v64 )
  {
    CertPolEngProvider::LoadProviderSkipped_DisabledForPKU2U<_GUID const &>(Uuid1);
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0j_EtwEventWriteTransfer(v19, v18, Uuid1);
    v20 = hKey;
    if ( !hKey )
      goto LABEL_20;
    goto LABEL_19;
  }
  if ( !UuidEqual(Uuid1, (UUID *)&stru_180020DC0, &Status) )
  {
    LODWORD(v64) = 0;
    if ( IsProviderEnabled(v65, hKey, (int *)&v64) < 0 || !(_DWORD)v64 )
    {
      CertPolEngProvider::LoadProviderSkipped_Disabled<_GUID const &>(Uuid1);
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0j_EtwEventWriteTransfer(v22, v21, Uuid1);
      v20 = hKey;
      if ( !hKey )
        goto LABEL_20;
LABEL_19:
      RegCloseKey(v20);
LABEL_20:
      if ( v65 )
        RegCloseKey(v65);
      return 2147942421LL;
    }
  }
  v64 = 0;
  if ( (int)GetProviderFlags(v65, &v64) >= 0 )
    *((_QWORD *)this + 268) = v64;
  pcbData = 260;
  ValueW = RegGetValueW(a2, a4, L"TrustedRootContainer", 2u, 0, (char *)this + 24, &pcbData);
  if ( ValueW )
  {
    v25 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xAD, v24, (const char *)ValueW, phkResultc);
    v26 = hKey;
    v14 = v25;
    if ( !hKey )
    {
LABEL_38:
      if ( v65 )
        RegCloseKey(v65);
      return v14;
    }
LABEL_37:
    RegCloseKey(v26);
    goto LABEL_38;
  }
  pcbData = 260;
  v27 = RegGetValueW(a2, a4, L"Name", 2u, 0, (char *)this + 1584, &pcbData);
  if ( v27 )
  {
    v29 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xB0, v28, (const char *)v27, phkResultd);
    v26 = hKey;
    v14 = v29;
    if ( !hKey )
      goto LABEL_38;
    goto LABEL_37;
  }
  pcbData = 260;
  if ( RegGetValueW(a2, a4, L"CertLRPCEndPoint", 2u, 0, (char *)this + 544, &pcbData) )
    *((_WORD *)this + 272) = 0;
  v30 = hKey;
  *((_DWORD *)this + 534) = 3;
  if ( v30 )
    RegCloseKey(v30);
  if ( v65 )
    RegCloseKey(v65);
  v31 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x2C000u, (char *)this + 24);
  *((_QWORD *)this + 263) = v31;
  if ( !v31 )
  {
    if ( !CertRegisterSystemStore((char *)this + 24, 0x22000u, 0, 0) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xC3,
               (unsigned int)"onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp",
               v32);
    v33 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x2C000u, (char *)this + 24);
    *((_QWORD *)this + 263) = v33;
    if ( !v33 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xC8,
               (unsigned int)"onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp",
               v34);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v36 = (char *)this + 2112;
  *((_QWORD *)this + 264) = EventW;
  if ( !EventW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xCB,
             (unsigned int)"onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp",
             v36);
  if ( !CertControlStore(*((HCERTSTORE *)this + 263), 0, 2u, v36) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xCD,
             (unsigned int)"onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp",
             v37);
  v38 = 0;
  v39 = 0;
  v40 = 0;
  while ( 1 )
  {
    v41 = (void *)*((_QWORD *)this + 263);
    pCertContext = 0;
    hKey = (HKEY)CertEnumCertificatesInStore(v41, v38);
    v42 = *(_QWORD *)wil::unique_any_t<wil::cert_context_t>::operator=(&pCertContext, &hKey);
    if ( hKey )
      CertFreeCertificateContext((PCCERT_CONTEXT)hKey);
    if ( !v42 )
      break;
    v38 = pCertContext;
    if ( v40 + pCertContext->pCertInfo->Subject.cbData < v40 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp",
        (const char *)0x80070216LL,
        phkResulte);
      if ( pCertContext )
        CertFreeCertificateContext(pCertContext);
      return 2147942934LL;
    }
    v40 += pCertContext->pCertInfo->Subject.cbData;
    ++v39;
  }
  hKey = 0;
  v68 = 0;
  v43 = lambda_6e0ffd5e143c7eb3c2a13d95c67a9782_::_lambda_6e0ffd5e143c7eb3c2a13d95c67a9782_(&v65, &v68);
  wil::ScopeExit__lambda_6e0ffd5e143c7eb3c2a13d95c67a9782___(v69, v43);
  v44 = CProviderRegistrationCache::AllocateAndInitializeIssuerList(v39, v40, &v68, (unsigned __int8 **)&hKey);
  if ( v44 )
  {
    LastError = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xE0, v45, (const char *)v44, phkResulte);
    goto LABEL_74;
  }
  v47 = hKey;
  v48 = 0;
  LODWORD(v64) = 0;
  while ( 1 )
  {
    v49 = pCertContext;
    v50 = (void *)*((_QWORD *)this + 263);
    pCertContext = 0;
    hKey = (HKEY)CertEnumCertificatesInStore(v50, v49);
    v51 = *(_QWORD *)wil::unique_any_t<wil::cert_context_t>::operator=(&pCertContext, &hKey);
    if ( hKey )
      CertFreeCertificateContext((PCCERT_CONTEXT)hKey);
    if ( !v51 )
      break;
    pCertInfo = pCertContext->pCertInfo;
    cbData = pCertInfo->Subject.cbData;
    if ( cbData )
    {
      memcpy_0(v47, pCertInfo->Subject.pbData, cbData);
      v54 = v48;
      v68->aIssuers[v54].cbData = pCertInfo->Subject.cbData;
      v68->aIssuers[v54].pbData = (BYTE *)v47;
      v47 = (HKEY)((char *)v47 + pCertInfo->Subject.cbData);
      ++v48;
    }
  }
  LODWORD(v64) = v48;
  memset_0(&pConfig, 0, 0x58u);
  pConfig.hExclusiveRoot = (HCERTSTORE)*((_QWORD *)this + 263);
  pConfig.cbSize = 88;
  pConfig.dwFlags = 1;
  if ( !CertCreateCertificateChainEngine(&pConfig, (HCERTCHAINENGINE *)this + 266) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xFB,
                  (unsigned int)"onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp",
                  v55);
LABEL_74:
    v14 = LastError;
    wil::details::ScopeExitFn__lambda_6e0ffd5e143c7eb3c2a13d95c67a9782___::_ScopeExitFn__lambda_6e0ffd5e143c7eb3c2a13d95c67a9782___(v69);
    if ( pCertContext )
      CertFreeCertificateContext(pCertContext);
    return v14;
  }
  *((_QWORD *)this + 265) = v68;
  v68 = 0;
  CertPolEngProvider::LoadProvider<_GUID &,unsigned short (&)[260],unsigned __int64 &,unsigned short (&)[260],unsigned short (&)[260],unsigned long &,unsigned long &>(
    (_DWORD)this + 8,
    (_DWORD)this + 1064,
    (_DWORD)this + 2144,
    (_DWORD)this + 1584,
    (__int64)this + 544,
    (__int64)this + 2136,
    (__int64)&v64);
  wil::details::ScopeExitFn__lambda_6e0ffd5e143c7eb3c2a13d95c67a9782___::_ScopeExitFn__lambda_6e0ffd5e143c7eb3c2a13d95c67a9782___(v69);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  return 0;
}

```

## disassembly

```asm
0x180004da0  mov     [rsp-8+arg_10], rbx
0x180004da5  push    rbp
0x180004da6  push    rdi
0x180004da7  push    r12
0x180004da9  push    r14
0x180004dab  push    r15
0x180004dad  lea     rbp, [rsp-2Fh]
0x180004db2  sub     rsp, 0F0h
0x180004db9  mov     rbx, [rbp+4Fh+Uuid1]
0x180004dbd  mov     r12, r8
0x180004dc0  mov     r15, rdx
0x180004dc3  mov     [rbp+4Fh+Status], 0
0x180004dca  mov     rdi, rcx
0x180004dcd  lea     r8, [rbp+4Fh+Status]; Status
0x180004dd1  mov     rcx, rbx; Uuid1
0x180004dd4  lea     rdx, stru_18001E210; Uuid2
0x180004ddb  mov     r14, r9
0x180004dde  call    cs:__imp_UuidEqual
0x180004de4  test    eax, eax
0x180004de6  jnz     short loc_180004E1C
0x180004de8  test    r15, r15
0x180004deb  jz      short loc_180004DF7
0x180004ded  test    r12, r12
0x180004df0  jz      short loc_180004DF7
0x180004df2  test    r14, r14
0x180004df5  jnz     short loc_180004E1C
0x180004df7  mov     rcx, [rbp+57h]; this
0x180004dfb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\identity\\certpo"...
0x180004e02  mov     r9d, 80070057h; char *
0x180004e08  mov     edx, 76h ; 'v'; void *
0x180004e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e12  mov     eax, 80070057h
0x180004e17  jmp     loc_180004F90
0x180004e1c  movups  xmm0, xmmword ptr [rbx]
0x180004e1f  mov     [rsp+110h+arg_0], rsi
0x180004e27  lea     r8, [rbp+4Fh+Status]; Status
0x180004e2b  lea     rdx, stru_18001E210; Uuid2
0x180004e32  mov     [rsp+110h+arg_8], r13
0x180004e3a  mov     rcx, rbx; Uuid1
0x180004e3d  movups  xmmword ptr [rdi+8], xmm0
0x180004e41  call    cs:__imp_UuidEqual
0x180004e47  test    eax, eax
0x180004e49  jnz     loc_180004F7B
0x180004e4f  lea     r8, [rbp+4Fh+Status]; Status
0x180004e53  mov     rcx, rbx; Uuid1
0x180004e56  lea     rdx, stru_180020DD0; Uuid2
0x180004e5d  call    cs:__imp_UuidEqual
0x180004e63  test    eax, eax
0x180004e65  jnz     loc_180004F7B
0x180004e6b  lea     rcx, [rdi+428h]; unsigned __int16 *
0x180004e72  mov     r8, r14; unsigned __int16 *
0x180004e75  mov     edx, 104h; unsigned __int64
0x180004e7a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004e7f  mov     r13d, eax
0x180004e82  test    eax, eax
0x180004e84  jns     short loc_180004EA6
0x180004e86  mov     rcx, [rbp+57h]; this
0x180004e8a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\identity\\certpo"...
0x180004e91  mov     r9d, eax; char *
0x180004e94  mov     edx, 84h; void *
0x180004e99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e9e  mov     eax, r13d
0x180004ea1  jmp     loc_180004F80
0x180004ea6  lea     rax, [rbp+4Fh+var_B8]
0x180004eaa  mov     [rbp+4Fh+var_B8], 0
0x180004eb2  mov     r9d, 20019h; samDesired
0x180004eb8  mov     [rsp+110h+phkResult], rax; unsigned int
0x180004ebd  xor     r8d, r8d; ulOptions
0x180004ec0  mov     rdx, r14; lpSubKey
0x180004ec3  mov     rcx, r12; hKey
0x180004ec6  call    cs:__imp_RegOpenKeyExW
0x180004ecc  test    eax, eax
0x180004ece  jz      short loc_180004EE8
0x180004ed0  mov     rcx, [rbp+57h]; this
0x180004ed4  mov     r9d, eax; char *
0x180004ed7  mov     edx, 8Dh; void *
0x180004edc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180004ee1  mov     ebx, eax
0x180004ee3  jmp     loc_1800050F2
0x180004ee8  lea     rax, [rsp+110h+hKey]
0x180004eed  mov     [rsp+110h+hKey], 0
0x180004ef6  mov     r9d, 20019h; samDesired
0x180004efc  mov     [rsp+110h+phkResult], rax; unsigned int
0x180004f01  xor     r8d, r8d; ulOptions
0x180004f04  mov     rdx, r14; lpSubKey
0x180004f07  mov     rcx, r15; hKey
0x180004f0a  call    cs:__imp_RegOpenKeyExW
0x180004f10  test    eax, eax
0x180004f12  jz      short loc_180004F20
0x180004f14  mov     rcx, [rbp+57h]; this
0x180004f18  mov     r9d, eax; char *
0x180004f1b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180004f20  mov     rdx, [rsp+110h+hKey]; HKEY
0x180004f25  lea     r8, [rbp+4Fh+var_C0]; int *
0x180004f29  mov     rcx, [rbp+4Fh+var_B8]; HKEY
0x180004f2d  mov     dword ptr [rbp+4Fh+var_C0], 0
0x180004f34  call    ?IsProviderDisabledForPKU2U@@YAJPEAUHKEY__@@0PEAH@Z; IsProviderDisabledForPKU2U(HKEY__ *,HKEY__ *,int *)
0x180004f39  test    eax, eax
0x180004f3b  js      short loc_180004FA8
0x180004f3d  cmp     dword ptr [rbp+4Fh+var_C0], 0
0x180004f41  jz      short loc_180004FA8
0x180004f43  mov     rcx, rbx
0x180004f46  call    ??$LoadProviderSkipped_DisabledForPKU2U@AEBU_GUID@@@CertPolEngProvider@@SAXAEBU_GUID@@@Z; CertPolEngProvider::LoadProviderSkipped_DisabledForPKU2U<_GUID const &>(_GUID const &)
0x180004f4b  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180004f52  jz      short loc_180004F5C
0x180004f54  mov     r8, rbx
0x180004f57  call    McTemplateU0j_EtwEventWriteTransfer
0x180004f5c  mov     rcx, [rsp+110h+hKey]; hKey
0x180004f61  test    rcx, rcx
0x180004f64  jz      short loc_180004F6C
0x180004f66  call    cs:__imp_RegCloseKey
0x180004f6c  mov     rcx, [rbp+4Fh+var_B8]; hKey
0x180004f70  test    rcx, rcx
0x180004f73  jz      short loc_180004F7B
0x180004f75  call    cs:__imp_RegCloseKey
0x180004f7b  mov     eax, 80070015h
0x180004f80  mov     rsi, [rsp+110h+arg_0]
0x180004f88  mov     r13, [rsp+110h+arg_8]
0x180004f90  mov     rbx, [rsp+110h+arg_10]
0x180004f98  add     rsp, 0F0h
0x180004f9f  pop     r15
0x180004fa1  pop     r14
0x180004fa3  pop     r12
0x180004fa5  pop     rdi
0x180004fa6  pop     rbp
0x180004fa7  retn
0x180004fa8  lea     r8, [rbp+4Fh+Status]; Status
0x180004fac  mov     rcx, rbx; Uuid1
0x180004faf  lea     rdx, stru_180020DC0; Uuid2
0x180004fb6  call    cs:__imp_UuidEqual
0x180004fbc  test    eax, eax
0x180004fbe  jnz     short loc_18000500B
0x180004fc0  mov     rdx, [rsp+110h+hKey]; HKEY
0x180004fc5  lea     r8, [rbp+4Fh+var_C0]; int *
0x180004fc9  mov     rcx, [rbp+4Fh+var_B8]; HKEY
0x180004fcd  mov     dword ptr [rbp+4Fh+var_C0], eax
0x180004fd0  call    ?IsProviderEnabled@@YAJPEAUHKEY__@@0PEAH@Z; IsProviderEnabled(HKEY__ *,HKEY__ *,int *)
0x180004fd5  test    eax, eax
0x180004fd7  js      short loc_180004FDF
0x180004fd9  cmp     dword ptr [rbp+4Fh+var_C0], 0
0x180004fdd  jnz     short loc_18000500B
0x180004fdf  mov     rcx, rbx
0x180004fe2  call    ??$LoadProviderSkipped_Disabled@AEBU_GUID@@@CertPolEngProvider@@SAXAEBU_GUID@@@Z; CertPolEngProvider::LoadProviderSkipped_Disabled<_GUID const &>(_GUID const &)
0x180004fe7  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180004fee  jz      short loc_180004FF8
0x180004ff0  mov     r8, rbx
0x180004ff3  call    McTemplateU0j_EtwEventWriteTransfer
0x180004ff8  mov     rcx, [rsp+110h+hKey]
0x180004ffd  test    rcx, rcx
0x180005000  jz      loc_180004F6C
0x180005006  jmp     loc_180004F66
0x18000500b  mov     rcx, [rbp+4Fh+var_B8]; HKEY
0x18000500f  lea     rdx, [rbp+4Fh+var_C0]; unsigned __int64 *
0x180005013  mov     [rbp+4Fh+var_C0], 0
0x18000501b  call    ?GetProviderFlags@@YAJPEAUHKEY__@@PEA_K@Z; GetProviderFlags(HKEY__ *,unsigned __int64 *)
0x180005020  test    eax, eax
0x180005022  js      short loc_18000502F
0x180005024  mov     rax, [rbp+4Fh+var_C0]
0x180005028  mov     [rdi+860h], rax
0x18000502f  lea     rax, [rbp+4Fh+var_C8]
0x180005033  mov     [rbp+4Fh+var_C8], 104h
0x18000503a  mov     [rsp+110h+pcbData], rax; pcbData
0x18000503f  lea     rbx, [rdi+18h]
0x180005043  mov     [rsp+110h+pvData], rbx; pvData
0x180005048  lea     r8, aTrustedrootcon; "TrustedRootContainer"
0x18000504f  mov     r9d, 2; dwFlags
0x180005055  mov     [rsp+110h+phkResult], 0; unsigned int
0x18000505e  mov     rdx, r14; lpSubKey
0x180005061  mov     rcx, r15; hkey
0x180005064  call    cs:__imp_RegGetValueW
0x18000506a  test    eax, eax
0x18000506c  jz      short loc_18000508D
0x18000506e  mov     rcx, [rbp+57h]; this
0x180005072  mov     r9d, eax; char *
0x180005075  mov     edx, 0ADh; void *
0x18000507a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000507f  mov     rcx, [rsp+110h+hKey]
0x180005084  mov     ebx, eax
0x180005086  test    rcx, rcx
0x180005089  jnz     short loc_1800050EC
0x18000508b  jmp     short loc_1800050F2
0x18000508d  lea     rcx, [rbp+4Fh+var_C8]
0x180005091  mov     [rbp+4Fh+var_C8], 104h
0x180005098  mov     [rsp+110h+pcbData], rcx; pcbData
0x18000509d  lea     rax, [rdi+630h]
0x1800050a4  mov     [rsp+110h+pvData], rax; pvData
0x1800050a9  lea     r8, aName; "Name"
0x1800050b0  mov     rcx, r15; hkey
0x1800050b3  mov     [rsp+110h+phkResult], 0; unsigned int
0x1800050bc  mov     r9d, 2; dwFlags
0x1800050c2  mov     rdx, r14; lpSubKey
0x1800050c5  call    cs:__imp_RegGetValueW
0x1800050cb  test    eax, eax
0x1800050cd  jz      short loc_18000510A
0x1800050cf  mov     rcx, [rbp+57h]; this
0x1800050d3  mov     r9d, eax; char *
0x1800050d6  mov     edx, 0B0h; void *
0x1800050db  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800050e0  mov     rcx, [rsp+110h+hKey]; hKey
0x1800050e5  mov     ebx, eax
0x1800050e7  test    rcx, rcx
0x1800050ea  jz      short loc_1800050F2
0x1800050ec  call    cs:__imp_RegCloseKey
0x1800050f2  mov     rcx, [rbp+4Fh+var_B8]; hKey
0x1800050f6  test    rcx, rcx
0x1800050f9  jz      loc_180005485
0x1800050ff  call    cs:__imp_RegCloseKey
0x180005105  jmp     loc_180005485
0x18000510a  lea     rax, [rbp+4Fh+var_C8]
0x18000510e  mov     [rbp+4Fh+var_C8], 104h
0x180005115  mov     [rsp+110h+pcbData], rax; pcbData
0x18000511a  lea     r12, [rdi+220h]
0x180005121  mov     [rsp+110h+pvData], r12; pvData
0x180005126  lea     r8, aCertlrpcendpoi; "CertLRPCEndPoint"
0x18000512d  mov     r9d, 2; dwFlags
0x180005133  mov     [rsp+110h+phkResult], 0; pdwType
0x18000513c  mov     rdx, r14; lpSubKey
0x18000513f  mov     rcx, r15; hkey
0x180005142  call    cs:__imp_RegGetValueW
0x180005148  test    eax, eax
0x18000514a  jz      short loc_180005153
0x18000514c  xor     eax, eax
0x18000514e  mov     [r12], ax
0x180005153  mov     rcx, [rsp+110h+hKey]; hKey
0x180005158  lea     r13, [rdi+858h]
0x18000515f  mov     dword ptr [r13+0], 3
0x180005167  test    rcx, rcx
0x18000516a  jz      short loc_180005172
0x18000516c  call    cs:__imp_RegCloseKey
0x180005172  mov     rcx, [rbp+4Fh+var_B8]; hKey
0x180005176  test    rcx, rcx
0x180005179  jz      short loc_180005181
0x18000517b  call    cs:__imp_RegCloseKey
0x180005181  mov     r9d, 2C000h; dwFlags
0x180005187  mov     [rsp+110h+phkResult], rbx; unsigned int
0x18000518c  xor     r8d, r8d; hCryptProv
0x18000518f  mov     edx, 10001h; dwEncodingType
0x180005194  mov     ecx, 0Ah; lpszStoreProvider
0x180005199  call    cs:__imp_CertOpenStore
0x18000519f  mov     [rdi+838h], rax
0x1800051a6  test    rax, rax
0x1800051a9  jnz     short loc_180005221
0x1800051ab  xor     r9d, r9d; pvReserved
0x1800051ae  xor     r8d, r8d; pStoreInfo
0x1800051b1  mov     edx, 22000h; dwFlags
0x1800051b6  mov     rcx, rbx; pvSystemStore
0x1800051b9  call    cs:__imp_CertRegisterSystemStore
0x1800051bf  test    eax, eax
0x1800051c1  jnz     short loc_1800051DD
0x1800051c3  mov     rcx, [rbp+57h]; this
0x1800051c7  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\identity\\certpo"...
0x1800051ce  mov     edx, 0C3h; void *
0x1800051d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800051d8  jmp     loc_180004F80
0x1800051dd  mov     r9d, 2C000h; dwFlags
0x1800051e3  mov     [rsp+110h+phkResult], rbx; pvPara
0x1800051e8  xor     r8d, r8d; hCryptProv
0x1800051eb  mov     edx, 10001h; dwEncodingType
0x1800051f0  mov     ecx, 0Ah; lpszStoreProvider
0x1800051f5  call    cs:__imp_CertOpenStore
0x1800051fb  mov     [rdi+838h], rax
0x180005202  test    rax, rax
0x180005205  jnz     short loc_180005221
0x180005207  mov     rcx, [rbp+57h]; this
0x18000520b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\identity\\certpo"...
0x180005212  mov     edx, 0C8h; void *
0x180005217  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000521c  jmp     loc_180004F80
0x180005221  xor     r9d, r9d; lpName
0x180005224  xor     r8d, r8d; bInitialState
0x180005227  mov     edx, 1; bManualReset
0x18000522c  xor     ecx, ecx; lpEventAttributes
0x18000522e  call    cs:__imp_CreateEventW
0x180005234  lea     r9, [rdi+840h]; char *
0x18000523b  mov     [r9], rax
0x18000523e  test    rax, rax
0x180005241  jnz     short loc_18000525D
0x180005243  mov     rcx, [rbp+57h]; this
0x180005247  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\identity\\certpo"...
0x18000524e  mov     edx, 0CBh; void *
0x180005253  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005258  jmp     loc_180004F80
0x18000525d  mov     rcx, [rdi+838h]; hCertStore
0x180005264  xor     edx, edx; dwFlags
0x180005266  mov     r8d, 2; dwCtrlType
0x18000526c  call    cs:__imp_CertControlStore
0x180005272  test    eax, eax
0x180005274  jnz     short loc_180005290
0x180005276  mov     rcx, [rbp+57h]; this
0x18000527a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\identity\\certpo"...
0x180005281  mov     edx, 0CDh; void *
0x180005286  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000528b  jmp     loc_180004F80
0x180005290  xor     edx, edx; pPrevCertContext
0x180005292  xor     r15d, r15d
0x180005295  xor     ebx, ebx
0x180005297  mov     rcx, [rdi+838h]; hCertStore
0x18000529e  mov     [rbp+4Fh+pCertContext], 0
0x1800052a6  call    cs:__imp_CertEnumCertificatesInStore
0x1800052ac  lea     rdx, [rsp+110h+hKey]
  ... truncated ...
```
