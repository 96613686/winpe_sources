# Windows::Internal::Management::Provision::ConfigurationSession::SetPolicyAsync(HSTRING__ *,HSTRING__ *,Windows::Internal::Management::Provision::IConfigurationData *,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::ConfigurationResult *> * *)

- ea: `0x18006c9d0`
- end: `0x18006cea0`
- name: `?SetPolicyAsync@ConfigurationSession@Provision@Management@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAUIConfigurationData@2345@PEAPEAU?$IAsyncOperation@PEAVConfigurationResult@Provision@Management@Internal@Windows@@@Foundation@5@@Z`
- size: `1232`
- prototype: `__int64(__int64, HSTRING, HSTRING, ...)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000992c`
- `0x18000a2a4`
- `0x180016b54`
- `0x180017074`
- `0x180017204`
- `0x18001736c`
- `0x1800173ec`
- `0x180019b2c`
- `0x180019f1c`
- `0x180019fb8`
- `0x18006a714`
- `0x18006a8e8`
- `0x18006aa28`
- `0x18006aaf8`
- `0x18006ad50`
- `0x18006b110`
- `0x18006b72c`
- `0x18006c0c4`
- `0x18006c9d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006cb3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006cbba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006cc35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006cda6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006cb3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006cbba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006cc35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006cda6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ccad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ccbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cccc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ca5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ccad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ccbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cccc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006cd4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006cd4e`

## string_xrefs

- `0x18006ca9a`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006cad3`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006cb4a`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006cbca`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006cc45`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006cd0e`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`
- `0x18006ce36`: `onecoreuap\admin\enterprisemgmt\enrollment\configurationsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18006c9d0  mov     rax, rsp
0x18006c9d3  mov     [rax+10h], rbx
0x18006c9d7  mov     [rax+18h], rsi
0x18006c9db  mov     [rax+20h], r9
0x18006c9df  push    rbp
0x18006c9e0  push    rdi
0x18006c9e1  push    r12
0x18006c9e3  push    r14
0x18006c9e5  push    r15
0x18006c9e7  lea     rbp, [rax-48h]
0x18006c9eb  sub     rsp, 120h
0x18006c9f2  xor     r12d, r12d
0x18006c9f5  mov     r15, rdx
0x18006c9f8  cmp     [rcx+30h], r12
0x18006c9fc  mov     rsi, rcx
0x18006c9ff  mov     edi, r12d
0x18006ca02  mov     rcx, r8; string
0x18006ca05  setnz   dil
0x18006ca09  mov     r14, r8
0x18006ca0c  xor     edx, edx; length
0x18006ca0e  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ca14  xor     edx, edx; length
0x18006ca16  mov     rcx, r15; string
0x18006ca19  mov     rbx, rax
0x18006ca1c  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ca22  mov     r8d, edi; int
0x18006ca25  mov     rdx, rbx; SubStr
0x18006ca28  mov     rcx, rax; unsigned __int16 *
0x18006ca2b  call    ?AccessCheckForCapability@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEBG0H@Z; Windows::Internal::Management::Provision::ConfigurationSession::AccessCheckForCapability(ushort const *,ushort const *,int)
0x18006ca30  mov     dword ptr [rsp+140h+var_E8], eax
0x18006ca34  mov     ebx, eax
0x18006ca36  test    eax, eax
0x18006ca38  jns     short loc_18006CAB3
0x18006ca3a  xor     edx, edx; length
0x18006ca3c  mov     rcx, r14; string
0x18006ca3f  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ca45  xor     edx, edx; length
0x18006ca47  mov     rcx, r15; string
0x18006ca4a  mov     [rbp+40h+string], rax
0x18006ca4e  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ca54  mov     rcx, [rsi+28h]; string
0x18006ca58  xor     edx, edx; length
0x18006ca5a  mov     [rsp+140h+sourceString], rax
0x18006ca5f  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ca65  cmp     [rsi+30h], r12
0x18006ca69  lea     r9, [rbp+40h+var_A0]
0x18006ca6d  mov     [rbp+40h+var_A0], rax
0x18006ca71  lea     r8, [rbp+40h+arg_0]
0x18006ca75  lea     rax, [rbp+40h+string]
0x18006ca79  setnz   [rbp+40h+arg_0]
0x18006ca7d  mov     [rsp+140h+var_118], rax
0x18006ca82  lea     rdx, [rsp+140h+var_E8]
0x18006ca87  lea     rax, [rsp+140h+sourceString]
0x18006ca8c  mov     qword ptr [rsp+140h+var_120], rax; int
0x18006ca91  call    ??$SetPolicyAsyncPreCheckFailed@AEAY0CI@$$CBDAEAJ_NPEBGPEBGPEBG@ConfigurationSessionTraceProvider@@SAXAEAY0CI@$$CBDAEAJ$$QEA_N$$QEAPEBG33@Z; ConfigurationSessionTraceProvider::SetPolicyAsyncPreCheckFailed<char const (&)[40],long &,bool,ushort const *,ushort const *,ushort const *>(char const (&)[40],long &,bool &&,ushort const * &&,ushort const * &&,ushort const * &&)
0x18006ca96  mov     rcx, [rbp+48h]; this
0x18006ca9a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006caa1  mov     r9d, ebx; char *
0x18006caa4  mov     edx, 1BDh; void *
0x18006caa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006caae  jmp     loc_18006CE82
0x18006cab3  lea     rcx, [rbp+40h+var_B0]
0x18006cab7  mov     [rbp+40h+var_B0], r12
0x18006cabb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006cac0  lea     rcx, [rbp+40h+var_B0]
0x18006cac4  call    ??$MakeAndInitialize@VConfigurationResult@Provision@Management@Internal@Windows@@V12345@$$V@Details@WRL@Microsoft@@YAJPEAPEAVConfigurationResult@Provision@Management@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Provision::ConfigurationResult,Windows::Internal::Management::Provision::ConfigurationResult,>(Windows::Internal::Management::Provision::ConfigurationResult * *)
0x18006cac9  mov     ebx, eax
0x18006cacb  test    eax, eax
0x18006cacd  jns     short loc_18006CAEC
0x18006cacf  mov     rcx, [rbp+48h]; this
0x18006cad3  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006cada  mov     r9d, eax; char *
0x18006cadd  mov     edx, 1C1h; void *
0x18006cae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cae7  jmp     loc_18006CE79
0x18006caec  lea     rcx, [rsp+140h+newString]
0x18006caf1  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18006caf6  xor     edx, edx
0x18006caf8  lea     rcx, [rsp+140h+newString]
0x18006cafd  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18006cb02  lea     rcx, [rsp+140h+newString]
0x18006cb07  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18006cb0c  test    al, al
0x18006cb0e  jnz     short loc_18006CB31
0x18006cb10  lea     rcx, [rsp+140h+var_F8]
0x18006cb15  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18006cb1a  mov     rdx, rax
0x18006cb1d  lea     rcx, [rsp+140h+newString]
0x18006cb22  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18006cb27  lea     rcx, [rsp+140h+var_F8]
0x18006cb2c  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006cb31  mov     rdx, [rsp+140h+newString]; newString
0x18006cb36  mov     rcx, [rsi+28h]; string
0x18006cb3a  call    cs:__imp_WindowsDuplicateString
0x18006cb40  mov     ebx, eax
0x18006cb42  test    eax, eax
0x18006cb44  jns     short loc_18006CB6D
0x18006cb46  mov     rcx, [rbp+48h]; this
0x18006cb4a  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006cb51  mov     r9d, eax; char *
0x18006cb54  mov     edx, 1C4h; void *
0x18006cb59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cb5e  lea     rcx, [rsp+140h+newString]
0x18006cb63  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006cb68  jmp     loc_18006CE79
0x18006cb6d  lea     rcx, [rsp+140h+var_D0]
0x18006cb72  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18006cb77  xor     edx, edx
0x18006cb79  lea     rcx, [rsp+140h+var_D0]
0x18006cb7e  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18006cb83  lea     rcx, [rsp+140h+var_D0]
0x18006cb88  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18006cb8d  test    al, al
0x18006cb8f  jnz     short loc_18006CBB2
0x18006cb91  lea     rcx, [rsp+140h+var_F8]
0x18006cb96  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18006cb9b  mov     rdx, rax
0x18006cb9e  lea     rcx, [rsp+140h+var_D0]
0x18006cba3  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18006cba8  lea     rcx, [rsp+140h+var_F8]
0x18006cbad  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006cbb2  mov     rdx, [rsp+140h+var_D0]; newString
0x18006cbb7  mov     rcx, r15; string
0x18006cbba  call    cs:__imp_WindowsDuplicateString
0x18006cbc0  mov     ebx, eax
0x18006cbc2  test    eax, eax
0x18006cbc4  jns     short loc_18006CBED
0x18006cbc6  mov     rcx, [rbp+48h]; this
0x18006cbca  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006cbd1  mov     r9d, eax; char *
0x18006cbd4  mov     edx, 1C7h; void *
0x18006cbd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cbde  lea     rcx, [rsp+140h+var_D0]
0x18006cbe3  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006cbe8  jmp     loc_18006CB5E
0x18006cbed  lea     rcx, [rbp+40h+var_C0]
0x18006cbf1  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18006cbf6  xor     edx, edx
0x18006cbf8  lea     rcx, [rbp+40h+var_C0]
0x18006cbfc  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18006cc01  lea     rcx, [rbp+40h+var_C0]
0x18006cc05  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18006cc0a  test    al, al
0x18006cc0c  jnz     short loc_18006CC2E
0x18006cc0e  lea     rcx, [rsp+140h+var_F8]
0x18006cc13  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18006cc18  mov     rdx, rax
0x18006cc1b  lea     rcx, [rbp+40h+var_C0]
0x18006cc1f  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18006cc24  lea     rcx, [rsp+140h+var_F8]
0x18006cc29  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006cc2e  mov     rdx, [rbp+40h+var_C0]; newString
0x18006cc32  mov     rcx, r14; string
0x18006cc35  call    cs:__imp_WindowsDuplicateString
0x18006cc3b  mov     ebx, eax
0x18006cc3d  test    eax, eax
0x18006cc3f  jns     short loc_18006CC67
0x18006cc41  mov     rcx, [rbp+48h]; this
0x18006cc45  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006cc4c  mov     r9d, eax; char *
0x18006cc4f  mov     edx, 1CAh; void *
0x18006cc54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cc59  lea     rcx, [rbp+40h+var_C0]
0x18006cc5d  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006cc62  jmp     loc_18006CBDE
0x18006cc67  lea     rcx, [rsp+140h+var_F8]
0x18006cc6c  call    ??$?0$$V@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)
0x18006cc71  cmp     [rsi+30h], r12
0x18006cc75  jz      loc_18006CDC9
0x18006cc7b  xor     edx, edx
0x18006cc7d  mov     [rsp+140h+sourceString], r12
0x18006cc82  lea     rcx, [rsp+140h+sourceString]
0x18006cc87  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006cc8c  mov     rcx, [rsi+30h]; struct Windows::System::IUser *
0x18006cc90  lea     rdx, [rsp+140h+sourceString]; unsigned __int16 **
0x18006cc95  call    ?GetUserSidFromUser@ConfigurationSession@Provision@Management@Internal@Windows@@CAJPEAUIUser@System@5@PEAPEAG@Z; Windows::Internal::Management::Provision::ConfigurationSession::GetUserSidFromUser(Windows::System::IUser *,ushort * *)
0x18006cc9a  mov     dword ptr [rsp+140h+var_E8], eax
0x18006cc9e  mov     ebx, eax
0x18006cca0  test    eax, eax
0x18006cca2  jns     loc_18006CD33
0x18006cca8  xor     edx, edx; length
0x18006ccaa  mov     rcx, r14; string
0x18006ccad  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ccb3  xor     edx, edx; length
0x18006ccb5  mov     rcx, r15; string
0x18006ccb8  mov     [rbp+40h+var_A0], rax
0x18006ccbc  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ccc2  mov     rcx, [rsi+28h]; string
0x18006ccc6  xor     edx, edx; length
0x18006ccc8  mov     qword ptr [rbp+40h+var_88], rax
0x18006cccc  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ccd2  cmp     [rsi+30h], r12
0x18006ccd6  lea     r9, [rbp+40h+var_98]
0x18006ccda  mov     [rbp+40h+var_98], rax
0x18006ccde  lea     r8, [rbp+40h+arg_0]
0x18006cce2  lea     rax, [rbp+40h+var_A0]
0x18006cce6  setnz   [rbp+40h+arg_0]
0x18006ccea  mov     [rsp+140h+var_118], rax
0x18006ccef  lea     rdx, [rsp+140h+var_E8]
0x18006ccf4  lea     rax, [rbp+40h+var_88]
0x18006ccf8  mov     qword ptr [rsp+140h+var_120], rax; int
0x18006ccfd  call    ??$SetPolicyAsyncPreCheckFailed@AEAY0CC@$$CBDAEAJ_NPEBGPEBGPEBG@ConfigurationSessionTraceProvider@@SAXAEAY0CC@$$CBDAEAJ$$QEA_N$$QEAPEBG33@Z; ConfigurationSessionTraceProvider::SetPolicyAsyncPreCheckFailed<char const (&)[34],long &,bool,ushort const *,ushort const *,ushort const *>(char const (&)[34],long &,bool &&,ushort const * &&,ushort const * &&,ushort const * &&)
0x18006cd02  mov     r9d, ebx; char *
0x18006cd05  mov     edx, 1DBh; void *
0x18006cd0a  mov     rcx, [rbp+48h]; this
0x18006cd0e  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006cd15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cd1a  lea     rcx, [rsp+140h+sourceString]
0x18006cd1f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006cd24  lea     rcx, [rsp+140h+var_F8]
0x18006cd29  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006cd2e  jmp     loc_18006CC59
0x18006cd33  mov     rcx, [rsp+140h+sourceString]; sourceString
0x18006cd38  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006cd3c  mov     [rbp+40h+string], r12
0x18006cd40  inc     rdx; length
0x18006cd43  cmp     [rcx+rdx*2], r12w
0x18006cd48  jnz     short loc_18006CD40
0x18006cd4a  lea     r8, [rbp+40h+string]; string
0x18006cd4e  call    cs:__imp_WindowsCreateString
0x18006cd54  mov     ebx, eax
0x18006cd56  test    eax, eax
0x18006cd58  jns     short loc_18006CD64
0x18006cd5a  mov     r9d, eax
0x18006cd5d  mov     edx, 1DFh
0x18006cd62  jmp     short loc_18006CD0A
0x18006cd64  xor     edx, edx
0x18006cd66  lea     rcx, [rsp+140h+var_F8]
0x18006cd6b  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::reset(HSTRING__ *)
0x18006cd70  lea     rcx, [rsp+140h+var_F8]
0x18006cd75  call    ??B?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEBA_NXZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator bool(void)
0x18006cd7a  test    al, al
0x18006cd7c  jnz     short loc_18006CD9D
0x18006cd7e  lea     rcx, [rbp+40h+var_98]
0x18006cd82  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$$V@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@0@XZ; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,>(void)
0x18006cd87  mov     rdx, rax
0x18006cd8a  lea     rcx, [rsp+140h+var_F8]
0x18006cd8f  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>> &&)
0x18006cd94  lea     rcx, [rbp+40h+var_98]
0x18006cd98  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006cd9d  mov     rdx, [rsp+140h+var_F8]; newString
0x18006cda2  mov     rcx, [rbp+40h+string]; string
0x18006cda6  call    cs:__imp_WindowsDuplicateString
0x18006cdac  mov     ebx, eax
0x18006cdae  test    eax, eax
0x18006cdb0  jns     short loc_18006CDBF
0x18006cdb2  mov     r9d, eax
0x18006cdb5  mov     edx, 1E0h
0x18006cdba  jmp     loc_18006CD0A
0x18006cdbf  lea     rcx, [rsp+140h+sourceString]
0x18006cdc4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006cdc9  lea     rax, [rbp+40h+var_B0]
0x18006cdcd  mov     rdx, rsi
0x18006cdd0  mov     [rsp+140h+var_108], rax
0x18006cdd5  lea     r9, [rsp+140h+var_F8]
0x18006cdda  lea     rax, [rbp+40h+arg_18]
0x18006cdde  mov     [rsp+140h+var_110], rax
0x18006cde3  lea     r8, [rsp+140h+newString]
0x18006cde8  lea     rax, [rbp+40h+var_C0]
0x18006cdec  mov     [rsp+140h+var_118], rax
0x18006cdf1  lea     rcx, [rbp+40h+var_80]
0x18006cdf5  lea     rax, [rsp+140h+var_D0]
0x18006cdfa  mov     qword ptr [rsp+140h+var_120], rax; int
0x18006cdff  call    _lambda_ff7bfbfcd73474f3344c425a40089742____lambda_ff7bfbfcd73474f3344c425a40089742__0
0x18006ce04  mov     rdx, [rbp+40h+arg_20]
0x18006ce08  lea     rcx, [rbp+40h+var_98]
0x18006ce0c  mov     r9, rax
0x18006ce0f  mov     dword ptr [rbp+40h+var_98], 3
0x18006ce16  mov     [rbp+40h+var_98+4], 80h
0x18006ce1e  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__Internal__Management__Provision__IConfigurationResult__Windows__Internal__Management__Provision__ConfigurationResult___Windows__Internal__ComTaskPoolHandler__lambda_ff7bfbfcd73474f3344c425a40089742___
0x18006ce23  lea     rcx, [rbp+40h+var_80]
0x18006ce27  mov     ebx, eax
0x18006ce29  call    _lambda_ff7bfbfcd73474f3344c425a40089742_____lambda_ff7bfbfcd73474f3344c425a40089742_
0x18006ce2e  test    ebx, ebx
0x18006ce30  jns     short loc_18006CE4F
0x18006ce32  mov     rcx, [rbp+48h]; this
0x18006ce36  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18006ce3d  mov     r9d, ebx; char *
0x18006ce40  mov     edx, 20Ah; void *
0x18006ce45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ce4a  jmp     loc_18006CD24
0x18006ce4f  lea     rcx, [rsp+140h+var_F8]
0x18006ce54  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006ce59  lea     rcx, [rbp+40h+var_C0]
0x18006ce5d  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006ce62  lea     rcx, [rsp+140h+var_D0]
0x18006ce67  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006ce6c  lea     rcx, [rsp+140h+newString]
0x18006ce71  call    ?_Decref@?$_Ptr_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@IEAAXXZ; std::_Ptr_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Decref(void)
0x18006ce76  mov     ebx, r12d
0x18006ce79  lea     rcx, [rbp+40h+var_B0]
0x18006ce7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ce82  lea     r11, [rsp+140h+var_20]
0x18006ce8a  mov     eax, ebx
0x18006ce8c  mov     rbx, [r11+38h]
0x18006ce90  mov     rsi, [r11+40h]
0x18006ce94  mov     rsp, r11
0x18006ce97  pop     r15
0x18006ce99  pop     r14
0x18006ce9b  pop     r12
  ... truncated ...
```
