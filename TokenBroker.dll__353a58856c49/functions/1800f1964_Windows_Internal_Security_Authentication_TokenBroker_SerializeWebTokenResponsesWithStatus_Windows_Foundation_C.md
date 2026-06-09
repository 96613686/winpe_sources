# Windows::Internal::Security::Authentication::TokenBroker::SerializeWebTokenResponsesWithStatus(Windows::Foundation::Collections::IVectorView<Windows::Security::Authentication::Web::Core::WebTokenResponse *> *,Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Internal::Security::Authentication::TokenBroker::AccountLookupContext,HSTRING__ *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus,Windows::Foundation::DateTime,Windows::Security::Authentication::Web::Core::IWebProviderError *,Windows::Storage::Streams::IBuffer * *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *)

- ea: `0x1800f1964`
- end: `0x1800f212d`
- name: `?SerializeWebTokenResponsesWithStatus@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAU?$IVectorView@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@Collections@Foundation@5@PEAUIWebTokenRequest@Core@Web@235@W4AccountLookupContext@12345@PEAUHSTRING__@@W4WebTokenRequestStatus@Core@Web@235@UDateTime@85@PEAUIWebProviderError@Core@Web@235@PEAPEAUIBuffer@Streams@Storage@5@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@785@@Z`
- size: `1993`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x1800ee430`

## callees

- `0x1800051c4`
- `0x180005288`
- `0x180007350`
- `0x18000bd40`
- `0x180010a70`
- `0x1800185b4`
- `0x180018e28`
- `0x18001a0a4`
- `0x180024544`
- `0x180024ae4`
- `0x18002594c`
- `0x180025bd8`
- `0x180027c4c`
- `0x180045820`
- `0x180045a04`
- `0x18004c014`
- `0x18004c064`
- `0x18004e490`
- `0x18004e4dc`
- `0x18004e800`
- `0x18004e850`
- `0x18004f788`
- `0x180056fd8`
- `0x180057ad0`
- `0x18008e690`
- `0x1800f1964`
- `0x180109c80`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1a2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1a2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f1d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1daf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1daf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f1e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f1bfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800f1bfc`

## string_xrefs

- `0x1800f1aae`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f1ae3`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f1e0a`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f1e28`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f1e84`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f1ea7`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f1ec1`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f1f07`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f1f50`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f2070`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f20ea`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::SerializeWebTokenResponsesWithStatus(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        __int64 a3,
        HSTRING a4,
        unsigned int a5,
        __int64 a6,
        __int64 (__fastcall ***a7)(_QWORD, GUID *, __int64 *),
        _QWORD *a8,
        __int64 a9)
{
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // r13
  _QWORD *v13; // rsi
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  BOOL v22; // esi
  __int64 (__fastcall *v23)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rdx
  int v27; // r9d
  unsigned int v28; // r14d
  unsigned int v29; // esi
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rbx
  int v31; // eax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v36)(_QWORD, GUID *, __int64); // rbx
  int v37; // eax
  int AccountWithContext; // eax
  int v39; // eax
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64 *); // rbx
  int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // rdx
  int v48; // eax
  int v49; // eax
  __int64 v50; // rdx
  __int64 *v51; // rax
  HSTRING *v52; // rax
  HSTRING *v53; // rax
  HSTRING *v54; // rax
  struct Windows::Storage::Streams::IBuffer **v55; // r8
  int v56; // eax
  __int64 v57; // rax
  int *v59; // [rsp+20h] [rbp-E0h]
  bool v60[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v61)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v62; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v63)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v64; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v65; // [rsp+68h] [rbp-98h] BYREF
  int v66; // [rsp+6Ch] [rbp-94h] BYREF
  int v67[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v68; // [rsp+78h] [rbp-88h] BYREF
  __int64 v69; // [rsp+80h] [rbp-80h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  int v71; // [rsp+90h] [rbp-70h] BYREF
  __int64 v72; // [rsp+98h] [rbp-68h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-58h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v75; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING StringRawBuffer; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v77; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v78[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v79; // [rsp+E8h] [rbp-18h]
  char v80; // [rsp+ECh] [rbp-14h]
  PCWSTR v81; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v82; // [rsp+F8h] [rbp-8h]
  _QWORD *v83; // [rsp+100h] [rbp+0h]
  HSTRING v84[4]; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v12 = a7;
  v13 = a8;
  v83 = a8;
  v82 = a9;
  v65 = 0;
  v72 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  v15 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(
          v14,
          &v72);
  v16 = v15;
  if ( v15 < 0 )
  {
    v17 = (unsigned int)v15;
    v18 = 762;
LABEL_81:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)v17,
      (int)v59);
    goto LABEL_82;
  }
  if ( !a1 || !a2 || !v13 || !a4 )
  {
    v16 = -2147024809;
    v17 = 2147942487LL;
    v18 = 769;
    goto LABEL_81;
  }
  if ( (unsigned int)dword_180175000 > 5 )
  {
    v60[0] = v12 != 0;
    v71 = a5;
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(a4, 0);
    v66 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
      v19,
      (unsigned int)byte_18015385B,
      v20,
      v21,
      (__int64)&v66,
      (__int64)&StringRawBuffer,
      (__int64)&v71,
      (__int64)v60);
  }
  v22 = IsMediumCaller(a4);
  v61 = 0;
  v23 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  v24 = v23(a2, &v61);
  v16 = v24;
  if ( v24 >= 0 )
  {
    v62 = 0;
    v25 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderSystemInformation>(
            &v61,
            &v62);
    v16 = v25;
    if ( v25 < 0 )
    {
      v26 = 795;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v25,
        (int)v59);
LABEL_77:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
      goto LABEL_78;
    }
    v25 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v62 + 72LL))(v62, 0);
    v16 = v25;
    if ( v25 < 0 )
    {
      v26 = 802;
      goto LABEL_13;
    }
    v25 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v62 + 56LL))(v62, 0);
    v16 = v25;
    if ( v25 < 0 )
    {
      v26 = 803;
      goto LABEL_13;
    }
    v25 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), unsigned int *))(*a1)[7])(
            a1,
            &v65);
    v16 = v25;
    if ( v25 < 0 )
    {
      v26 = 809;
      goto LABEL_13;
    }
    v28 = !v22;
    if ( (unsigned int)dword_180175000 > 5 )
    {
      v66 = v65;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180175000,
        (unsigned int)byte_180153769,
        0,
        v27,
        (__int64)&v66);
    }
    v29 = 0;
    if ( v65 )
    {
      while ( 1 )
      {
        v63 = 0;
        v30 = (*a1)[6];
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
        v31 = v30(a1, (GUID *)v29, (__int64 *)&v63);
        v16 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x334,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
            (const char *)(unsigned int)v31,
            (int)v59);
          goto LABEL_49;
        }
        string = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), HSTRING *))(*v63)[6])(v63, &string);
        if ( (unsigned int)dword_180175000 > 5 )
        {
          v60[0] = !WindowsIsStringEmpty(string);
          v66 = v29;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
            v32,
            (unsigned int)&dword_1801537A4,
            v33,
            v34,
            (__int64)&v66,
            (__int64)v60);
        }
        v68 = 0;
        v35 = v63;
        v36 = (*v63)[8];
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        v37 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 *))v36)(v35, &v68);
        v16 = v37;
        if ( v37 < 0 )
          break;
        if ( v68 )
        {
          *(_QWORD *)v67 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v67);
          v59 = v67;
          AccountWithContext = Windows::Internal::Security::Authentication::TokenBroker::ReFindAccountWithContext(
                                 v68,
                                 v61,
                                 v28,
                                 a4);
          v16 = AccountWithContext;
          if ( AccountWithContext < 0 )
          {
            v47 = 843;
            goto LABEL_52;
          }
          AccountWithContext = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v72 + 104LL))(
                                 v72,
                                 *(_QWORD *)v67);
          v16 = AccountWithContext;
          if ( AccountWithContext < 0 )
          {
            v47 = 846;
LABEL_52:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v47,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
              (const char *)(unsigned int)AccountWithContext,
              (int)v67);
            goto LABEL_46;
          }
          v74 = 0;
          v39 = Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenResponse>::As<Windows::Internal::Security::Authentication::Web::IWebAccountSetter>(
                  &v63,
                  (__int64)&v74);
          v16 = v39;
          if ( v39 < 0 )
          {
            v46 = 849;
LABEL_45:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v46,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
              (const char *)(unsigned int)v39,
              (int)v67);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
LABEL_46:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v67);
            goto LABEL_47;
          }
          v39 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v74 + 48LL))(v74, *(_QWORD *)v67);
          v16 = v39;
          if ( v39 < 0 )
          {
            v46 = 850;
            goto LABEL_45;
          }
          StringRawBuffer = 0;
          v77 = 0;
          if ( (int)Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                      (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v67,
                      (__int64)&v77) >= 0 )
            (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v77 + 48LL))(v77, &StringRawBuffer);
          if ( (unsigned int)dword_180175000 > 5 )
          {
            v81 = WindowsGetStringRawBuffer(StringRawBuffer, 0);
            v71 = v29;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
              v40,
              (unsigned int)word_180153722,
              v41,
              v42,
              (__int64)&v71,
              (__int64)&v81);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v77);
          if ( StringRawBuffer )
            WindowsDeleteString(StringRawBuffer);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v67);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        if ( string )
          WindowsDeleteString(string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
        if ( ++v29 >= v65 )
          goto LABEL_42;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x340,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v37,
        (int)v59);
LABEL_47:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      if ( string )
        WindowsDeleteString(string);
LABEL_49:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v63);
      goto LABEL_77;
    }
LABEL_42:
    v64 = 0;
    v43 = v72;
    v44 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v72 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    v45 = v44(v43, &v64);
    v16 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x365,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v45,
        (int)v59);
LABEL_76:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      goto LABEL_77;
    }
    v69 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
    v48 = ChooseEffectiveAccountHints(&a5, v82, v64, &v69);
    v16 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36A,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v48,
        (int)v59);
LABEL_75:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      goto LABEL_76;
    }
    memset(v78, 0, sizeof(v78));
    v79 = 0;
    v80 = 1;
    v49 = Windows::Internal::Security::CPropertiesSerializer::Initialize((Windows::Internal::Security::CPropertiesSerializer *)v78);
    v16 = v49;
    if ( v49 >= 0 )
    {
      if ( v65
        && (v51 = (__int64 *)Windows::Internal::StringReference::StringReference(v84, L"responses"),
            v49 = Windows::Internal::Security::AddVectorToSerializer<Windows::Security::Authentication::Web::Core::WebTokenResponse *>(
                    a1,
                    *v51,
                    (__int64)v78),
            v16 = v49,
            v49 < 0) )
      {
        v50 = 887;
      }
      else
      {
        v52 = Windows::Internal::StringReference::StringReference(v84, L"status");
        v49 = Windows::Internal::Security::CPropertiesSerializer::AddUInt32Property(
                (Windows::Internal::Security::CPropertiesSerializer *)v78,
                *v52,
                a5);
        v16 = v49;
        if ( v49 >= 0 )
        {
          v53 = Windows::Internal::StringReference::StringReference(v84, L"expiration");
          v49 = Windows::Internal::Security::CPropertiesSerializer::AddInt64Property(
                  (Windows::Internal::Security::CPropertiesSerializer *)v78,
                  *v53,
                  a6);
          v16 = v49;
          if ( v49 >= 0 )
          {
            if ( !v12
              || (v54 = Windows::Internal::StringReference::StringReference(v84, L"error"),
                  v49 = Windows::Internal::Security::AddObjectToSerializer<Windows::Security::Authentication::Web::Core::IWebProviderError *>(
                          v12,
                          *v54,
                          (Windows::Internal::Security::CPropertiesSerializer *)v78),
                  v16 = v49,
                  v49 >= 0) )
            {
              v75 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
              Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v78);
              v75 = *(Windows::Internal::Security::Authentication::TokenBroker **)&v78[0];
              v73 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
              v56 = Windows::Internal::Security::Authentication::TokenBroker::SerializePropertySet(
                      v75,
                      (struct Windows::Foundation::Collections::IPropertySet *)&v73,
                      v55);
              v16 = v56;
              if ( v56 >= 0 )
              {
                v57 = v73;
                v73 = 0;
                *v83 = v57;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x392,
                  (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
                  (const char *)(unsigned int)v56,
                  (int)v59);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v75);
              goto LABEL_74;
            }
            v50 = 904;
          }
          else
          {
            v50 = 896;
          }
        }
        else
        {
          v50 = 892;
        }
      }
    }
    else
    {
      v50 = 880;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v50,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v49,
      (int)v59);
LABEL_74:
    Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)v78);
    goto LABEL_75;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x319,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
    (const char *)(unsigned int)v24,
    (int)v59);
LABEL_78:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
LABEL_82:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  return v16;
}

```

## disassembly

```asm
0x1800f1964  mov     [rsp-8+arg_10], rbx
0x1800f1969  push    rbp
0x1800f196a  push    rsi
0x1800f196b  push    rdi
0x1800f196c  push    r12
0x1800f196e  push    r13
0x1800f1970  push    r14
0x1800f1972  push    r15
0x1800f1974  lea     rbp, [rsp-30h]
0x1800f1979  sub     rsp, 130h
0x1800f1980  mov     rax, cs:__security_cookie
0x1800f1987  xor     rax, rsp
0x1800f198a  mov     [rbp+60h+var_38], rax
0x1800f198e  mov     r12, r9
0x1800f1991  mov     rdi, rdx
0x1800f1994  mov     r15, rcx
0x1800f1997  mov     r13, [rbp+60h+arg_30]
0x1800f199e  mov     rsi, [rbp+60h+arg_38]
0x1800f19a5  mov     [rbp+60h+var_60], rsi
0x1800f19a9  mov     rax, [rbp+60h+arg_40]
0x1800f19b0  mov     [rbp+60h+var_68], rax
0x1800f19b4  xor     r14d, r14d
0x1800f19b7  mov     [rsp+160h+var_F8], r14d
0x1800f19bc  mov     [rbp+60h+var_C8], r14
0x1800f19c0  lea     rcx, [rbp+60h+var_C8]
0x1800f19c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f19c9  lea     rdx, [rbp+60h+var_C8]
0x1800f19cd  call    ??$CreateExternalObjectVector@VWebAccount@Credentials@Security@Windows@@V?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0> * *)
0x1800f19d2  mov     ebx, eax
0x1800f19d4  test    eax, eax
0x1800f19d6  jns     short loc_1800F19E5
0x1800f19d8  mov     r9d, eax
0x1800f19db  mov     edx, 2FAh
0x1800f19e0  jmp     loc_1800F20EA
0x1800f19e5  test    r15, r15
0x1800f19e8  jz      loc_1800F20DD
0x1800f19ee  test    rdi, rdi
0x1800f19f1  jz      loc_1800F20DD
0x1800f19f7  test    rsi, rsi
0x1800f19fa  jz      loc_1800F20DD
0x1800f1a00  test    r12, r12
0x1800f1a03  jz      loc_1800F20DD
0x1800f1a09  mov     eax, cs:dword_180175000
0x1800f1a0f  cmp     eax, 5
0x1800f1a12  jbe     short loc_1800F1A6E
0x1800f1a14  test    r13, r13
0x1800f1a17  setnz   [rsp+160h+var_120]
0x1800f1a1c  mov     eax, [rbp+60h+arg_20]
0x1800f1a22  mov     [rbp+60h+var_D0], eax
0x1800f1a25  xor     edx, edx; length
0x1800f1a27  mov     rcx, r12; string
0x1800f1a2a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f1a30  mov     [rbp+60h+var_A8], rax
0x1800f1a34  mov     [rsp+160h+var_F4], 1
0x1800f1a3c  lea     rax, [rsp+160h+var_120]
0x1800f1a41  mov     [rsp+160h+var_128], rax
0x1800f1a46  lea     rax, [rbp+60h+var_D0]
0x1800f1a4a  mov     [rsp+160h+var_130], rax
0x1800f1a4f  lea     rax, [rbp+60h+var_A8]
0x1800f1a53  mov     [rsp+160h+var_138], rax
0x1800f1a58  lea     rax, [rsp+160h+var_F4]
0x1800f1a5d  mov     qword ptr [rsp+160h+var_140], rax; int
0x1800f1a62  lea     rdx, byte_18015385B
0x1800f1a69  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1800f1a6e  mov     rcx, r12; string2
0x1800f1a71  call    ?IsMediumCaller@@YA_NPEAUHSTRING__@@@Z; IsMediumCaller(HSTRING__ *)
0x1800f1a76  movzx   esi, al
0x1800f1a79  mov     [rsp+160h+var_118], r14
0x1800f1a7e  mov     rcx, [rdi]
0x1800f1a81  mov     rbx, [rcx+30h]
0x1800f1a85  lea     rcx, [rsp+160h+var_118]
0x1800f1a8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1a8f  lea     rdx, [rsp+160h+var_118]
0x1800f1a94  mov     rcx, rdi
0x1800f1a97  mov     rax, rbx
0x1800f1a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1a9f  mov     ebx, eax
0x1800f1aa1  xor     edi, edi
0x1800f1aa3  test    eax, eax
0x1800f1aa5  jns     short loc_1800F1AC4
0x1800f1aa7  mov     rcx, [rbp+68h]; this
0x1800f1aab  mov     r9d, eax; char *
0x1800f1aae  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f1ab5  mov     edx, 319h; void *
0x1800f1aba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1abf  jmp     loc_1800F20C0
0x1800f1ac4  mov     [rsp+160h+var_110], rdi
0x1800f1ac9  lea     rdx, [rsp+160h+var_110]
0x1800f1ace  lea     rcx, [rsp+160h+var_118]
0x1800f1ad3  call    ??$As@UIWebAccountProviderSystemInformation@Credentials@Security@Internal@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProviderSystemInformation@Credentials@Security@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderSystemInformation>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountProviderSystemInformation>>)
0x1800f1ad8  mov     ebx, eax
0x1800f1ada  test    eax, eax
0x1800f1adc  jns     short loc_1800F1AFB
0x1800f1ade  mov     edx, 31Bh; void *
0x1800f1ae3  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f1aea  mov     r9d, eax; char *
0x1800f1aed  mov     rcx, [rbp+68h]; this
0x1800f1af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1af6  jmp     loc_1800F20B5
0x1800f1afb  mov     rcx, [rsp+160h+var_110]
0x1800f1b00  mov     rax, [rcx]
0x1800f1b03  xor     edx, edx
0x1800f1b05  mov     rax, [rax+48h]
0x1800f1b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1b0e  mov     ebx, eax
0x1800f1b10  test    eax, eax
0x1800f1b12  jns     short loc_1800F1B1B
0x1800f1b14  mov     edx, 322h
0x1800f1b19  jmp     short loc_1800F1AE3
0x1800f1b1b  mov     rcx, [rsp+160h+var_110]
0x1800f1b20  mov     rax, [rcx]
0x1800f1b23  xor     edx, edx
0x1800f1b25  mov     rax, [rax+38h]
0x1800f1b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1b2e  mov     ebx, eax
0x1800f1b30  test    eax, eax
0x1800f1b32  jns     short loc_1800F1B3B
0x1800f1b34  mov     edx, 323h
0x1800f1b39  jmp     short loc_1800F1AE3
0x1800f1b3b  mov     rax, [r15]
0x1800f1b3e  lea     rdx, [rsp+160h+var_F8]
0x1800f1b43  mov     rcx, r15
0x1800f1b46  mov     rax, [rax+38h]
0x1800f1b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1b4f  mov     ebx, eax
0x1800f1b51  test    eax, eax
0x1800f1b53  jns     short loc_1800F1B5C
0x1800f1b55  mov     edx, 329h
0x1800f1b5a  jmp     short loc_1800F1AE3
0x1800f1b5c  mov     r14d, esi
0x1800f1b5f  xor     r14d, 1
0x1800f1b63  mov     eax, cs:dword_180175000
0x1800f1b69  cmp     eax, 5
0x1800f1b6c  jbe     short loc_1800F1B96
0x1800f1b6e  mov     eax, [rsp+160h+var_F8]
0x1800f1b72  mov     [rsp+160h+var_F4], eax
0x1800f1b76  lea     rax, [rsp+160h+var_F4]
0x1800f1b7b  mov     qword ptr [rsp+160h+var_140], rax; int
0x1800f1b80  xor     r8d, r8d
0x1800f1b83  lea     rdx, byte_180153769
0x1800f1b8a  lea     rcx, dword_180175000
0x1800f1b91  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800f1b96  mov     esi, edi
0x1800f1b98  cmp     [rsp+160h+var_F8], edi
0x1800f1b9c  jbe     loc_1800F1DCC
0x1800f1ba2  mov     [rsp+160h+var_108], rdi
0x1800f1ba7  mov     rax, [r15]
0x1800f1baa  mov     rbx, [rax+30h]
0x1800f1bae  lea     rcx, [rsp+160h+var_108]
0x1800f1bb3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1bb8  lea     r8, [rsp+160h+var_108]
0x1800f1bbd  mov     edx, esi
0x1800f1bbf  mov     rcx, r15
0x1800f1bc2  mov     rax, rbx
0x1800f1bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1bca  mov     ebx, eax
0x1800f1bcc  test    eax, eax
0x1800f1bce  js      loc_1800F1EBA
0x1800f1bd4  mov     [rbp+60h+string], rdi
0x1800f1bd8  mov     rcx, [rsp+160h+var_108]
0x1800f1bdd  mov     rax, [rcx]
0x1800f1be0  lea     rdx, [rbp+60h+string]
0x1800f1be4  mov     rax, [rax+30h]
0x1800f1be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1bed  mov     eax, cs:dword_180175000
0x1800f1bf3  cmp     eax, 5
0x1800f1bf6  jbe     short loc_1800F1C2D
0x1800f1bf8  mov     rcx, [rbp+60h+string]; string
0x1800f1bfc  call    cs:__imp_WindowsIsStringEmpty
0x1800f1c02  test    eax, eax
0x1800f1c04  setz    [rsp+160h+var_120]
0x1800f1c09  mov     [rsp+160h+var_F4], esi
0x1800f1c0d  lea     rax, [rsp+160h+var_120]
0x1800f1c12  mov     [rsp+160h+var_138], rax
0x1800f1c17  lea     rax, [rsp+160h+var_F4]
0x1800f1c1c  mov     qword ptr [rsp+160h+var_140], rax; int
0x1800f1c21  lea     rdx, dword_1801537A4
0x1800f1c28  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1800f1c2d  mov     [rsp+160h+var_E8], rdi
0x1800f1c32  mov     rdi, [rsp+160h+var_108]
0x1800f1c37  mov     rax, [rdi]
0x1800f1c3a  mov     rbx, [rax+40h]
0x1800f1c3e  lea     rcx, [rsp+160h+var_E8]
0x1800f1c43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1c48  lea     rdx, [rsp+160h+var_E8]
0x1800f1c4d  mov     rcx, rdi
0x1800f1c50  mov     rax, rbx
0x1800f1c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1c58  mov     ebx, eax
0x1800f1c5a  xor     edi, edi
0x1800f1c5c  test    eax, eax
0x1800f1c5e  js      loc_1800F1EA0
0x1800f1c64  cmp     [rsp+160h+var_E8], rdi
0x1800f1c69  jz      loc_1800F1D9B
0x1800f1c6f  mov     qword ptr [rsp+160h+var_F0], rdi
0x1800f1c74  lea     rcx, [rsp+160h+var_F0]
0x1800f1c79  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1c7e  lea     rax, [rsp+160h+var_F0]
0x1800f1c83  mov     qword ptr [rsp+160h+var_140], rax; int
0x1800f1c88  mov     r9, r12
0x1800f1c8b  mov     r8d, r14d
0x1800f1c8e  mov     rdx, [rsp+160h+var_118]
0x1800f1c93  mov     rcx, [rsp+160h+var_E8]
0x1800f1c98  call    ?ReFindAccountWithContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccount@Credentials@35@PEAUIWebAccountProvider@735@W4AccountLookupContext@12345@PEAUHSTRING__@@PEAPEAU6735@@Z; Windows::Internal::Security::Authentication::TokenBroker::ReFindAccountWithContext(Windows::Security::Credentials::IWebAccount *,Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::Security::Authentication::TokenBroker::AccountLookupContext,HSTRING__ *,Windows::Security::Credentials::IWebAccount * *)
0x1800f1c9d  mov     ebx, eax
0x1800f1c9f  test    eax, eax
0x1800f1ca1  js      loc_1800F1E99
0x1800f1ca7  mov     rcx, [rbp+60h+var_C8]
0x1800f1cab  mov     rax, [rcx]
0x1800f1cae  mov     rdx, qword ptr [rsp+160h+var_F0]
0x1800f1cb3  mov     rax, [rax+68h]
0x1800f1cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1cbc  mov     ebx, eax
0x1800f1cbe  test    eax, eax
0x1800f1cc0  js      loc_1800F1E7F
0x1800f1cc6  mov     [rbp+60h+var_B8], rdi
0x1800f1cca  lea     rdx, [rbp+60h+var_B8]
0x1800f1cce  lea     rcx, [rsp+160h+var_108]
0x1800f1cd3  call    ??$As@UIWebAccountSetter@Web@Authentication@Security@Internal@Windows@@@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountSetter@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenResponse>::As<Windows::Internal::Security::Authentication::Web::IWebAccountSetter>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::IWebAccountSetter>>)
0x1800f1cd8  mov     ebx, eax
0x1800f1cda  test    eax, eax
0x1800f1cdc  js      loc_1800F1E78
0x1800f1ce2  mov     rcx, [rbp+60h+var_B8]
0x1800f1ce6  mov     rax, [rcx]
0x1800f1ce9  mov     rdx, qword ptr [rsp+160h+var_F0]
0x1800f1cee  mov     rax, [rax+30h]
0x1800f1cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1cf7  mov     ebx, eax
0x1800f1cf9  test    eax, eax
0x1800f1cfb  js      loc_1800F1E20
0x1800f1d01  mov     [rbp+60h+var_A8], rdi
0x1800f1d05  mov     [rbp+60h+var_A0], rdi
0x1800f1d09  lea     rdx, [rbp+60h+var_A0]
0x1800f1d0d  lea     rcx, [rsp+160h+var_F0]
0x1800f1d12  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x1800f1d17  test    eax, eax
0x1800f1d19  js      short loc_1800F1D2F
0x1800f1d1b  mov     rcx, [rbp+60h+var_A0]
0x1800f1d1f  mov     rax, [rcx]
0x1800f1d22  lea     rdx, [rbp+60h+var_A8]
0x1800f1d26  mov     rax, [rax+30h]
0x1800f1d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1d2f  mov     eax, cs:dword_180175000
0x1800f1d35  cmp     eax, 5
0x1800f1d38  jbe     short loc_1800F1D6C
0x1800f1d3a  xor     edx, edx; length
0x1800f1d3c  mov     rcx, [rbp+60h+var_A8]; string
0x1800f1d40  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f1d46  mov     [rbp+60h+var_70], rax
0x1800f1d4a  mov     [rbp+60h+var_D0], esi
0x1800f1d4d  lea     rax, [rbp+60h+var_70]
0x1800f1d51  mov     [rsp+160h+var_138], rax
0x1800f1d56  lea     rax, [rbp+60h+var_D0]
0x1800f1d5a  mov     qword ptr [rsp+160h+var_140], rax; int
0x1800f1d5f  lea     rdx, word_180153722
0x1800f1d66  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800f1d6b  nop
0x1800f1d6c  lea     rcx, [rbp+60h+var_A0]
0x1800f1d70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1d75  nop
0x1800f1d76  mov     rcx, [rbp+60h+var_A8]; string
0x1800f1d7a  test    rcx, rcx
0x1800f1d7d  jz      short loc_1800F1D86
0x1800f1d7f  call    cs:__imp_WindowsDeleteString
0x1800f1d85  nop
0x1800f1d86  lea     rcx, [rbp+60h+var_B8]
0x1800f1d8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1d8f  nop
0x1800f1d90  lea     rcx, [rsp+160h+var_F0]
0x1800f1d95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1d9a  nop
0x1800f1d9b  lea     rcx, [rsp+160h+var_E8]
0x1800f1da0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1da5  nop
0x1800f1da6  mov     rcx, [rbp+60h+string]; string
0x1800f1daa  test    rcx, rcx
0x1800f1dad  jz      short loc_1800F1DB6
0x1800f1daf  call    cs:__imp_WindowsDeleteString
0x1800f1db5  nop
0x1800f1db6  lea     rcx, [rsp+160h+var_108]
0x1800f1dbb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1dc0  inc     esi
0x1800f1dc2  cmp     esi, [rsp+160h+var_F8]
0x1800f1dc6  jb      loc_1800F1BA2
0x1800f1dcc  mov     [rsp+160h+var_100], rdi
0x1800f1dd1  mov     rdi, [rbp+60h+var_C8]
0x1800f1dd5  mov     rax, [rdi]
0x1800f1dd8  mov     rbx, [rax+40h]
0x1800f1ddc  lea     rcx, [rsp+160h+var_100]
0x1800f1de1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800f1de6  lea     rdx, [rsp+160h+var_100]
0x1800f1deb  mov     rcx, rdi
0x1800f1dee  mov     rax, rbx
0x1800f1df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1df6  mov     ebx, eax
0x1800f1df8  xor     r14d, r14d
0x1800f1dfb  test    eax, eax
0x1800f1dfd  jns     loc_1800F1ED4
0x1800f1e03  mov     rcx, [rbp+68h]; this
0x1800f1e07  mov     r9d, eax; char *
  ... truncated ...
```
