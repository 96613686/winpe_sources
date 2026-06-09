# CtapPluginCreateOperationRequestSigningKey

- ea: `0x180050428`
- end: `0x180050d3a`
- name: `CtapPluginCreateOperationRequestSigningKey`
- size: `2322`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800db110`
- `0x180115ecc`
- `0x180119c80`

## callees

- `0x18001d5e4`
- `0x1800350b4`
- `0x180036da4`
- `0x18003a9e8`
- `0x18004349c`
- `0x180043608`
- `0x18004ac74`
- `0x180050428`
- `0x180067630`
- `0x18007bf50`
- `0x18010c27c`
- `0x18010efb4`
- `0x18010f008`
- `0x18011c42c`
- `0x18012c620`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180050bc5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180050bc5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800504af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800504af`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180050b26`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180050b72`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180050b26`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180050b72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050902`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050902`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050a17`
- `bcrypt!BCryptGenerateKeyPair` at `0x180050597`
- `bcrypt!BCryptGenerateKeyPair` at `0x180050597`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800505f9`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800505f9`
- `bcrypt!BCryptExportKey` at `0x18005067e`
- `bcrypt!BCryptExportKey` at `0x180050717`
- `bcrypt!BCryptExportKey` at `0x1800507a7`
- `bcrypt!BCryptExportKey` at `0x180050851`
- `bcrypt!BCryptExportKey` at `0x18005067e`
- `bcrypt!BCryptExportKey` at `0x180050717`
- `bcrypt!BCryptExportKey` at `0x1800507a7`
- `bcrypt!BCryptExportKey` at `0x180050851`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180050526`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180050526`

## string_xrefs

- `0x180050467`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1800504d5`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18005053d`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1800505ae`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180050610`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180050695`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18005072e`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x1800507be`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180050868`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18005095e`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180050a73`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180050be7`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180050b47`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180050b93`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CtapPluginCreateOperationRequestSigningKey(__int64 a1, const WCHAR *a2, _QWORD *a3, _DWORD *a4)
{
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v8; // ebx
  __int64 result; // rax
  HKEY *v10; // rax
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  NTSTATUS v13; // eax
  unsigned int v14; // ebx
  NTSTATUS v15; // eax
  unsigned int v16; // ebx
  NTSTATUS v17; // eax
  unsigned int v18; // ebx
  NTSTATUS v19; // eax
  unsigned int v20; // ebx
  NTSTATUS v21; // eax
  unsigned int v22; // ebx
  const char *v23; // r9
  NTSTATUS v24; // eax
  unsigned int v25; // ebx
  NTSTATUS v26; // eax
  unsigned int v27; // ebx
  DWORD v28; // edi
  void *v29; // r14
  DWORD v30; // ebx
  void *v31; // rsi
  int v32; // eax
  bool v33; // sf
  int v34; // eax
  bool v35; // sf
  HLOCAL v36; // rax
  HLOCAL v37; // rbx
  int phkResult; // [rsp+20h] [rbp-118h]
  int phkResulta; // [rsp+20h] [rbp-118h]
  int phkResultb; // [rsp+20h] [rbp-118h]
  int phkResultc; // [rsp+20h] [rbp-118h]
  int phkResultd; // [rsp+20h] [rbp-118h]
  int phkResulte; // [rsp+20h] [rbp-118h]
  int phkResultf; // [rsp+20h] [rbp-118h]
  int phkResultg; // [rsp+20h] [rbp-118h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-F8h] BYREF
  _BYTE v47[8]; // [rsp+48h] [rbp-F0h] BYREF
  HKEY v48; // [rsp+50h] [rbp-E8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-E0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-D8h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp-D0h] BYREF
  ULONG cbOutput; // [rsp+6Ch] [rbp-CCh] BYREF
  PUCHAR pbOutput; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v54; // [rsp+78h] [rbp-C0h]
  __int64 v55; // [rsp+88h] [rbp-B0h]
  void *v56; // [rsp+90h] [rbp-A8h] BYREF
  DWORD v57; // [rsp+98h] [rbp-A0h]
  int v58; // [rsp+9Ch] [rbp-9Ch]
  void *Source; // [rsp+A0h] [rbp-98h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-90h]
  void *v61; // [rsp+B8h] [rbp-80h] BYREF
  DWORD v62; // [rsp+C0h] [rbp-78h]
  int v63; // [rsp+C4h] [rbp-74h]
  void *v64; // [rsp+C8h] [rbp-70h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-68h]
  PUCHAR v66[11]; // [rsp+E0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  hKey = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, &hKey);
  v8 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC04,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v8;
  }
  v48 = 0;
  v10 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v48);
  v11 = RegOpenKeyExW(hKey, a2, 0, 0xF003Fu, v10);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    if ( (v12 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0A,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)v12,
        phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v12;
  }
  phAlgorithm = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &phAlgorithm,
    0);
  v13 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"ECDSA_P384", 0, 0);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0F,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)v13,
      phkResulta);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v14;
  }
  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v15 = BCryptGenerateKeyPair(phAlgorithm, &phKey, 0, 0);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC13,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)v15,
      phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v16;
  }
  v17 = BCryptFinalizeKeyPair(phKey, 0);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC16,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)v17,
      phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v18;
  }
  cbOutput = 0;
  v19 = BCryptExportKey(phKey, 0, L"ECCPUBLICBLOB", 0, 0, &cbOutput, 0);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC19,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)v19,
      phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v20;
  }
  try
  {
    ((void (*)(void))std::vector<unsigned char>::vector<unsigned char>)();
    v21 = BCryptExportKey(phKey, 0, L"ECCPUBLICBLOB", pbOutput, cbOutput, &cbOutput, 0);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC1B,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)v21,
        phkResultc);
      std::vector<unsigned char>::_Tidy(&pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v22;
    }
    pcbResult = 0;
    v24 = BCryptExportKey(phKey, 0, L"ECCPRIVATEBLOB", 0, 0, &pcbResult, 0);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC1E,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)v24,
        phkResultd);
      std::vector<unsigned char>::_Tidy(&pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v25;
    }
    std::vector<unsigned char>::vector<unsigned char>(v66, pcbResult, v47);
    v26 = BCryptExportKey(phKey, 0, L"ECCPRIVATEBLOB", v66[0], pcbResult, &pcbResult, 0);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC20,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)v26,
        phkResulte);
      std::vector<unsigned char>::_Tidy(v66);
      std::vector<unsigned char>::_Tidy(&pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v27;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Source);
    CtapDataProtector::ProtectData(0, &pbOutput, &Source);
    v28 = v60 - (_DWORD)Source;
    v55 = v60 - (_QWORD)Source;
    v29 = CoTaskMemAlloc(v60 - (_QWORD)Source);
    v56 = v29;
    v57 = v28;
    v58 = HIDWORD(v55);
    if ( memcpy_s_3(v29, v60 - (_QWORD)Source, Source, v60 - (_QWORD)Source) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC26,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x8007010ALL,
        phkResulte);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v56);
      std::vector<unsigned char>::_Tidy(&Source);
      std::vector<unsigned char>::_Tidy(v66);
      std::vector<unsigned char>::_Tidy(&pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 2147942666LL;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v64);
    CtapDataProtector::ProtectData(0, v66, &v64);
    v30 = v65 - (_DWORD)v64;
    v55 = v65 - (_QWORD)v64;
    v31 = CoTaskMemAlloc(v65 - (_QWORD)v64);
    v61 = v31;
    v62 = v30;
    v63 = HIDWORD(v55);
    if ( memcpy_s_3(v31, v65 - (_QWORD)v64, v64, v65 - (_QWORD)v64) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC2C,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x8007010ALL,
        phkResulte);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v61);
      std::vector<unsigned char>::_Tidy(&v64);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v56);
      std::vector<unsigned char>::_Tidy(&Source);
      std::vector<unsigned char>::_Tidy(v66);
      std::vector<unsigned char>::_Tidy(&pbOutput);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 2147942666LL;
    }
    v32 = RegSetKeyValueW(v48, 0, L"RequestSignPrivateKey", 3u, v31, v30);
    v33 = v32 < 0;
    if ( v32 > 0 )
    {
      v32 = (unsigned __int16)v32 | 0x80070000;
      v33 = v32 < 0;
    }
    if ( v33 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x387,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
        (const char *)(unsigned int)v32,
        phkResultf);
    v34 = RegSetKeyValueW(v48, 0, L"RequestSignPubKey", 3u, v29, v28);
    v35 = v34 < 0;
    if ( v34 > 0 )
    {
      v34 = (unsigned __int16)v34 | 0x80070000;
      v35 = v34 < 0;
    }
    if ( v35 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x387,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
        (const char *)(unsigned int)v34,
        phkResultg);
    if ( a3 && a4 )
    {
      v36 = LocalAlloc(0x40u, v54 - (_QWORD)pbOutput);
      v37 = v36;
      if ( !v36 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC37,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
          (const char *)0x8007000ELL,
          phkResultg);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v61);
        std::vector<unsigned char>::_Tidy(&v64);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v56);
        std::vector<unsigned char>::_Tidy(&Source);
        std::vector<unsigned char>::_Tidy(v66);
        std::vector<unsigned char>::_Tidy(&pbOutput);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return 2147942414LL;
      }
      memcpy_s_3(v36, v54 - (_QWORD)pbOutput, pbOutput, v54 - (_QWORD)pbOutput);
      *a3 = v37;
      *a4 = v54 - (_DWORD)pbOutput;
    }
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v61);
    std::vector<unsigned char>::_Tidy(&v64);
    wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&v56);
    std::vector<unsigned char>::_Tidy(&Source);
    std::vector<unsigned char>::_Tidy(v66);
    std::vector<unsigned char>::_Tidy(&pbOutput);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC40,
                           (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x180050428  push    rbx
0x18005042a  push    rsi
0x18005042b  push    rdi
0x18005042c  push    r12
0x18005042e  push    r13
0x180050430  push    r14
0x180050432  push    r15
0x180050434  sub     rsp, 100h
0x18005043b  mov     r15, r9
0x18005043e  mov     r12, r8
0x180050441  mov     rdi, rdx
0x180050444  xor     r13d, r13d
0x180050447  mov     [rsp+138h+hKey], r13
0x18005044c  lea     rdx, [rsp+138h+hKey]
0x180050451  call    GetUserPluginAuthenticatorsRegKey
0x180050456  mov     ebx, eax
0x180050458  test    eax, eax
0x18005045a  jns     short loc_18005048A
0x18005045c  mov     rcx, [rsp+138h]; this
0x180050464  mov     r9d, eax; char *
0x180050467  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18005046e  mov     edx, 0C04h; void *
0x180050473  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050478  nop
0x180050479  lea     rcx, [rsp+138h+hKey]
0x18005047e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050483  mov     eax, ebx
0x180050485  jmp     loc_180050D26
0x18005048a  mov     [rsp+138h+var_E8], r13
0x18005048f  lea     rcx, [rsp+138h+var_E8]
0x180050494  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180050499  mov     [rsp+138h+phkResult], rax; int
0x18005049e  mov     r9d, 0F003Fh; samDesired
0x1800504a4  xor     r8d, r8d; ulOptions
0x1800504a7  mov     rdx, rdi; lpSubKey
0x1800504aa  mov     rcx, [rsp+138h+hKey]; hKey
0x1800504af  call    cs:__imp_RegOpenKeyExW
0x1800504b5  mov     ebx, eax
0x1800504b7  test    eax, eax
0x1800504b9  jz      short loc_180050503
0x1800504bb  jle     short loc_1800504C6
0x1800504bd  movzx   ebx, ax
0x1800504c0  or      ebx, 80070000h
0x1800504c6  test    ebx, ebx
0x1800504c8  jns     short loc_1800504E7
0x1800504ca  mov     rcx, [rsp+138h]; this
0x1800504d2  mov     r9d, ebx; char *
0x1800504d5  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800504dc  mov     edx, 0C0Ah; void *
0x1800504e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800504e6  nop
0x1800504e7  lea     rcx, [rsp+138h+var_E8]
0x1800504ec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800504f1  nop
0x1800504f2  lea     rcx, [rsp+138h+hKey]
0x1800504f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800504fc  mov     eax, ebx
0x1800504fe  jmp     loc_180050D26
0x180050503  mov     [rsp+138h+phAlgorithm], r13
0x180050508  xor     edx, edx
0x18005050a  lea     rcx, [rsp+138h+phAlgorithm]
0x18005050f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180050514  xor     r9d, r9d; dwFlags
0x180050517  xor     r8d, r8d; pszImplementation
0x18005051a  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x180050521  lea     rcx, [rsp+138h+phAlgorithm]; phAlgorithm
0x180050526  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18005052c  mov     ebx, eax
0x18005052e  test    eax, eax
0x180050530  jns     short loc_180050576
0x180050532  mov     rcx, [rsp+138h]; this
0x18005053a  mov     r9d, eax; char *
0x18005053d  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180050544  mov     edx, 0C0Fh; void *
0x180050549  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005054e  nop
0x18005054f  lea     rcx, [rsp+138h+phAlgorithm]
0x180050554  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180050559  nop
0x18005055a  lea     rcx, [rsp+138h+var_E8]
0x18005055f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050564  nop
0x180050565  lea     rcx, [rsp+138h+hKey]
0x18005056a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005056f  mov     eax, ebx
0x180050571  jmp     loc_180050D26
0x180050576  mov     [rsp+138h+phKey], r13
0x18005057b  xor     edx, edx
0x18005057d  lea     rcx, [rsp+138h+phKey]
0x180050582  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180050587  xor     r9d, r9d; dwFlags
0x18005058a  xor     r8d, r8d; dwLength
0x18005058d  lea     rdx, [rsp+138h+phKey]; phKey
0x180050592  mov     rcx, [rsp+138h+phAlgorithm]; hAlgorithm
0x180050597  call    cs:__imp_BCryptGenerateKeyPair
0x18005059d  mov     ebx, eax
0x18005059f  test    eax, eax
0x1800505a1  jns     short loc_1800505F2
0x1800505a3  mov     rcx, [rsp+138h]; this
0x1800505ab  mov     r9d, eax; char *
0x1800505ae  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800505b5  mov     edx, 0C13h; void *
0x1800505ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800505bf  nop
0x1800505c0  lea     rcx, [rsp+138h+phKey]
0x1800505c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800505ca  nop
0x1800505cb  lea     rcx, [rsp+138h+phAlgorithm]
0x1800505d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800505d5  nop
0x1800505d6  lea     rcx, [rsp+138h+var_E8]
0x1800505db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800505e0  nop
0x1800505e1  lea     rcx, [rsp+138h+hKey]
0x1800505e6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800505eb  mov     eax, ebx
0x1800505ed  jmp     loc_180050D26
0x1800505f2  xor     edx, edx; dwFlags
0x1800505f4  mov     rcx, [rsp+138h+phKey]; hKey
0x1800505f9  call    cs:__imp_BCryptFinalizeKeyPair
0x1800505ff  mov     ebx, eax
0x180050601  test    eax, eax
0x180050603  jns     short loc_180050654
0x180050605  mov     rcx, [rsp+138h]; this
0x18005060d  mov     r9d, eax; char *
0x180050610  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180050617  mov     edx, 0C16h; void *
0x18005061c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050621  nop
0x180050622  lea     rcx, [rsp+138h+phKey]
0x180050627  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005062c  nop
0x18005062d  lea     rcx, [rsp+138h+phAlgorithm]
0x180050632  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180050637  nop
0x180050638  lea     rcx, [rsp+138h+var_E8]
0x18005063d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050642  nop
0x180050643  lea     rcx, [rsp+138h+hKey]
0x180050648  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005064d  mov     eax, ebx
0x18005064f  jmp     loc_180050D26
0x180050654  mov     [rsp+138h+cbOutput], r13d
0x180050659  mov     [rsp+138h+dwFlags], r13d; dwFlags
0x18005065e  lea     rax, [rsp+138h+cbOutput]
0x180050663  mov     [rsp+138h+pcbResult], rax; pcbResult
0x180050668  mov     dword ptr [rsp+138h+phkResult], r13d; int
0x18005066d  xor     r9d, r9d; pbOutput
0x180050670  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x180050677  xor     edx, edx; hExportKey
0x180050679  mov     rcx, [rsp+138h+phKey]; hKey
0x18005067e  call    cs:__imp_BCryptExportKey
0x180050684  mov     ebx, eax
0x180050686  test    eax, eax
0x180050688  jns     short loc_1800506D9
0x18005068a  mov     rcx, [rsp+138h]; this
0x180050692  mov     r9d, eax; char *
0x180050695  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18005069c  mov     edx, 0C19h; void *
0x1800506a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800506a6  nop
0x1800506a7  lea     rcx, [rsp+138h+phKey]
0x1800506ac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800506b1  nop
0x1800506b2  lea     rcx, [rsp+138h+phAlgorithm]
0x1800506b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800506bc  nop
0x1800506bd  lea     rcx, [rsp+138h+var_E8]
0x1800506c2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800506c7  nop
0x1800506c8  lea     rcx, [rsp+138h+hKey]
0x1800506cd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800506d2  mov     eax, ebx
0x1800506d4  jmp     loc_180050D26
0x1800506d9  mov     edx, [rsp+138h+cbOutput]
0x1800506dd  lea     r8, [rsp+138h+var_F0]
0x1800506e2  lea     rcx, [rsp+138h+pbOutput]
0x1800506e7  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800506ec  nop
0x1800506ed  mov     eax, [rsp+138h+cbOutput]
0x1800506f1  mov     [rsp+138h+dwFlags], r13d; dwFlags
0x1800506f6  lea     rcx, [rsp+138h+cbOutput]
0x1800506fb  mov     [rsp+138h+pcbResult], rcx; pcbResult
0x180050700  mov     dword ptr [rsp+138h+phkResult], eax; int
0x180050704  mov     r9, [rsp+138h+pbOutput]; pbOutput
0x180050709  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x180050710  xor     edx, edx; hExportKey
0x180050712  mov     rcx, [rsp+138h+phKey]; hKey
0x180050717  call    cs:__imp_BCryptExportKey
0x18005071d  mov     ebx, eax
0x18005071f  test    eax, eax
0x180050721  jns     short loc_18005077D
0x180050723  mov     rcx, [rsp+138h]; this
0x18005072b  mov     r9d, eax; char *
0x18005072e  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180050735  mov     edx, 0C1Bh; void *
0x18005073a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005073f  nop
0x180050740  lea     rcx, [rsp+138h+pbOutput]
0x180050745  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18005074a  nop
0x18005074b  lea     rcx, [rsp+138h+phKey]
0x180050750  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180050755  nop
0x180050756  lea     rcx, [rsp+138h+phAlgorithm]
0x18005075b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180050760  nop
0x180050761  lea     rcx, [rsp+138h+var_E8]
0x180050766  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005076b  nop
0x18005076c  lea     rcx, [rsp+138h+hKey]
0x180050771  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050776  mov     eax, ebx
0x180050778  jmp     loc_180050D26
0x18005077d  mov     [rsp+138h+var_D0], r13d
0x180050782  mov     [rsp+138h+dwFlags], r13d; dwFlags
0x180050787  lea     rax, [rsp+138h+var_D0]
0x18005078c  mov     [rsp+138h+pcbResult], rax; pcbResult
0x180050791  mov     dword ptr [rsp+138h+phkResult], r13d; int
0x180050796  xor     r9d, r9d; pbOutput
0x180050799  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x1800507a0  xor     edx, edx; hExportKey
0x1800507a2  mov     rcx, [rsp+138h+phKey]; hKey
0x1800507a7  call    cs:__imp_BCryptExportKey
0x1800507ad  mov     ebx, eax
0x1800507af  test    eax, eax
0x1800507b1  jns     short loc_18005080D
0x1800507b3  mov     rcx, [rsp+138h]; this
0x1800507bb  mov     r9d, eax; char *
0x1800507be  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1800507c5  mov     edx, 0C1Eh; void *
0x1800507ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800507cf  nop
0x1800507d0  lea     rcx, [rsp+138h+pbOutput]
0x1800507d5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800507da  nop
0x1800507db  lea     rcx, [rsp+138h+phKey]
0x1800507e0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800507e5  nop
0x1800507e6  lea     rcx, [rsp+138h+phAlgorithm]
0x1800507eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800507f0  nop
0x1800507f1  lea     rcx, [rsp+138h+var_E8]
0x1800507f6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800507fb  nop
0x1800507fc  lea     rcx, [rsp+138h+hKey]
0x180050801  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050806  mov     eax, ebx
0x180050808  jmp     loc_180050D26
0x18005080d  mov     edx, [rsp+138h+var_D0]
0x180050811  lea     r8, [rsp+138h+var_F0]
0x180050816  lea     rcx, [rsp+138h+var_58]
0x18005081e  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180050823  nop
0x180050824  mov     eax, [rsp+138h+var_D0]
0x180050828  mov     [rsp+138h+dwFlags], r13d; dwFlags
0x18005082d  lea     rcx, [rsp+138h+var_D0]
0x180050832  mov     [rsp+138h+pcbResult], rcx; pcbResult
0x180050837  mov     dword ptr [rsp+138h+phkResult], eax; int
0x18005083b  mov     r9, [rsp+138h+var_58]; pbOutput
0x180050843  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x18005084a  xor     edx, edx; hExportKey
0x18005084c  mov     rcx, [rsp+138h+phKey]; hKey
0x180050851  call    cs:__imp_BCryptExportKey
0x180050857  mov     ebx, eax
0x180050859  test    eax, eax
0x18005085b  jns     short loc_1800508C5
0x18005085d  mov     rcx, [rsp+138h]; this
0x180050865  mov     r9d, eax; char *
0x180050868  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18005086f  mov     edx, 0C20h; void *
0x180050874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050879  nop
0x18005087a  lea     rcx, [rsp+138h+var_58]
0x180050882  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180050887  nop
0x180050888  lea     rcx, [rsp+138h+pbOutput]
0x18005088d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180050892  nop
0x180050893  lea     rcx, [rsp+138h+phKey]
0x180050898  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005089d  nop
0x18005089e  lea     rcx, [rsp+138h+phAlgorithm]
0x1800508a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800508a8  nop
0x1800508a9  lea     rcx, [rsp+138h+var_E8]
0x1800508ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800508b3  nop
0x1800508b4  lea     rcx, [rsp+138h+hKey]
0x1800508b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800508be  mov     eax, ebx
0x1800508c0  jmp     loc_180050D26
0x1800508c5  lea     rcx, [rsp+138h+Source]
0x1800508cd  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800508d2  nop
0x1800508d3  lea     r8, [rsp+138h+Source]
0x1800508db  lea     rdx, [rsp+138h+pbOutput]
0x1800508e0  xor     ecx, ecx
0x1800508e2  call    ?ProtectData@CtapDataProtector@@SAJQEAXAEAV?$vector@EV?$allocator@E@std@@@std@@1@Z; CtapDataProtector::ProtectData(void * const,std::vector<uchar> &,std::vector<uchar> &)
0x1800508e7  mov     rdi, [rsp+138h+var_90]
  ... truncated ...
```
