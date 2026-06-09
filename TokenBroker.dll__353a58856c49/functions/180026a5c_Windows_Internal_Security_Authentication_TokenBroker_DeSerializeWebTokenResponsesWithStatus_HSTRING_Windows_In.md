# Windows::Internal::Security::Authentication::TokenBroker::DeSerializeWebTokenResponsesWithStatus(HSTRING__ *,Windows::Internal::Security::Authentication::TokenBroker::AccountLookupContext,Windows::Storage::Streams::IBuffer *,Windows::Security::Credentials::IWebAccountProvider *,Windows::Security::Authentication::Web::Core::WebTokenRequestStatus *,Windows::Foundation::DateTime *,Windows::Security::Authentication::Web::Core::IWebProviderError * *,Windows::Foundation::Collections::IVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *> * *)

- ea: `0x180026a5c`
- end: `0x1800277af`
- name: `?DeSerializeWebTokenResponsesWithStatus@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUHSTRING__@@W4AccountLookupContext@12345@PEAUIBuffer@Streams@Storage@5@PEAUIWebAccountProvider@Credentials@35@PEAW4WebTokenRequestStatus@Core@Web@235@PEAUDateTime@Foundation@5@PEAPEAUIWebProviderError@Core@Web@235@PEAPEAU?$IVector@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@Collections@Foundation@5@@Z`
- size: `3411`
- prototype: `__int64 __usercall@<rax>(HSTRING string2@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005aa84`
- `0x1800ee994`
- `0x180109e6c`
- `0x18010a528`
- `0x18010aff4`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180016f44`
- `0x1800175c0`
- `0x180018720`
- `0x1800247e4`
- `0x180025bd8`
- `0x180026870`
- `0x180026a5c`
- `0x180027aa0`
- `0x180027c4c`
- `0x180027ccc`
- `0x180048de0`
- `0x18004c064`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002757f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800276b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800276cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800276e8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002757f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800276b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800276cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800276e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026df7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026f58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026df7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026e8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026f58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026fc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002705d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800270d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027252`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800272e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800273d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027465`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027532`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027634`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026fc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002705d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800270d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027252`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800272e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800273d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027465`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027532`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027634`

## string_xrefs

- `0x18002702a`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800270a3`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x180027168`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18002721f`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18002729a`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18002732f`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x180027418`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800274ab`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x180027591`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18002767a`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x180027701`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18002771b`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18002773f`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x18002776f`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::DeSerializeWebTokenResponsesWithStatus(
        HSTRING string2,
        unsigned int a2,
        Windows::Internal::Security::Authentication::TokenBroker *a3,
        __int64 a4,
        int *a5,
        _QWORD *a6,
        _QWORD *a7,
        _QWORD *a8)
{
  struct Windows::Foundation::Collections::IPropertySet **v12; // r8
  unsigned int v13; // r15d
  int v14; // eax
  unsigned int v15; // ebx
  struct Windows::Foundation::Collections::IPropertySet *v16; // rsi
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned int i; // r14d
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD); // rbx
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v25)(_QWORD, _QWORD); // rbx
  int v26; // eax
  __int64 v27; // rcx
  int AccountWithContext; // eax
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v30)(_QWORD, GUID *, _QWORD); // rdi
  int v31; // eax
  int v32; // eax
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v34; // rcx
  __int64 (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v36; // rcx
  int v37; // eax
  __int64 (__fastcall ***v38)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v39)(_QWORD, GUID *, __int64 *); // rdi
  int v40; // eax
  __int64 (__fastcall ***v41)(_QWORD, _QWORD, _QWORD); // rcx
  int v42; // r14d
  __int64 v43; // rax
  int v44; // edi
  __int64 v45; // rdi
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 v48; // r8
  int v49; // eax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 (__fastcall ***v56)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 (__fastcall ***v60)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v61; // rcx
  __int64 (__fastcall ***v62)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 (__fastcall ***v65)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 (__fastcall ***v71)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v72; // rcx
  __int64 (__fastcall ***v73)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 (__fastcall ***v76)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v77; // rcx
  int *v78; // [rsp+20h] [rbp-E0h]
  __int64 v79; // [rsp+30h] [rbp-D0h] BYREF
  int v80[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v81)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v82)(_QWORD, GUID *, _QWORD); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v83; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v84; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem[2]; // [rsp+68h] [rbp-98h] BYREF
  int v86; // [rsp+78h] [rbp-88h]
  char v87; // [rsp+7Ch] [rbp-84h]
  __int64 v88; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v89; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v90; // [rsp+90h] [rbp-70h] BYREF
  int v91; // [rsp+98h] [rbp-68h]
  struct Windows::Foundation::Collections::IPropertySet *v92; // [rsp+A0h] [rbp-60h] BYREF
  int *v93; // [rsp+A8h] [rbp-58h]
  _QWORD *v94; // [rsp+B0h] [rbp-50h]
  _QWORD *v95; // [rsp+B8h] [rbp-48h]
  _QWORD *v96; // [rsp+C0h] [rbp-40h]
  HSTRING string; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING v99; // [rsp+E8h] [rbp-18h] BYREF
  HSTRING_HEADER v100; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v93 = a5;
  v94 = a6;
  v95 = a7;
  v96 = a8;
  if ( !string2 || !a3 || !a4 || !a5 || !a6 || !a7 || !a8 )
    return 2147942487LL;
  v13 = 0;
  if ( !IsMediumCaller(string2) )
    v13 = a2;
  v92 = 0;
  v14 = Windows::Internal::Security::Authentication::TokenBroker::DeSerializePropertySet(
          a3,
          (struct Windows::Storage::Streams::IBuffer *)&v92,
          v12);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v14,
      (int)v78);
    if ( v92 )
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v92 + 16LL))(v92);
    return v15;
  }
  v84 = 0;
  *(_OWORD *)hMem = 0;
  v86 = 0;
  v87 = 1;
  v16 = v92;
  v17 = Windows::Internal::Security::CPropertiesSerializer::InitializeFromPropertySet(
          (Windows::Internal::Security::CPropertiesSerializer *)&v84,
          v92);
  v15 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v17,
      (int)v78);
LABEL_148:
    Windows::Internal::Security::CPropertiesSerializer::~CPropertiesSerializer((Windows::Internal::Security::CPropertiesSerializer *)&v84);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v92);
    return v15;
  }
  v79 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
  if ( WindowsCreateStringReference(L"responses", 9u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v18 = Windows::Internal::Security::GetVectorFromSerializer<Windows::Security::Authentication::Web::Core::WebTokenResponse *,long (*)(unsigned char *,unsigned long,Windows::Security::Authentication::Web::Core::IWebTokenResponse * *)>(
          (Windows::Internal::Security::CPropertiesSerializer *)&v84,
          string);
  v15 = v18;
  if ( v18 == -2147483637 )
  {
    v81 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
    v37 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::Web::Core::WebTokenResponse,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,0>>(
            v36,
            &v81);
    v15 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CD,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v37,
        (int)v78);
      v56 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v81;
      if ( v81 )
      {
        v81 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v56)[2])(v56);
      }
      v57 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      }
      LocalFree(hMem[1]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      if ( v16 )
        (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
      return v15;
    }
    v38 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v81;
    v39 = **v81;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
    v40 = v39(v38, &GUID_58dc4e4c_a84d_5ad6_a6d9_6ee477329c9f, &v79);
    v15 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CE,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v40,
        (int)v78);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
LABEL_147:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v79);
      goto LABEL_148;
    }
    v41 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v81;
    if ( v81 )
    {
      v81 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v41)[2])(v41);
    }
  }
  else
  {
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F4,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v18,
        (int)v78);
      v53 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
      LocalFree(hMem[1]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      if ( v16 )
        (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
      return v15;
    }
    v89 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v79 + 56LL))(v79, &v89);
    v15 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D7,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v19,
        (int)v78);
      v54 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      LocalFree(hMem[1]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      if ( v16 )
        (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
      return v15;
    }
    for ( i = 0; i < v89; ++i )
    {
      v82 = 0;
      v21 = v79;
      v22 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v79 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
      v23 = v22(v21, i, &v82);
      v15 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3DC,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)v23,
          (int)v78);
        v60 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v82;
        if ( v82 )
        {
          v82 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v60)[2])(v60);
        }
        v61 = v79;
        if ( v79 )
        {
          v79 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
        }
        LocalFree(hMem[1]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        if ( v16 )
          (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
        return v15;
      }
      v83 = 0;
      v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v82;
      v25 = (__int64 (__fastcall *)(_QWORD, _QWORD))(*v82)[8];
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
      v26 = v25(v24, &v83);
      v15 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3DF,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)v26,
          (int)v78);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v83);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v82);
        goto LABEL_147;
      }
      v27 = v83;
      if ( v83 )
      {
        *(_QWORD *)v80 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v80);
        v78 = v80;
        AccountWithContext = Windows::Internal::Security::Authentication::TokenBroker::ReFindAccountWithContext(
                               v83,
                               a4,
                               v13,
                               string2);
        v15 = AccountWithContext;
        if ( AccountWithContext < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3EA,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
            (const char *)(unsigned int)AccountWithContext,
            (int)v80);
          v69 = *(_QWORD *)v80;
          if ( *(_QWORD *)v80 )
          {
            *(_QWORD *)v80 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
          }
          v70 = v83;
          if ( v83 )
          {
            v83 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
          }
          v71 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v82;
          if ( v82 )
          {
            v82 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v71)[2])(v71);
          }
          v72 = v79;
          if ( v79 )
          {
            v79 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
          }
          LocalFree(hMem[1]);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
          if ( v16 )
            (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
          return v15;
        }
        v81 = 0;
        v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v82;
        v30 = **v82;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v81);
        v31 = v30(v29, &GUID_d9a260bf_ca96_4d92_af87_3d22326e66f5, &v81);
        v15 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3ED,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
            (const char *)(unsigned int)v31,
            (int)v80);
          v73 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v81;
          if ( v81 )
          {
            v81 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v73)[2])(v73);
          }
          v74 = *(_QWORD *)v80;
          if ( *(_QWORD *)v80 )
          {
            *(_QWORD *)v80 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
          }
          v75 = v83;
          if ( v83 )
          {
            v83 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
          }
          v76 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v82;
          if ( v82 )
          {
            v82 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v76)[2])(v76);
          }
          v77 = v79;
          if ( v79 )
          {
            v79 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
          }
          LocalFree(hMem[1]);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
          if ( v16 )
            (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
          return v15;
        }
        v32 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD))(*v81)[6])(
                v81,
                *(_QWORD *)v80);
        v15 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3EE,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
            (const char *)(unsigned int)v32,
            (int)v80);
          v62 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v81;
          if ( v81 )
          {
            v81 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v62)[2])(v62);
          }
          v63 = *(_QWORD *)v80;
          if ( *(_QWORD *)v80 )
          {
            *(_QWORD *)v80 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
          }
          v64 = v83;
          if ( v83 )
          {
            v83 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
          }
          v65 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v82;
          if ( v82 )
          {
            v82 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v65)[2])(v65);
          }
          v66 = v79;
          if ( v79 )
          {
            v79 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
          }
          LocalFree(hMem[1]);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
          if ( v16 )
            (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
          return v15;
        }
        v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v81;
        if ( v81 )
        {
          v81 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v33)[2])(v33);
        }
        v34 = *(_QWORD *)v80;
        if ( *(_QWORD *)v80 )
        {
          *(_QWORD *)v80 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        v27 = v83;
      }
      if ( v27 )
      {
        v83 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v35 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v82;
      if ( v82 )
      {
        v82 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v35)[2])(v35);
      }
    }
  }
  v42 = 0;
  if ( WindowsCreateStringReference(L"status", 6u, &v100, &v99) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v80[0] = 0;
  v90 = 0;
  v91 = 0;
  v15 = -2147024809;
  if ( v99 )
  {
    v43 = **((_QWORD **)&v84 + 1);
    string = (HSTRING)&v90;
    hstringHeader.Reserved.Reserved1 = 0;
    v44 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, HSTRING_HEADER *))(v43 + 48))(
            *((_QWORD *)&v84 + 1),
            v99,
            &hstringHeader);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&string);
    if ( v44 >= 0 )
    {
      string = v90;
      LODWORD(hstringHeader.Reserved.Reserved1) = v91;
      v80[0] = 0;
      v44 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&string);
      if ( v44 >= 0 )
      {
        v44 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 96LL))(v55, v80);
        if ( v44 >= 0 )
          v42 = v80[0];
      }
    }
  }
  else
  {
    v44 = -2147024809;
  }
  RoVariant::~RoVariant((RoVariant *)&v90);
  if ( v44 >= 0 )
  {
    v45 = 0;
    if ( WindowsCreateStringReference(L"expiration", 0xAu, &v100, &v99) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    *(_QWORD *)v80 = 0;
    v90 = 0;
    v91 = 0;
    if ( v99 )
    {
      v46 = **((_QWORD **)&v84 + 1);
      string = (HSTRING)&v90;
      hstringHeader.Reserved.Reserved1 = 0;
      v15 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, HSTRING_HEADER *))(v46 + 48))(
              *((_QWORD *)&v84 + 1),
              v99,
              &hstringHeader);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&string);
      if ( (v15 & 0x80000000) == 0 )
      {
        string = v90;
        LODWORD(hstringHeader.Reserved.Reserved1) = v91;
        *(_QWORD *)v80 = 0;
        v15 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&string);
        if ( (v15 & 0x80000000) == 0 )
        {
          v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v47 + 104LL))(v47, v80);
          if ( (v15 & 0x80000000) == 0 )
            v45 = *(_QWORD *)v80;
        }
      }
    }
    RoVariant::~RoVariant((RoVariant *)&v90);
    if ( (v15 & 0x80000000) == 0 )
    {
      v88 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      if ( WindowsCreateStringReference(L"error", 5u, &v100, &v99) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v49 = Windows::Internal::Security::GetObjectFromSerializer<Windows::Security::Authentication::Web::Core::IWebProviderError *,long (*)(unsigned char *,unsigned long,Windows::Security::Authentication::Web::Core::IWebProviderError * *)>(
              &v84,
              v99,
              v48,
              &v88);
      v15 = v49;
      if ( v49 == -2147483637 )
      {
        v15 = 0;
        v58 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        }
      }
      else if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x414,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)v49,
          (int)v78);
        v67 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
        }
        v68 = v79;
        if ( v79 )
        {
          v79 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
        }
        LocalFree(hMem[1]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        if ( v16 )
          (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
        return v15;
      }
      *v93 = v42;
      *v94 = v45;
      v50 = v88;
      v88 = 0;
      *v95 = v50;
      v51 = v79;
      v79 = 0;
      *v96 = v51;
      LocalFree(hMem[1]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
      if ( v16 )
        (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
      return v15;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x402,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)v15,
      (int)v78);
    goto LABEL_147;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3FB,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
    (const char *)(unsigned int)v44,
    (int)v78);
  v59 = v79;
  if ( v79 )
  {
    v79 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  }
  LocalFree(hMem[1]);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(hMem);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)&v84 + 8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
  if ( v16 )
    (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v44;
}

```

## disassembly

```asm
0x180026a5c  mov     [rsp-8+arg_8], rbx
0x180026a61  push    rbp
0x180026a62  push    rsi
0x180026a63  push    rdi
0x180026a64  push    r12
0x180026a66  push    r13
0x180026a68  push    r14
0x180026a6a  push    r15
0x180026a6c  lea     rbp, [rsp-10h]
0x180026a71  sub     rsp, 110h
0x180026a78  mov     rax, cs:__security_cookie
0x180026a7f  xor     rax, rsp
0x180026a82  mov     [rbp+40h+var_38], rax
0x180026a86  mov     r13, r9
0x180026a89  mov     rbx, r8
0x180026a8c  mov     edi, edx
0x180026a8e  mov     r12, rcx
0x180026a91  mov     rax, [rbp+40h+arg_20]
0x180026a95  mov     [rbp+40h+var_98], rax
0x180026a99  mov     rcx, [rbp+40h+arg_28]
0x180026a9d  mov     [rbp+40h+var_90], rcx
0x180026aa1  mov     rdx, [rbp+40h+arg_30]
0x180026aa8  mov     [rbp+40h+var_88], rdx
0x180026aac  mov     r8, [rbp+40h+arg_38]
0x180026ab3  mov     [rbp+40h+var_80], r8
0x180026ab7  test    r12, r12
0x180026aba  jz      loc_1800277A5
0x180026ac0  test    rbx, rbx
0x180026ac3  jz      loc_1800277A5
0x180026ac9  test    r9, r9
0x180026acc  jz      loc_1800277A5
0x180026ad2  test    rax, rax
0x180026ad5  jz      loc_1800277A5
0x180026adb  test    rcx, rcx
0x180026ade  jz      loc_1800277A5
0x180026ae4  test    rdx, rdx
0x180026ae7  jz      loc_1800277A5
0x180026aed  test    r8, r8
0x180026af0  jz      loc_1800277A5
0x180026af6  mov     rcx, r12; string2
0x180026af9  call    ?IsMediumCaller@@YA_NPEAUHSTRING__@@@Z; IsMediumCaller(HSTRING__ *)
0x180026afe  xor     r15d, r15d
0x180026b01  test    al, al
0x180026b03  cmovz   r15d, edi
0x180026b07  xor     edi, edi
0x180026b09  mov     [rbp+40h+var_A0], rdi
0x180026b0d  lea     rdx, [rbp+40h+var_A0]; struct Windows::Storage::Streams::IBuffer *
0x180026b11  mov     rcx, rbx; this
0x180026b14  call    ?DeSerializePropertySet@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIBuffer@Streams@Storage@5@PEAPEAUIPropertySet@Collections@Foundation@5@@Z; Windows::Internal::Security::Authentication::TokenBroker::DeSerializePropertySet(Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::IPropertySet * *)
0x180026b19  mov     ebx, eax
0x180026b1b  test    eax, eax
0x180026b1d  js      loc_180027673
0x180026b23  xorps   xmm0, xmm0
0x180026b26  movdqu  [rsp+140h+var_E8], xmm0
0x180026b2c  xorps   xmm1, xmm1
0x180026b2f  movdqu  xmmword ptr [rsp+140h+hMem], xmm1
0x180026b35  mov     [rsp+140h+var_C8], edi
0x180026b39  mov     [rsp+140h+var_C4], 1
0x180026b3e  mov     rsi, [rbp+40h+var_A0]
0x180026b42  mov     rdx, rsi; struct Windows::Foundation::Collections::IPropertySet *
0x180026b45  lea     rcx, [rsp+140h+var_E8]; this
0x180026b4a  call    ?InitializeFromPropertySet@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUIPropertySet@Collections@Foundation@4@@Z; Windows::Internal::Security::CPropertiesSerializer::InitializeFromPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180026b4f  mov     ebx, eax
0x180026b51  test    eax, eax
0x180026b53  js      loc_1800276FA
0x180026b59  mov     [rsp+140h+var_110], rdi
0x180026b5e  lea     rcx, [rsp+140h+var_110]
0x180026b63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026b68  lea     r9, [rbp+40h+string]; string
0x180026b6c  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x180026b70  lea     edx, [rdi+9]; length
0x180026b73  lea     rcx, aResponses; "responses"
0x180026b7a  call    cs:__imp_WindowsCreateStringReference
0x180026b80  test    eax, eax
0x180026b82  js      loc_1800276A7
0x180026b88  lea     r9, [rsp+140h+var_110]
0x180026b8d  mov     rdx, [rbp+40h+string]; HSTRING
0x180026b91  lea     rcx, [rsp+140h+var_E8]; this
0x180026b96  call    ??$GetVectorFromSerializer@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@P6AJPEAEKPEAPEAUIWebTokenResponse@23456@@Z@Security@Internal@Windows@@YAJAEAVCPropertiesSerializer@012@PEAUHSTRING__@@P6AJPEAEKPEAPEAUIWebTokenResponse@Core@Web@Authentication@02@@ZPEAPEAU?$IVector@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@Collections@Foundation@2@@Z; Windows::Internal::Security::GetVectorFromSerializer<Windows::Security::Authentication::Web::Core::WebTokenResponse *,long (*)(uchar *,ulong,Windows::Security::Authentication::Web::Core::IWebTokenResponse * *)>(Windows::Internal::Security::CPropertiesSerializer &,HSTRING__ *,long (*)(uchar *,ulong,Windows::Security::Authentication::Web::Core::IWebTokenResponse * *),Windows::Foundation::Collections::IVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *> * *)
0x180026b9b  mov     ebx, eax
0x180026b9d  cmp     eax, 8000000Bh
0x180026ba2  jz      loc_180026D69
0x180026ba8  test    eax, eax
0x180026baa  js      loc_180027023
0x180026bb0  mov     [rbp+40h+var_B8], edi
0x180026bb3  mov     rcx, [rsp+140h+var_110]
0x180026bb8  mov     rax, [rcx]
0x180026bbb  lea     rdx, [rbp+40h+var_B8]
0x180026bbf  mov     rax, [rax+38h]
0x180026bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bc8  mov     ebx, eax
0x180026bca  test    eax, eax
0x180026bcc  js      loc_18002709C
0x180026bd2  mov     r14d, edi
0x180026bd5  cmp     r14d, [rbp+40h+var_B8]
0x180026bd9  jnb     loc_180026DE0
0x180026bdf  mov     [rsp+140h+var_F8], rdi
0x180026be4  mov     rdi, [rsp+140h+var_110]
0x180026be9  mov     rax, [rdi]
0x180026bec  mov     rbx, [rax+30h]
0x180026bf0  lea     rcx, [rsp+140h+var_F8]
0x180026bf5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026bfa  lea     r8, [rsp+140h+var_F8]
0x180026bff  mov     edx, r14d
0x180026c02  mov     rcx, rdi
0x180026c05  mov     rax, rbx
0x180026c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c0d  mov     ebx, eax
0x180026c0f  xor     edi, edi
0x180026c11  test    eax, eax
0x180026c13  js      loc_180027293
0x180026c19  mov     [rsp+140h+var_F0], rdi
0x180026c1e  mov     rdi, [rsp+140h+var_F8]
0x180026c23  mov     rax, [rdi]
0x180026c26  mov     rbx, [rax+40h]
0x180026c2a  lea     rcx, [rsp+140h+var_F0]
0x180026c2f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026c34  lea     rdx, [rsp+140h+var_F0]
0x180026c39  mov     rcx, rdi
0x180026c3c  mov     rax, rbx
0x180026c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c44  mov     ebx, eax
0x180026c46  xor     edi, edi
0x180026c48  test    eax, eax
0x180026c4a  js      loc_180027738
0x180026c50  mov     rcx, [rsp+140h+var_F0]
0x180026c55  test    rcx, rcx
0x180026c58  jz      loc_180026D2E
0x180026c5e  mov     qword ptr [rsp+140h+var_108], rdi
0x180026c63  lea     rcx, [rsp+140h+var_108]
0x180026c68  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026c6d  lea     rax, [rsp+140h+var_108]
0x180026c72  mov     qword ptr [rsp+140h+var_120], rax; int
0x180026c77  mov     r9, r12
0x180026c7a  mov     r8d, r15d
0x180026c7d  mov     rdx, r13
0x180026c80  mov     rcx, [rsp+140h+var_F0]
0x180026c85  call    ?ReFindAccountWithContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccount@Credentials@35@PEAUIWebAccountProvider@735@W4AccountLookupContext@12345@PEAUHSTRING__@@PEAPEAU6735@@Z; Windows::Internal::Security::Authentication::TokenBroker::ReFindAccountWithContext(Windows::Security::Credentials::IWebAccount *,Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::Security::Authentication::TokenBroker::AccountLookupContext,HSTRING__ *,Windows::Security::Credentials::IWebAccount * *)
0x180026c8a  mov     ebx, eax
0x180026c8c  test    eax, eax
0x180026c8e  js      loc_1800274A4
0x180026c94  mov     [rsp+140h+var_100], rdi
0x180026c99  mov     rbx, [rsp+140h+var_F8]
0x180026c9e  mov     rax, [rbx]
0x180026ca1  mov     rdi, [rax]
0x180026ca4  lea     rcx, [rsp+140h+var_100]
0x180026ca9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026cae  lea     r8, [rsp+140h+var_100]
0x180026cb3  lea     rdx, _GUID_d9a260bf_ca96_4d92_af87_3d22326e66f5
0x180026cba  mov     rcx, rbx
0x180026cbd  mov     rax, rdi
0x180026cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cc5  mov     ebx, eax
0x180026cc7  xor     edi, edi
0x180026cc9  test    eax, eax
0x180026ccb  js      loc_18002758A
0x180026cd1  mov     rcx, [rsp+140h+var_100]
0x180026cd6  mov     rax, [rcx]
0x180026cd9  mov     rdx, qword ptr [rsp+140h+var_108]
0x180026cde  mov     rax, [rax+30h]
0x180026ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ce7  mov     ebx, eax
0x180026ce9  test    eax, eax
0x180026ceb  js      loc_180027328
0x180026cf1  mov     rcx, [rsp+140h+var_100]
0x180026cf6  test    rcx, rcx
0x180026cf9  jz      short loc_180026D0D
0x180026cfb  mov     [rsp+140h+var_100], rdi
0x180026d00  mov     rax, [rcx]
0x180026d03  mov     rax, [rax+10h]
0x180026d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d0c  nop
0x180026d0d  mov     rcx, qword ptr [rsp+140h+var_108]
0x180026d12  test    rcx, rcx
0x180026d15  jz      short loc_180026D29
0x180026d17  mov     qword ptr [rsp+140h+var_108], rdi
0x180026d1c  mov     rax, [rcx]
0x180026d1f  mov     rax, [rax+10h]
0x180026d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d28  nop
0x180026d29  mov     rcx, [rsp+140h+var_F0]
0x180026d2e  test    rcx, rcx
0x180026d31  jz      short loc_180026D45
0x180026d33  mov     [rsp+140h+var_F0], rdi
0x180026d38  mov     rax, [rcx]
0x180026d3b  mov     rax, [rax+10h]
0x180026d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d44  nop
0x180026d45  mov     rcx, [rsp+140h+var_F8]
0x180026d4a  test    rcx, rcx
0x180026d4d  jz      short loc_180026D61
0x180026d4f  mov     [rsp+140h+var_F8], rdi
0x180026d54  mov     rax, [rcx]
0x180026d57  mov     rax, [rax+10h]
0x180026d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d60  nop
0x180026d61  inc     r14d
0x180026d64  jmp     loc_180026BD5
0x180026d69  mov     [rsp+140h+var_100], rdi
0x180026d6e  lea     rcx, [rsp+140h+var_100]
0x180026d73  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026d78  lea     rdx, [rsp+140h+var_100]
0x180026d7d  call    ??$CreateExternalObjectVector@VWebTokenResponse@Core@Web@Authentication@Security@Windows@@V?$AgileVector@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@89Foundation@6@$0A@@Internal@Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWebTokenResponse@Core@Web@Authentication@Security@Windows@@@89Foundation@6@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::Web::Core::WebTokenResponse,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Core::WebTokenResponse *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Core::WebTokenResponse *>,0> * *)
0x180026d82  mov     ebx, eax
0x180026d84  test    eax, eax
0x180026d86  js      loc_180027161
0x180026d8c  mov     rbx, [rsp+140h+var_100]
0x180026d91  mov     rax, [rbx]
0x180026d94  mov     rdi, [rax]
0x180026d97  lea     rcx, [rsp+140h+var_110]
0x180026d9c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026da1  lea     r8, [rsp+140h+var_110]
0x180026da6  lea     rdx, _GUID_58dc4e4c_a84d_5ad6_a6d9_6ee477329c9f
0x180026dad  mov     rcx, rbx
0x180026db0  mov     rax, rdi
0x180026db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026db8  mov     ebx, eax
0x180026dba  xor     edi, edi
0x180026dbc  test    eax, eax
0x180026dbe  js      loc_180027714
0x180026dc4  mov     rcx, [rsp+140h+var_100]
0x180026dc9  test    rcx, rcx
0x180026dcc  jz      short loc_180026DE0
0x180026dce  mov     [rsp+140h+var_100], rdi
0x180026dd3  mov     rax, [rcx]
0x180026dd6  mov     rax, [rax+10h]
0x180026dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ddf  nop
0x180026de0  mov     r14d, edi
0x180026de3  lea     r9, [rbp+40h+var_58]; string
0x180026de7  lea     r8, [rbp+40h+var_50]; hstringHeader
0x180026deb  mov     edx, 6; length
0x180026df0  lea     rcx, aStatus; "status"
0x180026df7  call    cs:__imp_WindowsCreateStringReference
0x180026dfd  mov     r12d, 1
0x180026e03  test    eax, eax
0x180026e05  js      loc_1800276C1
0x180026e0b  mov     rdx, [rbp+40h+var_58]
0x180026e0f  mov     [rsp+140h+var_108], edi
0x180026e13  mov     [rbp+40h+var_B0], rdi
0x180026e17  mov     [rbp+40h+var_A8], edi
0x180026e1a  mov     ebx, 80070057h
0x180026e1f  test    rdx, rdx
0x180026e22  jz      loc_1800276F3
0x180026e28  mov     rcx, qword ptr [rsp+140h+var_E8+8]
0x180026e2d  mov     rax, [rcx]
0x180026e30  lea     r8, [rbp+40h+var_B0]
0x180026e34  mov     [rbp+40h+string], r8
0x180026e38  mov     qword ptr [rbp+40h+hstringHeader.Reserved], rdi
0x180026e3c  lea     r8, [rbp+40h+hstringHeader]
0x180026e40  mov     rax, [rax+30h]
0x180026e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e49  mov     edi, eax
0x180026e4b  lea     rcx, [rbp+40h+string]; this
0x180026e4f  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180026e54  mov     eax, edi
0x180026e56  shr     eax, 1Fh
0x180026e59  xor     al, r12b
0x180026e5c  jnz     loc_180027115
0x180026e62  lea     rcx, [rbp+40h+var_B0]; this
0x180026e66  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180026e6b  xor     r15d, r15d
0x180026e6e  test    edi, edi
0x180026e70  js      loc_180027218
0x180026e76  mov     edi, r15d
0x180026e79  lea     r9, [rbp+40h+var_58]; string
0x180026e7d  lea     r8, [rbp+40h+var_50]; hstringHeader
0x180026e81  lea     edx, [r15+0Ah]; length
0x180026e85  lea     rcx, aExpiration; "expiration"
0x180026e8c  call    cs:__imp_WindowsCreateStringReference
0x180026e92  test    eax, eax
0x180026e94  js      loc_180027571
0x180026e9a  mov     rdx, [rbp+40h+var_58]
0x180026e9e  mov     qword ptr [rsp+140h+var_108], r15
0x180026ea3  mov     [rbp+40h+var_B0], r15
0x180026ea7  mov     [rbp+40h+var_A8], r15d
0x180026eab  test    rdx, rdx
0x180026eae  jz      short loc_180026F26
0x180026eb0  mov     rcx, qword ptr [rsp+140h+var_E8+8]
0x180026eb5  mov     rax, [rcx]
0x180026eb8  lea     r8, [rbp+40h+var_B0]
0x180026ebc  mov     [rbp+40h+string], r8
0x180026ec0  mov     qword ptr [rbp+40h+hstringHeader.Reserved], r15
0x180026ec4  lea     r8, [rbp+40h+hstringHeader]
0x180026ec8  mov     rax, [rax+30h]
0x180026ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ed1  mov     ebx, eax
0x180026ed3  lea     rcx, [rbp+40h+string]; this
0x180026ed7  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180026edc  mov     ecx, ebx
0x180026ede  shr     ecx, 1Fh
0x180026ee1  xor     cl, r12b
0x180026ee4  jz      short loc_180026F26
0x180026ee6  mov     r8, [rbp+40h+var_B0]
0x180026eea  mov     [rbp+40h+string], r8
0x180026eee  mov     eax, [rbp+40h+var_A8]
0x180026ef1  mov     dword ptr [rbp+40h+hstringHeader.Reserved], eax
0x180026ef4  mov     qword ptr [rsp+140h+var_108], r15
0x180026ef9  lea     rcx, [rbp+40h+string]; this
0x180026efd  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
  ... truncated ...
```
