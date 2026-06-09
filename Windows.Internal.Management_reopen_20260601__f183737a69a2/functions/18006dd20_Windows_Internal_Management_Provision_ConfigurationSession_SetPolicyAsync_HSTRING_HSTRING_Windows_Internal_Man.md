# Windows::Internal::Management::Provision::ConfigurationSession::SetPolicyAsync(HSTRING__ *,HSTRING__ *,Windows::Internal::Management::Provision::IConfigurationData *,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::ConfigurationResult *> * *)

- ea: `0x18006dd20`
- end: `0x18006e243`
- name: `?SetPolicyAsync@ConfigurationSession@Provision@Management@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAUIConfigurationData@2345@PEAPEAU?$IAsyncOperation@PEAVConfigurationResult@Provision@Management@Internal@Windows@@@Foundation@5@@Z`
- size: `1315`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009be4`
- `0x18000a5c4`
- `0x180017298`
- `0x180017860`
- `0x1800179f8`
- `0x180017b70`
- `0x180017bf0`
- `0x1800184e8`
- `0x180018738`
- `0x1800187d4`
- `0x18006b94c`
- `0x18006bb24`
- `0x18006bc68`
- `0x18006bd3c`
- `0x18006bf9c`
- `0x18006c368`
- `0x18006c9cc`
- `0x18006d3e8`
- `0x18006dd20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006deac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006df32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006dfb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006e142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006deac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006df32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006dfb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006e142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006dd5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006dd72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006dd9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ddb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ddcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e031`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e05c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006dd5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006dd72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006dd9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ddb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ddcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e031`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006e05c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006e0e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006e0e4`

## string_xrefs

- `0x18006de0c`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006de45`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006dec2`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006df48`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006dfc9`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e0a4`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006e1d8`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`

## pseudocode

```c
__int64 Windows::Internal::Management::Provision::ConfigurationSession::SetPolicyAsync(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        ...)
{
  BOOL v5; // edi
  wchar_t *StringRawBuffer; // rbx
  const unsigned __int16 *v8; // rax
  unsigned int v9; // ebx
  const WCHAR *v10; // rax
  HSTRING v11; // rcx
  PCWSTR v12; // rax
  bool v13; // zf
  int v14; // ecx
  int v15; // eax
  __int64 v16; // rax
  HRESULT v17; // eax
  __int64 v18; // rax
  HRESULT v19; // eax
  __int64 v20; // rax
  HRESULT v21; // eax
  PCWSTR v22; // rax
  HSTRING v23; // rcx
  PCWSTR v24; // rax
  int v25; // ecx
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rdx
  HRESULT v29; // eax
  __int64 v30; // rax
  HRESULT v31; // eax
  __int64 v32; // rax
  __int64 v33; // r8
  int v35; // [rsp+28h] [rbp-E0h]
  int v36; // [rsp+28h] [rbp-E0h]
  int v37; // [rsp+28h] [rbp-E0h]
  PCNZWCH sourceString; // [rsp+48h] [rbp-C0h] BYREF
  HSTRING *v39[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A8h] BYREF
  HSTRING *newString[2]; // [rsp+68h] [rbp-A0h] BYREF
  HSTRING *v42[2]; // [rsp+78h] [rbp-90h] BYREF
  HSTRING *v43[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v44; // [rsp+98h] [rbp-70h] BYREF
  HSTRING string; // [rsp+A0h] [rbp-68h] BYREF
  PCWSTR v46; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v47[12]; // [rsp+B0h] [rbp-58h] BYREF
  int v48[2]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v49[96]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]
  bool v51; // [rsp+158h] [rbp+50h] BYREF
  __int64 v52; // [rsp+170h] [rbp+68h] BYREF
  va_list va; // [rsp+170h] [rbp+68h]
  __int64 v54; // [rsp+178h] [rbp+70h]
  va_list va1; // [rsp+180h] [rbp+78h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v52 = va_arg(va1, _QWORD);
  v54 = va_arg(va1, _QWORD);
  v5 = *(_QWORD *)(a1 + 48) != 0;
  StringRawBuffer = (wchar_t *)WindowsGetStringRawBuffer(a3, 0);
  v8 = WindowsGetStringRawBuffer(a2, 0);
  LODWORD(v40) = Windows::Internal::Management::Provision::ConfigurationSession::AccessCheckForCapability(
                   v8,
                   StringRawBuffer,
                   v5);
  v9 = v40;
  if ( (int)v40 >= 0 )
  {
    v44 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    v15 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Provision::ConfigurationResult,Windows::Internal::Management::Provision::ConfigurationResult,>(&v44);
    v9 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
        (const char *)(unsigned int)v15,
        v35);
LABEL_37:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      return v9;
    }
    wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(newString);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      newString,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(newString) )
    {
      v16 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v39);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        newString,
        v16);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v39);
    }
    v17 = WindowsDuplicateString(*(HSTRING *)(a1 + 40), newString[0]);
    v9 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
        (const char *)(unsigned int)v17,
        v35);
LABEL_9:
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(newString);
      goto LABEL_37;
    }
    wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(v42);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      v42,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(v42) )
    {
      v18 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v39);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        v42,
        v18);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v39);
    }
    v19 = WindowsDuplicateString(a2, v42[0]);
    v9 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
        (const char *)(unsigned int)v19,
        v35);
LABEL_14:
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v42);
      goto LABEL_9;
    }
    wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(v43);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
      v43,
      0);
    if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(v43) )
    {
      v20 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v39);
      std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
        v43,
        v20);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v39);
    }
    v21 = WindowsDuplicateString(a3, v43[0]);
    v9 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CA,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
        (const char *)(unsigned int)v21,
        v35);
LABEL_19:
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v43);
      goto LABEL_14;
    }
    wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(v39);
    if ( *(_QWORD *)(a1 + 48) )
    {
      sourceString = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &sourceString,
        0);
      LODWORD(v40) = Windows::Internal::Management::Provision::ConfigurationSession::GetUserSidFromUser(
                       *(struct Windows::System::IUser **)(a1 + 48),
                       (unsigned __int16 **)&sourceString);
      v9 = v40;
      if ( (int)v40 < 0 )
      {
        v46 = WindowsGetStringRawBuffer(a3, 0);
        v22 = WindowsGetStringRawBuffer(a2, 0);
        v23 = *(HSTRING *)(a1 + 40);
        *(_QWORD *)v48 = v22;
        v24 = WindowsGetStringRawBuffer(v23, 0);
        v13 = *(_QWORD *)(a1 + 48) == 0;
        *(_QWORD *)v47 = v24;
        v51 = !v13;
        ConfigurationSessionTraceProvider::SetPolicyAsyncPreCheckFailed<char const (&)[34],long &,bool,unsigned short const *,unsigned short const *,unsigned short const *>(
          v25,
          (unsigned int)&v40,
          (unsigned int)&v51,
          (unsigned int)v47,
          (__int64)v48,
          (__int64)&v46);
        v26 = v9;
        v27 = 475;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
          (const char *)v26,
          v35);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
LABEL_24:
        std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v39);
        goto LABEL_19;
      }
      v28 = -1;
      string = 0;
      do
        ++v28;
      while ( sourceString[v28] );
      v29 = WindowsCreateString(sourceString, v28, &string);
      v9 = v29;
      if ( v29 < 0 )
      {
        v26 = (unsigned int)v29;
        v27 = 479;
        goto LABEL_23;
      }
      wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(
        v39,
        0);
      if ( !(unsigned __int8)std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(v39) )
      {
        v30 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(v47);
        std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(
          v39,
          v30);
        std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v47);
      }
      v31 = WindowsDuplicateString(string, v39[0]);
      v9 = v31;
      if ( v31 < 0 )
      {
        v26 = (unsigned int)v31;
        v27 = 480;
        goto LABEL_23;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
    }
    v32 = lambda_ff7bfbfcd73474f3344c425a40089742_::_lambda_ff7bfbfcd73474f3344c425a40089742__0(
            (unsigned int)v49,
            a1,
            (unsigned int)newString,
            (unsigned int)v39,
            (__int64)v42,
            (__int64)v43,
            (__int64)va,
            (__int64)&v44);
    *(_DWORD *)v47 = 3;
    *(_QWORD *)&v47[4] = 128;
    v9 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Internal::Management::Provision::IConfigurationResult__Windows::Internal::Management::Provision::ConfigurationResult___Windows::Internal::ComTaskPoolHandler__lambda_ff7bfbfcd73474f3344c425a40089742___(
           v47,
           v54,
           v33,
           v32);
    lambda_ff7bfbfcd73474f3344c425a40089742_::__lambda_ff7bfbfcd73474f3344c425a40089742_(v49);
    if ( (v9 & 0x80000000) == 0 )
    {
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v39);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v43);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(v42);
      std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Decref(newString);
      v9 = 0;
      goto LABEL_37;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
      (const char *)v9,
      v37);
    goto LABEL_24;
  }
  string = (HSTRING)WindowsGetStringRawBuffer(a3, 0);
  v10 = WindowsGetStringRawBuffer(a2, 0);
  v11 = *(HSTRING *)(a1 + 40);
  sourceString = v10;
  v12 = WindowsGetStringRawBuffer(v11, 0);
  v13 = *(_QWORD *)(a1 + 48) == 0;
  v46 = v12;
  v51 = !v13;
  ConfigurationSessionTraceProvider::SetPolicyAsyncPreCheckFailed<char const (&)[40],long &,bool,unsigned short const *,unsigned short const *,unsigned short const *>(
    v14,
    (unsigned int)&v40,
    (unsigned int)&v51,
    (unsigned int)&v46,
    (__int64)&sourceString,
    (__int64)&string);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1BD,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\configurationsession.cpp",
    (const char *)v9,
    v36);
  return v9;
}

```

## disassembly

```asm
0x18006dd20  mov     rax, rsp
0x18006dd23  mov     [rax+10h], rbx
0x18006dd27  mov     [rax+18h], rsi
0x18006dd2b  mov     [rax+20h], r9
0x18006dd2f  push    rbp
0x18006dd30  push    rdi
0x18006dd31  push    r12
0x18006dd33  push    r14
0x18006dd35  push    r15
0x18006dd37  lea     rbp, [rax-48h]
0x18006dd3b  sub     rsp, 120h
0x18006dd42  xor     r12d, r12d
0x18006dd45  mov     r15, rdx
0x18006dd48  cmp     [rcx+30h], r12
0x18006dd4c  mov     rsi, rcx
0x18006dd4f  mov     edi, r12d
0x18006dd52  mov     rcx, r8; string
0x18006dd55  setnz   dil
0x18006dd59  mov     r14, r8
0x18006dd5c  xor     edx, edx; length
0x18006dd5e  call    cs:__imp_WindowsGetStringRawBuffer
0x18006dd65  nop     dword ptr [rax+rax+00h]
0x18006dd6a  xor     edx, edx; length
0x18006dd6c  mov     rcx, r15; string
0x18006dd6f  mov     rbx, rax
0x18006dd72  call    cs:__imp_WindowsGetStringRawBuffer
0x18006dd79  nop     dword ptr [rax+rax+00h]
0x18006dd7e  mov     r8d, edi; int
0x18006dd81  mov     rdx, rbx; SubStr
0x18006dd84  mov     rcx, rax; unsigned __int16 *
0x18006dd87  call    ?AccessCheckForCapability@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG0H@Z; Windows::Internal::Management::Provision::ConfigurationSession::AccessCheckForCapability(ushort const *,ushort const *,int)
0x18006dd8c  mov     dword ptr [rsp+140h+var_E8], eax
0x18006dd90  mov     ebx, eax
0x18006dd92  test    eax, eax
0x18006dd94  jns     loc_18006DE25
0x18006dd9a  xor     edx, edx; length
0x18006dd9c  mov     rcx, r14; string
0x18006dd9f  call    cs:__imp_WindowsGetStringRawBuffer
0x18006dda6  nop     dword ptr [rax+rax+00h]
0x18006ddab  xor     edx, edx; length
0x18006ddad  mov     rcx, r15; string
0x18006ddb0  mov     [rbp+40h+string], rax
0x18006ddb4  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ddbb  nop     dword ptr [rax+rax+00h]
0x18006ddc0  mov     rcx, [rsi+28h]; string
0x18006ddc4  xor     edx, edx; length
0x18006ddc6  mov     [rsp+140h+sourceString], rax
0x18006ddcb  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ddd2  nop     dword ptr [rax+rax+00h]
0x18006ddd7  cmp     [rsi+30h], r12
0x18006dddb  lea     r9, [rbp+40h+var_A0]
0x18006dddf  mov     [rbp+40h+var_A0], rax
0x18006dde3  lea     r8, [rbp+40h+arg_0]
0x18006dde7  lea     rax, [rbp+40h+string]
0x18006ddeb  setnz   [rbp+40h+arg_0]
0x18006ddef  mov     [rsp+140h+var_118], rax
0x18006ddf4  lea     rdx, [rsp+140h+var_E8]
0x18006ddf9  lea     rax, [rsp+140h+sourceString]
0x18006ddfe  mov     qword ptr [rsp+140h+var_120], rax; int
0x18006de03  call    ??$SetPolicyAsyncPreCheckFailed@AEAY0CI@$$CBDAEAJ_NPEBGPEBGPEBG@ConfigurationSessionTraceProvider@@SAXAEAY0CI@$$CBDAEAJ$$QEA_N$$QEAPEBG33@Z; ConfigurationSessionTraceProvider::SetPolicyAsyncPreCheckFailed<char const (&)[40],long &,bool,ushort const *,ushort const *,ushort const *>(char const (&)[40],long &,bool &&,ushort const * &&,ushort const * &&,ushort const * &&)
0x18006de08  mov     rcx, [rbp+48h]; this
0x18006de0c  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006de13  mov     r9d, ebx; char *
0x18006de16  mov     edx, 1BDh; void *
0x18006de1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006de20  jmp     loc_18006E224
0x18006de25  lea     rcx, [rbp+40h+var_B0]
0x18006de29  mov     [rbp+40h+var_B0], r12
0x18006de2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006de32  lea     rcx, [rbp+40h+var_B0]
0x18006de36  call    ??$MakeAndInitialize@VConfigurationResult@Provision@Management@Internal@Windows@@V12345@$$V@Details@WRL@Microsoft@@YAJPEAPEAVConfigurationResult@Provision@Management@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Provision::ConfigurationResult,Windows::Internal::Management::Provision::ConfigurationResult,>(Windows::Internal::Management::Provision::ConfigurationResult * *)
0x18006de3b  mov     ebx, eax
0x18006de3d  test    eax, eax
0x18006de3f  jns     short loc_18006DE5E
0x18006de41  mov     rcx, [rbp+48h]; this
0x18006de45  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006de4c  mov     r9d, eax; char *
0x18006de4f  mov     edx, 1C1h; void *
0x18006de54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006de59  jmp     loc_18006E21B
0x18006de5e  lea     rcx, [rsp+140h+newString]
0x18006de63  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18006de68  xor     edx, edx
0x18006de6a  lea     rcx, [rsp+140h+newString]
0x18006de6f  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18006de74  lea     rcx, [rsp+140h+newString]
0x18006de79  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18006de7e  test    al, al
0x18006de80  jnz     short loc_18006DEA3
0x18006de82  lea     rcx, [rsp+140h+var_F8]
0x18006de87  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18006de8c  mov     rdx, rax
0x18006de8f  lea     rcx, [rsp+140h+newString]
0x18006de94  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18006de99  lea     rcx, [rsp+140h+var_F8]
0x18006de9e  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006dea3  mov     rdx, [rsp+140h+newString]; newString
0x18006dea8  mov     rcx, [rsi+28h]; string
0x18006deac  call    cs:__imp_WindowsDuplicateString
0x18006deb3  nop     dword ptr [rax+rax+00h]
0x18006deb8  mov     ebx, eax
0x18006deba  test    eax, eax
0x18006debc  jns     short loc_18006DEE5
0x18006debe  mov     rcx, [rbp+48h]; this
0x18006dec2  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006dec9  mov     r9d, eax; char *
0x18006decc  mov     edx, 1C4h; void *
0x18006ded1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ded6  lea     rcx, [rsp+140h+newString]
0x18006dedb  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006dee0  jmp     loc_18006E21B
0x18006dee5  lea     rcx, [rsp+140h+var_D0]
0x18006deea  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18006deef  xor     edx, edx
0x18006def1  lea     rcx, [rsp+140h+var_D0]
0x18006def6  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18006defb  lea     rcx, [rsp+140h+var_D0]
0x18006df00  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18006df05  test    al, al
0x18006df07  jnz     short loc_18006DF2A
0x18006df09  lea     rcx, [rsp+140h+var_F8]
0x18006df0e  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18006df13  mov     rdx, rax
0x18006df16  lea     rcx, [rsp+140h+var_D0]
0x18006df1b  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18006df20  lea     rcx, [rsp+140h+var_F8]
0x18006df25  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006df2a  mov     rdx, [rsp+140h+var_D0]; newString
0x18006df2f  mov     rcx, r15; string
0x18006df32  call    cs:__imp_WindowsDuplicateString
0x18006df39  nop     dword ptr [rax+rax+00h]
0x18006df3e  mov     ebx, eax
0x18006df40  test    eax, eax
0x18006df42  jns     short loc_18006DF6B
0x18006df44  mov     rcx, [rbp+48h]; this
0x18006df48  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006df4f  mov     r9d, eax; char *
0x18006df52  mov     edx, 1C7h; void *
0x18006df57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006df5c  lea     rcx, [rsp+140h+var_D0]
0x18006df61  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006df66  jmp     loc_18006DED6
0x18006df6b  lea     rcx, [rbp+40h+var_C0]
0x18006df6f  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18006df74  xor     edx, edx
0x18006df76  lea     rcx, [rbp+40h+var_C0]
0x18006df7a  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18006df7f  lea     rcx, [rbp+40h+var_C0]
0x18006df83  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18006df88  test    al, al
0x18006df8a  jnz     short loc_18006DFAC
0x18006df8c  lea     rcx, [rsp+140h+var_F8]
0x18006df91  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18006df96  mov     rdx, rax
0x18006df99  lea     rcx, [rbp+40h+var_C0]
0x18006df9d  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18006dfa2  lea     rcx, [rsp+140h+var_F8]
0x18006dfa7  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006dfac  mov     rdx, [rbp+40h+var_C0]; newString
0x18006dfb0  mov     rcx, r14; string
0x18006dfb3  call    cs:__imp_WindowsDuplicateString
0x18006dfba  nop     dword ptr [rax+rax+00h]
0x18006dfbf  mov     ebx, eax
0x18006dfc1  test    eax, eax
0x18006dfc3  jns     short loc_18006DFEB
0x18006dfc5  mov     rcx, [rbp+48h]; this
0x18006dfc9  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006dfd0  mov     r9d, eax; char *
0x18006dfd3  mov     edx, 1CAh; void *
0x18006dfd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006dfdd  lea     rcx, [rbp+40h+var_C0]
0x18006dfe1  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006dfe6  jmp     loc_18006DF5C
0x18006dfeb  lea     rcx, [rsp+140h+var_F8]
0x18006dff0  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18006dff5  cmp     [rsi+30h], r12
0x18006dff9  jz      loc_18006E16B
0x18006dfff  xor     edx, edx
0x18006e001  mov     [rsp+140h+sourceString], r12
0x18006e006  lea     rcx, [rsp+140h+sourceString]
0x18006e00b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006e010  mov     rcx, [rsi+30h]; struct Windows::System::IUser *
0x18006e014  lea     rdx, [rsp+140h+sourceString]; unsigned __int16 **
0x18006e019  call    ?GetUserSidFromUser@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEAUIUser@System@5@PEAPEAG@Z; Windows::Internal::Management::Provision::ConfigurationSession::GetUserSidFromUser(Windows::System::IUser *,ushort * *)
0x18006e01e  mov     dword ptr [rsp+140h+var_E8], eax
0x18006e022  mov     ebx, eax
0x18006e024  test    eax, eax
0x18006e026  jns     loc_18006E0C9
0x18006e02c  xor     edx, edx; length
0x18006e02e  mov     rcx, r14; string
0x18006e031  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e038  nop     dword ptr [rax+rax+00h]
0x18006e03d  xor     edx, edx; length
0x18006e03f  mov     rcx, r15; string
0x18006e042  mov     [rbp+40h+var_A0], rax
0x18006e046  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e04d  nop     dword ptr [rax+rax+00h]
0x18006e052  mov     rcx, [rsi+28h]; string
0x18006e056  xor     edx, edx; length
0x18006e058  mov     qword ptr [rbp+40h+var_88], rax
0x18006e05c  call    cs:__imp_WindowsGetStringRawBuffer
0x18006e063  nop     dword ptr [rax+rax+00h]
0x18006e068  cmp     [rsi+30h], r12
0x18006e06c  lea     r9, [rbp+40h+var_98]
0x18006e070  mov     [rbp+40h+var_98], rax
0x18006e074  lea     r8, [rbp+40h+arg_0]
0x18006e078  lea     rax, [rbp+40h+var_A0]
0x18006e07c  setnz   [rbp+40h+arg_0]
0x18006e080  mov     [rsp+140h+var_118], rax
0x18006e085  lea     rdx, [rsp+140h+var_E8]
0x18006e08a  lea     rax, [rbp+40h+var_88]
0x18006e08e  mov     qword ptr [rsp+140h+var_120], rax; int
0x18006e093  call    ??$SetPolicyAsyncPreCheckFailed@AEAY0CC@$$CBDAEAJ_NPEBGPEBGPEBG@ConfigurationSessionTraceProvider@@SAXAEAY0CC@$$CBDAEAJ$$QEA_N$$QEAPEBG33@Z; ConfigurationSessionTraceProvider::SetPolicyAsyncPreCheckFailed<char const (&)[34],long &,bool,ushort const *,ushort const *,ushort const *>(char const (&)[34],long &,bool &&,ushort const * &&,ushort const * &&,ushort const * &&)
0x18006e098  mov     r9d, ebx; char *
0x18006e09b  mov     edx, 1DBh; void *
0x18006e0a0  mov     rcx, [rbp+48h]; this
0x18006e0a4  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006e0ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e0b0  lea     rcx, [rsp+140h+sourceString]
0x18006e0b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006e0ba  lea     rcx, [rsp+140h+var_F8]
0x18006e0bf  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006e0c4  jmp     loc_18006DFDD
0x18006e0c9  mov     rcx, [rsp+140h+sourceString]; sourceString
0x18006e0ce  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006e0d2  mov     [rbp+40h+string], r12
0x18006e0d6  inc     rdx; length
0x18006e0d9  cmp     [rcx+rdx*2], r12w
0x18006e0de  jnz     short loc_18006E0D6
0x18006e0e0  lea     r8, [rbp+40h+string]; string
0x18006e0e4  call    cs:__imp_WindowsCreateString
0x18006e0eb  nop     dword ptr [rax+rax+00h]
0x18006e0f0  mov     ebx, eax
0x18006e0f2  test    eax, eax
0x18006e0f4  jns     short loc_18006E100
0x18006e0f6  mov     r9d, eax
0x18006e0f9  mov     edx, 1DFh
0x18006e0fe  jmp     short loc_18006E0A0
0x18006e100  xor     edx, edx
0x18006e102  lea     rcx, [rsp+140h+var_F8]
0x18006e107  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18006e10c  lea     rcx, [rsp+140h+var_F8]
0x18006e111  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18006e116  test    al, al
0x18006e118  jnz     short loc_18006E139
0x18006e11a  lea     rcx, [rbp+40h+var_98]
0x18006e11e  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18006e123  mov     rdx, rax
0x18006e126  lea     rcx, [rsp+140h+var_F8]
0x18006e12b  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18006e130  lea     rcx, [rbp+40h+var_98]
0x18006e134  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006e139  mov     rdx, [rsp+140h+var_F8]; newString
0x18006e13e  mov     rcx, [rbp+40h+string]; string
0x18006e142  call    cs:__imp_WindowsDuplicateString
0x18006e149  nop     dword ptr [rax+rax+00h]
0x18006e14e  mov     ebx, eax
0x18006e150  test    eax, eax
0x18006e152  jns     short loc_18006E161
0x18006e154  mov     r9d, eax
0x18006e157  mov     edx, 1E0h
0x18006e15c  jmp     loc_18006E0A0
0x18006e161  lea     rcx, [rsp+140h+sourceString]
0x18006e166  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006e16b  lea     rax, [rbp+40h+var_B0]
0x18006e16f  mov     rdx, rsi
0x18006e172  mov     [rsp+140h+var_108], rax
0x18006e177  lea     r9, [rsp+140h+var_F8]
0x18006e17c  lea     rax, [rbp+40h+arg_18]
0x18006e180  mov     [rsp+140h+var_110], rax
0x18006e185  lea     r8, [rsp+140h+newString]
0x18006e18a  lea     rax, [rbp+40h+var_C0]
0x18006e18e  mov     [rsp+140h+var_118], rax
0x18006e193  lea     rcx, [rbp+40h+var_80]
0x18006e197  lea     rax, [rsp+140h+var_D0]
0x18006e19c  mov     qword ptr [rsp+140h+var_120], rax; int
0x18006e1a1  call    _lambda_ff7bfbfcd73474f3344c425a40089742____lambda_ff7bfbfcd73474f3344c425a40089742__0
0x18006e1a6  mov     rdx, [rbp+40h+arg_20]
0x18006e1aa  lea     rcx, [rbp+40h+var_98]
0x18006e1ae  mov     r9, rax
0x18006e1b1  mov     dword ptr [rbp+40h+var_98], 3
0x18006e1b8  mov     [rbp+40h+var_98+4], 80h
0x18006e1c0  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__Internal__Management__Provision__IConfigurationResult__Windows__Internal__Management__Provision__ConfigurationResult___Windows__Internal__ComTaskPoolHandler__lambda_ff7bfbfcd73474f3344c425a40089742___
0x18006e1c5  lea     rcx, [rbp+40h+var_80]
0x18006e1c9  mov     ebx, eax
0x18006e1cb  call    _lambda_ff7bfbfcd73474f3344c425a40089742_____lambda_ff7bfbfcd73474f3344c425a40089742_
0x18006e1d0  test    ebx, ebx
0x18006e1d2  jns     short loc_18006E1F1
0x18006e1d4  mov     rcx, [rbp+48h]; this
0x18006e1d8  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006e1df  mov     r9d, ebx; char *
0x18006e1e2  mov     edx, 20Ah; void *
0x18006e1e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e1ec  jmp     loc_18006E0BA
0x18006e1f1  lea     rcx, [rsp+140h+var_F8]
0x18006e1f6  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006e1fb  lea     rcx, [rbp+40h+var_C0]
0x18006e1ff  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006e204  lea     rcx, [rsp+140h+var_D0]
0x18006e209  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
  ... truncated ...
```
