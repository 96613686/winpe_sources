# TpmPolicySession::SealWithPolicyInfo(TpmPolicySession::PolicyInfo const *,ulong,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x18004ed74`
- end: `0x18004f1a8`
- name: `?SealWithPolicyInfo@TpmPolicySession@@YAJPEBUPolicyInfo@1@KPEBEKPEAPEAEPEAK@Z`
- size: `1076`
- prototype: `int(TpmPolicySession *__hidden this, const struct TpmPolicySession::PolicyInfo *, unsigned int, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047258`
- `0x18004f3f8`

## callees

- `0x18000782c`
- `0x18002ab60`
- `0x180047228`
- `0x18004826c`
- `0x18004d980`
- `0x18004ed74`
- `0x18004f1b0`
- `0x18005bef0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ef2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f035`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f04a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f0bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f0d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f108`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f11e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f170`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ef2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f035`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f04a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f0bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f0d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f108`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f11e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004f170`
- `ncrypt!NCryptEncrypt` at `0x18004efe0`
- `ncrypt!NCryptEncrypt` at `0x18004f080`
- `ncrypt!NCryptEncrypt` at `0x18004efe0`
- `ncrypt!NCryptEncrypt` at `0x18004f080`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004edb5`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004edb5`
- `ncrypt!NCryptOpenKey` at `0x18004ee19`
- `ncrypt!NCryptOpenKey` at `0x18004ee19`

## string_xrefs

- `0x18004edcc`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004ee30`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004ee91`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004ef07`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004eff7`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x18004f09b`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TpmPolicySession::SealWithPolicyInfo(
        const void *const *this,
        const struct TpmPolicySession::PolicyInfo *a2,
        BYTE *a3,
        const unsigned __int8 *a4,
        PBYTE *a5,
        unsigned __int8 **a6)
{
  DWORD v6; // r12d
  __int64 v8; // rsi
  SECURITY_STATUS v10; // eax
  unsigned int v11; // edi
  __int64 result; // rax
  SECURITY_STATUS v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // edi
  TpmPolicySession *v16; // r14
  const void *const *i; // rcx
  unsigned int v18; // ebx
  int v19; // r15d
  HLOCAL v20; // rcx
  const char *v21; // r9
  unsigned int v22; // esi
  SECURITY_STATUS v23; // eax
  int v24; // ebx
  BYTE **unique; // rax
  BYTE *v26; // rdx
  PBYTE v27; // rcx
  HLOCAL v28; // rcx
  SECURITY_STATUS v29; // eax
  PBYTE v30; // rcx
  HLOCAL v31; // rcx
  PBYTE v32; // rcx
  HLOCAL v33; // rcx
  HLOCAL v34; // rcx
  int dwFlags; // [rsp+20h] [rbp-A8h]
  int dwFlagsa; // [rsp+20h] [rbp-A8h]
  int dwFlagsb; // [rsp+20h] [rbp-A8h]
  int dwFlagsc; // [rsp+20h] [rbp-A8h]
  DWORD pcbResult; // [rsp+40h] [rbp-88h] BYREF
  PBYTE pbOutput; // [rsp+48h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-78h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-70h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+60h] [rbp-68h] BYREF
  HLOCAL v44; // [rsp+68h] [rbp-60h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+70h] [rbp-58h] BYREF
  _DWORD *v46; // [rsp+78h] [rbp-50h]
  _DWORD v47[2]; // [rsp+80h] [rbp-48h] BYREF
  HLOCAL v48; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v6 = (unsigned int)a4;
  v8 = (unsigned int)a2;
  phProvider = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phProvider,
    0);
  v10 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)(unsigned int)v10,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return v11;
  }
  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v13 = NCryptOpenKey(phProvider, &phKey, L"MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF-004E-4E2F-8A4D-0BF633DCB074", 0, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)(unsigned int)v13,
      dwFlagsa);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return v14;
  }
  v15 = 0;
  v16 = (TpmPolicySession *)&this[2 * v8];
  for ( i = this; i != (const void *const *)v16; i += 2 )
  {
    if ( v15 + *(_DWORD *)i < v15 )
    {
      v18 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xCF,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
              (const char *)0xC0000095LL,
              dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      return v18;
    }
    v15 += *(_DWORD *)i;
  }
  try
  {
    wil::make_unique_hlocal<unsigned char [0]>(&hMem);
    v22 = 0;
    while ( this != (const void *const *)v16 )
    {
      v19 = *(_DWORD *)this;
      if ( memcpy_s_0((char *)hMem + v22, v15 - v22, this[1], *(unsigned int *)this) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDC,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
          (const char *)0x8000FFFFLL,
          dwFlagsa);
        v20 = hMem;
        hMem = 0;
        if ( v20 )
          LocalFree(v20);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        return 2147549183LL;
      }
      v22 += v19;
      this += 2;
    }
    v47[0] = v15;
    v47[1] = 71;
    v48 = hMem;
    pPaddingInfo[0] = 0;
    pPaddingInfo[1] = 1;
    v46 = v47;
    pcbResult = 2048;
    wil::make_unique_hlocal<unsigned char [0]>(&pbOutput);
    v23 = NCryptEncrypt(phKey, a3, v6, pPaddingInfo, pbOutput, 0x800u, &pcbResult, 0x100u);
    v24 = v23;
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF5,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
        (const char *)(unsigned int)v23,
        dwFlagsb);
    if ( v24 == -2146893784 )
    {
      unique = (BYTE **)wil::make_unique_hlocal<unsigned char [0]>(&v44);
      v26 = *unique;
      *unique = 0;
      v27 = pbOutput;
      pbOutput = v26;
      if ( v27 )
        LocalFree(v27);
      v28 = v44;
      v44 = 0;
      if ( v28 )
        LocalFree(v28);
      v29 = NCryptEncrypt(phKey, a3, v6, pPaddingInfo, pbOutput, pcbResult, &pcbResult, 0x100u);
      v24 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x102,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
          (const char *)(unsigned int)v29,
          dwFlagsc);
        v30 = pbOutput;
        pbOutput = 0;
        if ( v30 )
          LocalFree(v30);
        v31 = hMem;
        hMem = 0;
        if ( v31 )
          LocalFree(v31);
LABEL_28:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        return (unsigned int)v24;
      }
    }
    else if ( v24 < 0 )
    {
      v32 = pbOutput;
      pbOutput = 0;
      if ( v32 )
        LocalFree(v32);
      v33 = hMem;
      hMem = 0;
      if ( v33 )
        LocalFree(v33);
      goto LABEL_28;
    }
    *a5 = pbOutput;
    *(_DWORD *)a6 = pcbResult;
    pbOutput = 0;
    v34 = hMem;
    hMem = 0;
    if ( v34 )
      LocalFree(v34);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x10C,
                           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
                           v21);
  }
  return result;
}

```

## disassembly

```asm
0x18004ed74  push    rbx
0x18004ed76  push    rsi
0x18004ed77  push    rdi
0x18004ed78  push    r12
0x18004ed7a  push    r13
0x18004ed7c  push    r14
0x18004ed7e  push    r15
0x18004ed80  sub     rsp, 90h
0x18004ed87  mov     r12d, r9d
0x18004ed8a  mov     r13, r8
0x18004ed8d  mov     esi, edx
0x18004ed8f  mov     rbx, rcx
0x18004ed92  xor     r15d, r15d
0x18004ed95  mov     [rsp+0C8h+phProvider], r15
0x18004ed9a  xor     edx, edx
0x18004ed9c  lea     rcx, [rsp+0C8h+phProvider]
0x18004eda1  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004eda6  xor     r8d, r8d; dwFlags
0x18004eda9  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18004edb0  lea     rcx, [rsp+0C8h+phProvider]; phProvider
0x18004edb5  call    cs:__imp_NCryptOpenStorageProvider
0x18004edbb  mov     edi, eax
0x18004edbd  test    eax, eax
0x18004edbf  jns     short loc_18004EDEF
0x18004edc1  mov     rcx, [rsp+0C8h]; this
0x18004edc9  mov     r9d, eax; char *
0x18004edcc  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004edd3  mov     edx, 0BDh; void *
0x18004edd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eddd  nop
0x18004edde  lea     rcx, [rsp+0C8h+phProvider]
0x18004ede3  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004ede8  mov     eax, edi
0x18004edea  jmp     loc_18004F195
0x18004edef  mov     [rsp+0C8h+phKey], r15
0x18004edf4  xor     edx, edx
0x18004edf6  lea     rcx, [rsp+0C8h+phKey]
0x18004edfb  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18004ee00  mov     [rsp+0C8h+dwFlags], r15d; int
0x18004ee05  xor     r9d, r9d; dwLegacyKeySpec
0x18004ee08  lea     r8, pszKeyName; "MICROSOFT_PCP_KSP_RSA_SEAL_KEY_3BD1C4BF"...
0x18004ee0f  lea     rdx, [rsp+0C8h+phKey]; phKey
0x18004ee14  mov     rcx, [rsp+0C8h+phProvider]; hProvider
0x18004ee19  call    cs:__imp_NCryptOpenKey
0x18004ee1f  mov     edi, eax
0x18004ee21  test    eax, eax
0x18004ee23  jns     short loc_18004EE5E
0x18004ee25  mov     rcx, [rsp+0C8h]; this
0x18004ee2d  mov     r9d, eax; char *
0x18004ee30  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004ee37  mov     edx, 0C6h; void *
0x18004ee3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ee41  nop
0x18004ee42  lea     rcx, [rsp+0C8h+phKey]
0x18004ee47  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004ee4c  nop
0x18004ee4d  lea     rcx, [rsp+0C8h+phProvider]
0x18004ee52  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004ee57  mov     eax, edi
0x18004ee59  jmp     loc_18004F195
0x18004ee5e  mov     edi, r15d
0x18004ee61  mov     r14, rsi
0x18004ee64  shl     r14, 4
0x18004ee68  add     r14, rbx
0x18004ee6b  mov     rcx, rbx
0x18004ee6e  cmp     rcx, r14
0x18004ee71  jz      short loc_18004EEC0
0x18004ee73  mov     edx, [rcx]
0x18004ee75  add     edx, edi
0x18004ee77  cmp     edx, edi
0x18004ee79  jb      short loc_18004EE83
0x18004ee7b  mov     edi, edx
0x18004ee7d  add     rcx, 10h
0x18004ee81  jmp     short loc_18004EE6E
0x18004ee83  mov     rcx, [rsp+0C8h]; this
0x18004ee8b  mov     r9d, 0C0000095h; char *
0x18004ee91  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004ee98  mov     edx, 0CFh; void *
0x18004ee9d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004eea2  mov     ebx, eax
0x18004eea4  lea     rcx, [rsp+0C8h+phKey]
0x18004eea9  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004eeae  nop
0x18004eeaf  lea     rcx, [rsp+0C8h+phProvider]
0x18004eeb4  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004eeb9  mov     eax, ebx
0x18004eebb  jmp     loc_18004F195
0x18004eec0  mov     edx, edi
0x18004eec2  lea     rcx, [rsp+0C8h+hMem]
0x18004eec7  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x18004eecc  nop
0x18004eecd  mov     esi, r15d
0x18004eed0  cmp     rbx, r14
0x18004eed3  jz      loc_18004EF5B
0x18004eed9  mov     r15d, [rbx]
0x18004eedc  mov     r9d, r15d; SourceSize
0x18004eedf  mov     edx, edi
0x18004eee1  sub     edx, esi; DestinationSize
0x18004eee3  mov     ecx, esi
0x18004eee5  add     rcx, [rsp+0C8h+hMem]; Destination
0x18004eeea  mov     r8, [rbx+8]; Source
0x18004eeee  call    memcpy_s_0
0x18004eef3  test    eax, eax
0x18004eef5  jz      short loc_18004EF4F
0x18004eef7  mov     rcx, [rsp+0C8h]; this
0x18004eeff  mov     ebx, 8000FFFFh
0x18004ef04  mov     r9d, ebx; char *
0x18004ef07  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004ef0e  mov     edx, 0DCh; void *
0x18004ef13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef18  nop
0x18004ef19  mov     rcx, [rsp+0C8h+hMem]; hMem
0x18004ef1e  mov     [rsp+0C8h+hMem], 0
0x18004ef27  test    rcx, rcx
0x18004ef2a  jz      short loc_18004EF33
0x18004ef2c  call    cs:__imp_LocalFree
0x18004ef32  nop
0x18004ef33  lea     rcx, [rsp+0C8h+phKey]
0x18004ef38  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004ef3d  nop
0x18004ef3e  lea     rcx, [rsp+0C8h+phProvider]
0x18004ef43  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004ef48  mov     eax, ebx
0x18004ef4a  jmp     loc_18004F195
0x18004ef4f  add     esi, r15d
0x18004ef52  add     rbx, 10h
0x18004ef56  jmp     loc_18004EED0
0x18004ef5b  mov     [rsp+0C8h+var_48], edi
0x18004ef62  mov     [rsp+0C8h+var_44], 47h ; 'G'
0x18004ef6d  mov     rax, [rsp+0C8h+hMem]
0x18004ef72  mov     [rsp+0C8h+var_40], rax
0x18004ef7a  xor     r15d, r15d
0x18004ef7d  mov     [rsp+0C8h+pPaddingInfo], r15d
0x18004ef82  mov     [rsp+0C8h+var_54], 1
0x18004ef8a  lea     rax, [rsp+0C8h+var_48]
0x18004ef92  mov     [rsp+0C8h+var_50], rax
0x18004ef97  mov     edx, 800h
0x18004ef9c  mov     [rsp+0C8h+var_88], edx
0x18004efa0  lea     rcx, [rsp+0C8h+pbOutput]
0x18004efa5  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x18004efaa  nop
0x18004efab  mov     eax, [rsp+0C8h+var_88]
0x18004efaf  mov     rdx, [rsp+0C8h+pbOutput]
0x18004efb4  mov     edi, 100h
0x18004efb9  mov     [rsp+0C8h+var_90], edi; dwFlags
0x18004efbd  lea     rcx, [rsp+0C8h+var_88]
0x18004efc2  mov     [rsp+0C8h+pcbResult], rcx; pcbResult
0x18004efc7  mov     [rsp+0C8h+cbOutput], eax; cbOutput
0x18004efcb  mov     qword ptr [rsp+0C8h+dwFlags], rdx; int
0x18004efd0  lea     r9, [rsp+0C8h+pPaddingInfo]; pPaddingInfo
0x18004efd5  mov     r8d, r12d; cbInput
0x18004efd8  mov     rdx, r13; pbInput
0x18004efdb  mov     rcx, [rsp+0C8h+phKey]; hKey
0x18004efe0  call    cs:__imp_NCryptEncrypt
0x18004efe6  mov     ebx, eax
0x18004efe8  mov     rcx, [rsp+0C8h]; this
0x18004eff0  test    eax, eax
0x18004eff2  jns     short loc_18004F006
0x18004eff4  mov     r9d, eax; char *
0x18004eff7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004effe  lea     edx, [rdi-0Bh]; void *
0x18004f001  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004f006  cmp     ebx, 80090028h
0x18004f00c  jnz     loc_18004F0F5
0x18004f012  mov     edx, [rsp+0C8h+var_88]
0x18004f016  lea     rcx, [rsp+0C8h+var_60]
0x18004f01b  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x18004f020  mov     rdx, [rax]
0x18004f023  mov     [rax], r15
0x18004f026  mov     rcx, [rsp+0C8h+pbOutput]; hMem
0x18004f02b  mov     [rsp+0C8h+pbOutput], rdx
0x18004f030  test    rcx, rcx
0x18004f033  jz      short loc_18004F03B
0x18004f035  call    cs:__imp_LocalFree
0x18004f03b  mov     rcx, [rsp+0C8h+var_60]; hMem
0x18004f040  mov     [rsp+0C8h+var_60], r15
0x18004f045  test    rcx, rcx
0x18004f048  jz      short loc_18004F050
0x18004f04a  call    cs:__imp_LocalFree
0x18004f050  mov     eax, [rsp+0C8h+var_88]
0x18004f054  mov     rdx, [rsp+0C8h+pbOutput]
0x18004f059  mov     [rsp+0C8h+var_90], edi; dwFlags
0x18004f05d  lea     rcx, [rsp+0C8h+var_88]
0x18004f062  mov     [rsp+0C8h+pcbResult], rcx; pcbResult
0x18004f067  mov     [rsp+0C8h+cbOutput], eax; cbOutput
0x18004f06b  mov     qword ptr [rsp+0C8h+dwFlags], rdx; int
0x18004f070  lea     r9, [rsp+0C8h+pPaddingInfo]; pPaddingInfo
0x18004f075  mov     r8d, r12d; cbInput
0x18004f078  mov     rdx, r13; pbInput
0x18004f07b  mov     rcx, [rsp+0C8h+phKey]; hKey
0x18004f080  call    cs:__imp_NCryptEncrypt
0x18004f086  mov     ebx, eax
0x18004f088  test    eax, eax
0x18004f08a  jns     loc_18004F13E
0x18004f090  mov     rcx, [rsp+0C8h]; this
0x18004f098  mov     r9d, eax; char *
0x18004f09b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x18004f0a2  mov     edx, 102h; void *
0x18004f0a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f0ac  nop
0x18004f0ad  mov     rcx, [rsp+0C8h+pbOutput]; hMem
0x18004f0b2  mov     [rsp+0C8h+pbOutput], r15
0x18004f0b7  test    rcx, rcx
0x18004f0ba  jz      short loc_18004F0C3
0x18004f0bc  call    cs:__imp_LocalFree
0x18004f0c2  nop
0x18004f0c3  mov     rcx, [rsp+0C8h+hMem]; hMem
0x18004f0c8  mov     [rsp+0C8h+hMem], r15
0x18004f0cd  test    rcx, rcx
0x18004f0d0  jz      short loc_18004F0D9
0x18004f0d2  call    cs:__imp_LocalFree
0x18004f0d8  nop
0x18004f0d9  lea     rcx, [rsp+0C8h+phKey]
0x18004f0de  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004f0e3  nop
0x18004f0e4  lea     rcx, [rsp+0C8h+phProvider]
0x18004f0e9  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004f0ee  mov     eax, ebx
0x18004f0f0  jmp     loc_18004F195
0x18004f0f5  test    ebx, ebx
0x18004f0f7  jns     short loc_18004F13E
0x18004f0f9  mov     rcx, [rsp+0C8h+pbOutput]; hMem
0x18004f0fe  mov     [rsp+0C8h+pbOutput], r15
0x18004f103  test    rcx, rcx
0x18004f106  jz      short loc_18004F10F
0x18004f108  call    cs:__imp_LocalFree
0x18004f10e  nop
0x18004f10f  mov     rcx, [rsp+0C8h+hMem]; hMem
0x18004f114  mov     [rsp+0C8h+hMem], r15
0x18004f119  test    rcx, rcx
0x18004f11c  jz      short loc_18004F125
0x18004f11e  call    cs:__imp_LocalFree
0x18004f124  nop
0x18004f125  lea     rcx, [rsp+0C8h+phKey]
0x18004f12a  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004f12f  nop
0x18004f130  lea     rcx, [rsp+0C8h+phProvider]
0x18004f135  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004f13a  mov     eax, ebx
0x18004f13c  jmp     short loc_18004F195
0x18004f13e  mov     rcx, [rsp+0C8h+arg_20]
0x18004f146  mov     rax, [rsp+0C8h+pbOutput]
0x18004f14b  mov     [rcx], rax
0x18004f14e  mov     rcx, [rsp+0C8h+arg_28]
0x18004f156  mov     eax, [rsp+0C8h+var_88]
0x18004f15a  mov     [rcx], eax
0x18004f15c  mov     [rsp+0C8h+pbOutput], r15
0x18004f161  mov     rcx, [rsp+0C8h+hMem]; hMem
0x18004f166  mov     [rsp+0C8h+hMem], r15
0x18004f16b  test    rcx, rcx
0x18004f16e  jz      short loc_18004F177
0x18004f170  call    cs:__imp_LocalFree
0x18004f176  nop
0x18004f177  lea     rcx, [rsp+0C8h+phKey]
0x18004f17c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004f181  nop
0x18004f182  lea     rcx, [rsp+0C8h+phProvider]
0x18004f187  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18004f18c  nop
0x18004f18d  xor     eax, eax
0x18004f18f  jmp     short loc_18004F195
0x18004f191  mov     eax, [rsp+0C8h+var_88]
0x18004f195  add     rsp, 90h
0x18004f19c  pop     r15
0x18004f19e  pop     r14
0x18004f1a0  pop     r13
0x18004f1a2  pop     r12
0x18004f1a4  pop     rdi
0x18004f1a5  pop     rsi
0x18004f1a6  pop     rbx
0x18004f1a7  retn
```
