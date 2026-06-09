# FindAccountWithContext(Windows::Internal::Security::Authentication::TokenBroker::AccountLookupContext,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ *,HSTRING__ *,IUnknown *,Windows::Security::Credentials::IWebAccount * *)

- ea: `0x18001ef40`
- end: `0x18001fbfc`
- name: `?FindAccountWithContext@@YAJW4AccountLookupContext@TokenBroker@Authentication@Security@Internal@Windows@@PEAUIWebAccountProvider@Credentials@46@PEAUHSTRING__@@2PEAUIUnknown@@PEAPEAUIWebAccount@846@@Z`
- size: `3260`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e7c0`
- `0x18001fc10`
- `0x18005d870`

## callees

- `0x18000bd40`
- `0x18000bd70`
- `0x18001e00c`
- `0x18001ef40`
- `0x1800200b4`
- `0x180020620`
- `0x180023a80`
- `0x1800262f0`
- `0x1800269f4`
- `0x180030a78`
- `0x180031270`
- `0x180053cfc`
- `0x18008e690`
- `0x1800b33f0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f1c0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f26e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f3ec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f4ad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f56e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f633`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f6ea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f7a8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fb9c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f1c0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f26e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f3ec`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f4ad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f56e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f633`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f6ea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f7a8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fb9c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f373`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f8de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fa50`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fb07`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f373`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f8de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fa50`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fb07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f35b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f8c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fa36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001faed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f35b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f8c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fa36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001faed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18001fa6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18001fb1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18001fa6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18001fb1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f25a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f3d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f55a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f61f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f6d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fb88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f25a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f3d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f55a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f61f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f6d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fb88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f2cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f2e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f452`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f51d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f96c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f9db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001fa14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001fa92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001facb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f2cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f2e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f452`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f51d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f96c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001f9db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001fa14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001fa92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001facb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f283`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f401`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f4c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f648`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f7bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f283`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f401`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f4c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f648`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f7bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbb1`

## string_xrefs

- `0x18001efec`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f053`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f0b5`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f128`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f1a1`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f23f`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f3be`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f47f`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f540`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f605`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f6bc`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f77a`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18001f354`: `delegatedTokenRequests`
- `0x18001f8bd`: `delegatedTokenRequests`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall FindAccountWithContext(
        INT32 a1,
        struct Windows::Security::Credentials::IWebAccountProvider *a2,
        HSTRING a3,
        __int64 a4,
        struct IUnknown *a5,
        __int64 a6)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  Windows::Internal::Security::Authentication::Web::CallerContext *v13; // rsi
  __int64 v14; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int PluginPFN; // eax
  __int64 v21; // rcx
  BOOL IsStringEmpty; // eax
  HSTRING v23; // rbx
  char v24; // r13
  char v25; // r14
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int IsPluginMultiUserAware; // eax
  unsigned int v31; // r14d
  __int64 v32; // rcx
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *AccountManagerInstance; // rax
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v34; // r14
  __int64 v35; // rcx
  unsigned int v36; // edx
  HSTRING v37; // rax
  unsigned int v38; // r15d
  unsigned int v39; // eax
  HSTRING v40; // rsi
  int BuiltInProviderType; // r12d
  bool v42; // zf
  __int64 v43; // rcx
  int v44; // [rsp+20h] [rbp-B9h]
  HSTRING v45; // [rsp+20h] [rbp-B9h]
  __int64 v46; // [rsp+28h] [rbp-B1h]
  __int64 v47; // [rsp+30h] [rbp-A9h]
  char v48; // [rsp+40h] [rbp-99h]
  __int64 v49; // [rsp+48h] [rbp-91h] BYREF
  bool v50; // [rsp+50h] [rbp-89h] BYREF
  INT32 result; // [rsp+54h] [rbp-85h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-81h] BYREF
  char v53; // [rsp+60h] [rbp-79h]
  Windows::Internal::Security::Authentication::Web::CallerContext *v54; // [rsp+68h] [rbp-71h] BYREF
  INT32 v55; // [rsp+70h] [rbp-69h] BYREF
  HSTRING v56; // [rsp+78h] [rbp-61h]
  _QWORD *v57; // [rsp+80h] [rbp-59h]
  __int64 v58; // [rsp+88h] [rbp-51h]
  __int64 v59; // [rsp+90h] [rbp-49h]
  HSTRING string; // [rsp+98h] [rbp-41h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-39h]
  __int64 (__fastcall *v62)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64, HSTRING, _QWORD, HSTRING, __int64, __int64); // [rsp+A8h] [rbp-31h]
  unsigned __int64 v63; // [rsp+B0h] [rbp-29h] BYREF
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v64; // [rsp+B8h] [rbp-21h]
  struct Windows::Security::Credentials::IWebAccountProvider *v65; // [rsp+C0h] [rbp-19h]
  HSTRING string2; // [rsp+C8h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]

  v59 = a4;
  v56 = a3;
  v55 = a1;
  v58 = a6;
  if ( !a2 || !a4 || !a6 )
    return 2147942487LL;
  v63 = 0;
  v65 = a2;
  (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)a2 + 8LL))(a2);
  v49 = 0;
  v8 = (**(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))a2)(
         a2,
         &GUID_c997b7de_ff59_4392_bcde_50ea5ffc1e1c,
         &v49);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v8,
      v44);
    v10 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
LABEL_37:
    (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)a2 + 16LL))(a2);
    return v9;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v49 + 48LL))(v49, &v63);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v11,
      v44);
    v12 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_37;
  }
  wil::make_unique_nothrow<Windows::Internal::Security::Authentication::Web::CallerContext,>(&v54);
  v13 = v54;
  if ( !v54 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v44);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v54,
      0);
    v14 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
LABEL_15:
    (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)a2 + 16LL))(a2);
    return 2147942414LL;
  }
  v16 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v54, a5, v63, 1);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v16,
      v44);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v54,
      0);
    v17 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_37;
  }
  Token = 0;
  v53 = 0;
  v18 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(&Token, *((_QWORD *)v13 + 2));
  v9 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v18,
      v44);
    if ( v53 )
      SetThreadToken(0, Token);
    if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v54,
      0);
    v19 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_37;
  }
  string = 0;
  PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(
                v13,
                a2,
                &string);
  v9 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)PluginPFN,
      v44);
    if ( string )
      WindowsDeleteString(string);
    if ( v53 )
      SetThreadToken(0, Token);
    if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v54,
      0);
    v21 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_37;
  }
  IsStringEmpty = WindowsIsStringEmpty(*((HSTRING *)v13 + 5));
  v23 = string;
  if ( IsStringEmpty )
  {
    v24 = 0;
  }
  else
  {
    v24 = 1;
    WindowsIsStringEmpty(*((HSTRING *)v13 + 5));
    if ( ComparePfns(*((HSTRING *)v13 + 9), v23) )
    {
      v25 = 1;
      goto LABEL_43;
    }
  }
  v25 = 0;
LABEL_43:
  v48 = v25;
  if ( a1 != 1 )
  {
    if ( a1 != 2 || WindowsIsStringEmpty(*((HSTRING *)v13 + 5)) )
      goto LABEL_93;
    if ( v56 )
    {
      if ( !v25 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
          (const char *)0x80070005LL,
          v44);
        if ( v23 )
          WindowsDeleteString(v23);
        if ( v53 )
          SetThreadToken(0, Token);
        if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(Token);
        wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
          &v54,
          0);
        v29 = v49;
        if ( v49 )
        {
          v49 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        goto LABEL_92;
      }
      goto LABEL_93;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v44);
    if ( v23 )
      WindowsDeleteString(v23);
    if ( v53 )
      SetThreadToken(0, Token);
    if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v54,
      0);
    v28 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)a2 + 16LL))(a2);
    return 2147942487LL;
  }
  if ( v24 && !v25 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl) )
    {
      if ( WindowsCreateStringReference(L"delegatedTokenRequests", 0x16u, &hstringHeader, &string2) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      if ( (int)Windows::Internal::Security::Authentication::Web::CallerContext::VerifyCapability(v13, string2) < 0 )
      {
        WindowsIsStringEmpty(*((HSTRING *)v13 + 5));
        if ( !ComparePfns(*((HSTRING *)v13 + 9), v56) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9B,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
            (const char *)0x80070005LL,
            v44);
          if ( v23 )
            WindowsDeleteString(v23);
          if ( v53 )
            SetThreadToken(0, Token);
          if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(Token);
          wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
            &v54,
            0);
          v26 = v49;
          if ( v49 )
          {
            v49 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
LABEL_92:
          (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)a2 + 16LL))(a2);
          return 2147942405LL;
        }
      }
    }
    else
    {
      WindowsIsStringEmpty(*((HSTRING *)v13 + 5));
      if ( !ComparePfns(*((HSTRING *)v13 + 9), v56) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
          (const char *)0x80070005LL,
          v44);
        if ( v23 )
          WindowsDeleteString(v23);
        if ( v53 )
          SetThreadToken(0, Token);
        if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(Token);
        wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
          &v54,
          0);
        v27 = v49;
        if ( v49 )
        {
          v49 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        goto LABEL_92;
      }
    }
  }
LABEL_93:
  v50 = 0;
  IsPluginMultiUserAware = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(
                             v13,
                             v23,
                             &v50);
  v31 = IsPluginMultiUserAware;
  if ( IsPluginMultiUserAware < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)IsPluginMultiUserAware,
      v44);
    if ( v23 )
      WindowsDeleteString(v23);
    if ( v53 )
      SetThreadToken(0, Token);
    if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v54,
      0);
    v32 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)a2 + 16LL))(a2);
    return v31;
  }
  v64 = 0;
  AccountManagerInstance = Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(
                             v50,
                             *((_QWORD *)v13 + 2));
  v34 = AccountManagerInstance;
  v64 = AccountManagerInstance;
  if ( !AccountManagerInstance )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v44);
    if ( v23 )
      WindowsDeleteString(v23);
    if ( v53 )
      SetThreadToken(0, Token);
    if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v54,
      0);
    v35 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    goto LABEL_15;
  }
  v36 = 0;
  result = 0;
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      if ( v24 && !v48 )
        goto LABEL_121;
      v36 = 1;
LABEL_120:
      result = v36;
LABEL_121:
      v57 = (_QWORD *)((char *)v13 + 8);
      v62 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64, HSTRING, _QWORD, HSTRING, __int64, __int64))(*(_QWORD *)AccountManagerInstance + 16LL);
      v61 = *((_QWORD *)v13 + 1);
LABEL_122:
      v37 = v56;
      goto LABEL_123;
    }
    if ( a1 == 2 )
    {
      v36 = 6;
      goto LABEL_120;
    }
  }
  if ( !v24 || v48 )
  {
    v36 = 7;
    result = 7;
  }
  v62 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64, HSTRING, _QWORD, HSTRING, __int64, __int64))(*(_QWORD *)AccountManagerInstance + 16LL);
  v57 = (_QWORD *)((char *)v13 + 8);
  v61 = *((_QWORD *)v13 + 1);
  if ( a1 )
    goto LABEL_122;
  if ( WindowsIsStringEmpty(*((HSTRING *)v13 + 5)) )
    v37 = 0;
  else
    v37 = (HSTRING)*((_QWORD *)v13 + 9);
  v36 = result;
LABEL_123:
  v38 = v62(v34, v59, v23, v36, v37, v58, v61);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl'::`2'::impl) )
  {
    if ( v55 == 1 )
    {
LABEL_139:
      if ( v38 != -2147024894 || v24 )
        goto LABEL_164;
      v47 = *v57;
      v46 = v58;
      v45 = v56;
      goto LABEL_162;
    }
    if ( v55 )
      goto LABEL_164;
    WindowsIsStringEmpty(*((HSTRING *)v13 + 5));
    v40 = (HSTRING)*((_QWORD *)v13 + 9);
    BuiltInProviderType = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType(a2);
    if ( v38 != -2147024894 || v24 || v48 || WindowsIsStringEmpty(v40) )
      goto LABEL_164;
    if ( WindowsCreateStringReference(L"NO_APPLICATION", 0xEu, &hstringHeader, &string2) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v55 = 0;
    WindowsCompareStringOrdinal(v40, string2, &v55);
    v42 = v55 == 0;
LABEL_159:
    if ( v42 || BuiltInProviderType != 3 )
      goto LABEL_164;
    v47 = *v57;
    v46 = v58;
    v45 = v40;
LABEL_162:
    v39 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64, HSTRING, _QWORD, HSTRING, __int64, __int64))(*(_QWORD *)v34 + 16LL))(
            v34,
            v59,
            v23,
            0,
            v45,
            v46,
            v47);
    goto LABEL_163;
  }
  if ( !v24 )
    goto LABEL_138;
  if ( WindowsCreateStringReference(L"delegatedTokenRequests", 0x16u, &hstringHeader, &string2) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( (int)Windows::Internal::Security::Authentication::Web::CallerContext::VerifyCapability(v13, string2) < 0 )
  {
LABEL_138:
    if ( v55 == 1 )
      goto LABEL_139;
    if ( v55 )
      goto LABEL_164;
    WindowsIsStringEmpty(*((HSTRING *)v13 + 5));
    v40 = (HSTRING)*((_QWORD *)v13 + 9);
    BuiltInProviderType = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType(a2);
    if ( v38 != -2147024894 || v24 || v48 || WindowsIsStringEmpty(v40) )
      goto LABEL_164;
    if ( WindowsCreateStringReference(L"NO_APPLICATION", 0xEu, &hstringHeader, &string2) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    result = 0;
    WindowsCompareStringOrdinal(v40, string2, &result);
    v42 = result == 0;
    goto LABEL_159;
  }
  if ( v38 == -2147024894 )
  {
    v39 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64, HSTRING, _QWORD, HSTRING, __int64, _QWORD))(*(_QWORD *)v34 + 16LL))(
            v34,
            v59,
            v23,
            result | 7u,
            v56,
            v58,
            *v57);
LABEL_163:
    v38 = v39;
  }
LABEL_164:
  if ( v34 )
    (**(void (__fastcall ***)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64))v34)(
      v34,
      1);
  if ( v23 )
    WindowsDeleteString(v23);
  if ( v53 )
    SetThreadToken(0, Token);
  if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(Token);
  wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
    &v54,
    0);
  v43 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)a2 + 16LL))(a2);
  return v38;
}

```

## disassembly

```asm
0x18001ef40  mov     [rsp-8+arg_0], rbx
0x18001ef45  push    rbp
0x18001ef46  push    rsi
0x18001ef47  push    rdi
0x18001ef48  push    r12
0x18001ef4a  push    r13
0x18001ef4c  push    r14
0x18001ef4e  push    r15
0x18001ef50  lea     rbp, [rsp-17h]
0x18001ef55  sub     rsp, 0F0h
0x18001ef5c  mov     rax, cs:__security_cookie
0x18001ef63  xor     rax, rsp
0x18001ef66  mov     [rbp+47h+var_38], rax
0x18001ef6a  mov     rax, r9
0x18001ef6d  mov     [rbp+47h+var_90], rax
0x18001ef71  mov     [rbp+47h+var_A8], r8
0x18001ef75  mov     rdi, rdx
0x18001ef78  mov     r15d, ecx
0x18001ef7b  mov     [rbp+47h+var_B0], ecx
0x18001ef7e  mov     r14, [rbp+47h+arg_20]
0x18001ef82  mov     rcx, [rbp+47h+arg_28]
0x18001ef86  mov     [rbp+47h+var_98], rcx
0x18001ef8a  test    rdx, rdx
0x18001ef8d  jz      loc_18001F5C6
0x18001ef93  test    rax, rax
0x18001ef96  jz      loc_18001F5C6
0x18001ef9c  test    rcx, rcx
0x18001ef9f  jz      loc_18001F5C6
0x18001efa5  xor     r12d, r12d
0x18001efa8  mov     [rbp+47h+var_70], r12
0x18001efac  mov     [rbp+47h+var_60], rdx
0x18001efb0  mov     rax, [rdx]
0x18001efb3  mov     rcx, rdx
0x18001efb6  mov     rax, [rax+8]
0x18001efba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efbf  nop
0x18001efc0  mov     [rsp+120h+var_D8], r12
0x18001efc5  mov     rax, [rdi]
0x18001efc8  lea     r8, [rsp+120h+var_D8]
0x18001efcd  lea     rdx, _GUID_c997b7de_ff59_4392_bcde_50ea5ffc1e1c
0x18001efd4  mov     rcx, rdi
0x18001efd7  mov     rax, [rax]
0x18001efda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efdf  mov     ebx, eax
0x18001efe1  test    eax, eax
0x18001efe3  jns     short loc_18001F031
0x18001efe5  mov     rcx, [rbp+4Fh]; this
0x18001efe9  mov     r9d, eax; char *
0x18001efec  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18001eff3  mov     edx, 78h ; 'x'; void *
0x18001eff8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001effd  nop
0x18001effe  mov     rcx, [rsp+120h+var_D8]
0x18001f003  test    rcx, rcx
0x18001f006  jz      short loc_18001F01A
0x18001f008  mov     [rsp+120h+var_D8], r12
0x18001f00d  mov     rax, [rcx]
0x18001f010  mov     rax, [rax+10h]
0x18001f014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f019  nop
0x18001f01a  mov     rax, [rdi]
0x18001f01d  mov     rcx, rdi
0x18001f020  mov     rax, [rax+10h]
0x18001f024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f029  nop
0x18001f02a  mov     eax, ebx
0x18001f02c  jmp     loc_18001F5CB
0x18001f031  mov     rcx, [rsp+120h+var_D8]
0x18001f036  mov     rax, [rcx]
0x18001f039  lea     rdx, [rbp+47h+var_70]
0x18001f03d  mov     rax, [rax+30h]
0x18001f041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f046  mov     ebx, eax
0x18001f048  test    eax, eax
0x18001f04a  jns     short loc_18001F098
0x18001f04c  mov     rcx, [rbp+4Fh]; this
0x18001f050  mov     r9d, eax; char *
0x18001f053  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18001f05a  mov     edx, 79h ; 'y'; void *
0x18001f05f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f064  nop
0x18001f065  mov     rcx, [rsp+120h+var_D8]
0x18001f06a  test    rcx, rcx
0x18001f06d  jz      short loc_18001F081
0x18001f06f  mov     [rsp+120h+var_D8], r12
0x18001f074  mov     rax, [rcx]
0x18001f077  mov     rax, [rax+10h]
0x18001f07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f080  nop
0x18001f081  mov     rax, [rdi]
0x18001f084  mov     rcx, rdi
0x18001f087  mov     rax, [rax+10h]
0x18001f08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f090  nop
0x18001f091  mov     eax, ebx
0x18001f093  jmp     loc_18001F5CB
0x18001f098  lea     rcx, [rbp+47h+var_B8]
0x18001f09c  call    ??$make_unique_nothrow@VCallerContext@Web@Authentication@Security@Internal@Windows@@$$V@wil@@YA?AV?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<Windows::Internal::Security::Authentication::Web::CallerContext,>(void)
0x18001f0a1  nop
0x18001f0a2  mov     rsi, [rbp+47h+var_B8]
0x18001f0a6  test    rsi, rsi
0x18001f0a9  jnz     short loc_18001F109
0x18001f0ab  mov     rcx, [rbp+4Fh]; this
0x18001f0af  mov     r9d, 8007000Eh; char *
0x18001f0b5  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18001f0bc  mov     edx, 7Ch ; '|'; void *
0x18001f0c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f0c6  nop
0x18001f0c7  xor     edx, edx
0x18001f0c9  lea     rcx, [rbp+47h+var_B8]
0x18001f0cd  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18001f0d2  nop
0x18001f0d3  mov     rcx, [rsp+120h+var_D8]
0x18001f0d8  test    rcx, rcx
0x18001f0db  jz      short loc_18001F0EF
0x18001f0dd  mov     [rsp+120h+var_D8], r12
0x18001f0e2  mov     rax, [rcx]
0x18001f0e5  mov     rax, [rax+10h]
0x18001f0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0ee  nop
0x18001f0ef  mov     rcx, [rdi]
0x18001f0f2  mov     rax, [rcx+10h]
0x18001f0f6  mov     rcx, rdi
0x18001f0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0fe  nop
0x18001f0ff  mov     eax, 8007000Eh
0x18001f104  jmp     loc_18001F5CB
0x18001f109  mov     r9b, 1; bool
0x18001f10c  mov     r8, [rbp+47h+var_70]; unsigned __int64
0x18001f110  mov     rdx, r14; struct IUnknown *
0x18001f113  mov     rcx, rsi; this
0x18001f116  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x18001f11b  mov     ebx, eax
0x18001f11d  test    eax, eax
0x18001f11f  jns     short loc_18001F179
0x18001f121  mov     rcx, [rbp+4Fh]; this
0x18001f125  mov     r9d, eax; char *
0x18001f128  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18001f12f  mov     edx, 7Dh ; '}'; void *
0x18001f134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f139  nop
0x18001f13a  xor     edx, edx
0x18001f13c  lea     rcx, [rbp+47h+var_B8]
0x18001f140  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18001f145  nop
0x18001f146  mov     rcx, [rsp+120h+var_D8]
0x18001f14b  test    rcx, rcx
0x18001f14e  jz      short loc_18001F162
0x18001f150  mov     [rsp+120h+var_D8], r12
0x18001f155  mov     rax, [rcx]
0x18001f158  mov     rax, [rax+10h]
0x18001f15c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f161  nop
0x18001f162  mov     rax, [rdi]
0x18001f165  mov     rcx, rdi
0x18001f168  mov     rax, [rax+10h]
0x18001f16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f171  nop
0x18001f172  mov     eax, ebx
0x18001f174  jmp     loc_18001F5CB
0x18001f179  mov     [rsp+120h+Token], r12
0x18001f17e  mov     [rbp+47h+var_C0], 0
0x18001f182  mov     rdx, [rsi+10h]; unsigned __int64
0x18001f186  lea     rcx, [rsp+120h+Token]; TokenHandle
0x18001f18b  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x18001f190  mov     ebx, eax
0x18001f192  test    eax, eax
0x18001f194  jns     loc_18001F21B
0x18001f19a  mov     rcx, [rbp+4Fh]; this
0x18001f19e  mov     r9d, eax; char *
0x18001f1a1  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18001f1a8  mov     edx, 7Fh; void *
0x18001f1ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f1b2  nop
0x18001f1b3  cmp     [rbp+47h+var_C0], 0
0x18001f1b7  jz      short loc_18001F1C6
0x18001f1b9  mov     rdx, [rsp+120h+Token]; Token
0x18001f1be  xor     ecx, ecx; Thread
0x18001f1c0  call    cs:__imp_SetThreadToken
0x18001f1c6  mov     rcx, [rsp+120h+Token]; hObject
0x18001f1cb  lea     rax, [rcx-1]
0x18001f1cf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f1d3  ja      short loc_18001F1DC
0x18001f1d5  call    cs:__imp_CloseHandle
0x18001f1db  nop
0x18001f1dc  xor     edx, edx
0x18001f1de  lea     rcx, [rbp+47h+var_B8]
0x18001f1e2  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18001f1e7  nop
0x18001f1e8  mov     rcx, [rsp+120h+var_D8]
0x18001f1ed  test    rcx, rcx
0x18001f1f0  jz      short loc_18001F204
0x18001f1f2  mov     [rsp+120h+var_D8], r12
0x18001f1f7  mov     rax, [rcx]
0x18001f1fa  mov     rax, [rax+10h]
0x18001f1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f203  nop
0x18001f204  mov     rax, [rdi]
0x18001f207  mov     rcx, rdi
0x18001f20a  mov     rax, [rax+10h]
0x18001f20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f213  nop
0x18001f214  mov     eax, ebx
0x18001f216  jmp     loc_18001F5CB
0x18001f21b  mov     [rbp+47h+string], r12
0x18001f21f  lea     r8, [rbp+47h+string]; HSTRING *
0x18001f223  mov     rdx, rdi; struct Windows::Security::Credentials::IWebAccountProvider *
0x18001f226  mov     rcx, rsi; this
0x18001f229  call    ?GetPluginPFN@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x18001f22e  mov     ebx, eax
0x18001f230  test    eax, eax
0x18001f232  jns     loc_18001F2C9
0x18001f238  mov     rcx, [rbp+4Fh]; this
0x18001f23c  mov     r9d, eax; char *
0x18001f23f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18001f246  mov     edx, 86h; void *
0x18001f24b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f250  nop
0x18001f251  mov     rcx, [rbp+47h+string]; string
0x18001f255  test    rcx, rcx
0x18001f258  jz      short loc_18001F261
0x18001f25a  call    cs:__imp_WindowsDeleteString
0x18001f260  nop
0x18001f261  cmp     [rbp+47h+var_C0], 0
0x18001f265  jz      short loc_18001F274
0x18001f267  mov     rdx, [rsp+120h+Token]; Token
0x18001f26c  xor     ecx, ecx; Thread
0x18001f26e  call    cs:__imp_SetThreadToken
0x18001f274  mov     rcx, [rsp+120h+Token]; hObject
0x18001f279  lea     rax, [rcx-1]
0x18001f27d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f281  ja      short loc_18001F28A
0x18001f283  call    cs:__imp_CloseHandle
0x18001f289  nop
0x18001f28a  xor     edx, edx
0x18001f28c  lea     rcx, [rbp+47h+var_B8]
0x18001f290  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18001f295  nop
0x18001f296  mov     rcx, [rsp+120h+var_D8]
0x18001f29b  test    rcx, rcx
0x18001f29e  jz      short loc_18001F2B2
0x18001f2a0  mov     [rsp+120h+var_D8], r12
0x18001f2a5  mov     rax, [rcx]
0x18001f2a8  mov     rax, [rax+10h]
0x18001f2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2b1  nop
0x18001f2b2  mov     rax, [rdi]
0x18001f2b5  mov     rcx, rdi
0x18001f2b8  mov     rax, [rax+10h]
0x18001f2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2c1  nop
0x18001f2c2  mov     eax, ebx
0x18001f2c4  jmp     loc_18001F5CB
0x18001f2c9  mov     rcx, [rsi+28h]; string
0x18001f2cd  call    cs:__imp_WindowsIsStringEmpty
0x18001f2d3  mov     r12d, 48h ; 'H'
0x18001f2d9  mov     rbx, [rbp+47h+string]
0x18001f2dd  test    eax, eax
0x18001f2df  jnz     short loc_18001F30C
0x18001f2e1  mov     r13b, 1
0x18001f2e4  mov     rcx, [rsi+28h]; string
0x18001f2e8  call    cs:__imp_WindowsIsStringEmpty
0x18001f2ee  mov     rcx, rsi
0x18001f2f1  test    eax, eax
0x18001f2f3  mov     eax, r12d
0x18001f2f6  mov     rdx, rbx; HSTRING
0x18001f2f9  mov     rcx, [rax+rcx]; string
0x18001f2fd  call    ?ComparePfns@@YA_NPEAUHSTRING__@@0@Z; ComparePfns(HSTRING__ *,HSTRING__ *)
0x18001f302  test    al, al
0x18001f304  jz      short loc_18001F30F
0x18001f306  movzx   r14d, r13b
0x18001f30a  jmp     short loc_18001F312
0x18001f30c  xor     r13b, r13b
0x18001f30f  xor     r14b, r14b
0x18001f312  mov     [rsp+120h+var_E0], r14b
0x18001f317  cmp     r15d, 1
0x18001f31b  jnz     loc_18001F50F
0x18001f321  test    r13b, r13b
0x18001f324  jz      loc_18001F695
0x18001f32a  test    r14b, r14b
0x18001f32d  jnz     loc_18001F695
0x18001f333  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests> `wil::Feature<__WilFeatureTraits_Feature_DelegatedTokenRequests>::GetImpl(void)'::`2'::impl
0x18001f33a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DelegatedTokenRequests@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DelegatedTokenRequests>::__private_IsEnabled(void)
0x18001f33f  test    al, al
0x18001f341  jz      loc_18001F44E
0x18001f347  lea     r9, [rbp+47h+string2]; string
0x18001f34b  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x18001f34f  mov     edx, 16h; length
0x18001f354  lea     rcx, aDelegatedtoken; "delegatedTokenRequests"
0x18001f35b  call    cs:__imp_WindowsCreateStringReference
0x18001f361  test    eax, eax
0x18001f363  jns     short loc_18001F379
0x18001f365  xor     r9d, r9d; lpArguments
0x18001f368  xor     r8d, r8d; nNumberOfArguments
0x18001f36b  mov     edx, r15d; dwExceptionFlags
0x18001f36e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001f373  call    cs:__imp_RaiseException
0x18001f379  mov     rdx, [rbp+47h+string2]; HSTRING
0x18001f37d  mov     rcx, rsi; this
0x18001f380  call    ?VerifyCapability@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::Web::CallerContext::VerifyCapability(HSTRING__ *)
  ... truncated ...
```
