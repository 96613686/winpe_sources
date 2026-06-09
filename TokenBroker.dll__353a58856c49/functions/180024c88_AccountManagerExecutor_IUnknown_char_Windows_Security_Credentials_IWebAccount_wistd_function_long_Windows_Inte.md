# AccountManagerExecutor(IUnknown *,char *,Windows::Security::Credentials::IWebAccount *,wistd::function<long (Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Internal::String &,Windows::Internal::String &,Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *,Windows::Security::Credentials::IWebAccountProvider *)>)

- ea: `0x180024c88`
- end: `0x1800256a5`
- name: `?AccountManagerExecutor@@YAJPEAUIUnknown@@PEADPEAUIWebAccount@Credentials@Security@Windows@@V?$function@$$A6AJPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@AEAVString@56@1PEAVIAccountManager@TokenBroker@3456@PEAUIWebAccountProvider@Credentials@46@@Z@wistd@@@Z`
- size: `2589`
- prototype: `__int64 __fastcall(struct IUnknown *, __int64, Windows::Internal::Security::Authentication::TokenBroker *, __int64)`
- caller_count: `13`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180057310`
- `0x180060250`
- `0x1800d6210`
- `0x1800d62c0`
- `0x1800d6360`
- `0x1800d6400`
- `0x1800d6490`
- `0x1800d6530`
- `0x1800d66f0`
- `0x1800d67a0`
- `0x1800d6850`
- `0x1800d6920`
- `0x1800d69d0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000bd70`
- `0x1800200b4`
- `0x180023a80`
- `0x180024000`
- `0x180024c88`
- `0x1800256ac`
- `0x180026058`
- `0x18002607c`
- `0x180026180`
- `0x1800262f0`
- `0x1800266b0`
- `0x180026728`
- `0x1800269f4`
- `0x18006072c`
- `0x1800d3ce4`
- `0x1800d3d10`
- `0x1800d3ddc`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180025016`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800250f0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800252b6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180025016`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800250f0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800252b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002507b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002508f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800250b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002514d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025161`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025185`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002526f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025313`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002534b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002543d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002547f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800254d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800254e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025505`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002555b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002556f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002558b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800255f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002560a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002507b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002508f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800250b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002514d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025161`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025185`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002526f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025313`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002534b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800253ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002543d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002547f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800254d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800254e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025505`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002555b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002556f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002558b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800255f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002560a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180024cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180024cdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025684`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025684`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180024db5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180024db5`

## string_xrefs

- `0x1800251cb`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x180025647`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x180024ff0`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x1800251a7`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x180025210`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x180025240`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x180025290`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x18002536c`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x180025421`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x180025463`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x1800254a0`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x180025526`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`
- `0x1800255ac`: `onecore\ds\security\tokenbroker\broker\lib\tbaccountmanagerinternal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AccountManagerExecutor(
        struct IUnknown *a1,
        __int64 a2,
        Windows::Internal::Security::Authentication::TokenBroker *a3,
        __int64 a4)
{
  int AccountIdFromWebAccount; // eax
  unsigned int v8; // ebx
  __int64 (__fastcall *v9)(Windows::Internal::Security::Authentication::TokenBroker *, Windows::Internal::Security::Authentication::TokenBroker **); // rbx
  int v10; // eax
  unsigned __int64 *v11; // r8
  int UserContextFromProvider; // eax
  Windows::Internal::Security::Authentication::TokenBroker *v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  __int64 (__fastcall *v16)(Windows::Internal::Security::Authentication::TokenBroker *, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v17; // eax
  int v18; // ebx
  int v19; // eax
  int PluginPFN; // eax
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *AccountManagerInstance; // rsi
  Windows::Internal::Security::Authentication::Web::CallerContext *v22; // r14
  int IsPluginMultiUserAware; // eax
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v24; // rdx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  HANDLE v28; // rcx
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v29; // rdx
  struct Windows::Security::Credentials::IWebAccountProvider *v30; // rcx
  __int64 v31; // rcx
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v32; // rdx
  struct Windows::Security::Credentials::IWebAccountProvider *v33; // rcx
  unsigned int v34; // ebx
  const char *v35; // r9
  __int64 result; // rax
  __int64 v37; // r9
  __int64 v38; // rdx
  Windows::Internal::Security::Authentication::TokenBroker *v39; // rcx
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v40; // rdx
  struct Windows::Security::Credentials::IWebAccountProvider *v41; // rcx
  struct Windows::Security::Credentials::IWebAccountProvider *v42; // rcx
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v43; // rdx
  int v44; // [rsp+20h] [rbp-178h]
  int v45; // [rsp+20h] [rbp-178h]
  int v46; // [rsp+20h] [rbp-178h]
  int v47; // [rsp+50h] [rbp-148h] BYREF
  bool v48; // [rsp+54h] [rbp-144h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v49; // [rsp+58h] [rbp-140h] BYREF
  HSTRING string; // [rsp+60h] [rbp-138h] BYREF
  Windows::Internal::Security::Authentication::Web::CallerContext *v51; // [rsp+68h] [rbp-130h] BYREF
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v52; // [rsp+70h] [rbp-128h] BYREF
  HSTRING v53; // [rsp+78h] [rbp-120h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v54; // [rsp+80h] [rbp-118h] BYREF
  HSTRING v55; // [rsp+88h] [rbp-110h] BYREF
  HANDLE Token; // [rsp+90h] [rbp-108h] BYREF
  char v57; // [rsp+98h] [rbp-100h]
  unsigned __int64 v58; // [rsp+A0h] [rbp-F8h] BYREF
  ULONGLONG TickCount64; // [rsp+A8h] [rbp-F0h] BYREF
  __int64 v60; // [rsp+B0h] [rbp-E8h] BYREF
  int v61[2]; // [rsp+B8h] [rbp-E0h] BYREF
  _QWORD v62[3]; // [rsp+C0h] [rbp-D8h] BYREF
  char v63; // [rsp+D8h] [rbp-C0h]
  _BYTE v64[80]; // [rsp+E0h] [rbp-B8h] BYREF
  char v65; // [rsp+130h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]
  __int64 v67; // [rsp+1A8h] [rbp+10h] BYREF
  __int64 v68; // [rsp+1B8h] [rbp+20h]

  v68 = a4;
  v67 = a2;
  try
  {
    string = 0;
    AccountIdFromWebAccount = Windows::Internal::Security::Authentication::TokenBroker::GetAccountIdFromWebAccount(
                                a3,
                                (struct Windows::Security::Credentials::IWebAccount *)&string,
                                (HSTRING *)a3);
    v8 = AccountIdFromWebAccount;
    v47 = AccountIdFromWebAccount;
    if ( AccountIdFromWebAccount >= 0 )
    {
      if ( WindowsIsStringEmpty(string) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
          (const char *)0x80070057LL,
          v44);
        if ( string )
          WindowsDeleteString(string);
        wistd::function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>::~function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>(a4);
        return 2147942487LL;
      }
      v58 = 0;
      v54 = 0;
      v9 = *(__int64 (__fastcall **)(Windows::Internal::Security::Authentication::TokenBroker *, Windows::Internal::Security::Authentication::TokenBroker **))(*(_QWORD *)a3 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      v10 = v9(a3, &v54);
      v8 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA67,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)v10,
          v44);
        v39 = v54;
        if ( v54 )
        {
          v54 = 0;
          (*(void (__fastcall **)(Windows::Internal::Security::Authentication::TokenBroker *))(*(_QWORD *)v39 + 16LL))(v39);
        }
      }
      else
      {
        UserContextFromProvider = Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(
                                    v54,
                                    (struct Windows::Security::Credentials::IWebAccountProvider *)&v58,
                                    v11);
        v8 = UserContextFromProvider;
        if ( UserContextFromProvider >= 0 )
        {
          v13 = v54;
          if ( v54 )
          {
            v54 = 0;
            (*(void (__fastcall **)(Windows::Internal::Security::Authentication::TokenBroker *))(*(_QWORD *)v13 + 16LL))(v13);
          }
          std::make_unique<Windows::Internal::Security::Authentication::Web::CallerContext,,0>(&v51);
          v14 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v51, a1, v58, 1);
          v8 = v14;
          v47 = v14;
          if ( v14 >= 0 )
          {
            v55 = 0;
            v53 = 0;
            TickCount64 = GetTickCount64();
            v60 = 0;
            v15 = lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b_::_lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b_(
                    (unsigned int)&v65,
                    (unsigned int)&v60,
                    (unsigned int)&v67,
                    (unsigned int)&v47,
                    (__int64)&string,
                    (__int64)&v55,
                    (__int64)&v53,
                    (__int64)&v51,
                    (__int64)&TickCount64);
            wil::scope_exit__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___(v64, v15);
            v49 = 0;
            v16 = *(__int64 (__fastcall **)(Windows::Internal::Security::Authentication::TokenBroker *, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)a3 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
            v17 = v16(a3, &v49);
            v18 = v17;
            v47 = v17;
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x69,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
                (const char *)(unsigned int)v17,
                v45);
              v42 = v49;
              if ( v49 )
              {
                v49 = 0;
                (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v42 + 16LL))(v42);
              }
              wil::details::lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___::_lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___(v64);
              if ( v53 )
                WindowsDeleteString(v53);
              if ( v55 )
                WindowsDeleteString(v55);
              if ( v51 )
                Windows::Internal::Security::Authentication::Web::CallerContext::`scalar deleting destructor'(v51, 1u);
              if ( !string )
                goto LABEL_111;
              goto LABEL_110;
            }
            v19 = (*(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *))(*(_QWORD *)v49 + 48LL))(
                    v49,
                    &v55);
            v18 = v19;
            v47 = v19;
            if ( v19 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6A,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
                (const char *)(unsigned int)v19,
                v45);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
              wil::details::lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___::_lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___(v64);
              if ( v53 )
                WindowsDeleteString(v53);
              if ( v55 )
                WindowsDeleteString(v55);
              std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v51);
              if ( !string )
                goto LABEL_111;
              goto LABEL_110;
            }
            PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(
                          v51,
                          v49,
                          &v53);
            v18 = PluginPFN;
            v47 = PluginPFN;
            if ( PluginPFN < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6B,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
                (const char *)(unsigned int)PluginPFN,
                v45);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
              wil::details::lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___::_lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___(v64);
              if ( v53 )
                WindowsDeleteString(v53);
              if ( v55 )
                WindowsDeleteString(v55);
              std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v51);
              if ( !string )
                goto LABEL_111;
              goto LABEL_110;
            }
            v52 = 0;
            v62[1] = &v52;
            AccountManagerInstance = 0;
            v62[2] = 0;
            v63 = 1;
            v22 = v51;
            v48 = 0;
            IsPluginMultiUserAware = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(
                                       v51,
                                       v53,
                                       &v48);
            v18 = IsPluginMultiUserAware;
            if ( IsPluginMultiUserAware < 0 )
            {
              v37 = (unsigned int)IsPluginMultiUserAware;
              v38 = 32;
            }
            else
            {
              AccountManagerInstance = Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(
                                         v48,
                                         *((_QWORD *)v22 + 2));
              if ( AccountManagerInstance )
                goto LABEL_14;
              v18 = -2147024882;
              v37 = 2147942414LL;
              v38 = 37;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v38,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
              (const char *)v37,
              v45);
LABEL_14:
            v47 = v18;
            v24 = v52;
            v52 = AccountManagerInstance;
            if ( v24 )
              ((void (*)(void))std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator())();
            if ( v18 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6F,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
                (const char *)(unsigned int)v18,
                v45);
              v43 = v52;
              v52 = 0;
              if ( v43 )
                ((void (*)(void))std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator())();
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
              wil::details::lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___::_lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___(v64);
              if ( v53 )
                WindowsDeleteString(v53);
              if ( v55 )
                WindowsDeleteString(v55);
              std::_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>::~_Temporary_owner<Windows::Internal::Security::Authentication::Web::CallerContext>(&v51);
              if ( !string )
                goto LABEL_111;
            }
            else
            {
              Token = 0;
              v57 = 0;
              v25 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
                      &Token,
                      *((_QWORD *)v51 + 2));
              v18 = v25;
              v47 = v25;
              if ( v25 >= 0 )
              {
                v54 = v49;
                *(_QWORD *)v61 = v52;
                v62[0] = v51;
                v26 = *(_QWORD *)(a4 + 112);
                if ( !v26 )
                  __fastfail(7u);
                v27 = (*(__int64 (__fastcall **)(__int64, _QWORD *, HSTRING *, HSTRING *))(*(_QWORD *)v26 + 32LL))(
                        v26,
                        v62,
                        &string,
                        &v53);
                v18 = v27;
                v47 = v27;
                if ( v27 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x75,
                    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
                    (const char *)(unsigned int)v27,
                    (int)v61);
                  if ( v57 )
                    SetThreadToken(0, Token);
                  v28 = Token;
                  if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                    CloseHandle(Token);
                  v29 = v52;
                  v52 = 0;
                  if ( v29 )
                    std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator()(
                      v28,
                      v29);
                  v30 = v49;
                  if ( v49 )
                  {
                    v49 = 0;
                    (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v30 + 16LL))(v30);
                  }
                  wil::details::lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___::_lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___(v64);
                  if ( v53 )
                    WindowsDeleteString(v53);
                  if ( v55 )
                    WindowsDeleteString(v55);
                  if ( v51 )
                    Windows::Internal::Security::Authentication::Web::CallerContext::`scalar deleting destructor'(
                      v51,
                      1u);
                  if ( !string )
                    goto LABEL_111;
                  goto LABEL_110;
                }
                if ( v57 )
                  SetThreadToken(0, Token);
                Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&Token);
                v32 = v52;
                v52 = 0;
                if ( v32 )
                  std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator()(
                    v31,
                    v32);
                v33 = v49;
                if ( v49 )
                {
                  v49 = 0;
                  (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v33 + 16LL))(v33);
                }
                wil::details::lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___::_lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___(v64);
                if ( v53 )
                  WindowsDeleteString(v53);
                if ( v55 )
                  WindowsDeleteString(v55);
                if ( v51 )
                  Windows::Internal::Security::Authentication::Web::CallerContext::`scalar deleting destructor'(v51, 1u);
                if ( string )
                  WindowsDeleteString(string);
                v34 = v47;
                wistd::function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>::~function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>(a4);
                return v34;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x73,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
                (const char *)(unsigned int)v25,
                v45);
              if ( v57 )
                SetThreadToken(0, Token);
              Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&Token);
              v40 = v52;
              v52 = 0;
              if ( v40 )
                ((void (*)(void))std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator())();
              v41 = v49;
              if ( v49 )
              {
                v49 = 0;
                (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *))(*(_QWORD *)v41 + 16LL))(v41);
              }
              wil::details::lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___::_lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___(v64);
              if ( v53 )
                WindowsDeleteString(v53);
              if ( v55 )
                WindowsDeleteString(v55);
              if ( v51 )
                Windows::Internal::Security::Authentication::Web::CallerContext::`scalar deleting destructor'(v51, 1u);
              if ( !string )
                goto LABEL_111;
            }
LABEL_110:
            WindowsDeleteString(string);
LABEL_111:
            wistd::function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>::~function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>(a4);
            return (unsigned int)v18;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4B,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
            (const char *)(unsigned int)v14,
            v44);
          if ( v51 )
            Windows::Internal::Security::Authentication::Web::CallerContext::`scalar deleting destructor'(v51, 1u);
          if ( string )
            goto LABEL_86;
          goto LABEL_87;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA68,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)UserContextFromProvider,
          v44);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
      }
      v47 = v8;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
        (const char *)v8,
        v46);
      if ( !string )
        goto LABEL_87;
      goto LABEL_86;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
      (const char *)(unsigned int)AccountIdFromWebAccount,
      v44);
    if ( string )
LABEL_86:
      WindowsDeleteString(string);
LABEL_87:
    wistd::function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>::~function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>(a4);
    result = v8;
  }
  catch ( ... )
  {
    LODWORD(v49) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x77,
                     (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbaccountmanagerinternal.cpp",
                     v35);
    wistd::function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>::~function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>(v68);
    return (unsigned int)v49;
  }
  return result;
}

```

## disassembly

```asm
0x180024c88  mov     [rsp+arg_0], rbx
0x180024c8d  mov     [rsp+arg_18], r9
0x180024c92  mov     [rsp+arg_8], rdx
0x180024c97  push    rsi
0x180024c98  push    rdi
0x180024c99  push    r12
0x180024c9b  push    r14
0x180024c9d  push    r15
0x180024c9f  sub     rsp, 170h
0x180024ca6  mov     rdi, r9
0x180024ca9  mov     rsi, r8
0x180024cac  mov     r14, rcx
0x180024caf  xor     r15d, r15d
0x180024cb2  mov     [rsp+198h+var_148], r15d
0x180024cb7  mov     [rsp+198h+string], r15
0x180024cbc  lea     rdx, [rsp+198h+string]; struct Windows::Security::Credentials::IWebAccount *
0x180024cc1  mov     rcx, r8; this
0x180024cc4  call    ?GetAccountIdFromWebAccount@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccount@Credentials@35@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetAccountIdFromWebAccount(Windows::Security::Credentials::IWebAccount *,HSTRING__ * *)
0x180024cc9  mov     ebx, eax
0x180024ccb  mov     [rsp+198h+var_148], eax
0x180024ccf  test    eax, eax
0x180024cd1  js      loc_180025416
0x180024cd7  mov     rcx, [rsp+198h+string]; string
0x180024cdc  call    cs:__imp_WindowsIsStringEmpty
0x180024ce2  test    eax, eax
0x180024ce4  jnz     loc_180025453
0x180024cea  mov     [rsp+198h+var_F8], r15
0x180024cf2  mov     [rsp+198h+var_118], r15
0x180024cfa  mov     rax, [rsi]
0x180024cfd  mov     rbx, [rax+30h]
0x180024d01  lea     rcx, [rsp+198h+var_118]
0x180024d09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024d0e  lea     rdx, [rsp+198h+var_118]
0x180024d16  mov     rcx, rsi
0x180024d19  mov     rax, rbx
0x180024d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d21  mov     ebx, eax
0x180024d23  test    eax, eax
0x180024d25  js      loc_1800251C0
0x180024d2b  lea     rdx, [rsp+198h+var_F8]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180024d33  mov     rcx, [rsp+198h+var_118]; this
0x180024d3b  call    ?GetUserContextFromProvider@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@35@AEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(Windows::Security::Credentials::IWebAccountProvider *,unsigned __int64 &)
0x180024d40  mov     ebx, eax
0x180024d42  test    eax, eax
0x180024d44  js      loc_18002563C
0x180024d4a  mov     rcx, [rsp+198h+var_118]
0x180024d52  test    rcx, rcx
0x180024d55  jz      short loc_180024D6C
0x180024d57  mov     [rsp+198h+var_118], r15
0x180024d5f  mov     rax, [rcx]
0x180024d62  mov     rax, [rax+10h]
0x180024d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d6b  nop
0x180024d6c  mov     [rsp+198h+var_148], r15d
0x180024d71  lea     rcx, [rsp+198h+var_130]
0x180024d76  call    ??$make_unique@VCallerContext@Web@Authentication@Security@Internal@Windows@@$$V$0A@@std@@YA?AV?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@@0@XZ; std::make_unique<Windows::Internal::Security::Authentication::Web::CallerContext,,0>(void)
0x180024d7b  nop
0x180024d7c  mov     r12d, 1
0x180024d82  mov     r9b, r12b; bool
0x180024d85  mov     r8, [rsp+198h+var_F8]; unsigned __int64
0x180024d8d  mov     rdx, r14; struct IUnknown *
0x180024d90  mov     rcx, [rsp+198h+var_130]; this
0x180024d95  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x180024d9a  mov     ebx, eax
0x180024d9c  mov     [rsp+198h+var_148], eax
0x180024da0  test    eax, eax
0x180024da2  js      loc_180025235
0x180024da8  mov     [rsp+198h+var_110], r15
0x180024db0  mov     [rsp+198h+var_120], r15
0x180024db5  call    cs:__imp_GetTickCount64
0x180024dbb  mov     [rsp+198h+var_F0], rax
0x180024dc3  mov     [rsp+198h+var_E8], r15
0x180024dcb  lea     rax, [rsp+198h+var_F0]
0x180024dd3  mov     [rsp+198h+var_158], rax
0x180024dd8  lea     rax, [rsp+198h+var_130]
0x180024ddd  mov     [rsp+198h+var_160], rax
0x180024de2  lea     rax, [rsp+198h+var_120]
0x180024de7  mov     [rsp+198h+var_168], rax
0x180024dec  lea     rax, [rsp+198h+var_110]
0x180024df4  mov     [rsp+198h+var_170], rax
0x180024df9  lea     rax, [rsp+198h+string]
0x180024dfe  mov     qword ptr [rsp+198h+var_178], rax; int
0x180024e03  lea     r9, [rsp+198h+var_148]
0x180024e08  lea     r8, [rsp+198h+arg_8]
0x180024e10  lea     rdx, [rsp+198h+var_E8]
0x180024e18  lea     rcx, [rsp+198h+var_68]
0x180024e20  call    _lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b____lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b_
0x180024e25  mov     rdx, rax
0x180024e28  lea     rcx, [rsp+198h+var_B8]
0x180024e30  call    wil__scope_exit__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___
0x180024e35  nop
0x180024e36  mov     [rsp+198h+var_140], r15
0x180024e3b  mov     rax, [rsi]
0x180024e3e  mov     rbx, [rax+30h]
0x180024e42  lea     rcx, [rsp+198h+var_140]
0x180024e47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024e4c  lea     rdx, [rsp+198h+var_140]
0x180024e51  mov     rcx, rsi
0x180024e54  mov     rax, rbx
0x180024e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e5c  mov     ebx, eax
0x180024e5e  mov     [rsp+198h+var_148], eax
0x180024e62  test    eax, eax
0x180024e64  js      loc_180025361
0x180024e6a  mov     rcx, [rsp+198h+var_140]
0x180024e6f  mov     rax, [rcx]
0x180024e72  lea     rdx, [rsp+198h+var_110]
0x180024e7a  mov     rax, [rax+30h]
0x180024e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e83  mov     ebx, eax
0x180024e85  mov     [rsp+198h+var_148], eax
0x180024e89  test    eax, eax
0x180024e8b  js      loc_180025495
0x180024e91  lea     r8, [rsp+198h+var_120]; HSTRING *
0x180024e96  mov     rdx, [rsp+198h+var_140]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180024e9b  mov     rcx, [rsp+198h+var_130]; this
0x180024ea0  call    ?GetPluginPFN@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x180024ea5  mov     ebx, eax
0x180024ea7  mov     [rsp+198h+var_148], eax
0x180024eab  test    eax, eax
0x180024ead  js      loc_18002551B
0x180024eb3  mov     [rsp+198h+var_128], r15
0x180024eb8  lea     rax, [rsp+198h+var_128]
0x180024ebd  mov     [rsp+198h+var_D0], rax
0x180024ec5  mov     rsi, r15
0x180024ec8  mov     [rsp+198h+var_C8], r15
0x180024ed0  mov     [rsp+198h+var_C0], r12b
0x180024ed8  mov     r14, [rsp+198h+var_130]
0x180024edd  mov     [rsp+198h+var_144], r15b
0x180024ee2  lea     r8, [rsp+198h+var_144]; bool *
0x180024ee7  mov     rdx, [rsp+198h+var_120]; HSTRING
0x180024eec  mov     rcx, r14; struct Windows::Internal::Security::Authentication::Web::CallerContext *
0x180024eef  call    ?IsPluginMultiUserAware@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@QEAUHSTRING__@@PEA_N@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(Windows::Internal::Security::Authentication::Web::CallerContext *,HSTRING__ * const,bool *)
0x180024ef4  mov     ebx, eax
0x180024ef6  test    eax, eax
0x180024ef8  js      loc_18002519F
0x180024efe  mov     rdx, [r14+10h]; unsigned __int64
0x180024f02  mov     cl, [rsp+198h+var_144]; bool
0x180024f06  call    ?GetAccountManagerInstance@CAccountManagerFactory@TokenBroker@Authentication@Security@Internal@Windows@@SAPEAVIAccountManager@23456@_N_K@Z; Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(bool,unsigned __int64)
0x180024f0b  mov     rsi, rax
0x180024f0e  test    rax, rax
0x180024f11  jz      loc_18002566B
0x180024f17  mov     [rsp+198h+var_148], ebx
0x180024f1b  mov     rdx, [rsp+198h+var_128]
0x180024f20  mov     [rsp+198h+var_128], rsi
0x180024f25  test    rdx, rdx
0x180024f28  jz      short loc_180024F2F
0x180024f2a  call    ??R?$default_delete@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@std@@QEBAXPEAVStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@Z; std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator()(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo *)
0x180024f2f  test    ebx, ebx
0x180024f31  js      loc_1800255A1
0x180024f37  mov     [rsp+198h+Token], r15
0x180024f3f  mov     [rsp+198h+var_100], r15b
0x180024f47  mov     rdx, [rsp+198h+var_130]
0x180024f4c  mov     rdx, [rdx+10h]; unsigned __int64
0x180024f50  lea     rcx, [rsp+198h+Token]; TokenHandle
0x180024f58  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x180024f5d  mov     ebx, eax
0x180024f5f  mov     [rsp+198h+var_148], eax
0x180024f63  test    eax, eax
0x180024f65  js      loc_180025285
0x180024f6b  mov     rax, [rsp+198h+var_140]
0x180024f70  mov     [rsp+198h+var_118], rax
0x180024f78  mov     rax, [rsp+198h+var_128]
0x180024f7d  mov     qword ptr [rsp+198h+var_E0], rax
0x180024f85  mov     rax, [rsp+198h+var_130]
0x180024f8a  mov     [rsp+198h+var_D8], rax
0x180024f92  mov     rcx, [rdi+70h]
0x180024f96  test    rcx, rcx
0x180024f99  jz      loc_18002567D
0x180024f9f  mov     rax, [rcx]
0x180024fa2  lea     rdx, [rsp+198h+var_118]
0x180024faa  mov     [rsp+198h+var_170], rdx
0x180024faf  lea     rdx, [rsp+198h+var_E0]
0x180024fb7  mov     qword ptr [rsp+198h+var_178], rdx; int
0x180024fbc  lea     r9, [rsp+198h+var_120]
0x180024fc1  lea     r8, [rsp+198h+string]
0x180024fc6  lea     rdx, [rsp+198h+var_D8]
0x180024fce  mov     rax, [rax+20h]
0x180024fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fd7  mov     ebx, eax
0x180024fd9  mov     [rsp+198h+var_148], eax
0x180024fdd  test    eax, eax
0x180024fdf  jns     loc_1800250DC
0x180024fe5  mov     rcx, [rsp+198h]; this
0x180024fed  mov     r9d, eax; char *
0x180024ff0  lea     r8, aOnecoreDsSecur_40; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180024ff7  mov     edx, 75h ; 'u'; void *
0x180024ffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025001  nop
0x180025002  cmp     [rsp+198h+var_100], r15b
0x18002500a  jz      short loc_18002501C
0x18002500c  mov     rdx, [rsp+198h+Token]; Token
0x180025014  xor     ecx, ecx; Thread
0x180025016  call    cs:__imp_SetThreadToken
0x18002501c  mov     rcx, [rsp+198h+Token]; hObject
0x180025024  lea     rax, [rcx-1]
0x180025028  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002502c  jbe     loc_180025684
0x180025032  mov     rdx, [rsp+198h+var_128]
0x180025037  mov     [rsp+198h+var_128], r15
0x18002503c  test    rdx, rdx
0x18002503f  jz      short loc_180025047
0x180025041  call    ??R?$default_delete@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@std@@QEBAXPEAVStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@Z; std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator()(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo *)
0x180025046  nop
0x180025047  mov     rcx, [rsp+198h+var_140]
0x18002504c  test    rcx, rcx
0x18002504f  jz      short loc_180025063
0x180025051  mov     [rsp+198h+var_140], r15
0x180025056  mov     rax, [rcx]
0x180025059  mov     rax, [rax+10h]
0x18002505d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025062  nop
0x180025063  lea     rcx, [rsp+198h+var_B8]
0x18002506b  call    wil__details__lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b______lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___
0x180025070  nop
0x180025071  mov     rcx, [rsp+198h+var_120]; string
0x180025076  test    rcx, rcx
0x180025079  jz      short loc_180025082
0x18002507b  call    cs:__imp_WindowsDeleteString
0x180025081  nop
0x180025082  mov     rcx, [rsp+198h+var_110]; string
0x18002508a  test    rcx, rcx
0x18002508d  jz      short loc_180025096
0x18002508f  call    cs:__imp_WindowsDeleteString
0x180025095  nop
0x180025096  mov     rcx, [rsp+198h+var_130]; this
0x18002509b  test    rcx, rcx
0x18002509e  jz      short loc_1800250A9
0x1800250a0  mov     edx, r12d; unsigned int
0x1800250a3  call    ??_GCallerContext@Web@Authentication@Security@Internal@Windows@@QEAAPEAXI@Z; Windows::Internal::Security::Authentication::Web::CallerContext::`scalar deleting destructor'(uint)
0x1800250a8  nop
0x1800250a9  mov     rcx, [rsp+198h+string]; string
0x1800250ae  test    rcx, rcx
0x1800250b1  jz      short loc_1800250BA
0x1800250b3  call    cs:__imp_WindowsDeleteString
0x1800250b9  nop
0x1800250ba  mov     rcx, rdi
0x1800250bd  call    ??1?$function@$$A6AXAEBU_WNF_UMGR_USER_CHANGED_DATA@@@Z@wistd@@QEAA@XZ; wistd::function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>::~function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>(void)
0x1800250c2  mov     eax, ebx
0x1800250c4  mov     rbx, [rsp+198h+arg_0]
0x1800250cc  add     rsp, 170h
0x1800250d3  pop     r15
0x1800250d5  pop     r14
0x1800250d7  pop     r12
0x1800250d9  pop     rdi
0x1800250da  pop     rsi
0x1800250db  retn
0x1800250dc  cmp     [rsp+198h+var_100], r15b
0x1800250e4  jz      short loc_1800250F6
0x1800250e6  mov     rdx, [rsp+198h+Token]; Token
0x1800250ee  xor     ecx, ecx; Thread
0x1800250f0  call    cs:__imp_SetThreadToken
0x1800250f6  lea     rcx, [rsp+198h+Token]; this
0x1800250fe  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x180025103  nop
0x180025104  mov     rdx, [rsp+198h+var_128]
0x180025109  mov     [rsp+198h+var_128], r15
0x18002510e  test    rdx, rdx
0x180025111  jz      short loc_180025119
0x180025113  call    ??R?$default_delete@VStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@std@@QEBAXPEAVStoredObjectInfo@TokenBroker@Authentication@Security@Internal@Windows@@@Z; std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator()(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo *)
0x180025118  nop
0x180025119  mov     rcx, [rsp+198h+var_140]
0x18002511e  test    rcx, rcx
0x180025121  jz      short loc_180025135
0x180025123  mov     [rsp+198h+var_140], r15
0x180025128  mov     rax, [rcx]
0x18002512b  mov     rax, [rax+10h]
0x18002512f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025134  nop
0x180025135  lea     rcx, [rsp+198h+var_B8]
0x18002513d  call    wil__details__lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b______lambda_call__lambda_acfecdc67cb2cfbadfc6b7a5aa2bc14b___
0x180025142  nop
0x180025143  mov     rcx, [rsp+198h+var_120]; string
0x180025148  test    rcx, rcx
0x18002514b  jz      short loc_180025154
0x18002514d  call    cs:__imp_WindowsDeleteString
0x180025153  nop
0x180025154  mov     rcx, [rsp+198h+var_110]; string
0x18002515c  test    rcx, rcx
0x18002515f  jz      short loc_180025168
0x180025161  call    cs:__imp_WindowsDeleteString
0x180025167  nop
0x180025168  mov     rcx, [rsp+198h+var_130]; this
0x18002516d  test    rcx, rcx
0x180025170  jz      short loc_18002517B
0x180025172  mov     edx, r12d; unsigned int
0x180025175  call    ??_GCallerContext@Web@Authentication@Security@Internal@Windows@@QEAAPEAXI@Z; Windows::Internal::Security::Authentication::Web::CallerContext::`scalar deleting destructor'(uint)
0x18002517a  nop
0x18002517b  mov     rcx, [rsp+198h+string]; string
0x180025180  test    rcx, rcx
0x180025183  jz      short loc_18002518C
0x180025185  call    cs:__imp_WindowsDeleteString
0x18002518b  nop
0x18002518c  mov     ebx, [rsp+198h+var_148]
0x180025190  mov     rcx, rdi
0x180025193  call    ??1?$function@$$A6AXAEBU_WNF_UMGR_USER_CHANGED_DATA@@@Z@wistd@@QEAA@XZ; wistd::function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>::~function<void (_WNF_UMGR_USER_CHANGED_DATA const &)>(void)
0x180025198  mov     eax, ebx
0x18002519a  jmp     loc_1800250C4
0x18002519f  mov     r9d, eax; char *
0x1800251a2  mov     edx, 20h ; ' '; void *
  ... truncated ...
```
