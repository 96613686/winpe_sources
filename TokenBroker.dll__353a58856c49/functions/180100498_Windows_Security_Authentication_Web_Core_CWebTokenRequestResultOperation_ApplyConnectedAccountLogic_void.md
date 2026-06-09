# Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation::ApplyConnectedAccountLogic(void)

- ea: `0x180100498`
- end: `0x180100ce9`
- name: `?ApplyConnectedAccountLogic@CWebTokenRequestResultOperation@Core@Web@Authentication@Security@Windows@@AEAAJXZ`
- size: `2129`
- prototype: `__int64 __fastcall(Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180100fb8`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180024544`
- `0x180026728`
- `0x18003100c`
- `0x18004e850`
- `0x18004fdbc`
- `0x180063ff0`
- `0x18007ef3c`
- `0x18009942c`
- `0x18009a4c4`
- `0x18009a50c`
- `0x18009adec`
- `0x1800f3534`
- `0x1800f3584`
- `0x1800fe818`
- `0x1800fe9e4`
- `0x180100498`
- `0x1801026d0`
- `0x1801031fc`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180100910`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180100950`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801009a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801009c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801009d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180100910`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180100950`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801009a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801009c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801009d4`

## string_xrefs

- `0x1801008f1`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x180100935`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x180100988`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x18010055e`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`
- `0x18010058f`: `onecore\ds\security\tokenbroker\api\lib\webtokenrequestresultoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation::ApplyConnectedAccountLogic(
        Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation *this)
{
  unsigned int v2; // r14d
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned __int64 *v8; // r8
  int UserContextFromProvider; // eax
  int v10; // eax
  Windows::Internal::Security::Authentication::TokenBroker *v11; // rdi
  __int64 (__fastcall *v12)(Windows::Internal::Security::Authentication::TokenBroker *, __int64, __int64 *); // rbx
  int v13; // eax
  int v14; // ecx
  int v15; // r9d
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v30; // eax
  struct Windows::Security::Credentials::IWebAccountProvider *v31; // r12
  __int64 (__fastcall ***v32)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *); // rbx
  int PluginPFN; // eax
  HSTRING v34; // rcx
  int v35; // eax
  HSTRING v36; // rdi
  struct Windows::Security::Credentials::IWebAccountProvider *v37; // r8
  HSTRING v38; // rbx
  int v39; // eax
  int v40; // eax
  __int64 v41; // rdx
  __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, __int64 *); // rbx
  int v49; // eax
  int v50; // eax
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequest *v51; // rdx
  unsigned __int64 v52; // r9
  __int64 v53; // rdx
  int v54; // eax
  int v55; // eax
  int v56; // [rsp+20h] [rbp-89h]
  __int64 v57; // [rsp+40h] [rbp-69h] BYREF
  __int64 v58; // [rsp+48h] [rbp-61h] BYREF
  __int64 v59; // [rsp+50h] [rbp-59h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v60; // [rsp+58h] [rbp-51h] BYREF
  HSTRING string; // [rsp+60h] [rbp-49h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v62; // [rsp+68h] [rbp-41h] BYREF
  HSTRING v63; // [rsp+70h] [rbp-39h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v64; // [rsp+78h] [rbp-31h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v65; // [rsp+80h] [rbp-29h] BYREF
  __int64 v66; // [rsp+88h] [rbp-21h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v67; // [rsp+90h] [rbp-19h] BYREF
  __int64 v68; // [rsp+98h] [rbp-11h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v70; // [rsp+A8h] [rbp-1h] BYREF
  int v71[2]; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  __int64 v73; // [rsp+110h] [rbp+67h] BYREF
  int v74; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v75; // [rsp+120h] [rbp+77h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v76; // [rsp+128h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &dword_180155E14,
      0,
      0);
  v2 = 0;
  v64 = 0;
  v3 = *((_QWORD *)this + 2);
  v4 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v3 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  v5 = v4(v3, &v64);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1239;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)v5,
      v56);
    goto LABEL_97;
  }
  if ( !Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsConnectedAccountProvider(v64) )
  {
LABEL_6:
    v6 = v2;
LABEL_97:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    return v6;
  }
  if ( (unsigned int)dword_180175000 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      byte_180155E6D,
      0,
      0);
  v5 = Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation::InitializeTokenBrokerInternal(this);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 1251;
    goto LABEL_11;
  }
  v75 = 0;
  v70 = 0;
  UserContextFromProvider = Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(
                              v64,
                              (struct Windows::Security::Credentials::IWebAccountProvider *)&v70,
                              v8);
  if ( UserContextFromProvider < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)UserContextFromProvider,
      v56);
  v76 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  v10 = Windows::Internal::Security::Authentication::TokenBroker::ConvertAndSetProxyT<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5>(
          *((__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 11),
          &v76);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EE,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)v10,
      v56);
LABEL_96:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    goto LABEL_97;
  }
  v57 = 0;
  v11 = v76;
  v12 = *(__int64 (__fastcall **)(Windows::Internal::Security::Authentication::TokenBroker *, __int64, __int64 *))(*(_QWORD *)v76 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  v13 = v12(v11, v70, &v57);
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F1,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)v13,
      v56);
LABEL_95:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    goto LABEL_96;
  }
  v58 = 0;
  v14 = BlockOnCompletionAndGetResults<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(
          v57,
          (__int64)&v58);
  if ( v14 >= 0 )
  {
    v16 = v58;
    v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v58 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    v14 = v17(v16, &v75);
  }
  if ( !v75 )
  {
    if ( (unsigned int)dword_180175000 > 5 )
    {
      LODWORD(v73) = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180175000,
        (unsigned int)&word_180155ECE,
        0,
        v15,
        (__int64)&v73);
    }
    v63 = 0;
    string = (HSTRING)v64;
    v62 = 0;
    v60 = 0;
    v59 = 0;
    LODWORD(v73) = 4;
    v67 = 0;
    v18 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,std::nullptr_t,enum Windows::Security::Authentication::Web::Core::WebTokenRequestStatus,std::nullptr_t,std::nullptr_t,std::nullptr_t,Windows::Security::Credentials::IWebAccountProvider *>(
            &v63,
            &v67,
            &v73,
            &v59);
    v6 = v18;
    if ( v18 < 0 )
    {
      v19 = 1301;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v18,
        (int)&v60);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
LABEL_94:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
      goto LABEL_95;
    }
    v18 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::CWebTokenRequestResult>::As<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v63,
            (__int64)this + 8);
    v6 = v18;
    if ( v18 < 0 )
    {
      v19 = 1303;
      goto LABEL_25;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
    goto LABEL_6;
  }
  v74 = 0;
  v20 = *((_QWORD *)this + 3);
  if ( !v20 )
    goto LABEL_77;
  v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 56LL))(v20, &v74);
  v6 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x523,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)v21,
      v56);
    goto LABEL_94;
  }
  if ( !v74 )
  {
LABEL_77:
    v73 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    v44 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(
            v43,
            &v73);
    v6 = v44;
    if ( v44 >= 0 )
    {
      v44 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v73 + 104LL))(v73, v75);
      v6 = v44;
      if ( v44 >= 0 )
      {
        v46 = v73;
        v73 = *((_QWORD *)this + 3);
        *((_QWORD *)this + 3) = v46;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
        goto LABEL_83;
      }
      v45 = 1326;
    }
    else
    {
      v45 = 1325;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)(unsigned int)v44,
      v56);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
    goto LABEL_94;
  }
  if ( v74 == 1 )
  {
    v59 = 0;
    v22 = *((_QWORD *)this + 3);
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v22 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
    v24 = v23(v22, 0, &v59);
    v6 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x535,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v24,
        v56);
LABEL_37:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
      goto LABEL_94;
    }
    v60 = 0;
    v25 = v59;
    v26 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v59 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    v27 = v26(v25, &v60);
    v6 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x538,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v27,
        v56);
LABEL_40:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
      goto LABEL_37;
    }
    v62 = 0;
    v28 = v75;
    v29 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v75 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    v30 = v29(v28, &v62);
    v6 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53B,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v30,
        v56);
LABEL_43:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      goto LABEL_40;
    }
    v31 = v62;
    if ( !v62
      || (v32 = (__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v60) == 0 )
    {
      v2 = -2147024809;
      goto LABEL_72;
    }
    LOBYTE(v73) = 0;
    if ( v62 != v60 )
    {
      string = 0;
      v63 = 0;
      PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(
                    (__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v62,
                    &string);
      v2 = PluginPFN;
      if ( PluginPFN < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14D,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
          (const char *)(unsigned int)PluginPFN,
          v56);
        goto LABEL_49;
      }
      v35 = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(v32, &v63);
      v2 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
          (const char *)(unsigned int)v35,
          v56);
        if ( v63 )
          WindowsDeleteString(v63);
LABEL_49:
        v34 = string;
        if ( !string )
        {
LABEL_72:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x545,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
            (const char *)v2,
            v56);
          goto LABEL_73;
        }
LABEL_50:
        WindowsDeleteString(v34);
        goto LABEL_72;
      }
      v36 = v63;
      v37 = (struct Windows::Security::Credentials::IWebAccountProvider *)v32;
      v38 = string;
      v39 = Windows::Internal::Security::Authentication::TokenBroker::PluginManager::CompareProviders(
              v31,
              string,
              v37,
              v63,
              (unsigned __int8 *)&v73);
      v2 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14F,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
          (const char *)(unsigned int)v39,
          v56);
        if ( v36 )
          WindowsDeleteString(v36);
        if ( !v38 )
          goto LABEL_72;
        v34 = v38;
        goto LABEL_50;
      }
      v2 = 0;
      if ( v36 )
        WindowsDeleteString(v36);
      if ( v38 )
        WindowsDeleteString(v38);
      if ( !(_BYTE)v73 )
      {
        string = 0;
        v67 = v64;
        v63 = 0;
        *(_QWORD *)v71 = 0;
        v68 = 0;
        LODWORD(v73) = 2;
        v69 = 0;
        v40 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,std::nullptr_t,enum Windows::Security::Authentication::Web::Core::WebTokenRequestStatus,std::nullptr_t,std::nullptr_t,std::nullptr_t,Windows::Security::Credentials::IWebAccountProvider *>(
                &string,
                &v69,
                &v73,
                &v68);
        v6 = v40;
        if ( v40 >= 0 )
        {
          v40 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::CWebTokenRequestResult>::As<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
                  (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&string,
                  (__int64)this + 8);
          v6 = v40;
          if ( v40 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
LABEL_73:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
            goto LABEL_29;
          }
          v41 = 1363;
        }
        else
        {
          v41 = 1361;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v41,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
          (const char *)(unsigned int)v40,
          (int)v71);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        goto LABEL_43;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
LABEL_83:
    v66 = 0;
    v47 = v75;
    v48 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v75 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    v49 = v48(v47, &v66);
    v6 = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x568,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
        (const char *)(unsigned int)v49,
        v56);
LABEL_93:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      goto LABEL_94;
    }
    v65 = 0;
    v69 = v66;
    v68 = *((_QWORD *)this + 2);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
    v50 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::Core::CWebTokenRequest,Windows::Security::Authentication::Web::Core::CWebTokenRequest,Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Security::Credentials::IWebAccountProvider *>(
            &v65,
            &v68,
            &v69);
    v6 = v50;
    if ( v50 >= 0 )
    {
      v54 = Windows::Internal::Security::Authentication::TokenBroker::SetDefaultAccountRequest(v65, v51);
      v6 = v54;
      if ( v54 >= 0 )
      {
        v55 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::CWebTokenRequest>::As<Windows::Security::Authentication::Web::Core::IWebTokenRequest>(
                (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v65,
                (__int64)this + 16);
        v6 = v55;
        if ( v55 >= 0 )
        {
LABEL_92:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
          goto LABEL_93;
        }
        v52 = (unsigned int)v55;
        v53 = 1398;
      }
      else
      {
        v52 = (unsigned int)v54;
        v53 = 1395;
      }
    }
    else
    {
      v52 = (unsigned int)v50;
      v53 = 1388;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v53,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtokenrequestresultoperation.cpp",
      (const char *)v52,
      v56);
    goto LABEL_92;
  }
  if ( (unsigned int)dword_180175000 > 2 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      qword_180155C90,
      0,
      0);
  TryOriginateError(-2147024809, 0x3F5u);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180100498  push    rbp
0x18010049a  push    rbx
0x18010049b  push    rsi
0x18010049c  push    rdi
0x18010049d  push    r12
0x18010049f  push    r13
0x1801004a1  push    r14
0x1801004a3  push    r15
0x1801004a5  lea     rbp, [rsp-1Fh]
0x1801004aa  sub     rsp, 0C8h
0x1801004b1  mov     r15, rcx
0x1801004b4  mov     eax, cs:dword_180175000
0x1801004ba  lea     r12, dword_180175000
0x1801004c1  cmp     eax, 4
0x1801004c4  jbe     short loc_1801004DB
0x1801004c6  xor     r9d, r9d
0x1801004c9  xor     r8d, r8d
0x1801004cc  lea     rdx, dword_180155E14
0x1801004d3  mov     rcx, r12
0x1801004d6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801004db  xor     r14d, r14d
0x1801004de  mov     [rbp+57h+var_88], r14
0x1801004e2  lea     r13, [r15+10h]
0x1801004e6  mov     rdi, [r13+0]
0x1801004ea  mov     rax, [rdi]
0x1801004ed  mov     rbx, [rax+30h]
0x1801004f1  lea     rcx, [rbp+57h+var_88]
0x1801004f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801004fa  lea     rdx, [rbp+57h+var_88]
0x1801004fe  mov     rcx, rdi
0x180100501  mov     rax, rbx
0x180100504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100509  mov     ebx, eax
0x18010050b  test    eax, eax
0x18010050d  jns     short loc_180100516
0x18010050f  mov     edx, 4D7h
0x180100514  jmp     short loc_18010055E
0x180100516  mov     rcx, [rbp+57h+var_88]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18010051a  call    ?IsConnectedAccountProvider@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SA_NPEAUIWebAccountProvider@Credentials@46@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::IsConnectedAccountProvider(Windows::Security::Credentials::IWebAccountProvider *)
0x18010051f  test    al, al
0x180100521  jnz     short loc_18010052B
0x180100523  mov     ebx, r14d
0x180100526  jmp     loc_180100CCA
0x18010052b  mov     eax, cs:dword_180175000
0x180100531  cmp     eax, 5
0x180100534  jbe     short loc_18010054B
0x180100536  xor     r9d, r9d
0x180100539  xor     r8d, r8d
0x18010053c  lea     rdx, byte_180155E6D
0x180100543  mov     rcx, r12
0x180100546  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010054b  mov     rcx, r15; this
0x18010054e  call    ?InitializeTokenBrokerInternal@CWebTokenRequestResultOperation@Core@Web@Authentication@Security@Windows@@AEAAJXZ; Windows::Security::Authentication::Web::Core::CWebTokenRequestResultOperation::InitializeTokenBrokerInternal(void)
0x180100553  mov     ebx, eax
0x180100555  test    eax, eax
0x180100557  jns     short loc_180100576
0x180100559  mov     edx, 4E3h; void *
0x18010055e  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180100565  mov     r9d, eax; char *
0x180100568  mov     rcx, [rbp+5Fh]; this
0x18010056c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100571  jmp     loc_180100CCA
0x180100576  mov     [rbp+57h+arg_10], r14
0x18010057a  mov     [rbp+57h+var_58], r14
0x18010057e  lea     rdx, [rbp+57h+var_58]; struct Windows::Security::Credentials::IWebAccountProvider *
0x180100582  mov     rcx, [rbp+57h+var_88]; this
0x180100586  call    ?GetUserContextFromProvider@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@35@AEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(Windows::Security::Credentials::IWebAccountProvider *,unsigned __int64 &)
0x18010058b  mov     rcx, [rbp+5Fh]; this
0x18010058f  lea     rsi, aOnecoreDsSecur_20; "onecore\\ds\\security\\tokenbroker\\api"...
0x180100596  test    eax, eax
0x180100598  jns     short loc_1801005AA
0x18010059a  mov     r9d, eax; char *
0x18010059d  mov     r8, rsi; unsigned int
0x1801005a0  mov     edx, 4EBh; void *
0x1801005a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801005aa  mov     [rbp+57h+arg_18], r14
0x1801005ae  lea     rcx, [rbp+57h+arg_18]
0x1801005b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801005b7  lea     rdx, [rbp+57h+arg_18]
0x1801005bb  mov     rcx, [r15+58h]
0x1801005bf  call    ??$ConvertAndSetProxyT@UITokenBrokerInternalStatics5@Web@Authentication@Security@Internal@Windows@@@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUITokenBrokerInternalStatics@Web@1234@PEAPEAUITokenBrokerInternalStatics5@61234@@Z; Windows::Internal::Security::Authentication::TokenBroker::ConvertAndSetProxyT<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5>(Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics *,Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics5 * *)
0x1801005c4  mov     ebx, eax
0x1801005c6  test    eax, eax
0x1801005c8  jns     short loc_1801005E3
0x1801005ca  mov     rcx, [rbp+5Fh]; this
0x1801005ce  mov     r9d, eax; char *
0x1801005d1  mov     r8, rsi; unsigned int
0x1801005d4  mov     edx, 4EEh; void *
0x1801005d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801005de  jmp     loc_180100CB6
0x1801005e3  mov     [rbp+57h+var_C0], r14
0x1801005e7  mov     rdi, [rbp+57h+arg_18]
0x1801005eb  mov     rax, [rdi]
0x1801005ee  mov     rbx, [rax+38h]
0x1801005f2  lea     rcx, [rbp+57h+var_C0]
0x1801005f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801005fb  lea     r8, [rbp+57h+var_C0]
0x1801005ff  mov     rdx, [rbp+57h+var_58]
0x180100603  mov     rcx, rdi
0x180100606  mov     rax, rbx
0x180100609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010060e  mov     ebx, eax
0x180100610  test    eax, eax
0x180100612  jns     short loc_18010062D
0x180100614  mov     rcx, [rbp+5Fh]; this
0x180100618  mov     r9d, eax; char *
0x18010061b  mov     r8, rsi; unsigned int
0x18010061e  mov     edx, 4F1h; void *
0x180100623  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100628  jmp     loc_180100CAC
0x18010062d  mov     [rbp+57h+var_B8], r14
0x180100631  lea     rdx, [rbp+57h+var_B8]
0x180100635  mov     rcx, [rbp+57h+var_C0]
0x180100639  call    ??$BlockOnCompletionAndGetResults@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@UIGetDefaultSignInAccountResult@23456@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>>,tagCOWAIT_FLAGS,void *)
0x18010063e  mov     ecx, eax
0x180100640  test    eax, eax
0x180100642  js      short loc_180100669
0x180100644  mov     rdi, [rbp+57h+var_B8]
0x180100648  mov     rax, [rdi]
0x18010064b  mov     rbx, [rax+30h]
0x18010064f  lea     rcx, [rbp+57h+arg_10]
0x180100653  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100658  lea     rdx, [rbp+57h+arg_10]
0x18010065c  mov     rcx, rdi
0x18010065f  mov     rax, rbx
0x180100662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100667  mov     ecx, eax
0x180100669  cmp     [rbp+57h+arg_10], r14
0x18010066d  jnz     loc_180100768
0x180100673  mov     eax, cs:dword_180175000
0x180100679  cmp     eax, 5
0x18010067c  jbe     short loc_18010069C
0x18010067e  mov     dword ptr [rbp+57h+arg_0], ecx
0x180100681  lea     rax, [rbp+57h+arg_0]
0x180100685  mov     [rsp+100h+var_E0], rax
0x18010068a  xor     r8d, r8d
0x18010068d  lea     rdx, word_180155ECE
0x180100694  mov     rcx, r12
0x180100697  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18010069c  mov     [rbp+57h+var_90], r14
0x1801006a0  mov     rax, [rbp+57h+var_88]
0x1801006a4  mov     [rbp+57h+string], rax
0x1801006a8  mov     [rbp+57h+var_98], r14
0x1801006ac  mov     [rbp+57h+var_A8], r14
0x1801006b0  mov     [rbp+57h+var_B0], r14
0x1801006b4  mov     dword ptr [rbp+57h+arg_0], 4
0x1801006bb  mov     [rbp+57h+var_70], r14
0x1801006bf  lea     rax, [rbp+57h+string]
0x1801006c3  mov     [rsp+100h+var_D0], rax
0x1801006c8  lea     rax, [rbp+57h+var_98]
0x1801006cc  mov     [rsp+100h+var_D8], rax
0x1801006d1  lea     rax, [rbp+57h+var_A8]
0x1801006d5  mov     [rsp+100h+var_E0], rax; int
0x1801006da  lea     r9, [rbp+57h+var_B0]
0x1801006de  lea     r8, [rbp+57h+arg_0]
0x1801006e2  lea     rdx, [rbp+57h+var_70]
0x1801006e6  lea     rcx, [rbp+57h+var_90]
0x1801006ea  call    ??$MakeAndInitialize@VCWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@V123456@$$TW4WebTokenRequestStatus@23456@$$T$$T$$TPEAUIWebAccountProvider@Credentials@56@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@012@$$QEA$$T$$QEAW4WebTokenRequestStatus@Core@Web@Authentication@Security@Windows@@111$$QEAPEAUIWebAccountProvider@Credentials@89@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,Windows::Security::Authentication::Web::Core::CWebTokenRequestResult,std::nullptr_t,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus,std::nullptr_t,std::nullptr_t,std::nullptr_t,Windows::Security::Credentials::IWebAccountProvider *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::CWebTokenRequestResult>>,Windows::Security::Authentication::Web::Core::$$T$$QEAW4WebTokenRequestStatus &&,Windows::Security::Authentication::Web::Core::$$T$$QEAW4WebTokenRequestStatus &&,Windows::Security::Authentication::Web::Core::$$T$$QEAW4WebTokenRequestStatus &&,Windows::Security::Authentication::Web::Core::$$T$$QEAW4WebTokenRequestStatus &&,Windows::Security::Credentials::IWebAccountProvider * &&)
0x1801006ef  mov     ebx, eax
0x1801006f1  test    eax, eax
0x1801006f3  jns     short loc_180100718
0x1801006f5  mov     edx, 515h; void *
0x1801006fa  mov     r8, rsi; unsigned int
0x1801006fd  mov     r9d, eax; char *
0x180100700  mov     rcx, [rbp+5Fh]; this
0x180100704  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100709  nop
0x18010070a  lea     rcx, [rbp+57h+var_90]
0x18010070e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100713  jmp     loc_180100CA2
0x180100718  lea     rdx, [r15+8]
0x18010071c  lea     rcx, [rbp+57h+var_90]
0x180100720  call    ??$As@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@?$ComPtr@VCWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::CWebTokenRequestResult>::As<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>>)
0x180100725  mov     ebx, eax
0x180100727  test    eax, eax
0x180100729  jns     short loc_180100732
0x18010072b  mov     edx, 517h
0x180100730  jmp     short loc_1801006FA
0x180100732  lea     rcx, [rbp+57h+var_90]
0x180100736  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010073b  nop
0x18010073c  lea     rcx, [rbp+57h+var_B8]
0x180100740  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100745  nop
0x180100746  lea     rcx, [rbp+57h+var_C0]
0x18010074a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010074f  nop
0x180100750  lea     rcx, [rbp+57h+arg_18]
0x180100754  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100759  nop
0x18010075a  lea     rcx, [rbp+57h+arg_10]
0x18010075e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100763  jmp     loc_180100523
0x180100768  mov     [rbp+57h+arg_8], r14d
0x18010076c  mov     rcx, [r15+18h]
0x180100770  test    rcx, rcx
0x180100773  jz      loc_180100B51
0x180100779  mov     rax, [rcx]
0x18010077c  lea     rdx, [rbp+57h+arg_8]
0x180100780  mov     rax, [rax+38h]
0x180100784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100789  mov     ebx, eax
0x18010078b  test    eax, eax
0x18010078d  jns     short loc_1801007A8
0x18010078f  mov     rcx, [rbp+5Fh]; this
0x180100793  mov     r9d, eax; char *
0x180100796  mov     r8, rsi; unsigned int
0x180100799  mov     edx, 523h; void *
0x18010079e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801007a3  jmp     loc_180100CA2
0x1801007a8  mov     eax, [rbp+57h+arg_8]
0x1801007ab  test    eax, eax
0x1801007ad  jz      loc_180100B51
0x1801007b3  cmp     eax, 1
0x1801007b6  jnz     loc_180100AE4
0x1801007bc  mov     [rbp+57h+var_B0], r14
0x1801007c0  mov     rdi, [r15+18h]
0x1801007c4  mov     rax, [rdi]
0x1801007c7  mov     rbx, [rax+30h]
0x1801007cb  lea     rcx, [rbp+57h+var_B0]
0x1801007cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801007d4  lea     r8, [rbp+57h+var_B0]
0x1801007d8  xor     edx, edx
0x1801007da  mov     rcx, rdi
0x1801007dd  mov     rax, rbx
0x1801007e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801007e5  mov     ebx, eax
0x1801007e7  test    eax, eax
0x1801007e9  jns     short loc_18010080E
0x1801007eb  mov     rcx, [rbp+5Fh]; this
0x1801007ef  mov     r9d, eax; char *
0x1801007f2  mov     r8, rsi; unsigned int
0x1801007f5  mov     edx, 535h; void *
0x1801007fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801007ff  nop
0x180100800  lea     rcx, [rbp+57h+var_B0]
0x180100804  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100809  jmp     loc_180100CA2
0x18010080e  mov     [rbp+57h+var_A8], r14
0x180100812  mov     rdi, [rbp+57h+var_B0]
0x180100816  mov     rax, [rdi]
0x180100819  mov     rbx, [rax+30h]
0x18010081d  lea     rcx, [rbp+57h+var_A8]
0x180100821  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100826  lea     rdx, [rbp+57h+var_A8]
0x18010082a  mov     rcx, rdi
0x18010082d  mov     rax, rbx
0x180100830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100835  mov     ebx, eax
0x180100837  test    eax, eax
0x180100839  jns     short loc_18010085B
0x18010083b  mov     rcx, [rbp+5Fh]; this
0x18010083f  mov     r9d, eax; char *
0x180100842  mov     r8, rsi; unsigned int
0x180100845  mov     edx, 538h; void *
0x18010084a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010084f  nop
0x180100850  lea     rcx, [rbp+57h+var_A8]
0x180100854  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100859  jmp     short loc_180100800
0x18010085b  mov     [rbp+57h+var_98], r14
0x18010085f  mov     rdi, [rbp+57h+arg_10]
0x180100863  mov     rax, [rdi]
0x180100866  mov     rbx, [rax+30h]
0x18010086a  lea     rcx, [rbp+57h+var_98]
0x18010086e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180100873  lea     rdx, [rbp+57h+var_98]
0x180100877  mov     rcx, rdi
0x18010087a  mov     rax, rbx
0x18010087d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100882  mov     ebx, eax
0x180100884  test    eax, eax
0x180100886  jns     short loc_1801008A8
0x180100888  mov     rcx, [rbp+5Fh]; this
0x18010088c  mov     r9d, eax; char *
0x18010088f  mov     r8, rsi; unsigned int
0x180100892  mov     edx, 53Bh; void *
0x180100897  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010089c  nop
0x18010089d  lea     rcx, [rbp+57h+var_98]
0x1801008a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801008a6  jmp     short loc_180100850
0x1801008a8  mov     r12, [rbp+57h+var_98]
0x1801008ac  test    r12, r12
0x1801008af  jz      loc_180100AA7
0x1801008b5  mov     rbx, [rbp+57h+var_A8]
0x1801008b9  test    rbx, rbx
0x1801008bc  jz      loc_180100AA7
0x1801008c2  mov     byte ptr [rbp+57h+arg_0], r14b
0x1801008c6  cmp     r12, rbx
0x1801008c9  jz      loc_180100A85
0x1801008cf  mov     [rbp+57h+string], r14
0x1801008d3  mov     [rbp+57h+var_90], r14
0x1801008d7  lea     rdx, [rbp+57h+string]; HSTRING *
0x1801008db  mov     rcx, r12; struct Windows::Security::Credentials::IWebAccountProvider *
0x1801008de  call    ?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x1801008e3  mov     r14d, eax
0x1801008e6  test    eax, eax
0x1801008e8  jns     short loc_18010091B
0x1801008ea  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
