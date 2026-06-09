# Windows::Internal::Security::Authentication::Web::InvokeToDeleteAccountAction(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccount *)

- ea: `0x1800e2094`
- end: `0x1800e27f2`
- name: `?InvokeToDeleteAccountAction@Web@Authentication@Security@Internal@Windows@@YAJPEAVCallerContext@12345@PEAUIWebAccount@Credentials@35@@Z`
- size: `1886`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::Web *__hidden this, struct Windows::Internal::Security::Authentication::Web::CallerContext *, struct Windows::Security::Credentials::IWebAccount *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800baadc`

## callees

- `0x180004654`
- `0x180007350`
- `0x18000bd40`
- `0x18000d250`
- `0x18000fcf8`
- `0x1800200b4`
- `0x1800262f0`
- `0x1800269f4`
- `0x18002d940`
- `0x18004c014`
- `0x1800545cc`
- `0x180063a74`
- `0x180074978`
- `0x18008a6a8`
- `0x18008e690`
- `0x1800b3aa4`
- `0x1800bf828`
- `0x1800d3c94`
- `0x1800e1bec`
- `0x1800e2094`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e2356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e236d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e2599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e25af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e2356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e236d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e2599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e25af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e21a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e21e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e22e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e2619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e26ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e279d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e27ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e21a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e21e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e22e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e2619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e26ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e279d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e27ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e20d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800e20d0`

## string_xrefs

- `0x1800e27e0`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x1800e2186`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x1800e22d0`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x1800e246b`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x1800e268c`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x1800e26f2`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`
- `0x1800e2768`: `onecore\ds\security\tokenbroker\broker\lib\manageroperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::Security::Authentication::Web::InvokeToDeleteAccountAction(
        Windows::Internal::Security::Authentication::Web *this,
        struct Windows::Internal::Security::Authentication::Web::CallerContext *a2,
        struct Windows::Security::Credentials::IWebAccount *a3)
{
  __int64 (__fastcall *v5)(struct Windows::Internal::Security::Authentication::Web::CallerContext *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int PluginPFN; // ebx
  __int64 v7; // rdx
  struct Windows::Security::Credentials::IWebAccountProvider *v8; // rdi
  __int64 (__fastcall *v9)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *); // rbx
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *AccountManagerInstance; // rsi
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  __int64 (__fastcall *v16)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, struct Windows::Internal::Security::Authentication::Web::CallerContext *, __int64 *, HSTRING); // rdi
  HSTRING v17; // rbx
  __int64 v18; // rdx
  unsigned int v19; // r14d
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, _QWORD); // rbx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  HSTRING v25; // rbx
  __int64 CurrentSystemTimeAsInt64; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  HSTRING v29; // rbx
  __int64 v30; // rax
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v35; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v36; // [rsp+58h] [rbp-A8h] BYREF
  bool v37; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v38; // [rsp+68h] [rbp-98h] BYREF
  __int64 v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+78h] [rbp-88h] BYREF
  __int64 v41; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64); // [rsp+88h] [rbp-78h] BYREF
  PCWSTR v43; // [rsp+90h] [rbp-70h] BYREF
  int v44; // [rsp+98h] [rbp-68h] BYREF
  int v45; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING StringRawBuffer; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v48; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v49[6]; // [rsp+B8h] [rbp-48h] BYREF
  char v50; // [rsp+E8h] [rbp-18h]
  int v51; // [rsp+F0h] [rbp-10h] BYREF
  int v52; // [rsp+F4h] [rbp-Ch] BYREF
  __int64 v53; // [rsp+F8h] [rbp-8h] BYREF
  ULONGLONG TickCount64; // [rsp+100h] [rbp+0h] BYREF
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v55; // [rsp+108h] [rbp+8h]
  PCWSTR v56; // [rsp+110h] [rbp+10h] BYREF
  PCWSTR v57; // [rsp+118h] [rbp+18h] BYREF
  HSTRING v58[4]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v33 = 0;
  v51 = 0;
  TickCount64 = GetTickCount64();
  v53 = 0;
  string = 0;
  v36 = 0;
  Windows::Internal::String::Initialize((Windows::Internal::String *)&v36, L"NULL", 4u);
  Windows::Internal::String::Initialize((Windows::Internal::String *)&string, L"NULL", 4u);
  v49[0] = &string;
  v49[1] = &v36;
  v49[2] = &v53;
  v49[3] = &v33;
  v49[4] = &v51;
  v49[5] = &TickCount64;
  v50 = 1;
  v35 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::CallerContext *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  PluginPFN = v5(a2, &v35);
  v33 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    v7 = 230;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
      (const char *)(unsigned int)PluginPFN,
      v32);
    goto LABEL_64;
  }
  WindowsDeleteString(string);
  string = 0;
  PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(
                this,
                (__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v35,
                &string);
  v33 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    v7 = 231;
    goto LABEL_3;
  }
  v8 = v35;
  v9 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *))(*(_QWORD *)v35 + 48LL);
  WindowsDeleteString(v36);
  v36 = 0;
  PluginPFN = v9(v8, &v36);
  v33 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    v7 = 232;
    goto LABEL_3;
  }
  v37 = 0;
  PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(
                this,
                string,
                &v37);
  v33 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    v7 = 235;
    goto LABEL_3;
  }
  v55 = 0;
  AccountManagerInstance = Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(
                             v37,
                             *((_QWORD *)this + 2));
  v55 = AccountManagerInstance;
  if ( !AccountManagerInstance )
  {
    PluginPFN = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEF,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
      (const char *)0x8007000ELL,
      v32);
    goto LABEL_64;
  }
  v39 = 0;
  v11 = (**(__int64 (__fastcall ***)(struct Windows::Internal::Security::Authentication::Web::CallerContext *, GUID *, __int64 *))a2)(
          a2,
          &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824,
          &v39);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)v11,
      v32);
  wil::com_ptr_t<Windows::Internal::Security::Credentials::IWebAccountSystemInformation,wil::err_exception_policy>::com_ptr_t<Windows::Internal::Security::Credentials::IWebAccountSystemInformation,wil::err_exception_policy>(
    &v40,
    (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))a2);
  v38 = 0;
  PluginPFN = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL))(v39, &v38);
  v33 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    v12 = 248;
    goto LABEL_14;
  }
  v44 = 0;
  PluginPFN = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 48LL))(v40, &v44);
  v33 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    v12 = 251;
    goto LABEL_14;
  }
  if ( (unsigned int)dword_180175000 > 5 )
  {
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(string, 0);
    v45 = v44;
    v43 = WindowsGetStringRawBuffer(v38, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v13,
      (unsigned int)&byte_1801517AF,
      v14,
      v15,
      (__int64)&v43,
      (__int64)&v45,
      (__int64)&StringRawBuffer);
  }
  if ( !v44 )
    TrySignalAccountEvent(8, v38, string, v35, 0);
  PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginManagerInternal::InvokeToCleanupDeletedAccount(
                this,
                a2,
                string);
  v51 = PluginPFN;
  if ( PluginPFN < 0 )
    goto LABEL_15;
  v32 = (int)v35;
  PluginPFN = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, HSTRING, HSTRING, _QWORD))(*(_QWORD *)AccountManagerInstance + 40LL))(
                AccountManagerInstance,
                v38,
                string,
                *((_QWORD *)this + 1));
  v33 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    v12 = 280;
    goto LABEL_14;
  }
  if ( v44 )
    goto LABEL_60;
  v41 = 0;
  v16 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, struct Windows::Internal::Security::Authentication::Web::CallerContext *, __int64 *, HSTRING))(*(_QWORD *)AccountManagerInstance + 112LL);
  v17 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  PluginPFN = v16(AccountManagerInstance, a2, &v41, v17);
  v33 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    v18 = 286;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
      (const char *)(unsigned int)PluginPFN,
      v32);
    goto LABEL_31;
  }
  if ( !v41 )
    goto LABEL_47;
  v48 = 0;
  PluginPFN = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 56LL))(v41, &v48);
  v33 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    v18 = 291;
    goto LABEL_30;
  }
  v19 = 0;
  if ( !v48 )
  {
LABEL_47:
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)v58,
      L"ProviderDefaultAccountCacheExpiration");
    v25 = v58[0];
    CurrentSystemTimeAsInt64 = GetCurrentSystemTimeAsInt64();
    PluginPFN = SetTokenCacheExpirationTime(string, CurrentSystemTimeAsInt64, v25);
    if ( PluginPFN < 0 )
    {
      v18 = 321;
      goto LABEL_30;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_60:
    Windows::Internal::StringReference::_ConstructorHelper(
      (Windows::Internal::StringReference *)v58,
      L"EnumApiCacheExpiration");
    v29 = v58[0];
    v30 = GetCurrentSystemTimeAsInt64();
    PluginPFN = SetTokenCacheExpirationTime(string, v30, v29);
    if ( PluginPFN >= 0 )
    {
      PluginPFN = v33;
      goto LABEL_15;
    }
    v12 = 324;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
      (const char *)(unsigned int)PluginPFN,
      v32);
    goto LABEL_15;
  }
  while ( 1 )
  {
    v42 = 0;
    v43 = 0;
    v46 = 0;
    v20 = v41;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v41 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    PluginPFN = v21(v20, v19, &v42);
    v33 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      v28 = 298;
      goto LABEL_56;
    }
    PluginPFN = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                  &v42,
                  (__int64)&v43);
    v33 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      v28 = 299;
      goto LABEL_56;
    }
    PluginPFN = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Internal::Security::Credentials::IWebAccountSystemInformation>(
                  &v42,
                  (__int64)&v46);
    v33 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      v28 = 300;
LABEL_56:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
        (const char *)(unsigned int)PluginPFN,
        v32);
      goto LABEL_52;
    }
    StringRawBuffer = 0;
    PluginPFN = (*(__int64 (__fastcall **)(PCWSTR, HSTRING *))(*(_QWORD *)v43 + 48LL))(v43, &StringRawBuffer);
    v33 = PluginPFN;
    if ( PluginPFN < 0 )
      break;
    v45 = 0;
    PluginPFN = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 48LL))(v46, &v45);
    v33 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      v27 = 306;
      goto LABEL_50;
    }
    if ( (unsigned int)dword_180175000 > 5 )
    {
      v56 = WindowsGetStringRawBuffer(string, 0);
      v52 = v45;
      v57 = WindowsGetStringRawBuffer(StringRawBuffer, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v22,
        (unsigned int)byte_18015180B,
        v23,
        v24,
        (__int64)&v57,
        (__int64)&v52,
        (__int64)&v56);
    }
    v32 = (int)v35;
    PluginPFN = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, HSTRING, HSTRING, _QWORD))(*(_QWORD *)AccountManagerInstance + 40LL))(
                  AccountManagerInstance,
                  StringRawBuffer,
                  string,
                  *((_QWORD *)this + 1));
    v33 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      v27 = 316;
      goto LABEL_50;
    }
    if ( StringRawBuffer )
      WindowsDeleteString(StringRawBuffer);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    if ( ++v19 >= v48 )
      goto LABEL_47;
  }
  v27 = 303;
LABEL_50:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v27,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manageroperation.cpp",
    (const char *)(unsigned int)PluginPFN,
    v32);
  if ( StringRawBuffer )
    WindowsDeleteString(StringRawBuffer);
LABEL_52:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
LABEL_31:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_15:
  if ( v38 )
    WindowsDeleteString(v38);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v40);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v39);
  (**(void (__fastcall ***)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64))AccountManagerInstance)(
    AccountManagerInstance,
    1);
LABEL_64:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v50 = 0;
  lambda_c35ff4b285c6bf33532f26e56f2f55a7_::operator()(v49);
  if ( v36 )
    WindowsDeleteString(v36);
  if ( string )
    WindowsDeleteString(string);
  return (unsigned int)PluginPFN;
}

```

## disassembly

```asm
0x1800e2094  mov     [rsp-8+arg_10], rbx
0x1800e2099  push    rbp
0x1800e209a  push    rsi
0x1800e209b  push    rdi
0x1800e209c  push    r12
0x1800e209e  push    r13
0x1800e20a0  push    r14
0x1800e20a2  push    r15
0x1800e20a4  lea     rbp, [rsp-50h]
0x1800e20a9  sub     rsp, 150h
0x1800e20b0  mov     rax, cs:__security_cookie
0x1800e20b7  xor     rax, rsp
0x1800e20ba  mov     [rbp+80h+var_40], rax
0x1800e20be  mov     r14, rdx
0x1800e20c1  mov     r15, rcx
0x1800e20c4  xor     r12d, r12d
0x1800e20c7  mov     [rsp+180h+var_140], r12d
0x1800e20cc  mov     [rbp+80h+var_90], r12d
0x1800e20d0  call    cs:__imp_GetTickCount64
0x1800e20d6  mov     [rbp+80h+var_80], rax
0x1800e20da  mov     [rbp+80h+var_88], r12
0x1800e20de  mov     [rsp+180h+string], r12
0x1800e20e3  mov     [rsp+180h+var_128], r12
0x1800e20e8  lea     ebx, [r12+4]
0x1800e20ed  mov     r8d, ebx; unsigned int
0x1800e20f0  lea     rdx, aNull_1; "NULL"
0x1800e20f7  lea     rcx, [rsp+180h+var_128]; this
0x1800e20fc  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x1800e2101  mov     r8d, ebx; unsigned int
0x1800e2104  lea     rdx, aNull_1; "NULL"
0x1800e210b  lea     rcx, [rsp+180h+string]; this
0x1800e2110  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x1800e2115  lea     rax, [rsp+180h+string]
0x1800e211a  mov     [rbp+80h+var_C8], rax
0x1800e211e  lea     rax, [rsp+180h+var_128]
0x1800e2123  mov     [rbp+80h+var_C0], rax
0x1800e2127  lea     rax, [rbp+80h+var_88]
0x1800e212b  mov     [rbp+80h+var_B8], rax
0x1800e212f  lea     rax, [rsp+180h+var_140]
0x1800e2134  mov     [rbp+80h+var_B0], rax
0x1800e2138  lea     rax, [rbp+80h+var_90]
0x1800e213c  mov     [rbp+80h+var_A8], rax
0x1800e2140  lea     rax, [rbp+80h+var_80]
0x1800e2144  mov     [rbp+80h+var_A0], rax
0x1800e2148  lea     r13d, [r12+1]
0x1800e214d  mov     [rbp+80h+var_98], r13b
0x1800e2151  mov     [rsp+180h+var_130], r12
0x1800e2156  mov     rax, [r14]
0x1800e2159  mov     rbx, [rax+30h]
0x1800e215d  lea     rcx, [rsp+180h+var_130]
0x1800e2162  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e2167  lea     rdx, [rsp+180h+var_130]
0x1800e216c  mov     rcx, r14
0x1800e216f  mov     rax, rbx
0x1800e2172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2177  mov     ebx, eax
0x1800e2179  mov     [rsp+180h+var_140], eax
0x1800e217d  test    eax, eax
0x1800e217f  jns     short loc_1800E21A1
0x1800e2181  mov     edx, 0E6h; void *
0x1800e2186  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800e218d  mov     r9d, ebx; char *
0x1800e2190  mov     rcx, [rbp+88h]; this
0x1800e2197  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e219c  jmp     loc_1800E277A
0x1800e21a1  mov     rcx, [rsp+180h+string]; string
0x1800e21a6  call    cs:__imp_WindowsDeleteString
0x1800e21ac  mov     [rsp+180h+string], r12
0x1800e21b1  lea     r8, [rsp+180h+string]; HSTRING *
0x1800e21b6  mov     rdx, [rsp+180h+var_130]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800e21bb  mov     rcx, r15; this
0x1800e21be  call    ?GetPluginPFN@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x1800e21c3  mov     ebx, eax
0x1800e21c5  mov     [rsp+180h+var_140], eax
0x1800e21c9  test    eax, eax
0x1800e21cb  jns     short loc_1800E21D4
0x1800e21cd  mov     edx, 0E7h
0x1800e21d2  jmp     short loc_1800E2186
0x1800e21d4  mov     rdi, [rsp+180h+var_130]
0x1800e21d9  mov     rax, [rdi]
0x1800e21dc  mov     rbx, [rax+30h]
0x1800e21e0  mov     rcx, [rsp+180h+var_128]; string
0x1800e21e5  call    cs:__imp_WindowsDeleteString
0x1800e21eb  mov     [rsp+180h+var_128], r12
0x1800e21f0  lea     rdx, [rsp+180h+var_128]
0x1800e21f5  mov     rcx, rdi
0x1800e21f8  mov     rax, rbx
0x1800e21fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2200  mov     ebx, eax
0x1800e2202  mov     [rsp+180h+var_140], eax
0x1800e2206  test    eax, eax
0x1800e2208  jns     short loc_1800E2214
0x1800e220a  mov     edx, 0E8h
0x1800e220f  jmp     loc_1800E2186
0x1800e2214  mov     [rsp+180h+var_120], r12b
0x1800e2219  lea     r8, [rsp+180h+var_120]; bool *
0x1800e221e  mov     rdx, [rsp+180h+string]; HSTRING
0x1800e2223  mov     rcx, r15; struct Windows::Internal::Security::Authentication::Web::CallerContext *
0x1800e2226  call    ?IsPluginMultiUserAware@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@QEAUHSTRING__@@PEA_N@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(Windows::Internal::Security::Authentication::Web::CallerContext *,HSTRING__ * const,bool *)
0x1800e222b  mov     ebx, eax
0x1800e222d  mov     [rsp+180h+var_140], eax
0x1800e2231  test    eax, eax
0x1800e2233  jns     short loc_1800E223F
0x1800e2235  mov     edx, 0EBh
0x1800e223a  jmp     loc_1800E2186
0x1800e223f  mov     [rbp+80h+var_78], r12
0x1800e2243  mov     rdx, [r15+10h]; unsigned __int64
0x1800e2247  mov     cl, [rsp+180h+var_120]; bool
0x1800e224b  call    ?GetAccountManagerInstance@CAccountManagerFactory@TokenBroker@Authentication@Security@Internal@Windows@@SAPEAVIAccountManager@23456@_N_K@Z; Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(bool,unsigned __int64)
0x1800e2250  mov     rsi, rax
0x1800e2253  mov     [rbp+80h+var_78], rax
0x1800e2257  test    rax, rax
0x1800e225a  jz      loc_1800E2759
0x1800e2260  mov     [rsp+180h+var_110], r12
0x1800e2265  mov     rcx, [r14]
0x1800e2268  mov     rax, [rcx]
0x1800e226b  lea     r8, [rsp+180h+var_110]
0x1800e2270  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x1800e2277  mov     rcx, r14
0x1800e227a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e227f  mov     rcx, [rbp+88h]; this
0x1800e2286  test    eax, eax
0x1800e2288  js      loc_1800E27DD
0x1800e228e  mov     rdx, r14
0x1800e2291  lea     rcx, [rsp+180h+var_108]
0x1800e2296  call    ??$?0UIWebAccount@Credentials@Security@Windows@@@?$com_ptr_t@UIWebAccountSystemInformation@Credentials@Security@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIWebAccount@Credentials@Security@Windows@@U?$integral_constant@D$0A@@wistd@@@Z; wil::com_ptr_t<Windows::Internal::Security::Credentials::IWebAccountSystemInformation,wil::err_exception_policy>::com_ptr_t<Windows::Internal::Security::Credentials::IWebAccountSystemInformation,wil::err_exception_policy>(Windows::Security::Credentials::IWebAccount *,wistd::integral_constant<char,0>)
0x1800e229b  nop
0x1800e229c  mov     [rsp+180h+var_118], r12
0x1800e22a1  mov     rcx, [rsp+180h+var_110]
0x1800e22a6  mov     rax, [rcx]
0x1800e22a9  lea     rdx, [rsp+180h+var_118]
0x1800e22ae  mov     rax, [rax+30h]
0x1800e22b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e22b7  mov     ebx, eax
0x1800e22b9  mov     [rsp+180h+var_140], eax
0x1800e22bd  test    eax, eax
0x1800e22bf  jns     short loc_1800E231A
0x1800e22c1  mov     edx, 0F8h; void *
0x1800e22c6  mov     rcx, [rbp+88h]; this
0x1800e22cd  mov     r9d, ebx; char *
0x1800e22d0  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800e22d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e22dc  nop
0x1800e22dd  mov     rcx, [rsp+180h+var_118]; string
0x1800e22e2  test    rcx, rcx
0x1800e22e5  jz      short loc_1800E22EE
0x1800e22e7  call    cs:__imp_WindowsDeleteString
0x1800e22ed  nop
0x1800e22ee  lea     rcx, [rsp+180h+var_108]
0x1800e22f3  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800e22f8  nop
0x1800e22f9  lea     rcx, [rsp+180h+var_110]
0x1800e22fe  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x1800e2303  nop
0x1800e2304  mov     rax, [rsi]
0x1800e2307  mov     edx, r13d
0x1800e230a  mov     rcx, rsi
0x1800e230d  mov     rax, [rax]
0x1800e2310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2315  jmp     loc_1800E277A
0x1800e231a  mov     [rbp+80h+var_E8], r12d
0x1800e231e  mov     rcx, [rsp+180h+var_108]
0x1800e2323  mov     rax, [rcx]
0x1800e2326  lea     rdx, [rbp+80h+var_E8]
0x1800e232a  mov     rax, [rax+30h]
0x1800e232e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2333  mov     ebx, eax
0x1800e2335  mov     [rsp+180h+var_140], eax
0x1800e2339  test    eax, eax
0x1800e233b  jns     short loc_1800E2344
0x1800e233d  mov     edx, 0FBh
0x1800e2342  jmp     short loc_1800E22C6
0x1800e2344  mov     eax, cs:dword_180175000
0x1800e234a  cmp     eax, 5
0x1800e234d  jbe     short loc_1800E239E
0x1800e234f  xor     edx, edx; length
0x1800e2351  mov     rcx, [rsp+180h+string]; string
0x1800e2356  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e235c  mov     [rbp+80h+var_D8], rax
0x1800e2360  mov     eax, [rbp+80h+var_E8]
0x1800e2363  mov     [rbp+80h+var_E4], eax
0x1800e2366  xor     edx, edx; length
0x1800e2368  mov     rcx, [rsp+180h+var_118]; string
0x1800e236d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e2373  mov     [rbp+80h+var_F0], rax
0x1800e2377  lea     rax, [rbp+80h+var_D8]
0x1800e237b  mov     [rsp+180h+var_150], rax
0x1800e2380  lea     rax, [rbp+80h+var_E4]
0x1800e2384  mov     [rsp+180h+var_158], rax
0x1800e2389  lea     rax, [rbp+80h+var_F0]
0x1800e238d  mov     qword ptr [rsp+180h+var_160], rax
0x1800e2392  lea     rdx, byte_1801517AF
0x1800e2399  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800e239e  cmp     [rbp+80h+var_E8], r12d
0x1800e23a2  jnz     short loc_1800E23C2
0x1800e23a4  mov     qword ptr [rsp+180h+var_160], r12
0x1800e23a9  mov     r9, [rsp+180h+var_130]
0x1800e23ae  mov     r8, [rsp+180h+string]
0x1800e23b3  mov     rdx, [rsp+180h+var_118]
0x1800e23b8  mov     ecx, 8
0x1800e23bd  call    ?TrySignalAccountEvent@@YAXW4SystemEventType@Web@Authentication@Security@Internal@Windows@@PEAUHSTRING__@@1PEAUIWebAccountProvider@Credentials@46@1@Z; TrySignalAccountEvent(Windows::Internal::Security::Authentication::Web::SystemEventType,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ *)
0x1800e23c2  mov     r8, [rsp+180h+string]; HSTRING
0x1800e23c7  mov     rdx, r14; struct Windows::Security::Credentials::IWebAccount *
0x1800e23ca  mov     rcx, r15; struct Windows::Internal::Security::Authentication::Web::CallerContext *
0x1800e23cd  call    ?InvokeToCleanupDeletedAccount@PluginManagerInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccount@Credentials@46@PEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManagerInternal::InvokeToCleanupDeletedAccount(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccount *,HSTRING__ *)
0x1800e23d2  mov     ebx, eax
0x1800e23d4  mov     [rbp+80h+var_90], eax
0x1800e23d7  test    eax, eax
0x1800e23d9  js      loc_1800E22DD
0x1800e23df  mov     rax, [rsi]
0x1800e23e2  mov     rcx, [rsp+180h+var_130]
0x1800e23e7  mov     qword ptr [rsp+180h+var_160], rcx; int
0x1800e23ec  mov     r9, [r15+8]
0x1800e23f0  mov     r8, [rsp+180h+string]
0x1800e23f5  mov     rdx, [rsp+180h+var_118]
0x1800e23fa  mov     rcx, rsi
0x1800e23fd  mov     rax, [rax+28h]
0x1800e2401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2406  mov     ebx, eax
0x1800e2408  mov     [rsp+180h+var_140], eax
0x1800e240c  test    eax, eax
0x1800e240e  jns     short loc_1800E241A
0x1800e2410  mov     edx, 118h
0x1800e2415  jmp     loc_1800E22C6
0x1800e241a  cmp     [rbp+80h+var_E8], r12d
0x1800e241e  jnz     loc_1800E2717
0x1800e2424  mov     [rbp+80h+var_100], r12
0x1800e2428  mov     rax, [rsi]
0x1800e242b  mov     rdi, [rax+70h]
0x1800e242f  mov     rbx, [rsp+180h+string]
0x1800e2434  lea     rcx, [rbp+80h+var_100]
0x1800e2438  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e243d  mov     r9, rbx
0x1800e2440  lea     r8, [rbp+80h+var_100]
0x1800e2444  mov     rdx, r14
0x1800e2447  mov     rcx, rsi
0x1800e244a  mov     rax, rdi
0x1800e244d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2452  mov     ebx, eax
0x1800e2454  mov     [rsp+180h+var_140], eax
0x1800e2458  test    eax, eax
0x1800e245a  jns     short loc_1800E2486
0x1800e245c  mov     edx, 11Eh; void *
0x1800e2461  mov     rcx, [rbp+88h]; this
0x1800e2468  mov     r9d, ebx; char *
0x1800e246b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800e2472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2477  nop
0x1800e2478  lea     rcx, [rbp+80h+var_100]
0x1800e247c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e2481  jmp     loc_1800E22DD
0x1800e2486  mov     rcx, [rbp+80h+var_100]
0x1800e248a  test    rcx, rcx
0x1800e248d  jz      loc_1800E264A
0x1800e2493  mov     [rbp+80h+var_D0], r12d
0x1800e2497  mov     rax, [rcx]
0x1800e249a  lea     rdx, [rbp+80h+var_D0]
0x1800e249e  mov     rax, [rax+38h]
0x1800e24a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e24a7  mov     ebx, eax
0x1800e24a9  mov     [rsp+180h+var_140], eax
0x1800e24ad  test    eax, eax
0x1800e24af  jns     short loc_1800E24B8
0x1800e24b1  mov     edx, 123h
0x1800e24b6  jmp     short loc_1800E2461
0x1800e24b8  mov     r14d, r12d
0x1800e24bb  cmp     [rbp+80h+var_D0], r12d
0x1800e24bf  jbe     loc_1800E264A
0x1800e24c5  mov     [rbp+80h+var_F8], r12
0x1800e24c9  mov     [rbp+80h+var_F0], r12
0x1800e24cd  mov     [rbp+80h+var_E0], r12
0x1800e24d1  mov     rdi, [rbp+80h+var_100]
0x1800e24d5  mov     rax, [rdi]
0x1800e24d8  mov     rbx, [rax+30h]
0x1800e24dc  lea     rcx, [rbp+80h+var_F8]
0x1800e24e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e24e5  lea     r8, [rbp+80h+var_F8]
0x1800e24e9  mov     edx, r14d
0x1800e24ec  mov     rcx, rdi
0x1800e24ef  mov     rax, rbx
0x1800e24f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e24f7  mov     ebx, eax
0x1800e24f9  mov     [rsp+180h+var_140], eax
0x1800e24fd  test    eax, eax
0x1800e24ff  js      loc_1800E2707
0x1800e2505  lea     rdx, [rbp+80h+var_F0]
0x1800e2509  lea     rcx, [rbp+80h+var_F8]
0x1800e250d  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x1800e2512  mov     ebx, eax
0x1800e2514  mov     [rsp+180h+var_140], eax
0x1800e2518  test    eax, eax
0x1800e251a  js      loc_1800E2700
0x1800e2520  lea     rdx, [rbp+80h+var_E0]
0x1800e2524  lea     rcx, [rbp+80h+var_F8]
0x1800e2528  call    ??$As@UIWebAccountSystemInformation@Credentials@Security@Internal@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountSystemInformation@Credentials@Security@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Internal::Security::Credentials::IWebAccountSystemInformation>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountSystemInformation>>)
0x1800e252d  mov     ebx, eax
0x1800e252f  mov     [rsp+180h+var_140], eax
0x1800e2533  test    eax, eax
0x1800e2535  js      loc_1800E26E3
0x1800e253b  mov     [rbp+80h+var_D8], r12
  ... truncated ...
```
