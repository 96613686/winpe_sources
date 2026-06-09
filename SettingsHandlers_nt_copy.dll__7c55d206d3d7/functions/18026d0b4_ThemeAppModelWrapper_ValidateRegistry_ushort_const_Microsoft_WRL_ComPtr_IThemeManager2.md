# ThemeAppModelWrapper::ValidateRegistry(ushort const *,Microsoft::WRL::ComPtr<IThemeManager2>)

- ea: `0x18026d0b4`
- end: `0x18026dd81`
- name: `?ValidateRegistry@ThemeAppModelWrapper@@QEAAJPEBGV?$ComPtr@UIThemeManager2@@@WRL@Microsoft@@@Z`
- size: `3277`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18010d480`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18001e4b0`
- `0x180024410`
- `0x18002e1f4`
- `0x180041004`
- `0x1800684c8`
- `0x18006956c`
- `0x1800740f4`
- `0x180078f3c`
- `0x1802693b8`
- `0x180269414`
- `0x18026943c`
- `0x180269564`
- `0x18026a458`
- `0x18026b000`
- `0x18026cd68`
- `0x18026d0b4`
- `0x18026dd88`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026d723`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026d753`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026daaa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026dbf7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026d723`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026d753`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026daaa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18026dbf7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18026d582`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18026d582`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18026d471`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18026d471`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18026d1ec`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18026d1ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026d91e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026d9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026d9f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026da15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026db22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026db41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dbb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dc6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dc8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dcfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dd23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026d91e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026d9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026d9f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026da15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026db22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026db41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dbb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dc6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dc8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dcfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026dd23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026da86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026dbd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026da86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026dbd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ThemeAppModelWrapper::ValidateRegistry(const unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // r15d
  const char *v8; // r9
  __int64 result; // rax
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int i; // esi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 **); // rbx
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  HKEY *v18; // rax
  unsigned int v19; // eax
  DWORD v20; // r12d
  unsigned int v21; // eax
  int ThemeNameFromAppxName; // eax
  int j; // ebx
  int AllThemes; // eax
  int v25; // eax
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, _QWORD, __int64 **); // rdi
  int v28; // eax
  unsigned int v29; // edi
  __int64 *v30; // rsi
  __int64 (__fastcall *v31)(__int64 *, HSTRING *); // rdi
  int v32; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 v34; // rcx
  int v35; // eax
  const WCHAR *v36; // rax
  __int64 v37; // rcx
  int v38; // eax
  int phkResult; // [rsp+20h] [rbp-4D8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-4D8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-4D8h]
  int phkResultc; // [rsp+20h] [rbp-4D8h]
  __int128 v43; // [rsp+40h] [rbp-4B8h] BYREF
  __int64 v44; // [rsp+50h] [rbp-4A8h]
  HSTRING string; // [rsp+58h] [rbp-4A0h] BYREF
  __int64 v46; // [rsp+60h] [rbp-498h] BYREF
  __int64 *v47; // [rsp+68h] [rbp-490h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-488h] BYREF
  int v49; // [rsp+78h] [rbp-480h] BYREF
  unsigned int v50; // [rsp+7Ch] [rbp-47Ch] BYREF
  __int64 v51; // [rsp+80h] [rbp-478h] BYREF
  DWORD cchValueName; // [rsp+88h] [rbp-470h] BYREF
  _QWORD *v53; // [rsp+90h] [rbp-468h]
  __int64 v54; // [rsp+98h] [rbp-460h]
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-458h] BYREF
  WCHAR String1[264]; // [rsp+2B0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+0h]

  try
  {
    v53 = a3;
    v5 = ValidateRegistryRootState(a1);
    v6 = v5;
    v7 = 0;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)v5,
        phkResult);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a3);
      return v6;
    }
    std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>(&v43);
    v49 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a3 + 64LL))(*a3, &v49);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
        (const char *)(unsigned int)v10,
        phkResult);
      if ( (_QWORD)v43 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
          v43,
          *((_QWORD *)&v43 + 1));
        std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
        v43 = 0;
        v44 = 0;
      }
      goto LABEL_63;
    }
    v51 = v49;
    if ( v49 > (unsigned __int64)((v44 - (__int64)v43) >> 3) )
    {
      if ( (unsigned __int64)v49 > 0x1FFFFFFFFFFFFFFFLL )
        std::_Xlength_error("vector too long");
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Reallocate<0>(
        &v43,
        &v51);
    }
    for ( i = 0; (int)i < v49; ++i )
    {
      v47 = 0;
      v13 = *a3;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)*a3 + 72LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      v15 = v14(v13, i, &v47);
      v11 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
          (const char *)(unsigned int)v15,
          phkResult);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        if ( (_QWORD)v43 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
            v43,
            *((_QWORD *)&v43 + 1));
          std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
          v43 = 0;
          v44 = 0;
        }
        goto LABEL_63;
      }
      v46 = 0;
      v16 = *v47;
      v46 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v16 + 24))(v47, &v46);
      v11 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD5,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
          (const char *)(unsigned int)v17,
          phkResult);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        if ( (_QWORD)v43 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
            v43,
            *((_QWORD *)&v43 + 1));
          std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
          v43 = 0;
          v44 = 0;
        }
        goto LABEL_63;
      }
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &string,
        v46,
        -1);
      if ( *((_QWORD *)&v43 + 1) == v44 )
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v43,
          *((_QWORD *)&v43 + 1),
          &string);
      else
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_back_with_unused_capacity<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v43,
          &string);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&string);
      if ( !*(_QWORD *)(v43 + 8LL * (int)i) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD7,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
          (const char *)0x8007000ELL,
          phkResult);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        if ( (_QWORD)v43 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
            v43,
            *((_QWORD *)&v43 + 1));
          std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
          v43 = 0;
          v44 = 0;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a3);
        return 2147942414LL;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    }
    hKey = 0;
    v18 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v19 = RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize\\ThemeAppxMapping",
            0,
            1u,
            v18);
    if ( v19 == 2 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( (_QWORD)v43 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
          v43,
          *((_QWORD *)&v43 + 1));
        std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
        v43 = 0;
        v44 = 0;
      }
LABEL_33:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a3);
      return 0;
    }
    if ( v19 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xE2,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
              (const char *)v19,
              phkResulta);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( (_QWORD)v43 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
          v43,
          *((_QWORD *)&v43 + 1));
        std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
        v43 = 0;
        v44 = 0;
      }
      goto LABEL_63;
    }
    v20 = 0;
LABEL_39:
    cchValueName = 260;
    v21 = RegEnumValueW(hKey, v20, ValueName, &cchValueName, 0, 0, 0, 0);
    if ( v21 == 259 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( (_QWORD)v43 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
          v43,
          *((_QWORD *)&v43 + 1));
        std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
        v43 = 0;
        v44 = 0;
      }
      goto LABEL_33;
    }
    if ( v21 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xF0,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
              (const char *)v21,
              phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( (_QWORD)v43 )
      {
        std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
          v43,
          *((_QWORD *)&v43 + 1));
        std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
        v43 = 0;
        v44 = 0;
      }
    }
    else
    {
      cchValueName = 260;
      ThemeNameFromAppxName = ThemeAppModelWrapper::GetThemeNameFromAppxName(ValueName, String1, &cchValueName);
      v11 = ThemeNameFromAppxName;
      if ( ThemeNameFromAppxName >= 0 )
      {
        for ( j = 0; j < v49; ++j )
        {
          if ( CompareStringOrdinal(ValueName, -1, *(LPCWCH *)(v43 + 8LL * j), -1, 0) == 2
            || CompareStringOrdinal(String1, -1, *(LPCWCH *)(v43 + 8LL * j), -1, 0) == 2 )
          {
            goto LABEL_92;
          }
        }
        v46 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        AllThemes = ThemeAppModelWrapper::FindAllThemes(a1, &v46);
        v11 = AllThemes;
        if ( AllThemes >= 0 )
        {
          v50 = 0;
          v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 56LL))(v46, &v50);
          v11 = v25;
          if ( v25 >= 0 )
          {
            v54 = 0;
            while ( 1 )
            {
              if ( v7 >= v50 )
              {
                v7 = 0;
                goto LABEL_91;
              }
              v47 = 0;
              v26 = v46;
              v27 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v46 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
              v28 = v27(v26, v7, &v47);
              v29 = v28;
              if ( v28 < 0 )
                break;
              string = 0;
              v30 = v47;
              v31 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v47 + 104);
              WindowsDeleteString(0);
              string = 0;
              v32 = v31(v30, &string);
              v29 = v32;
              if ( v32 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x110,
                  (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeap"
                                "pmodelwrapper.cpp",
                  (const char *)(unsigned int)v32,
                  phkResultb);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                WindowsDeleteString(0);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                if ( (_QWORD)v43 )
                {
                  std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
                    v43,
                    *((_QWORD *)&v43 + 1));
                  std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
                  v43 = 0;
                  v44 = 0;
                }
                goto LABEL_88;
              }
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( CompareStringOrdinal(StringRawBuffer, -1, ValueName, -1, 0) == 2 )
              {
                v34 = v46;
                v51 = v46;
                v7 = 0;
                if ( v46 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
                v35 = ThemeAppModelWrapper::UninstallTheme(v34, ValueName, &v51);
                v29 = v35;
                if ( v35 >= 0 )
                  goto LABEL_81;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x113,
                  (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeap"
                                "pmodelwrapper.cpp",
                  (const char *)(unsigned int)v35,
                  phkResultc);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                WindowsDeleteString(0);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                if ( (_QWORD)v43 )
                {
                  std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
                    v43,
                    *((_QWORD *)&v43 + 1));
                  std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
                  v43 = 0;
                  v44 = 0;
                }
LABEL_88:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a3);
                return v29;
              }
              v36 = WindowsGetStringRawBuffer(string, 0);
              if ( CompareStringOrdinal(v36, -1, String1, -1, 0) == 2 )
              {
                v37 = v46;
                v51 = v46;
                v7 = 0;
                if ( v46 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
                v38 = ThemeAppModelWrapper::UninstallTheme(v37, String1, &v51);
                v29 = v38;
                if ( v38 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x118,
                    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\theme"
                                  "appmodelwrapper.cpp",
                    (const char *)(unsigned int)v38,
                    phkResultb);
                  WindowsDeleteString(string);
                  string = 0;
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                  WindowsDeleteString(0);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  if ( (_QWORD)v43 )
                  {
                    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
                      v43,
                      *((_QWORD *)&v43 + 1));
                    std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
                    v43 = 0;
                    v44 = 0;
                  }
                  goto LABEL_88;
                }
LABEL_81:
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
LABEL_91:
                WindowsDeleteString(0);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
LABEL_92:
                ++v20;
                goto LABEL_39;
              }
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
              ++v7;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x10E,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
              (const char *)(unsigned int)v28,
              phkResultb);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
            WindowsDeleteString(0);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            if ( (_QWORD)v43 )
            {
              std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
                v43,
                *((_QWORD *)&v43 + 1));
              std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
              v43 = 0;
              v44 = 0;
            }
            goto LABEL_88;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x107,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
            (const char *)(unsigned int)v25,
            phkResultb);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          if ( (_QWORD)v43 )
          {
            std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
              v43,
              *((_QWORD *)&v43 + 1));
            std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
            v43 = 0;
            v44 = 0;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x105,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
            (const char *)(unsigned int)AllThemes,
            phkResultb);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          if ( (_QWORD)v43 )
          {
            std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
              v43,
              *((_QWORD *)&v43 + 1));
            std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
            v43 = 0;
            v44 = 0;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF7,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
          (const char *)(unsigned int)ThemeNameFromAppxName,
          phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        if ( (_QWORD)v43 )
        {
          std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
            v43,
            *((_QWORD *)&v43 + 1));
          std::_Deallocate<16>(v43, (v44 - v43) & 0xFFFFFFFFFFFFFFF8uLL);
          v43 = 0;
          v44 = 0;
        }
      }
    }
LABEL_63:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a3);
    result = v11;
  }
  catch ( ... )
  {
    v50 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x120,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
            v8);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v53);
    return v50;
  }
  return result;
}

```

## disassembly

```asm
0x18026d0b4  mov     [rsp+arg_8], rbx
0x18026d0b9  mov     [rsp+arg_18], rsi
0x18026d0be  push    rdi
0x18026d0bf  push    r12
0x18026d0c1  push    r13
0x18026d0c3  push    r14
0x18026d0c5  push    r15
0x18026d0c7  sub     rsp, 4D0h
0x18026d0ce  mov     rax, cs:__security_cookie
0x18026d0d5  xor     rax, rsp
0x18026d0d8  mov     [rsp+4F8h+var_38], rax
0x18026d0e0  mov     r14, r8
0x18026d0e3  mov     r13, rcx
0x18026d0e6  mov     [rsp+4F8h+var_468], r8
0x18026d0ee  call    ?ValidateRegistryRootState@@YAJPEBG@Z; ValidateRegistryRootState(ushort const *)
0x18026d0f3  mov     ebx, eax
0x18026d0f5  xor     r15d, r15d
0x18026d0f8  test    eax, eax
0x18026d0fa  jns     short loc_18026D128
0x18026d0fc  mov     rcx, [rsp+4F8h]; this
0x18026d104  mov     r9d, eax; char *
0x18026d107  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026d10e  mov     edx, 0C9h; void *
0x18026d113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d118  nop
0x18026d119  mov     rcx, r14
0x18026d11c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d121  mov     eax, ebx
0x18026d123  jmp     loc_18026DD53
0x18026d128  lea     rcx, [rsp+4F8h+var_4B8]; void *
0x18026d12d  call    ??0?$vector@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIVoiceInformation@SpeechSynthesis@Media@Windows@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>::vector<Microsoft::WRL::ComPtr<Windows::Media::SpeechSynthesis::IVoiceInformation>>(void)
0x18026d132  nop
0x18026d133  mov     [rsp+4F8h+var_480], r15d
0x18026d138  mov     rcx, [r14]
0x18026d13b  mov     rax, [rcx]
0x18026d13e  lea     rdx, [rsp+4F8h+var_480]
0x18026d143  mov     rax, [rax+40h]
0x18026d147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026d14c  mov     ebx, eax
0x18026d14e  test    eax, eax
0x18026d150  jns     short loc_18026D1B6
0x18026d152  mov     rcx, [rsp+4F8h]; this
0x18026d15a  mov     r9d, eax; char *
0x18026d15d  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026d164  mov     edx, 0CDh; void *
0x18026d169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d16e  nop
0x18026d16f  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d174  test    rcx, rcx
0x18026d177  jz      short loc_18026D1A7
0x18026d179  mov     rdx, qword ptr [rsp+4F8h+var_4B8+8]
0x18026d17e  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x18026d183  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d188  mov     rdx, [rsp+4F8h+var_4A8]
0x18026d18d  sub     rdx, rcx
0x18026d190  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18026d194  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18026d199  xorps   xmm0, xmm0
0x18026d19c  movdqu  [rsp+4F8h+var_4B8], xmm0
0x18026d1a2  mov     [rsp+4F8h+var_4A8], r15
0x18026d1a7  mov     rcx, r14
0x18026d1aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d1af  mov     eax, ebx
0x18026d1b1  jmp     loc_18026DD53
0x18026d1b6  movsxd  rcx, [rsp+4F8h+var_480]
0x18026d1bb  mov     [rsp+4F8h+var_478], rcx
0x18026d1c3  mov     rax, [rsp+4F8h+var_4A8]
0x18026d1c8  sub     rax, qword ptr [rsp+4F8h+var_4B8]
0x18026d1cd  sar     rax, 3
0x18026d1d1  cmp     rcx, rax
0x18026d1d4  jbe     short loc_18026D20A
0x18026d1d6  mov     rax, 1FFFFFFFFFFFFFFFh
0x18026d1e0  cmp     rcx, rax
0x18026d1e3  jbe     short loc_18026D1F8
0x18026d1e5  lea     rcx, aVectorTooLong; "vector too long"
0x18026d1ec  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18026d1f8  lea     rdx, [rsp+4F8h+var_478]
0x18026d200  lea     rcx, [rsp+4F8h+var_4B8]
0x18026d205  call    ??$_Reallocate@$0A@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAXAEA_K@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Reallocate<0>(unsigned __int64 &)
0x18026d20a  mov     esi, r15d
0x18026d20d  cmp     esi, [rsp+4F8h+var_480]
0x18026d211  jge     loc_18026D446
0x18026d217  mov     [rsp+4F8h+var_490], r15
0x18026d21c  mov     rdi, [r14]
0x18026d21f  mov     rax, [rdi]
0x18026d222  mov     rbx, [rax+48h]
0x18026d226  lea     rcx, [rsp+4F8h+var_490]
0x18026d22b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d230  lea     r8, [rsp+4F8h+var_490]
0x18026d235  mov     edx, esi
0x18026d237  mov     rcx, rdi
0x18026d23a  mov     rax, rbx
0x18026d23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026d242  mov     ebx, eax
0x18026d244  test    eax, eax
0x18026d246  jns     short loc_18026D2B7
0x18026d248  mov     rcx, [rsp+4F8h]; this
0x18026d250  mov     r9d, eax; char *
0x18026d253  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026d25a  mov     edx, 0D3h; void *
0x18026d25f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d264  nop
0x18026d265  lea     rcx, [rsp+4F8h+var_490]
0x18026d26a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d26f  nop
0x18026d270  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d275  test    rcx, rcx
0x18026d278  jz      short loc_18026D2A8
0x18026d27a  mov     rdx, qword ptr [rsp+4F8h+var_4B8+8]
0x18026d27f  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x18026d284  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d289  mov     rdx, [rsp+4F8h+var_4A8]
0x18026d28e  sub     rdx, rcx
0x18026d291  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18026d295  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18026d29a  xorps   xmm0, xmm0
0x18026d29d  movdqu  [rsp+4F8h+var_4B8], xmm0
0x18026d2a3  mov     [rsp+4F8h+var_4A8], r15
0x18026d2a8  mov     rcx, r14
0x18026d2ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d2b0  mov     eax, ebx
0x18026d2b2  jmp     loc_18026DD53
0x18026d2b7  mov     [rsp+4F8h+var_498], r15
0x18026d2bc  mov     rcx, [rsp+4F8h+var_490]
0x18026d2c1  mov     rax, [rcx]
0x18026d2c4  mov     [rsp+4F8h+var_498], r15
0x18026d2c9  lea     rdx, [rsp+4F8h+var_498]
0x18026d2ce  mov     rax, [rax+18h]
0x18026d2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026d2d7  mov     ebx, eax
0x18026d2d9  test    eax, eax
0x18026d2db  jns     short loc_18026D357
0x18026d2dd  mov     rcx, [rsp+4F8h]; this
0x18026d2e5  mov     r9d, eax; char *
0x18026d2e8  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026d2ef  mov     edx, 0D5h; void *
0x18026d2f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d2f9  nop
0x18026d2fa  lea     rcx, [rsp+4F8h+var_498]
0x18026d2ff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18026d304  nop
0x18026d305  lea     rcx, [rsp+4F8h+var_490]
0x18026d30a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d30f  nop
0x18026d310  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d315  test    rcx, rcx
0x18026d318  jz      short loc_18026D348
0x18026d31a  mov     rdx, qword ptr [rsp+4F8h+var_4B8+8]
0x18026d31f  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x18026d324  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d329  mov     rdx, [rsp+4F8h+var_4A8]
0x18026d32e  sub     rdx, rcx
0x18026d331  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18026d335  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18026d33a  xorps   xmm0, xmm0
0x18026d33d  movdqu  [rsp+4F8h+var_4B8], xmm0
0x18026d343  mov     [rsp+4F8h+var_4A8], r15
0x18026d348  mov     rcx, r14
0x18026d34b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d350  mov     eax, ebx
0x18026d352  jmp     loc_18026DD53
0x18026d357  or      r8, 0FFFFFFFFFFFFFFFFh
0x18026d35b  mov     rdx, [rsp+4F8h+var_498]
0x18026d360  lea     rcx, [rsp+4F8h+string]
0x18026d365  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18026d36a  nop
0x18026d36b  mov     rdx, qword ptr [rsp+4F8h+var_4B8+8]
0x18026d370  lea     rcx, [rsp+4F8h+var_4B8]
0x18026d375  cmp     rdx, [rsp+4F8h+var_4A8]
0x18026d37a  jz      short loc_18026D388
0x18026d37c  lea     rdx, [rsp+4F8h+string]
0x18026d381  call    ??$_Emplace_back_with_unused_capacity@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_back_with_unused_capacity<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18026d386  jmp     short loc_18026D393
0x18026d388  lea     r8, [rsp+4F8h+string]
0x18026d38d  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18026d392  nop
0x18026d393  lea     rcx, [rsp+4F8h+string]
0x18026d398  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18026d39d  movsxd  rcx, esi
0x18026d3a0  mov     rax, qword ptr [rsp+4F8h+var_4B8]
0x18026d3a5  cmp     [rax+rcx*8], r15
0x18026d3a9  jz      short loc_18026D3C7
0x18026d3ab  lea     rcx, [rsp+4F8h+var_498]
0x18026d3b0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18026d3b5  nop
0x18026d3b6  lea     rcx, [rsp+4F8h+var_490]
0x18026d3bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d3c0  inc     esi
0x18026d3c2  jmp     loc_18026D20D
0x18026d3c7  mov     rcx, [rsp+4F8h]; this
0x18026d3cf  mov     ebx, 8007000Eh
0x18026d3d4  mov     r9d, ebx; char *
0x18026d3d7  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026d3de  mov     edx, 0D7h; void *
0x18026d3e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026d3e8  nop
0x18026d3e9  lea     rcx, [rsp+4F8h+var_498]
0x18026d3ee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18026d3f3  nop
0x18026d3f4  lea     rcx, [rsp+4F8h+var_490]
0x18026d3f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d3fe  nop
0x18026d3ff  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d404  test    rcx, rcx
0x18026d407  jz      short loc_18026D437
0x18026d409  mov     rdx, qword ptr [rsp+4F8h+var_4B8+8]
0x18026d40e  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x18026d413  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d418  mov     rdx, [rsp+4F8h+var_4A8]
0x18026d41d  sub     rdx, rcx
0x18026d420  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18026d424  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18026d429  xorps   xmm0, xmm0
0x18026d42c  movdqu  [rsp+4F8h+var_4B8], xmm0
0x18026d432  mov     [rsp+4F8h+var_4A8], r15
0x18026d437  mov     rcx, r14
0x18026d43a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d43f  mov     eax, ebx
0x18026d441  jmp     loc_18026DD53
0x18026d446  mov     [rsp+4F8h+hKey], r15
0x18026d44b  lea     rcx, [rsp+4F8h+hKey]
0x18026d450  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18026d455  mov     [rsp+4F8h+phkResult], rax; unsigned int
0x18026d45a  mov     r9d, 1; samDesired
0x18026d460  xor     r8d, r8d; ulOptions
0x18026d463  lea     rdx, aSoftwareMicros_71; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18026d46a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18026d471  call    cs:__imp_RegOpenKeyExW
0x18026d478  nop     dword ptr [rax+rax+00h]
0x18026d47d  cmp     eax, 2
0x18026d480  jnz     short loc_18026D4D4
0x18026d482  lea     rcx, [rsp+4F8h+hKey]
0x18026d487  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026d48c  nop
0x18026d48d  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d492  test    rcx, rcx
0x18026d495  jz      short loc_18026D4C5
0x18026d497  mov     rdx, qword ptr [rsp+4F8h+var_4B8+8]
0x18026d49c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x18026d4a1  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d4a6  mov     rdx, [rsp+4F8h+var_4A8]
0x18026d4ab  sub     rdx, rcx
0x18026d4ae  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18026d4b2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18026d4b7  xorps   xmm0, xmm0
0x18026d4ba  movdqu  [rsp+4F8h+var_4B8], xmm0
0x18026d4c0  mov     [rsp+4F8h+var_4A8], r15
0x18026d4c5  mov     rcx, r14
0x18026d4c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d4cd  xor     eax, eax
0x18026d4cf  jmp     loc_18026DD53
0x18026d4d4  test    eax, eax
0x18026d4d6  jz      short loc_18026D548
0x18026d4d8  mov     rcx, [rsp+4F8h]; this
0x18026d4e0  mov     r9d, eax; char *
0x18026d4e3  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026d4ea  mov     edx, 0E2h; void *
0x18026d4ef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18026d4f4  mov     ebx, eax
0x18026d4f6  lea     rcx, [rsp+4F8h+hKey]
0x18026d4fb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026d500  nop
0x18026d501  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d506  test    rcx, rcx
0x18026d509  jz      short loc_18026D539
0x18026d50b  mov     rdx, qword ptr [rsp+4F8h+var_4B8+8]
0x18026d510  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x18026d515  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d51a  mov     rdx, [rsp+4F8h+var_4A8]
0x18026d51f  sub     rdx, rcx
0x18026d522  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18026d526  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18026d52b  xorps   xmm0, xmm0
0x18026d52e  movdqu  [rsp+4F8h+var_4B8], xmm0
0x18026d534  mov     [rsp+4F8h+var_4A8], r15
0x18026d539  mov     rcx, r14
0x18026d53c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18026d541  mov     eax, ebx
0x18026d543  jmp     loc_18026DD53
0x18026d548  mov     r12d, r15d
0x18026d54b  mov     [rsp+4F8h+cchValueName], 104h
0x18026d556  mov     [rsp+4F8h+lpcbData], r15; lpcbData
0x18026d55b  mov     [rsp+4F8h+lpData], r15; lpData
0x18026d560  mov     [rsp+4F8h+lpType], r15; lpType
0x18026d565  mov     [rsp+4F8h+phkResult], r15; int
0x18026d56a  lea     r9, [rsp+4F8h+cchValueName]; lpcchValueName
0x18026d572  lea     r8, [rsp+4F8h+ValueName]; lpValueName
0x18026d57a  mov     edx, r12d; dwIndex
0x18026d57d  mov     rcx, [rsp+4F8h+hKey]; hKey
0x18026d582  call    cs:__imp_RegEnumValueW
0x18026d589  nop     dword ptr [rax+rax+00h]
0x18026d58e  cmp     eax, 103h
0x18026d593  jnz     short loc_18026D5E7
0x18026d595  lea     rcx, [rsp+4F8h+hKey]
0x18026d59a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026d59f  nop
0x18026d5a0  mov     rcx, qword ptr [rsp+4F8h+var_4B8]
0x18026d5a5  test    rcx, rcx
0x18026d5a8  jz      short loc_18026D5D8
0x18026d5aa  mov     rdx, qword ptr [rsp+4F8h+var_4B8+8]
  ... truncated ...
```
