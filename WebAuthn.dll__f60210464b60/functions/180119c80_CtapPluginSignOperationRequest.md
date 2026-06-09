# CtapPluginSignOperationRequest

- ea: `0x180119c80`
- end: `0x18011a3c3`
- name: `CtapPluginSignOperationRequest`
- size: `1859`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a76f8`

## callees

- `0x18001d5e4`
- `0x1800350b4`
- `0x180036da4`
- `0x18004349c`
- `0x180043608`
- `0x18004ac74`
- `0x18004e08c`
- `0x180050428`
- `0x1800537a4`
- `0x180067630`
- `0x18007bf50`
- `0x18010b830`
- `0x18010c240`
- `0x18010d820`
- `0x180119c80`
- `0x18011c42c`
- `0x18012c75c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011a298`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011a298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a23f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a2fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a23f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a2fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18011a359`
- `bcrypt!BCryptImportKeyPair` at `0x18011a098`
- `bcrypt!BCryptImportKeyPair` at `0x18011a098`
- `bcrypt!BCryptSignHash` at `0x18011a20c`
- `bcrypt!BCryptSignHash` at `0x18011a2ca`
- `bcrypt!BCryptSignHash` at `0x18011a20c`
- `bcrypt!BCryptSignHash` at `0x18011a2ca`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180119fc7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180119fd9`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180119fc7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180119fd9`

## string_xrefs

- `0x180119cbe`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119cf3`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119d35`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119d92`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119de5`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119f12`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119fef`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011a0bc`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011a175`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011a223`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x18011a2e1`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginmanagement.cpp`
- `0x180119e6c`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x180119ef6`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CtapPluginSignOperationRequest(
        __int64 a1,
        const WCHAR *a2,
        UCHAR *a3,
        ULONG a4,
        UCHAR **a5,
        ULONG *a6)
{
  ULONG *v10; // rbx
  __int64 result; // rax
  int UserPluginAuthenticatorsRegKey; // eax
  unsigned int v13; // edi
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // edi
  int v17; // eax
  unsigned __int8 *v18; // rdi
  char *v19; // rdx
  size_t v20; // r8
  int v21; // eax
  unsigned int v22; // edi
  const char *v23; // r9
  NTSTATUS v24; // edi
  int v25; // eax
  unsigned int v26; // edi
  NTSTATUS v27; // eax
  UCHAR *v28; // rdi
  NTSTATUS v29; // eax
  unsigned int v30; // ebx
  int pbInput; // [rsp+20h] [rbp-D8h]
  int pbInputd; // [rsp+20h] [rbp-D8h]
  int pbInputa; // [rsp+20h] [rbp-D8h]
  int pbInputb; // [rsp+20h] [rbp-D8h]
  int pbInputc; // [rsp+20h] [rbp-D8h]
  HKEY hKey; // [rsp+40h] [rbp-B8h] BYREF
  BCRYPT_KEY_HANDLE v37; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+50h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A0h] BYREF
  void *Source; // [rsp+60h] [rbp-98h] BYREF
  size_t v41; // [rsp+68h] [rbp-90h]
  PUCHAR v42; // [rsp+70h] [rbp-88h] BYREF
  UCHAR *v43; // [rsp+78h] [rbp-80h]
  void *Destination; // [rsp+88h] [rbp-70h] BYREF
  __int64 v45; // [rsp+90h] [rbp-68h]
  BCRYPT_KEY_HANDLE *p_pv; // [rsp+A0h] [rbp-58h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+A8h] [rbp-50h] BYREF
  char v48; // [rsp+B0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v10 = a6;
  if ( !a6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4D,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80004003LL,
      pbInput);
    return 2147500035LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4E,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80004003LL,
      pbInput);
    return 2147500035LL;
  }
  *a6 = 0;
  *a5 = 0;
  v37 = 0;
  v38 = 0;
  UserPluginAuthenticatorsRegKey = GetUserPluginAuthenticatorsRegKey(a1, (__int64)&v38);
  v13 = UserPluginAuthenticatorsRegKey;
  if ( UserPluginAuthenticatorsRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC54,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)UserPluginAuthenticatorsRegKey,
      pbInput);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
    return v13;
  }
  hKey = 0;
  v14 = wil::reg::open_unique_key_nothrow(v38, a2, &hKey, 0);
  v16 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC57,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)(unsigned int)v14,
      pbInput);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
    return v16;
  }
  if ( !hKey )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5A,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
      (const char *)0x80070002LL,
      pbInput);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
    return 2147942402LL;
  }
  Source = 0;
  v41 = 0;
  a6 = (ULONG *)hKey;
  v17 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,wil::err_returncode_policy>(
          &a6,
          v15,
          L"RequestSignPrivateKey",
          &Source);
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xABB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)(unsigned int)v17,
      8);
    CtapPluginCreateOperationRequestSigningKey(a1, a2, 0, 0);
    v18 = (unsigned __int8 *)hKey;
    v19 = (char *)Source + v41;
    v20 = v41;
    if ( Source > (char *)Source + v41 )
      v20 = 0;
    if ( v20 )
      memset_0(Source, 0, v20);
    a6 = (ULONG *)v18;
    v21 = wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,wil::err_returncode_policy>(
            &a6,
            v19,
            L"RequestSignPrivateKey",
            &Source);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xABB,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
        (const char *)(unsigned int)v21,
        8);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC61,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)v22,
        pbInputd);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&Source);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
      return v22;
    }
  }
  try
  {
    std::vector<unsigned char>::vector<unsigned char>(&Destination, v41, &a6);
    memcpy_s_3(Destination, v45 - (_QWORD)Destination, Source, v45 - (_QWORD)Destination);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v42);
    if ( (int)CtapDataProtector::UnprotectData(0, &Destination, &v42) < 0 )
    {
      RegDeleteKeyW(hKey, L"RequestSignPrivateKey");
      RegDeleteKeyW(hKey, L"RequestSignPubKey");
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC6D,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)0x80090015LL,
        8);
      std::vector<unsigned char>::_Tidy(&v42);
      std::vector<unsigned char>::_Tidy(&Destination);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&Source);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
      return 2148073493LL;
    }
    p_pv = &v37;
    phKey = 0;
    v48 = 1;
    v24 = BCryptImportKeyPair((BCRYPT_ALG_HANDLE)0x2F1, 0, L"ECCPRIVATEBLOB", &phKey, v42, (_DWORD)v43 - (_DWORD)v42, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_pv);
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC72,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)v24,
        pbInputa);
      std::vector<unsigned char>::_Tidy(&v42);
      std::vector<unsigned char>::_Tidy(&Destination);
      wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&Source);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
      return (unsigned int)v24;
    }
    if ( v42 != v43 )
      v43 = v42;
    LODWORD(a6) = 0;
    pv = 0;
    p_pv = &pv;
    LOBYTE(phKey) = 1;
    v25 = CtapPluginInternal::HashOperationBlobForSignature(a3, a4, (PUCHAR *)&pv, (unsigned __int8 **)&a6);
    v26 = v25;
    if ( v25 >= 0 )
    {
      v27 = BCryptSignHash(v37, 0, (PUCHAR)pv, (ULONG)a6, 0, *v10, v10, 0);
      v26 = v27;
      if ( v27 >= 0 )
      {
        v28 = (UCHAR *)LocalAlloc(0x40u, *v10);
        v29 = BCryptSignHash(v37, 0, (PUCHAR)pv, (ULONG)a6, v28, *v10, v10, 0);
        v30 = v29;
        if ( v29 >= 0 )
        {
          *a5 = v28;
          if ( pv )
            CoTaskMemFree(pv);
          std::vector<unsigned char>::_Tidy(&v42);
          std::vector<unsigned char>::_Tidy(&Destination);
          wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&Source);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC86,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
            (const char *)(unsigned int)v29,
            pbInputc);
          if ( pv )
            CoTaskMemFree(pv);
          std::vector<unsigned char>::_Tidy(&v42);
          std::vector<unsigned char>::_Tidy(&Destination);
          wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&Source);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
          return v30;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC82,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)v27,
        pbInputb);
      if ( !pv )
        goto LABEL_27;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC7F,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
        (const char *)(unsigned int)v25,
        pbInputa);
      if ( !pv )
      {
LABEL_27:
        std::vector<unsigned char>::_Tidy(&v42);
        std::vector<unsigned char>::_Tidy(&Destination);
        wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(&Source);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v38);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
        return v26;
      }
    }
    CoTaskMemFree(pv);
    goto LABEL_27;
  }
  catch ( ... )
  {
    LODWORD(a6) = wil::details::in1diag3::Return_CaughtException(
                    retaddr,
                    (void *)0xC8C,
                    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginmanagement.cpp",
                    v23);
    return (unsigned int)a6;
  }
  return result;
}

```

## disassembly

```asm
0x180119c80  push    rbx
0x180119c82  push    rsi
0x180119c83  push    rdi
0x180119c84  push    r12
0x180119c86  push    r13
0x180119c88  push    r14
0x180119c8a  push    r15
0x180119c8c  sub     rsp, 0C0h
0x180119c93  mov     r12d, r9d
0x180119c96  mov     r13, r8
0x180119c99  mov     r15, rdx
0x180119c9c  mov     r14, rcx
0x180119c9f  mov     rbx, [rsp+0F8h+arg_28]
0x180119ca7  xor     eax, eax
0x180119ca9  test    rbx, rbx
0x180119cac  jnz     short loc_180119CD6
0x180119cae  mov     rcx, [rsp+0F8h]; this
0x180119cb6  mov     ebx, 80004003h
0x180119cbb  mov     r9d, ebx; char *
0x180119cbe  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180119cc5  mov     edx, 0C4Dh; void *
0x180119cca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119ccf  mov     eax, ebx
0x180119cd1  jmp     loc_18011A3AF
0x180119cd6  mov     rsi, [rsp+0F8h+arg_20]
0x180119cde  test    rsi, rsi
0x180119ce1  jnz     short loc_180119D0B
0x180119ce3  mov     rcx, [rsp+0F8h]; this
0x180119ceb  mov     ebx, 80004003h
0x180119cf0  mov     r9d, ebx; char *
0x180119cf3  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180119cfa  mov     edx, 0C4Eh; void *
0x180119cff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119d04  mov     eax, ebx
0x180119d06  jmp     loc_18011A3AF
0x180119d0b  mov     [rbx], eax
0x180119d0d  mov     [rsi], rax
0x180119d10  mov     [rsp+0F8h+var_B0], rax
0x180119d15  mov     [rsp+0F8h+var_A8], rax
0x180119d1a  lea     rdx, [rsp+0F8h+var_A8]
0x180119d1f  call    GetUserPluginAuthenticatorsRegKey
0x180119d24  mov     edi, eax
0x180119d26  test    eax, eax
0x180119d28  jns     short loc_180119D63
0x180119d2a  mov     rcx, [rsp+0F8h]; this
0x180119d32  mov     r9d, eax; char *
0x180119d35  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180119d3c  mov     edx, 0C54h; void *
0x180119d41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119d46  nop
0x180119d47  lea     rcx, [rsp+0F8h+var_A8]
0x180119d4c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180119d51  nop
0x180119d52  lea     rcx, [rsp+0F8h+var_B0]
0x180119d57  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180119d5c  mov     eax, edi
0x180119d5e  jmp     loc_18011A3AF
0x180119d63  mov     [rsp+0F8h+hKey], 0
0x180119d6c  xor     r9d, r9d
0x180119d6f  lea     r8, [rsp+0F8h+hKey]
0x180119d74  mov     rdx, r15
0x180119d77  mov     rcx, [rsp+0F8h+var_A8]
0x180119d7c  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180119d81  mov     edi, eax
0x180119d83  test    eax, eax
0x180119d85  jns     short loc_180119DCB
0x180119d87  mov     rcx, [rsp+0F8h]; this
0x180119d8f  mov     r9d, eax; char *
0x180119d92  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180119d99  mov     edx, 0C57h; void *
0x180119d9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119da3  nop
0x180119da4  lea     rcx, [rsp+0F8h+hKey]
0x180119da9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180119dae  nop
0x180119daf  lea     rcx, [rsp+0F8h+var_A8]
0x180119db4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180119db9  nop
0x180119dba  lea     rcx, [rsp+0F8h+var_B0]
0x180119dbf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180119dc4  mov     eax, edi
0x180119dc6  jmp     loc_18011A3AF
0x180119dcb  mov     rax, [rsp+0F8h+hKey]
0x180119dd0  test    rax, rax
0x180119dd3  jnz     short loc_180119E1E
0x180119dd5  mov     rcx, [rsp+0F8h]; this
0x180119ddd  mov     ebx, 80070002h
0x180119de2  mov     r9d, ebx; char *
0x180119de5  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180119dec  mov     edx, 0C5Ah; void *
0x180119df1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119df6  nop
0x180119df7  lea     rcx, [rsp+0F8h+hKey]
0x180119dfc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180119e01  nop
0x180119e02  lea     rcx, [rsp+0F8h+var_A8]
0x180119e07  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180119e0c  nop
0x180119e0d  lea     rcx, [rsp+0F8h+var_B0]
0x180119e12  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180119e17  mov     eax, ebx
0x180119e19  jmp     loc_18011A3AF
0x180119e1e  mov     [rsp+0F8h+Source], 0
0x180119e27  mov     [rsp+0F8h+var_90], 0
0x180119e30  mov     [rsp+0F8h+arg_28], rax
0x180119e38  mov     dword ptr [rsp+0F8h+pbInput], 8; int
0x180119e40  lea     r9, [rsp+0F8h+Source]
0x180119e45  lea     r8, aRequestsignpri; "RequestSignPrivateKey"
0x180119e4c  lea     rcx, [rsp+0F8h+arg_28]
0x180119e54  call    ??$get_value_with_type@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &,ulong)
0x180119e59  test    eax, eax
0x180119e5b  jns     loc_180119F56
0x180119e61  mov     rcx, [rsp+0F8h]; this
0x180119e69  mov     r9d, eax; char *
0x180119e6c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180119e73  mov     edx, 0ABBh; void *
0x180119e78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119e7d  xor     r9d, r9d
0x180119e80  xor     r8d, r8d
0x180119e83  mov     rdx, r15
0x180119e86  mov     rcx, r14
0x180119e89  call    CtapPluginCreateOperationRequestSigningKey
0x180119e8e  mov     rdi, [rsp+0F8h+hKey]
0x180119e93  mov     rcx, [rsp+0F8h+Source]; void *
0x180119e98  mov     rdx, [rsp+0F8h+var_90]
0x180119e9d  add     rdx, rcx
0x180119ea0  mov     r8, rdx
0x180119ea3  sub     r8, rcx
0x180119ea6  xor     r14d, r14d
0x180119ea9  cmp     rcx, rdx
0x180119eac  cmova   r8, r14; Size
0x180119eb0  test    r8, r8
0x180119eb3  jz      short loc_180119EBC
0x180119eb5  xor     edx, edx; Val
0x180119eb7  call    memset_0
0x180119ebc  mov     [rsp+0F8h+arg_28], rdi
0x180119ec4  mov     dword ptr [rsp+0F8h+pbInput], 8; int
0x180119ecc  lea     r9, [rsp+0F8h+Source]
0x180119ed1  lea     r8, aRequestsignpri; "RequestSignPrivateKey"
0x180119ed8  lea     rcx, [rsp+0F8h+arg_28]
0x180119ee0  call    ??$get_value_with_type@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@Uerr_returncode_policy@2@@?$reg_view_t@Uerr_returncode_policy@wil@@@reg_view_details@reg@wil@@AEBAJPEBG0AEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@3@K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_returncode_policy>::get_value_with_type<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,wil::err_returncode_policy>(ushort const *,ushort const *,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &,ulong)
0x180119ee5  mov     edi, eax
0x180119ee7  test    eax, eax
0x180119ee9  jns     short loc_180119F59
0x180119eeb  mov     rcx, [rsp+0F8h]; this
0x180119ef3  mov     r9d, eax; char *
0x180119ef6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180119efd  mov     edx, 0ABBh; void *
0x180119f02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119f07  mov     rcx, [rsp+0F8h]; this
0x180119f0f  mov     r9d, edi; char *
0x180119f12  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180119f19  mov     edx, 0C61h; void *
0x180119f1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180119f23  nop
0x180119f24  lea     rcx, [rsp+0F8h+Source]
0x180119f29  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x180119f2e  nop
0x180119f2f  lea     rcx, [rsp+0F8h+hKey]
0x180119f34  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180119f39  nop
0x180119f3a  lea     rcx, [rsp+0F8h+var_A8]
0x180119f3f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180119f44  nop
0x180119f45  lea     rcx, [rsp+0F8h+var_B0]
0x180119f4a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180119f4f  mov     eax, edi
0x180119f51  jmp     loc_18011A3AF
0x180119f56  xor     r14d, r14d
0x180119f59  lea     r8, [rsp+0F8h+arg_28]
0x180119f61  mov     rdx, [rsp+0F8h+var_90]
0x180119f66  lea     rcx, [rsp+0F8h+Destination]
0x180119f6e  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180119f73  nop
0x180119f74  mov     rdx, [rsp+0F8h+var_68]
0x180119f7c  mov     rcx, [rsp+0F8h+Destination]; Destination
0x180119f84  sub     rdx, rcx; DestinationSize
0x180119f87  mov     r9, rdx; SourceSize
0x180119f8a  mov     r8, [rsp+0F8h+Source]; Source
0x180119f8f  call    memcpy_s_3
0x180119f94  lea     rcx, [rsp+0F8h+var_88]
0x180119f99  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180119f9e  nop
0x180119f9f  lea     r8, [rsp+0F8h+var_88]
0x180119fa4  lea     rdx, [rsp+0F8h+Destination]
0x180119fac  xor     ecx, ecx
0x180119fae  call    ?UnprotectData@CtapDataProtector@@SAJQEAXAEAV?$vector@EV?$allocator@E@std@@@std@@1@Z; CtapDataProtector::UnprotectData(void * const,std::vector<uchar> &,std::vector<uchar> &)
0x180119fb3  test    eax, eax
0x180119fb5  jns     loc_18011A04C
0x180119fbb  lea     rdx, aRequestsignpri; "RequestSignPrivateKey"
0x180119fc2  mov     rcx, [rsp+0F8h+hKey]; hKey
0x180119fc7  call    cs:__imp_RegDeleteKeyW
0x180119fcd  lea     rdx, aRequestsignpub; "RequestSignPubKey"
0x180119fd4  mov     rcx, [rsp+0F8h+hKey]; hKey
0x180119fd9  call    cs:__imp_RegDeleteKeyW
0x180119fdf  mov     rcx, [rsp+0F8h]; this
0x180119fe7  mov     ebx, 80090015h
0x180119fec  mov     r9d, ebx; char *
0x180119fef  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180119ff6  mov     edx, 0C6Dh; void *
0x180119ffb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a000  nop
0x18011a001  lea     rcx, [rsp+0F8h+var_88]
0x18011a006  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18011a00b  nop
0x18011a00c  lea     rcx, [rsp+0F8h+Destination]
0x18011a014  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18011a019  nop
0x18011a01a  lea     rcx, [rsp+0F8h+Source]
0x18011a01f  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18011a024  nop
0x18011a025  lea     rcx, [rsp+0F8h+hKey]
0x18011a02a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011a02f  nop
0x18011a030  lea     rcx, [rsp+0F8h+var_A8]
0x18011a035  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011a03a  nop
0x18011a03b  lea     rcx, [rsp+0F8h+var_B0]
0x18011a040  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18011a045  mov     eax, ebx
0x18011a047  jmp     loc_18011A3AF
0x18011a04c  mov     rcx, [rsp+0F8h+var_88]
0x18011a051  lea     rax, [rsp+0F8h+var_B0]
0x18011a056  mov     [rsp+0F8h+var_58], rax
0x18011a05e  mov     [rsp+0F8h+phKey], r14
0x18011a066  mov     [rsp+0F8h+var_48], 1
0x18011a06e  mov     eax, dword ptr [rsp+0F8h+var_80]
0x18011a072  sub     eax, ecx
0x18011a074  mov     [rsp+0F8h+dwFlags], r14d; dwFlags
0x18011a079  mov     [rsp+0F8h+cbInput], eax; cbInput
0x18011a07d  mov     [rsp+0F8h+pbInput], rcx; int
0x18011a082  lea     r9, [rsp+0F8h+phKey]; phKey
0x18011a08a  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x18011a091  xor     edx, edx; hImportKey
0x18011a093  mov     ecx, 2F1h; hAlgorithm
0x18011a098  call    cs:__imp_BCryptImportKeyPair
0x18011a09e  mov     edi, eax
0x18011a0a0  lea     rcx, [rsp+0F8h+var_58]
0x18011a0a8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18011a0ad  test    edi, edi
0x18011a0af  jns     short loc_18011A119
0x18011a0b1  mov     rcx, [rsp+0F8h]; this
0x18011a0b9  mov     r9d, edi; char *
0x18011a0bc  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011a0c3  mov     edx, 0C72h; void *
0x18011a0c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a0cd  nop
0x18011a0ce  lea     rcx, [rsp+0F8h+var_88]
0x18011a0d3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18011a0d8  nop
0x18011a0d9  lea     rcx, [rsp+0F8h+Destination]
0x18011a0e1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18011a0e6  nop
0x18011a0e7  lea     rcx, [rsp+0F8h+Source]
0x18011a0ec  call    ?reset@?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18011a0f1  nop
0x18011a0f2  lea     rcx, [rsp+0F8h+hKey]
0x18011a0f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011a0fc  nop
0x18011a0fd  lea     rcx, [rsp+0F8h+var_A8]
0x18011a102  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011a107  nop
0x18011a108  lea     rcx, [rsp+0F8h+var_B0]
0x18011a10d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18011a112  mov     eax, edi
0x18011a114  jmp     loc_18011A3AF
0x18011a119  mov     rax, [rsp+0F8h+var_88]
0x18011a11e  cmp     rax, [rsp+0F8h+var_80]
0x18011a123  jz      short loc_18011A12A
0x18011a125  mov     [rsp+0F8h+var_80], rax
0x18011a12a  mov     dword ptr [rsp+0F8h+arg_28], r14d
0x18011a132  mov     [rsp+0F8h+pv], r14
0x18011a137  lea     rax, [rsp+0F8h+pv]
0x18011a13c  mov     [rsp+0F8h+var_58], rax
0x18011a144  mov     byte ptr [rsp+0F8h+phKey], 1
0x18011a14c  lea     r9, [rsp+0F8h+arg_28]; unsigned __int8 **
0x18011a154  lea     r8, [rsp+0F8h+pv]; unsigned int
0x18011a159  mov     edx, r12d; cbInput
0x18011a15c  mov     rcx, r13; pbInput
0x18011a15f  call    ?HashOperationBlobForSignature@CtapPluginInternal@@YAJQEAEKPEAPEAEPEAK@Z; CtapPluginInternal::HashOperationBlobForSignature(uchar * const,ulong,uchar * *,ulong *)
0x18011a164  mov     edi, eax
0x18011a166  test    eax, eax
0x18011a168  jns     short loc_18011A1E3
0x18011a16a  mov     rcx, [rsp+0F8h]; this
0x18011a172  mov     r9d, eax; char *
0x18011a175  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011a17c  mov     edx, 0C7Fh; void *
0x18011a181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011a186  nop
0x18011a187  mov     rcx, [rsp+0F8h+pv]; pv
0x18011a18c  test    rcx, rcx
0x18011a18f  jz      short loc_18011A198
0x18011a191  call    cs:__imp_CoTaskMemFree
0x18011a197  nop
0x18011a198  lea     rcx, [rsp+0F8h+var_88]
0x18011a19d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18011a1a2  nop
0x18011a1a3  lea     rcx, [rsp+0F8h+Destination]
0x18011a1ab  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18011a1b0  nop
  ... truncated ...
```
