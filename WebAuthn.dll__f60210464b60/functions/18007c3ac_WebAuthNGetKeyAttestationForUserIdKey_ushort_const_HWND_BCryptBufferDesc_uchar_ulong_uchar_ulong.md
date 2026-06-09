# WebAuthNGetKeyAttestationForUserIdKey(ushort const *,HWND__ *,_BCryptBufferDesc *,uchar * *,ulong *,uchar * *,ulong *)

- ea: `0x18007c3ac`
- end: `0x18007c8c1`
- name: `?WebAuthNGetKeyAttestationForUserIdKey@@YAJPEBGPEAUHWND__@@PEAU_BCryptBufferDesc@@PEAPEAEPEAK34@Z`
- size: `1301`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszKeyName@<rcx>, HWND@<rdx>, struct _BCryptBufferDesc *@<r8>, unsigned __int8 **@<r9>, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001f2c4`

## callees

- `0x180002c6c`
- `0x18001687c`
- `0x180019938`
- `0x180020584`
- `0x180020614`
- `0x180036da4`
- `0x180046820`
- `0x1800627e0`
- `0x18007c3ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c76c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c812`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c827`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c76c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c812`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c827`
- `ngcutils!NgcGetAttestationStatement` at `0x18007c72b`
- `ngcutils!NgcGetAttestationStatement` at `0x18007c72b`
- `ngcutils!NgcGetNCryptBinaryBlob` at `0x18007c7d1`
- `ngcutils!NgcGetNCryptBinaryBlob` at `0x18007c7d1`
- `ngcutils!NgcSetNCryptWindowHandle` at `0x18007c630`
- `ngcutils!NgcSetNCryptWindowHandle` at `0x18007c630`
- `ncrypt!NCryptOpenKey` at `0x18007c5e5`
- `ncrypt!NCryptOpenKey` at `0x18007c69f`
- `ncrypt!NCryptOpenKey` at `0x18007c5e5`
- `ncrypt!NCryptOpenKey` at `0x18007c69f`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007c57f`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007c57f`

## string_xrefs

- `0x18007c3e9`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c416`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c44b`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c480`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c4b5`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c596`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c5fc`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c64a`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c6b6`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c74c`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`
- `0x18007c7f2`: `onecore\ds\security\fido\webauthn\dll\webauthnncrypt.cpp`

## pseudocode

```c
__int64 __fastcall WebAuthNGetKeyAttestationForUserIdKey(
        LPCWSTR pszKeyName,
        HWND a2,
        struct _BCryptBufferDesc *a3,
        HLOCAL *a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  __int64 result; // rax
  unsigned int *v11; // rsi
  unsigned __int8 **v12; // r14
  unsigned int *v13; // r15
  __int64 v14; // r8
  __int64 v15; // r9
  _DWORD *v16; // r8
  __int64 v17; // r9
  int v18; // r8d
  int v19; // r9d
  char *v20; // rdx
  int *v21; // rcx
  SECURITY_STATUS v22; // eax
  unsigned int v23; // ebx
  const char *v24; // r9
  SECURITY_STATUS v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  SECURITY_STATUS v29; // eax
  unsigned int v30; // ebx
  int AttestationStatement; // ebx
  HLOCAL v32; // rcx
  HLOCAL v33; // rcx
  int dwFlags; // [rsp+20h] [rbp-88h]
  int dwFlagsa; // [rsp+20h] [rbp-88h]
  int dwFlagsb; // [rsp+20h] [rbp-88h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+30h] [rbp-78h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-70h] BYREF
  NCRYPT_KEY_HANDLE v39; // [rsp+40h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-60h] BYREF
  int v41; // [rsp+50h] [rbp-58h] BYREF
  HLOCAL v42; // [rsp+58h] [rbp-50h] BYREF
  int v43[2]; // [rsp+60h] [rbp-48h] BYREF
  HLOCAL *p_hMem; // [rsp+68h] [rbp-40h] BYREF
  __int64 v45; // [rsp+70h] [rbp-38h] BYREF
  char v46; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  unsigned int v48; // [rsp+B0h] [rbp+8h] BYREF
  struct _BCryptBufferDesc *v49; // [rsp+C0h] [rbp+18h]

  v49 = a3;
  if ( !pszKeyName )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EC,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  v11 = a5;
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  v12 = a6;
  if ( !a6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  v13 = a7;
  if ( !a7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
      (const char *)0x80090027LL,
      dwFlags);
    return 2148073511LL;
  }
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                            a2,
                            a3) )
    {
      v16 = *(_DWORD **)(wil::details::static_lazy<FidoTraceProvider>::get() + 16);
      if ( *v16 <= 5u || !(unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL, v16, v17) )
        goto LABEL_19;
      v20 = (char *)&unk_180185ED8;
      LODWORD(v21) = v18;
    }
    else
    {
      if ( (unsigned int)dword_1801AB180 <= 5
        || !(unsigned __int8)tlgKeywordOn(&dword_1801AB180, 0x400000000000LL, v14, v15) )
      {
        goto LABEL_19;
      }
      v20 = byte_180185F1D;
      v21 = &dword_1801AB180;
    }
    *(_QWORD *)v43 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (_DWORD)v21,
      (_DWORD)v20,
      v18,
      v19,
      (__int64)v43);
LABEL_19:
    phProvider = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phProvider,
      0);
    v22 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x205,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
        (const char *)(unsigned int)v22,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      return v23;
    }
    phKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &phKey,
      0);
    v25 = NCryptOpenKey(phProvider, &phKey, pszKeyName, 0, 0x40u);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20D,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
        (const char *)(unsigned int)v25,
        dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      return v26;
    }
    v27 = NgcSetNCryptWindowHandle(phKey, a2);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x212,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
        (const char *)(unsigned int)v27,
        dwFlagsa);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      return v28;
    }
    v39 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
      &v39,
      0);
    v29 = NCryptOpenKey(phProvider, &v39, pszKeyName, 0, 0x100u);
    v30 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21F,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
        (const char *)(unsigned int)v29,
        dwFlagsb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v39);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      return v30;
    }
    v41 = 0;
    hMem = 0;
    p_hMem = &hMem;
    v45 = 0;
    v46 = 1;
    AttestationStatement = NgcGetAttestationStatement(phKey, v39, v49, &v45);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( AttestationStatement < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
        (const char *)(unsigned int)AttestationStatement,
        (int)&v41);
      v32 = hMem;
      hMem = 0;
      if ( !v32 )
      {
LABEL_30:
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v39);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
        return (unsigned int)AttestationStatement;
      }
LABEL_29:
      LocalFree(v32);
      goto LABEL_30;
    }
    v48 = 0;
    v42 = 0;
    p_hMem = &v42;
    v45 = 0;
    v46 = 1;
    AttestationStatement = NgcGetNCryptBinaryBlob(v39, L"SmartCardKeyCertificate", &v45, &v48);
    wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( AttestationStatement < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x230,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
        (const char *)(unsigned int)AttestationStatement,
        (int)&v41);
      v33 = v42;
      v42 = 0;
      if ( v33 )
        LocalFree(v33);
      v32 = hMem;
      hMem = 0;
      if ( !v32 )
        goto LABEL_30;
      goto LABEL_29;
    }
    *v12 = (unsigned __int8 *)v42;
    *v13 = v48;
    *a4 = hMem;
    *v11 = v41;
    v42 = 0;
    hMem = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v39);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x23B,
                           (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnncrypt.cpp",
                           v24);
  }
  return result;
}

```

## disassembly

```asm
0x18007c3ac  mov     [rsp+arg_8], rbx
0x18007c3b1  mov     [rsp+arg_18], rsi
0x18007c3b6  mov     [rsp+arg_10], r8
0x18007c3bb  push    rdi
0x18007c3bc  push    r12
0x18007c3be  push    r13
0x18007c3c0  push    r14
0x18007c3c2  push    r15
0x18007c3c4  sub     rsp, 80h
0x18007c3cb  mov     r12, r9
0x18007c3ce  mov     r13, rdx
0x18007c3d1  mov     rdi, rcx
0x18007c3d4  test    rcx, rcx
0x18007c3d7  jnz     short loc_18007C401
0x18007c3d9  mov     rcx, [rsp+0A8h]; this
0x18007c3e1  mov     ebx, 80090027h
0x18007c3e6  mov     r9d, ebx; char *
0x18007c3e9  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c3f0  mov     edx, 1ECh; void *
0x18007c3f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c3fa  mov     eax, ebx
0x18007c3fc  jmp     loc_18007C8A3
0x18007c401  test    r12, r12
0x18007c404  jnz     short loc_18007C42E
0x18007c406  mov     rcx, [rsp+0A8h]; this
0x18007c40e  mov     ebx, 80090027h
0x18007c413  mov     r9d, ebx; char *
0x18007c416  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c41d  mov     edx, 1EDh; void *
0x18007c422  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c427  mov     eax, ebx
0x18007c429  jmp     loc_18007C8A3
0x18007c42e  mov     rsi, [rsp+0A8h+arg_20]
0x18007c436  test    rsi, rsi
0x18007c439  jnz     short loc_18007C463
0x18007c43b  mov     rcx, [rsp+0A8h]; this
0x18007c443  mov     ebx, 80090027h
0x18007c448  mov     r9d, ebx; char *
0x18007c44b  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c452  mov     edx, 1EEh; void *
0x18007c457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c45c  mov     eax, ebx
0x18007c45e  jmp     loc_18007C8A3
0x18007c463  mov     r14, [rsp+0A8h+arg_28]
0x18007c46b  test    r14, r14
0x18007c46e  jnz     short loc_18007C498
0x18007c470  mov     rcx, [rsp+0A8h]; this
0x18007c478  mov     ebx, 80090027h
0x18007c47d  mov     r9d, ebx; char *
0x18007c480  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c487  mov     edx, 1EFh; void *
0x18007c48c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c491  mov     eax, ebx
0x18007c493  jmp     loc_18007C8A3
0x18007c498  mov     r15, [rsp+0A8h+arg_30]
0x18007c4a0  test    r15, r15
0x18007c4a3  jnz     short loc_18007C4CD
0x18007c4a5  mov     rcx, [rsp+0A8h]; this
0x18007c4ad  mov     ebx, 80090027h
0x18007c4b2  mov     r9d, ebx; char *
0x18007c4b5  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c4bc  mov     edx, 1F0h; void *
0x18007c4c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c4c6  mov     eax, ebx
0x18007c4c8  jmp     loc_18007C8A3
0x18007c4cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x18007c4d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x18007c4d9  test    al, al
0x18007c4db  jz      short loc_18007C510
0x18007c4dd  call    ?get@?$static_lazy@VFidoTraceProvider@@@details@wil@@QEAAPEAVFidoTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoTraceProvider>::get(void (*)(void))
0x18007c4e2  mov     r8, [rax+10h]
0x18007c4e6  mov     eax, [r8]
0x18007c4e9  cmp     eax, 5
0x18007c4ec  jbe     short loc_18007C55B
0x18007c4ee  mov     rdx, 400000000000h
0x18007c4f8  mov     rcx, r8
0x18007c4fb  call    _tlgKeywordOn
0x18007c500  test    al, al
0x18007c502  jz      short loc_18007C55B
0x18007c504  lea     rdx, unk_180185ED8
0x18007c50b  mov     rcx, r8
0x18007c50e  jmp     short loc_18007C543
0x18007c510  mov     eax, cs:dword_1801AB180
0x18007c516  cmp     eax, 5
0x18007c519  jbe     short loc_18007C55B
0x18007c51b  mov     rdx, 400000000000h
0x18007c525  lea     rcx, dword_1801AB180
0x18007c52c  call    _tlgKeywordOn
0x18007c531  test    al, al
0x18007c533  jz      short loc_18007C55B
0x18007c535  lea     rdx, byte_180185F1D
0x18007c53c  lea     rcx, dword_1801AB180
0x18007c543  lea     rax, [rsp+0A8h+var_48]
0x18007c548  mov     qword ptr [rsp+0A8h+dwFlags], rax; int
0x18007c54d  mov     qword ptr [rsp+0A8h+var_48], 1000000h
0x18007c556  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18007c55b  mov     [rsp+0A8h+phProvider], 0
0x18007c564  xor     edx, edx
0x18007c566  lea     rcx, [rsp+0A8h+phProvider]
0x18007c56b  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18007c570  xor     r8d, r8d; dwFlags
0x18007c573  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x18007c57a  lea     rcx, [rsp+0A8h+phProvider]; phProvider
0x18007c57f  call    cs:__imp_NCryptOpenStorageProvider
0x18007c585  mov     ebx, eax
0x18007c587  test    eax, eax
0x18007c589  jns     short loc_18007C5B8
0x18007c58b  mov     rcx, [rsp+0A8h]; this
0x18007c593  mov     r9d, eax; char *
0x18007c596  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c59d  mov     edx, 205h; void *
0x18007c5a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c5a7  lea     rcx, [rsp+0A8h+phProvider]
0x18007c5ac  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c5b1  mov     eax, ebx
0x18007c5b3  jmp     loc_18007C8A3
0x18007c5b8  mov     [rsp+0A8h+phKey], 0
0x18007c5c1  xor     edx, edx
0x18007c5c3  lea     rcx, [rsp+0A8h+phKey]
0x18007c5c8  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18007c5cd  mov     [rsp+0A8h+dwFlags], 40h ; '@'; int
0x18007c5d5  xor     r9d, r9d; dwLegacyKeySpec
0x18007c5d8  mov     r8, rdi; pszKeyName
0x18007c5db  lea     rdx, [rsp+0A8h+phKey]; phKey
0x18007c5e0  mov     rcx, [rsp+0A8h+phProvider]; hProvider
0x18007c5e5  call    cs:__imp_NCryptOpenKey
0x18007c5eb  mov     ebx, eax
0x18007c5ed  test    eax, eax
0x18007c5ef  jns     short loc_18007C628
0x18007c5f1  mov     rcx, [rsp+0A8h]; this
0x18007c5f9  mov     r9d, eax; char *
0x18007c5fc  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c603  mov     edx, 20Dh; void *
0x18007c608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c60d  lea     rcx, [rsp+0A8h+phKey]
0x18007c612  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c617  lea     rcx, [rsp+0A8h+phProvider]
0x18007c61c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c621  mov     eax, ebx
0x18007c623  jmp     loc_18007C8A3
0x18007c628  mov     rdx, r13
0x18007c62b  mov     rcx, [rsp+0A8h+phKey]
0x18007c630  call    cs:__imp_NgcSetNCryptWindowHandle
0x18007c636  mov     ebx, eax
0x18007c638  xor     r13d, r13d
0x18007c63b  test    eax, eax
0x18007c63d  jns     short loc_18007C676
0x18007c63f  mov     rcx, [rsp+0A8h]; this
0x18007c647  mov     r9d, eax; char *
0x18007c64a  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c651  mov     edx, 212h; void *
0x18007c656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c65b  lea     rcx, [rsp+0A8h+phKey]
0x18007c660  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c665  lea     rcx, [rsp+0A8h+phProvider]
0x18007c66a  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c66f  mov     eax, ebx
0x18007c671  jmp     loc_18007C8A3
0x18007c676  mov     [rsp+0A8h+var_68], r13
0x18007c67b  xor     edx, edx
0x18007c67d  lea     rcx, [rsp+0A8h+var_68]
0x18007c682  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18007c687  mov     [rsp+0A8h+dwFlags], 100h; int
0x18007c68f  xor     r9d, r9d; dwLegacyKeySpec
0x18007c692  mov     r8, rdi; pszKeyName
0x18007c695  lea     rdx, [rsp+0A8h+var_68]; phKey
0x18007c69a  mov     rcx, [rsp+0A8h+phProvider]; hProvider
0x18007c69f  call    cs:__imp_NCryptOpenKey
0x18007c6a5  mov     ebx, eax
0x18007c6a7  test    eax, eax
0x18007c6a9  jns     short loc_18007C6EC
0x18007c6ab  mov     rcx, [rsp+0A8h]; this
0x18007c6b3  mov     r9d, eax; char *
0x18007c6b6  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c6bd  mov     edx, 21Fh; void *
0x18007c6c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c6c7  lea     rcx, [rsp+0A8h+var_68]
0x18007c6cc  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c6d1  lea     rcx, [rsp+0A8h+phKey]
0x18007c6d6  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c6db  lea     rcx, [rsp+0A8h+phProvider]
0x18007c6e0  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c6e5  mov     eax, ebx
0x18007c6e7  jmp     loc_18007C8A3
0x18007c6ec  mov     [rsp+0A8h+var_58], r13d
0x18007c6f1  mov     [rsp+0A8h+hMem], r13
0x18007c6f6  lea     rax, [rsp+0A8h+hMem]
0x18007c6fb  mov     [rsp+0A8h+var_40], rax
0x18007c700  mov     [rsp+0A8h+var_38], r13
0x18007c705  mov     [rsp+0A8h+var_30], 1
0x18007c70a  lea     rax, [rsp+0A8h+var_58]
0x18007c70f  mov     qword ptr [rsp+0A8h+dwFlags], rax; int
0x18007c714  lea     r9, [rsp+0A8h+var_38]
0x18007c719  mov     r8, [rsp+0A8h+arg_10]
0x18007c721  mov     rdx, [rsp+0A8h+var_68]
0x18007c726  mov     rcx, [rsp+0A8h+phKey]
0x18007c72b  call    cs:__imp_NgcGetAttestationStatement
0x18007c731  mov     ebx, eax
0x18007c733  lea     rcx, [rsp+0A8h+var_40]
0x18007c738  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18007c73d  test    ebx, ebx
0x18007c73f  jns     short loc_18007C797
0x18007c741  mov     rcx, [rsp+0A8h]; this
0x18007c749  mov     r9d, ebx; char *
0x18007c74c  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c753  mov     edx, 228h; void *
0x18007c758  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c75d  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18007c762  mov     [rsp+0A8h+hMem], r13
0x18007c767  test    rcx, rcx
0x18007c76a  jz      short loc_18007C772
0x18007c76c  call    cs:__imp_LocalFree
0x18007c772  lea     rcx, [rsp+0A8h+var_68]
0x18007c777  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c77c  lea     rcx, [rsp+0A8h+phKey]
0x18007c781  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c786  lea     rcx, [rsp+0A8h+phProvider]
0x18007c78b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c790  mov     eax, ebx
0x18007c792  jmp     loc_18007C8A3
0x18007c797  mov     [rsp+0A8h+arg_0], r13d
0x18007c79f  mov     [rsp+0A8h+var_50], r13
0x18007c7a4  lea     rax, [rsp+0A8h+var_50]
0x18007c7a9  mov     [rsp+0A8h+var_40], rax
0x18007c7ae  mov     [rsp+0A8h+var_38], r13
0x18007c7b3  mov     [rsp+0A8h+var_30], 1
0x18007c7b8  lea     r9, [rsp+0A8h+arg_0]
0x18007c7c0  lea     r8, [rsp+0A8h+var_38]
0x18007c7c5  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18007c7cc  mov     rcx, [rsp+0A8h+var_68]
0x18007c7d1  call    cs:__imp_NgcGetNCryptBinaryBlob
0x18007c7d7  mov     ebx, eax
0x18007c7d9  lea     rcx, [rsp+0A8h+var_40]
0x18007c7de  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18007c7e3  test    ebx, ebx
0x18007c7e5  jns     short loc_18007C84F
0x18007c7e7  mov     rcx, [rsp+0A8h]; this
0x18007c7ef  mov     r9d, ebx; char *
0x18007c7f2  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18007c7f9  mov     edx, 230h; void *
0x18007c7fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c803  mov     rcx, [rsp+0A8h+var_50]; hMem
0x18007c808  mov     [rsp+0A8h+var_50], r13
0x18007c80d  test    rcx, rcx
0x18007c810  jz      short loc_18007C818
0x18007c812  call    cs:__imp_LocalFree
0x18007c818  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18007c81d  mov     [rsp+0A8h+hMem], r13
0x18007c822  test    rcx, rcx
0x18007c825  jz      short loc_18007C82D
0x18007c827  call    cs:__imp_LocalFree
0x18007c82d  lea     rcx, [rsp+0A8h+var_68]
0x18007c832  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c837  lea     rcx, [rsp+0A8h+phKey]
0x18007c83c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c841  lea     rcx, [rsp+0A8h+phProvider]
0x18007c846  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c84b  mov     eax, ebx
0x18007c84d  jmp     short loc_18007C8A3
0x18007c84f  mov     rax, [rsp+0A8h+var_50]
0x18007c854  mov     [r14], rax
0x18007c857  mov     eax, [rsp+0A8h+arg_0]
0x18007c85e  mov     [r15], eax
0x18007c861  mov     rax, [rsp+0A8h+hMem]
0x18007c866  mov     [r12], rax
0x18007c86a  mov     eax, [rsp+0A8h+var_58]
0x18007c86e  mov     [rsi], eax
0x18007c870  mov     [rsp+0A8h+var_50], r13
0x18007c875  mov     [rsp+0A8h+hMem], r13
0x18007c87a  lea     rcx, [rsp+0A8h+var_68]
0x18007c87f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c884  lea     rcx, [rsp+0A8h+phKey]
0x18007c889  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c88e  lea     rcx, [rsp+0A8h+phProvider]
0x18007c893  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18007c898  xor     eax, eax
0x18007c89a  jmp     short loc_18007C8A3
0x18007c89c  mov     eax, [rsp+0A8h+arg_0]
0x18007c8a3  lea     r11, [rsp+0A8h+var_28]
0x18007c8ab  mov     rbx, [r11+38h]
0x18007c8af  mov     rsi, [r11+48h]
0x18007c8b3  mov     rsp, r11
0x18007c8b6  pop     r15
0x18007c8b8  pop     r14
0x18007c8ba  pop     r13
0x18007c8bc  pop     r12
0x18007c8be  pop     rdi
0x18007c8bf  retn
```
