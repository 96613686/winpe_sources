# Windows::Internal::Security::Authentication::TokenBroker::PluginManagerInternal::InvokeToAddAccount(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,uint,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x1800bf168`
- end: `0x1800bf822`
- name: `?InvokeToAddAccount@PluginManagerInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@IPEAUIPropertySet@Collections@Foundation@6@@Z`
- size: `1722`
- prototype: `static int(struct Windows::Internal::Security::Authentication::Web::CallerContext *, struct Windows::Security::Credentials::IWebAccountProvider *, unsigned int, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ba518`
- `0x1800ba95c`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180040980`
- `0x1800412e0`
- `0x18004e850`
- `0x180063fc4`
- `0x180081df0`
- `0x180083a54`
- `0x18008e690`
- `0x18008fccc`
- `0x18009b954`
- `0x1800a2cb4`
- `0x1800a2d04`
- `0x1800a3e98`
- `0x1800a3edc`
- `0x1800b3c18`
- `0x1800bf168`
- `0x1800e3f2c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf26b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf65f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf7d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf7ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf26b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf65f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf679`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf7d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf7ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800bf1d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800bf1d7`
- `ext-ms-win-webtokenrequest-win32-l1-1-0!InvokePluginAsWin32` at `0x1800bf454`
- `ext-ms-win-webtokenrequest-win32-l1-1-0!InvokePluginAsWin32` at `0x1800bf454`

## string_xrefs

- `0x1800bf235`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bf2ae`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bf350`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bf399`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bf3f8`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bf470`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bf4c0`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bf605`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bf494`: `Windows.Internal.PlatformExtensions.TokenBrokerExperience`
- `0x1800bf5bb`: `Windows.Internal.PlatformExtensions.TokenBrokerExperience`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginManagerInternal::InvokeToAddAccount(
        struct Windows::Internal::Security::Authentication::Web::CallerContext *a1,
        struct Windows::Security::Credentials::IWebAccountProvider *a2,
        int a3,
        struct Windows::Foundation::Collections::IPropertySet *a4)
{
  __int64 v4; // r15
  struct Windows::Internal::String *v7; // r8
  int v8; // r9d
  PCWSTR StringRawBuffer; // rax
  int AumId; // eax
  int ExtensionForProvider; // ebx
  char v13; // si
  __int64 WindowSizeForWebAccountProviderOperation; // rax
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  HSTRING v20; // rbx
  int v21; // edi
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 *v24; // rdi
  __int64 v25; // rdx
  __int64 v26; // rax
  bool v27; // zf
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64 *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING, __int64); // r14
  __int64 (__fastcall *v30)(__int64 *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING, __int64); // r14
  __int64 *v31; // rdi
  __int64 v32; // rax
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64 *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING, __int64); // r14
  __int64 (__fastcall *v35)(__int64 *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING, __int64); // r14
  __int64 v36; // r8
  int v37; // r9d
  int v38; // [rsp+28h] [rbp-B9h]
  __int64 *v39; // [rsp+48h] [rbp-99h] BYREF
  HSTRING string; // [rsp+50h] [rbp-91h] BYREF
  void *v41; // [rsp+58h] [rbp-89h] BYREF
  int v42[2]; // [rsp+60h] [rbp-81h] BYREF
  __int64 v43; // [rsp+68h] [rbp-79h] BYREF
  __int64 v44; // [rsp+70h] [rbp-71h] BYREF
  HSTRING v45; // [rsp+78h] [rbp-69h] BYREF
  __int64 v46; // [rsp+80h] [rbp-61h] BYREF
  __int64 v47; // [rsp+88h] [rbp-59h] BYREF
  int v48; // [rsp+90h] [rbp-51h] BYREF
  __int64 v49; // [rsp+98h] [rbp-49h]
  __int64 v50; // [rsp+A8h] [rbp-39h] BYREF
  _QWORD v51[2]; // [rsp+B0h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-21h] BYREF
  struct Windows::Foundation::Collections::IPropertySet **v53; // [rsp+D8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+5Fh]
  struct Windows::Foundation::Collections::IPropertySet *v55; // [rsp+160h] [rbp+7Fh] BYREF

  v55 = a4;
  v4 = a3;
  v45 = 0;
  v46 = 0;
  string = 0;
  (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *))(*(_QWORD *)a2 + 48LL))(
    a2,
    &string);
  if ( (unsigned int)dword_180175000 > 5 )
  {
    if ( WindowsIsStringEmpty(string) )
      StringRawBuffer = L"null";
    else
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    *(_QWORD *)v42 = StringRawBuffer;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_180175000,
      (unsigned int)byte_18014E9B3,
      0,
      v8,
      (__int64)v42);
  }
  AumId = Windows::Internal::Security::Authentication::Web::GetAumId(
            a2,
            (struct Windows::Security::Credentials::IWebAccountProvider *)&v45,
            v7);
  ExtensionForProvider = AumId;
  if ( AumId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x702,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)AumId,
      v38);
LABEL_8:
    if ( string )
      WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    if ( v45 )
      WindowsDeleteString(v45);
    return (unsigned int)ExtensionForProvider;
  }
  v44 = 0;
  LOBYTE(v42[1]) = 0;
  ExtensionForProvider = Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionForProvider(
                           a2,
                           (__int64)&v44,
                           *(__int64 *)v42);
  if ( (int)(ExtensionForProvider + 0x80000000) >= 0 && ExtensionForProvider != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x709,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)ExtensionForProvider,
      v38);
LABEL_16:
    std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(&v44);
    goto LABEL_8;
  }
  v13 = 0;
  if ( v44 )
  {
    WindowSizeForWebAccountProviderOperation = Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::GetWindowSizeForWebAccountProviderOperation(
                                                 v44,
                                                 v51,
                                                 2);
    v49 = *(_QWORD *)WindowSizeForWebAccountProviderOperation;
    v13 = *(_BYTE *)(WindowSizeForWebAccountProviderOperation + 8);
  }
  *(_QWORD *)v42 = 0;
  v41 = 0;
  v51[0] = 0;
  v50 = 0;
  v48 = 2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  hstringHeader.Reserved.Reserved1 = &v48;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v50;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = v51;
  v53 = &v55;
  v17 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<Windows::Security::Authentication::Web::Provider::CWebAccountProviderActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_>(
          v16,
          v15,
          &v41,
          (__int64)&hstringHeader);
  ExtensionForProvider = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v17,
      v38);
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
    goto LABEL_16;
  }
  v47 = 0;
  ExtensionForProvider = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>(
                           (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v41,
                           (__int64)&v47);
  if ( ExtensionForProvider < 0 )
  {
    v18 = 1824;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)ExtensionForProvider,
      v38);
LABEL_25:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    goto LABEL_21;
  }
  ExtensionForProvider = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 56LL))(v47, *((_QWORD *)a1 + 1));
  if ( ExtensionForProvider < 0 )
  {
    v18 = 1825;
    goto LABEL_24;
  }
  v43 = 0;
  v19 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<IInspectable>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v41,
          (__int64)&v43);
  ExtensionForProvider = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x725,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v19,
      v38);
LABEL_30:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    goto LABEL_25;
  }
  v39 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)IsInvokePluginAsWin32Present() )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      v20 = v45;
      v21 = InvokePluginAsWin32(v45, v43, v4, &v39);
      if ( v21 < 0 )
      {
        v22 = 1839;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
          (const char *)(unsigned int)v21,
          v38);
LABEL_64:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
        std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(&v44);
        if ( string )
          WindowsDeleteString(string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        if ( v20 )
          WindowsDeleteString(v20);
        return (unsigned int)v21;
      }
      goto LABEL_60;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v53 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.PlatformExtensions.TokenBrokerExperience",
      0x3Au,
      0x39u);
    ExtensionForProvider = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract>(
                             v53,
                             &v39,
                             (unsigned int)v4);
    if ( ExtensionForProvider < 0 )
    {
      v23 = 1846;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)ExtensionForProvider,
        v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      goto LABEL_30;
    }
    v24 = v39;
    if ( v39 )
    {
      v26 = *v39;
      v20 = v45;
      v53 = 0;
      v27 = v13 == 0;
      v28 = v43;
      if ( v27 )
      {
        v30 = *(__int64 (__fastcall **)(__int64 *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING, __int64))(v26 + 48);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.WebAccountProvider",
          0x1Bu,
          0x1Au);
        v38 = v4;
        v21 = v30(v24, v53, v20, v28);
        if ( v21 < 0 )
        {
          v22 = 1864;
          goto LABEL_35;
        }
      }
      else
      {
        v29 = *(__int64 (__fastcall **)(__int64 *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING, __int64))(v26 + 56);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.WebAccountProvider",
          0x1Bu,
          0x1Au);
        v38 = v4;
        v21 = v29(v24, v53, v20, v28);
        if ( v21 < 0 )
        {
          v22 = 1856;
          goto LABEL_35;
        }
      }
LABEL_60:
      v21 = (*(__int64 (__fastcall **)(__int64 *))(*v39 + 64))(v39);
      if ( v21 < 0
        && (unsigned int)dword_180175000 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_180175000, 0x400000000000LL, v36) )
      {
        v48 = v21;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180175000,
          (unsigned int)&dword_18014E984,
          0,
          v37,
          (__int64)&v48);
      }
      goto LABEL_64;
    }
    v25 = 1847;
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v53 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.PlatformExtensions.TokenBrokerExperience",
      0x3Au,
      0x39u);
    ExtensionForProvider = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract>(
                             v53,
                             &v39,
                             (unsigned int)v4);
    if ( ExtensionForProvider < 0 )
    {
      v23 = 1873;
      goto LABEL_38;
    }
    v31 = v39;
    if ( v39 )
    {
      v32 = *v39;
      v20 = v45;
      v53 = 0;
      v27 = v13 == 0;
      v33 = v43;
      if ( v27 )
      {
        v35 = *(__int64 (__fastcall **)(__int64 *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING, __int64))(v32 + 48);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.WebAccountProvider",
          0x1Bu,
          0x1Au);
        v38 = v4;
        v21 = v35(v31, v53, v20, v33);
        if ( v21 < 0 )
        {
          v22 = 1891;
          goto LABEL_35;
        }
      }
      else
      {
        v34 = *(__int64 (__fastcall **)(__int64 *, struct Windows::Foundation::Collections::IPropertySet **, HSTRING, __int64))(v32 + 56);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.WebAccountProvider",
          0x1Bu,
          0x1Au);
        v38 = v4;
        v21 = v34(v31, v53, v20, v33);
        if ( v21 < 0 )
        {
          v22 = 1883;
          goto LABEL_35;
        }
      }
      goto LABEL_60;
    }
    v25 = 1874;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
    (const char *)0x80004001LL,
    v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
  std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(&v44);
  if ( string )
    WindowsDeleteString(string);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  if ( v45 )
    WindowsDeleteString(v45);
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800bf168  mov     rax, rsp
0x1800bf16b  mov     [rax+20h], r9
0x1800bf16f  push    rbp
0x1800bf170  push    rbx
0x1800bf171  push    rsi
0x1800bf172  push    rdi
0x1800bf173  push    r12
0x1800bf175  push    r14
0x1800bf177  push    r15
0x1800bf179  lea     rbp, [rax-5Fh]
0x1800bf17d  sub     rsp, 100h
0x1800bf184  movaps  xmmword ptr [rax-48h], xmm6
0x1800bf188  movaps  xmmword ptr [rax-58h], xmm7
0x1800bf18c  mov     rax, cs:__security_cookie
0x1800bf193  xor     rax, rsp
0x1800bf196  mov     [rbp+57h+var_58], rax
0x1800bf19a  movsxd  r15, r8d
0x1800bf19d  mov     rdi, rdx
0x1800bf1a0  mov     r14, rcx
0x1800bf1a3  xor     r12d, r12d
0x1800bf1a6  mov     [rbp+57h+var_C0], r12
0x1800bf1aa  mov     [rbp+57h+var_B8], r12
0x1800bf1ae  mov     [rsp+130h+string], r12
0x1800bf1b3  mov     rax, [rdx]
0x1800bf1b6  lea     rdx, [rsp+130h+string]
0x1800bf1bb  mov     rcx, rdi
0x1800bf1be  mov     rax, [rax+30h]
0x1800bf1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf1c7  mov     eax, cs:dword_180175000
0x1800bf1cd  cmp     eax, 5
0x1800bf1d0  jbe     short loc_1800BF21C
0x1800bf1d2  mov     rcx, [rsp+130h+string]; string
0x1800bf1d7  call    cs:__imp_WindowsIsStringEmpty
0x1800bf1dd  test    eax, eax
0x1800bf1df  jz      short loc_1800BF1EA
0x1800bf1e1  lea     rax, aNull; "null"
0x1800bf1e8  jmp     short loc_1800BF1F7
0x1800bf1ea  xor     edx, edx; length
0x1800bf1ec  mov     rcx, [rsp+130h+string]; string
0x1800bf1f1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bf1f7  mov     [rsp+58h], rax
0x1800bf1fc  lea     rax, [rsp+130h+var_D8]
0x1800bf201  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800bf206  xor     r8d, r8d
0x1800bf209  lea     rdx, byte_18014E9B3
0x1800bf210  lea     rcx, dword_180175000
0x1800bf217  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800bf21c  lea     rdx, [rbp+57h+var_C0]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800bf220  mov     rcx, rdi; this
0x1800bf223  call    ?GetAumId@Web@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@35@AEAVString@45@@Z; Windows::Internal::Security::Authentication::Web::GetAumId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &)
0x1800bf228  mov     ebx, eax
0x1800bf22a  test    eax, eax
0x1800bf22c  jns     short loc_1800BF278
0x1800bf22e  mov     rcx, [rbp+5Fh]; this
0x1800bf232  mov     r9d, eax; char *
0x1800bf235  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bf23c  mov     edx, 702h; void *
0x1800bf241  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf246  nop
0x1800bf247  mov     rcx, [rsp+130h+string]; string
0x1800bf24c  test    rcx, rcx
0x1800bf24f  jz      short loc_1800BF258
0x1800bf251  call    cs:__imp_WindowsDeleteString
0x1800bf257  nop
0x1800bf258  lea     rcx, [rbp+57h+var_B8]
0x1800bf25c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf261  nop
0x1800bf262  mov     rcx, [rbp+57h+var_C0]; string
0x1800bf266  test    rcx, rcx
0x1800bf269  jz      short loc_1800BF271
0x1800bf26b  call    cs:__imp_WindowsDeleteString
0x1800bf271  mov     eax, ebx
0x1800bf273  jmp     loc_1800BF7F6
0x1800bf278  mov     [rbp+57h+var_C8], r12
0x1800bf27c  mov     byte ptr [rbp+57h+var_D8+4], r12b
0x1800bf280  mov     r8, qword ptr [rsp+130h+var_D8]
0x1800bf285  lea     rdx, [rbp+57h+var_C8]
0x1800bf289  mov     rcx, rdi; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800bf28c  call    ?FindExtensionForProvider@SystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAV?$unique_ptr@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@V?$optional@W4ExtensionType@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@Z; Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::FindExtensionForProvider(Windows::Security::Credentials::IWebAccountProvider *,std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension> &,std::optional<Windows::Internal::Security::Authentication::TokenBroker::ExtensionType>)
0x1800bf291  mov     ebx, eax
0x1800bf293  mov     eax, 80000000h
0x1800bf298  lea     ecx, [rbx+rax]
0x1800bf29b  test    eax, ecx
0x1800bf29d  jnz     short loc_1800BF2CE
0x1800bf29f  cmp     ebx, 80070002h
0x1800bf2a5  jz      short loc_1800BF2CE
0x1800bf2a7  mov     rcx, [rbp+5Fh]; this
0x1800bf2ab  mov     r9d, ebx; char *
0x1800bf2ae  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bf2b5  mov     edx, 709h; void *
0x1800bf2ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf2bf  nop
0x1800bf2c0  lea     rcx, [rbp+57h+var_C8]
0x1800bf2c4  call    ??1?$unique_ptr@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@U?$default_delete@VSystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::SystemExtension>(void)
0x1800bf2c9  jmp     loc_1800BF247
0x1800bf2ce  mov     sil, r12b
0x1800bf2d1  mov     ebx, 2
0x1800bf2d6  mov     rcx, [rbp+57h+var_C8]
0x1800bf2da  test    rcx, rcx
0x1800bf2dd  jz      short loc_1800BF2F6
0x1800bf2df  mov     r8d, ebx
0x1800bf2e2  lea     rdx, [rbp+57h+var_88]
0x1800bf2e6  call    ?GetWindowSizeForWebAccountProviderOperation@SystemExtension@TokenBroker@Authentication@Security@Internal@Windows@@QEAA?AV?$optional@USize@Foundation@Windows@@@std@@W4WebAccountProviderOperationKind@Provider@Web@346@@Z; Windows::Internal::Security::Authentication::TokenBroker::SystemExtension::GetWindowSizeForWebAccountProviderOperation(Windows::Security::Authentication::Web::Provider::WebAccountProviderOperationKind)
0x1800bf2eb  mov     rcx, [rax]
0x1800bf2ee  mov     [rbp+57h+var_A0], rcx
0x1800bf2f2  mov     sil, [rax+8]
0x1800bf2f6  mov     qword ptr [rsp+130h+var_D8], r12
0x1800bf2fb  mov     [rsp+130h+var_E0], r12
0x1800bf300  mov     [rbp+57h+var_88], r12
0x1800bf304  mov     [rbp+57h+var_90], r12
0x1800bf308  mov     [rbp+57h+var_A8], ebx
0x1800bf30b  lea     rcx, [rsp+130h+var_E0]
0x1800bf310  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf315  lea     rax, [rbp+57h+var_A8]
0x1800bf319  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800bf31d  lea     rax, [rbp+57h+var_90]
0x1800bf321  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x1800bf325  lea     rax, [rbp+57h+var_88]
0x1800bf329  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x1800bf32d  lea     rax, [rbp+57h+arg_18]
0x1800bf331  mov     [rbp+57h+var_60], rax
0x1800bf335  lea     r9, [rbp+57h+hstringHeader]
0x1800bf339  lea     r8, [rsp+130h+var_E0]
0x1800bf33e  call    ??$_MakeAndInitializeOnSTAThread@VCWebAccountProviderActivatedEventArgs@Provider@Web@Authentication@Security@Windows@@UIActivatedEventArgs@Activation@ApplicationModel@6@V_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_@@@Z; Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<Windows::Security::Authentication::Web::Provider::CWebAccountProviderActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_f570e3bbb038c7d48dd55e7fafb2e1c1_ const &)
0x1800bf343  mov     ebx, eax
0x1800bf345  test    eax, eax
0x1800bf347  jns     short loc_1800BF37C
0x1800bf349  mov     rcx, [rbp+5Fh]; this
0x1800bf34d  mov     r9d, eax; char *
0x1800bf350  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bf357  mov     edx, 71Dh; void *
0x1800bf35c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf361  nop
0x1800bf362  lea     rcx, [rsp+130h+var_E0]
0x1800bf367  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf36c  nop
0x1800bf36d  lea     rcx, [rsp+130h+var_D8]
0x1800bf372  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf377  jmp     loc_1800BF2C0
0x1800bf37c  mov     [rbp+57h+var_B0], r12
0x1800bf380  lea     rdx, [rbp+57h+var_B0]
0x1800bf384  lea     rcx, [rsp+130h+var_E0]
0x1800bf389  call    ??$As@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIActivatedEventArgsInternal@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgsInternal>>)
0x1800bf38e  mov     ebx, eax
0x1800bf390  test    eax, eax
0x1800bf392  jns     short loc_1800BF3B8
0x1800bf394  mov     edx, 720h; void *
0x1800bf399  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bf3a0  mov     r9d, ebx; char *
0x1800bf3a3  mov     rcx, [rbp+5Fh]; this
0x1800bf3a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf3ac  nop
0x1800bf3ad  lea     rcx, [rbp+57h+var_B0]
0x1800bf3b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf3b6  jmp     short loc_1800BF362
0x1800bf3b8  mov     rcx, [rbp+57h+var_B0]
0x1800bf3bc  mov     rax, [rcx]
0x1800bf3bf  mov     rdx, [r14+8]
0x1800bf3c3  mov     rax, [rax+38h]
0x1800bf3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf3cc  mov     ebx, eax
0x1800bf3ce  test    eax, eax
0x1800bf3d0  jns     short loc_1800BF3D9
0x1800bf3d2  mov     edx, 721h
0x1800bf3d7  jmp     short loc_1800BF399
0x1800bf3d9  mov     [rbp+57h+var_D0], r12
0x1800bf3dd  lea     rdx, [rbp+57h+var_D0]
0x1800bf3e1  lea     rcx, [rsp+130h+var_E0]
0x1800bf3e6  call    ??$As@UIInspectable@@@?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInspectable@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<IInspectable>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInspectable>>)
0x1800bf3eb  mov     ebx, eax
0x1800bf3ed  test    eax, eax
0x1800bf3ef  jns     short loc_1800BF415
0x1800bf3f1  mov     rcx, [rbp+5Fh]; this
0x1800bf3f5  mov     r9d, eax; char *
0x1800bf3f8  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bf3ff  mov     edx, 725h; void *
0x1800bf404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf409  nop
0x1800bf40a  lea     rcx, [rbp+57h+var_D0]
0x1800bf40e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf413  jmp     short loc_1800BF3AD
0x1800bf415  mov     [rsp+130h+var_F0], r12
0x1800bf41a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WAMPluginWin32Activation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WAMPluginWin32Activation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WAMPluginWin32Activation> `wil::Feature<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::GetImpl(void)'::`2'::impl
0x1800bf421  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WAMPluginWin32Activation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WAMPluginWin32Activation>::__private_IsEnabled(void)
0x1800bf426  test    al, al
0x1800bf428  jz      loc_1800BF5A3
0x1800bf42e  call    IsInvokePluginAsWin32Present
0x1800bf433  lea     rcx, [rsp+130h+var_F0]
0x1800bf438  test    al, al
0x1800bf43a  jz      short loc_1800BF481
0x1800bf43c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf441  mov     r8, r15
0x1800bf444  lea     r9, [rsp+130h+var_F0]
0x1800bf449  mov     rdx, [rbp+57h+var_D0]
0x1800bf44d  mov     rbx, [rbp+57h+var_C0]
0x1800bf451  mov     rcx, rbx
0x1800bf454  call    cs:__imp_InvokePluginAsWin32
0x1800bf45a  mov     edi, eax
0x1800bf45c  test    eax, eax
0x1800bf45e  jns     loc_1800BF72D
0x1800bf464  mov     edx, 72Fh; void *
0x1800bf469  mov     rcx, [rbp+5Fh]; this
0x1800bf46d  mov     r9d, edi; char *
0x1800bf470  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bf477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf47c  jmp     loc_1800BF78C
0x1800bf481  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf486  mov     [rbp+57h+var_60], r12
0x1800bf48a  mov     r9d, 39h ; '9'; unsigned int
0x1800bf490  lea     r8d, [r9+1]; unsigned int
0x1800bf494  lea     rdx, aWindowsInterna_36; "Windows.Internal.PlatformExtensions.Tok"...
0x1800bf49b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800bf49f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800bf4a4  mov     r8d, r15d
0x1800bf4a7  lea     rdx, [rsp+130h+var_F0]
0x1800bf4ac  mov     rcx, [rbp+57h+var_60]
0x1800bf4b0  call    ??$TryActivateContractExtension@UITokenBrokerExperienceContract@PlatformExtensions@Internal@Windows@@@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAPEAUITokenBrokerExperienceContract@012@UWindowId@WindowManagement@ApplicationModel@12@@Z; Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract>(HSTRING__ *,Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x1800bf4b5  mov     ebx, eax
0x1800bf4b7  test    eax, eax
0x1800bf4b9  jns     short loc_1800BF4E3
0x1800bf4bb  mov     edx, 736h; void *
0x1800bf4c0  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bf4c7  mov     r9d, ebx; char *
0x1800bf4ca  mov     rcx, [rbp+5Fh]; this
0x1800bf4ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf4d3  nop
0x1800bf4d4  lea     rcx, [rsp+130h+var_F0]
0x1800bf4d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf4de  jmp     loc_1800BF40A
0x1800bf4e3  mov     rdi, [rsp+130h+var_F0]
0x1800bf4e8  test    rdi, rdi
0x1800bf4eb  jnz     short loc_1800BF4F7
0x1800bf4ed  mov     edx, 737h
0x1800bf4f2  jmp     loc_1800BF5FF
0x1800bf4f7  mov     rax, [rdi]
0x1800bf4fa  mov     rbx, [rbp+57h+var_C0]
0x1800bf4fe  mov     r9d, 1Ah; unsigned int
0x1800bf504  lea     r8d, [r9+1]; unsigned int
0x1800bf508  lea     rdx, aWindowsWebacco_0; "Windows.WebAccountProvider"
0x1800bf50f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800bf513  mov     [rbp+57h+var_60], r12
0x1800bf517  test    sil, sil
0x1800bf51a  mov     rsi, [rbp+57h+var_D0]
0x1800bf51e  jz      short loc_1800BF56B
0x1800bf520  mov     r14, [rax+38h]
0x1800bf524  movss   xmm7, dword ptr [rbp+57h+var_A0]
0x1800bf529  movss   xmm6, dword ptr [rbp+57h+var_A0+4]
0x1800bf52e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800bf533  nop
0x1800bf534  unpcklps xmm7, xmm6
0x1800bf537  movsd   [rsp+130h+var_108], xmm7
0x1800bf53d  mov     [rsp+130h+var_110], r15d
0x1800bf542  mov     r9, rsi
0x1800bf545  mov     r8, rbx
0x1800bf548  mov     rdx, [rbp+57h+var_60]
0x1800bf54c  mov     rcx, rdi
0x1800bf54f  mov     rax, r14
0x1800bf552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf557  mov     edi, eax
0x1800bf559  test    eax, eax
0x1800bf55b  jns     loc_1800BF72D
0x1800bf561  mov     edx, 740h
0x1800bf566  jmp     loc_1800BF469
0x1800bf56b  mov     r14, [rax+30h]
0x1800bf56f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800bf574  nop
0x1800bf575  mov     [rsp+130h+var_110], r15d
0x1800bf57a  mov     r9, rsi
0x1800bf57d  mov     r8, rbx
0x1800bf580  mov     rdx, [rbp+57h+var_60]
0x1800bf584  mov     rcx, rdi
0x1800bf587  mov     rax, r14
0x1800bf58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf58f  mov     edi, eax
0x1800bf591  test    eax, eax
0x1800bf593  jns     loc_1800BF72D
0x1800bf599  mov     edx, 748h
0x1800bf59e  jmp     loc_1800BF469
0x1800bf5a3  lea     rcx, [rsp+130h+var_F0]
0x1800bf5a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf5ad  mov     [rbp+57h+var_60], r12
0x1800bf5b1  mov     r9d, 39h ; '9'; unsigned int
0x1800bf5b7  lea     r8d, [r9+1]; unsigned int
0x1800bf5bb  lea     rdx, aWindowsInterna_36; "Windows.Internal.PlatformExtensions.Tok"...
0x1800bf5c2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800bf5c6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800bf5cb  mov     r8d, r15d
0x1800bf5ce  lea     rdx, [rsp+130h+var_F0]
0x1800bf5d3  mov     rcx, [rbp+57h+var_60]
0x1800bf5d7  call    ??$TryActivateContractExtension@UITokenBrokerExperienceContract@PlatformExtensions@Internal@Windows@@@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAPEAUITokenBrokerExperienceContract@012@UWindowId@WindowManagement@ApplicationModel@12@@Z; Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract>(HSTRING__ *,Windows::Internal::PlatformExtensions::ITokenBrokerExperienceContract * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x1800bf5dc  mov     ebx, eax
0x1800bf5de  test    eax, eax
0x1800bf5e0  jns     short loc_1800BF5EC
0x1800bf5e2  mov     edx, 751h
0x1800bf5e7  jmp     loc_1800BF4C0
0x1800bf5ec  mov     rdi, [rsp+130h+var_F0]
0x1800bf5f1  test    rdi, rdi
0x1800bf5f4  jnz     loc_1800BF689
0x1800bf5fa  mov     edx, 752h; void *
0x1800bf5ff  mov     r9d, 80004001h; char *
  ... truncated ...
```
