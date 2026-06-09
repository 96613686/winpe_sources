# PerFolderRootCache::Register(winrt::Windows::Internal::Storage::PerFolderRootInfo const &)

- ea: `0x1800589d8`
- end: `0x180058feb`
- name: `?Register@PerFolderRootCache@@QEAA?AV?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@AEBUPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Z`
- size: `1555`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180059040`
- `0x1800590f8`

## callees

- `0x180004d6c`
- `0x180007900`
- `0x18000f478`
- `0x180015fa0`
- `0x180016b38`
- `0x180016d78`
- `0x18001d320`
- `0x18001d848`
- `0x18002037c`
- `0x180021d14`
- `0x180022648`
- `0x180024bb4`
- `0x18002b060`
- `0x18003393c`
- `0x1800348e8`
- `0x1800356d8`
- `0x180037780`
- `0x180056a2c`
- `0x180056bfc`
- `0x180056c5c`
- `0x180057940`
- `0x180058898`
- `0x1800589d8`
- `0x180059c98`
- `0x180059ef8`
- `0x180059f44`
- `0x18005b1bc`
- `0x1800790fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180058cae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180058cae`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058c84`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058e12`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058e5c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058c84`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058e12`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058e5c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180058c61`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180058c61`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180058b2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180058d19`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180058b2f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180058d19`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180058d81`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180058dc0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180058e94`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180058d81`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180058dc0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180058e94`

## string_xrefs

- `0x180058f5b`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`
- `0x180058f70`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`
- `0x180058f85`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`
- `0x180058f9a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`
- `0x180058faf`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`
- `0x180058fc4`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`
- `0x180058fd9`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
LPCWSTR *__fastcall PerFolderRootCache::Register(__int64 a1, LPCWSTR *a2, __int64 a3)
{
  unsigned __int16 **v6; // rdx
  __int64 v7; // rdi
  unsigned __int16 *v8; // r12
  HKEY v9; // rbx
  __int64 v10; // r8
  __int128 v11; // xmm6
  HKEY v12; // rbx
  unsigned int v13; // eax
  __int64 v14; // rax
  LPCWSTR v15; // rdx
  __int64 v16; // rsi
  HKEY v17; // rbx
  __int128 v18; // xmm6
  HKEY v19; // rbx
  HRESULT v20; // eax
  const WCHAR *v21; // rdx
  unsigned int v22; // eax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  int v25; // eax
  const GUID *v26; // rax
  int v27; // eax
  const GUID *v28; // rax
  int v29; // eax
  winrt::hstring *v30; // rax
  const unsigned __int16 *v31; // rax
  int v32; // eax
  DWORD dwOptions; // [rsp+28h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+28h] [rbp-E0h]
  HKEY phkResult; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 *v37; // [rsp+60h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+70h] [rbp-98h]
  LPCWSTR *v40; // [rsp+78h] [rbp-90h]
  LPCWSTR *v41; // [rsp+80h] [rbp-88h]
  HKEY *p_hKey; // [rsp+88h] [rbp-80h]
  LPCWSTR *v43; // [rsp+90h] [rbp-78h]
  char v44; // [rsp+98h] [rbp-70h]
  _BYTE v45[56]; // [rsp+A8h] [rbp-60h] BYREF
  HKEY v46; // [rsp+E0h] [rbp-28h]
  GUID pguid; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v48[16]; // [rsp+F8h] [rbp-10h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+108h] [rbp+0h] BYREF
  __m128i si128; // [rsp+118h] [rbp+10h]
  OLECHAR sz[40]; // [rsp+128h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D0h] [rbp+C8h]

  v40 = a2;
  LODWORD(v39) = 0;
  v37 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::start_and_watch_errors(
    &v37,
    v45);
  wil::com_ptr_t<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>,wil::err_returncode_policy>(&v37);
  v37 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v37,
    0);
  CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&v37, v6);
  v7 = -1;
  v8 = v37;
  if ( v37 )
  {
    v9 = v46;
    phkResult = v46;
    if ( v46 )
      _InterlockedIncrement((volatile signed __int32 *)v46 + 92);
    tip2::details::shared_data<0,0,0>::begin_update(v9 + 2);
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
    std::wstring::_Assign<unsigned short>(v9 + 68, v8);
    tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>(&phkResult);
  }
  v11 = *(_OWORD *)winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::PropertyProviderClsid(
                     a3,
                     &pguid);
  v12 = v46;
  phkResult = v46;
  if ( v46 )
    _InterlockedIncrement((volatile signed __int32 *)v46 + 92);
  tip2::details::shared_data<0,0,0>::begin_update(v12 + 2);
  *((_OWORD *)v12 + 19) = v11;
  tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>(&phkResult);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v13 = RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\PerFolderRoots",
          0,
          0,
          0,
          0x20006u,
          0,
          &hKey,
          0);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xE6,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
      (const char *)v13,
      dwOptions);
  v14 = winrt::impl::consume_WindowsUdk_Storage_DestinationList_IAutomaticDestinationListLoadOptions<winrt::WindowsUdk::Storage::DestinationList::IAutomaticDestinationListLoadOptions>::AppPath(
          a3,
          &phkResult);
  pguid = *(GUID *)winrt::hstring::operator std::basic_string_view<unsigned short>(v14, v48);
  PerFolderRootCache::Lookup(a1, a2, &pguid);
  LODWORD(v39) = 1;
  winrt::handle_type<winrt::impl::hstring_traits>::close(&phkResult);
  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  v15 = *a2;
  if ( *a2 )
  {
    if ( lpSubKey != (LPCWSTR *)v15 )
    {
      if ( *((_QWORD *)v15 + 3) > 7u )
        v15 = *(LPCWSTR *)v15;
      std::wstring::_Assign<unsigned short>(lpSubKey, v15);
    }
    v16 = *((_QWORD *)*a2 + 9);
    if ( v16 )
    {
      v17 = v46;
      phkResult = v46;
      if ( v46 )
        _InterlockedIncrement((volatile signed __int32 *)v46 + 92);
      tip2::details::shared_data<0,0,0>::begin_update(v17 + 2);
      do
        ++v7;
      while ( *(_WORD *)(v16 + 2 * v7) );
      std::wstring::_Assign<unsigned short>(v17 + 80, v16);
      tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>(&phkResult);
    }
    v18 = *(_OWORD *)(*a2 + 28);
    v19 = v46;
    phkResult = v46;
    if ( v46 )
      _InterlockedIncrement((volatile signed __int32 *)v46 + 92);
    tip2::details::shared_data<0,0,0>::begin_update(v19 + 2);
    *((_OWORD *)v19 + 22) = v18;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>(&phkResult);
  }
  else
  {
    pguid = 0;
    v20 = CoCreateGuid(&pguid);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
        (const char *)(unsigned int)v20,
        dwOptions);
    StringFromGUID2(&pguid, sz, 39);
    do
      ++v7;
    while ( sz[v7] );
    std::wstring::_Assign<unsigned short>(lpSubKey, sz);
  }
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 16));
  *(_QWORD *)&pguid.Data1 = a1 + 16;
  WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>::clear(a1 + 24);
  std::vector<std::shared_ptr<PerFolderRootInfo const>>::clear(a1 + 80);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 104));
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v21 = (const WCHAR *)lpSubKey;
  if ( si128.m128i_i64[1] > 7uLL )
    v21 = lpSubKey[0];
  v22 = RegCreateKeyExW(hKey, v21, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
  if ( v22 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x103,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
      (const char *)v22,
      dwOptionsa);
  v41 = a2;
  p_hKey = &hKey;
  v43 = lpSubKey;
  v44 = 1;
  v23 = (_QWORD *)winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::FolderType(
                    a3,
                    v48);
  if ( *v23 == *(_QWORD *)&FOLDERTYPEID_Invalid.Data1 && v23[1] == *(_QWORD *)FOLDERTYPEID_Invalid.Data4 )
  {
    RegDeleteValueW(phkResult, L"FolderType");
  }
  else
  {
    v26 = (const GUID *)winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::FolderType(
                          a3,
                          v48);
    StringFromGUID2(v26, sz, 39);
    v27 = SHRegSetString(phkResult, 0, L"FolderType", sz);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
        (const char *)(unsigned int)v27,
        dwOptionsa);
  }
  v24 = (_QWORD *)winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::PropertyProviderClsid(
                    a3,
                    v48);
  if ( *v24 == *(_QWORD *)&GUID_NULL.Data1 && v24[1] == *(_QWORD *)GUID_NULL.Data4 )
  {
    RegDeleteValueW(phkResult, L"PropertyProvider");
  }
  else
  {
    v28 = (const GUID *)winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::PropertyProviderClsid(
                          a3,
                          v48);
    StringFromGUID2(v28, sz, 39);
    v29 = SHRegSetString(phkResult, 0, L"PropertyProvider", sz);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11C,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
        (const char *)(unsigned int)v29,
        dwOptionsa);
  }
  if ( v8 )
  {
    v25 = SHRegSetString(phkResult, 0, L"RegisteredAppID", v8);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
        (const char *)(unsigned int)v25,
        dwOptionsa);
  }
  else
  {
    RegDeleteValueW(phkResult, L"RegisteredAppID");
  }
  v30 = (winrt::hstring *)winrt::impl::consume_WindowsUdk_Storage_DestinationList_IAutomaticDestinationListLoadOptions<winrt::WindowsUdk::Storage::DestinationList::IAutomaticDestinationListLoadOptions>::AppPath(
                            a3,
                            v48);
  v31 = winrt::hstring::c_str(v30);
  v32 = SHRegSetString(phkResult, 0, L"Path", v31);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
      (const char *)(unsigned int)v32,
      dwOptionsa);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v48);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&pguid);
  tip2::details::shared_data<0,0,0>::complete_without_lock(v46 + 2);
  std::wstring::_Tidy_deallocate(lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v37);
  tip2::test_watcher<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::~test_watcher<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>(v45);
  return a2;
}

```

## disassembly

```asm
0x1800589d8  mov     rax, rsp
0x1800589db  mov     [rax+20h], rbx
0x1800589df  push    rbp
0x1800589e0  push    rsi
0x1800589e1  push    rdi
0x1800589e2  push    r12
0x1800589e4  push    r13
0x1800589e6  push    r14
0x1800589e8  push    r15
0x1800589ea  lea     rbp, [rax-0C8h]
0x1800589f1  sub     rsp, 190h
0x1800589f8  movaps  xmmword ptr [rax-48h], xmm6
0x1800589fc  mov     rax, cs:__security_cookie
0x180058a03  xor     rax, rsp
0x180058a06  mov     [rbp+0C0h+var_50], rax
0x180058a0a  mov     r15, r8
0x180058a0d  mov     r14, rdx
0x180058a10  mov     r13, rcx
0x180058a13  mov     [rsp+1C0h+var_150], rdx
0x180058a18  xor     esi, esi
0x180058a1a  mov     dword ptr [rsp+1C0h+var_158], esi
0x180058a1e  mov     [rsp+1C0h+var_168], rsi
0x180058a23  lea     rdx, [rbp+0C0h+var_120]
0x180058a27  lea     rcx, [rsp+1C0h+var_168]
0x180058a2c  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_PerFolderRootRegisterTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_PerFolderRootRegisterTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::start_and_watch_errors(void)
0x180058a31  lea     rcx, [rsp+1C0h+var_168]
0x180058a36  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PerFolderRootRegisterTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>,wil::err_returncode_policy>(void)
0x180058a3b  nop
0x180058a3c  mov     [rsp+1C0h+var_168], rsi
0x180058a41  xor     edx, edx
0x180058a43  lea     rcx, [rsp+1C0h+var_168]
0x180058a48  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058a4d  lea     rcx, [rsp+1C0h+var_168]; this
0x180058a52  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x180058a57  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180058a5b  mov     r12, [rsp+1C0h+var_168]
0x180058a60  test    r12, r12
0x180058a63  jz      short loc_180058AAB
0x180058a65  mov     rbx, [rbp+0C0h+var_E8]
0x180058a69  mov     [rsp+1C0h+var_170], rbx
0x180058a6e  test    rbx, rbx
0x180058a71  jz      short loc_180058A7A
0x180058a73  lock inc dword ptr [rbx+170h]
0x180058a7a  lea     rcx, [rbx+8]
0x180058a7e  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180058a83  nop
0x180058a84  mov     r8, rdi
0x180058a87  inc     r8
0x180058a8a  cmp     [r12+r8*2], si
0x180058a8f  jnz     short loc_180058A87
0x180058a91  lea     rcx, [rbx+110h]
0x180058a98  mov     rdx, r12
0x180058a9b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180058aa0  nop
0x180058aa1  lea     rcx, [rsp+1C0h+var_170]
0x180058aa6  call    ??1?$test_data_control@V?$merged_data@U_tip_PerFolderRootRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>(void)
0x180058aab  lea     rdx, [rbp+0C0h+pguid]
0x180058aaf  mov     rcx, r15
0x180058ab2  call    ?PropertyProviderClsid@?$consume_Windows_Internal_Storage_IPerFolderRootInfo@UIPerFolderRootInfo@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::PropertyProviderClsid(void)
0x180058ab7  movups  xmm6, xmmword ptr [rax]
0x180058aba  mov     rbx, [rbp+0C0h+var_E8]
0x180058abe  mov     [rsp+1C0h+var_170], rbx
0x180058ac3  test    rbx, rbx
0x180058ac6  jz      short loc_180058ACF
0x180058ac8  lock inc dword ptr [rbx+170h]
0x180058acf  lea     rcx, [rbx+8]
0x180058ad3  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180058ad8  movdqu  xmmword ptr [rbx+130h], xmm6
0x180058ae0  lea     rcx, [rsp+1C0h+var_170]
0x180058ae5  call    ??1?$test_data_control@V?$merged_data@U_tip_PerFolderRootRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>(void)
0x180058aea  mov     [rsp+1C0h+hKey], rsi
0x180058aef  xor     edx, edx
0x180058af1  lea     rcx, [rsp+1C0h+hKey]
0x180058af6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180058afb  mov     [rsp+1C0h+lpdwDisposition], rsi; lpdwDisposition
0x180058b00  lea     rax, [rsp+1C0h+hKey]
0x180058b05  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180058b0a  mov     [rsp+1C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180058b0f  mov     [rsp+1C0h+samDesired], 20006h; samDesired
0x180058b17  mov     [rsp+1C0h+dwOptions], esi; int
0x180058b1b  xor     r9d, r9d; lpClass
0x180058b1e  xor     r8d, r8d; Reserved
0x180058b21  lea     rdx, ?PerFolderRegKey@Details@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180058b28  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180058b2f  call    cs:__imp_RegCreateKeyExW
0x180058b35  mov     rcx, [rbp+0C8h]; this
0x180058b3c  test    eax, eax
0x180058b3e  jnz     loc_180058FAC
0x180058b44  lea     rdx, [rsp+1C0h+var_170]
0x180058b49  mov     rcx, r15
0x180058b4c  call    ?AppPath@?$consume_WindowsUdk_Storage_DestinationList_IAutomaticDestinationListLoadOptions@UIAutomaticDestinationListLoadOptions@DestinationList@Storage@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_Storage_DestinationList_IAutomaticDestinationListLoadOptions<winrt::WindowsUdk::Storage::DestinationList::IAutomaticDestinationListLoadOptions>::AppPath(void)
0x180058b51  nop
0x180058b52  lea     rdx, [rbp+0C0h+var_D0]
0x180058b56  mov     rcx, rax
0x180058b59  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ; winrt::hstring::operator std::basic_string_view<ushort>(void)
0x180058b5e  movups  xmm0, xmmword ptr [rax]
0x180058b61  movdqu  xmmword ptr [rbp+0C0h+pguid.Data1], xmm0
0x180058b66  lea     r8, [rbp+0C0h+pguid]
0x180058b6a  mov     rdx, r14
0x180058b6d  mov     rcx, r13
0x180058b70  call    ?Lookup@PerFolderRootCache@@QEAA?AV?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; PerFolderRootCache::Lookup(std::basic_string_view<ushort>)
0x180058b75  mov     dword ptr [rsp+1C0h+var_158], 1
0x180058b7d  lea     rcx, [rsp+1C0h+var_170]
0x180058b82  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180058b87  xorps   xmm0, xmm0
0x180058b8a  movups  xmmword ptr [rbp+0C0h+lpSubKey], xmm0
0x180058b8e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180058b96  movdqu  [rbp+0C0h+var_B0], xmm1
0x180058b9b  mov     word ptr [rbp+0C0h+lpSubKey], si
0x180058b9f  mov     rdx, [r14]
0x180058ba2  test    rdx, rdx
0x180058ba5  jz      loc_180058C59
0x180058bab  lea     rax, [rbp+0C0h+lpSubKey]
0x180058baf  cmp     rax, rdx
0x180058bb2  jz      short loc_180058BCB
0x180058bb4  mov     r8, [rdx+10h]
0x180058bb8  cmp     qword ptr [rdx+18h], 7
0x180058bbd  jbe     short loc_180058BC2
0x180058bbf  mov     rdx, [rdx]
0x180058bc2  lea     rcx, [rbp+0C0h+lpSubKey]
0x180058bc6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180058bcb  mov     rax, [r14]
0x180058bce  mov     rsi, [rax+48h]
0x180058bd2  test    rsi, rsi
0x180058bd5  jz      short loc_180058C1E
0x180058bd7  mov     rbx, [rbp+0C0h+var_E8]
0x180058bdb  mov     [rsp+1C0h+var_170], rbx
0x180058be0  test    rbx, rbx
0x180058be3  jz      short loc_180058BEC
0x180058be5  lock inc dword ptr [rbx+170h]
0x180058bec  lea     rcx, [rbx+8]
0x180058bf0  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180058bf5  nop
0x180058bf6  xor     eax, eax
0x180058bf8  inc     rdi
0x180058bfb  cmp     [rsi+rdi*2], ax
0x180058bff  jnz     short loc_180058BF8
0x180058c01  lea     rcx, [rbx+140h]
0x180058c08  mov     r8, rdi
0x180058c0b  mov     rdx, rsi
0x180058c0e  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180058c13  nop
0x180058c14  lea     rcx, [rsp+1C0h+var_170]
0x180058c19  call    ??1?$test_data_control@V?$merged_data@U_tip_PerFolderRootRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>(void)
0x180058c1e  mov     rax, [r14]
0x180058c21  movups  xmm6, xmmword ptr [rax+38h]
0x180058c25  mov     rbx, [rbp+0C0h+var_E8]
0x180058c29  mov     [rsp+1C0h+var_170], rbx
0x180058c2e  xor     esi, esi
0x180058c30  test    rbx, rbx
0x180058c33  jz      short loc_180058C3C
0x180058c35  lock inc dword ptr [rbx+170h]
0x180058c3c  lea     rcx, [rbx+8]
0x180058c40  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180058c45  movdqu  xmmword ptr [rbx+160h], xmm6
0x180058c4d  lea     rcx, [rsp+1C0h+var_170]
0x180058c52  call    ??1?$test_data_control@V?$merged_data@U_tip_PerFolderRootRegisterTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>::~test_data_control<tip2::details::merged_data<_tip_PerFolderRootRegisterTest,_tip_PerFolderRootRegisterTest>>(void)
0x180058c57  jmp     short loc_180058CA7
0x180058c59  movups  xmmword ptr [rbp+0C0h+pguid.Data1], xmm0
0x180058c5d  lea     rcx, [rbp+0C0h+pguid]; pguid
0x180058c61  call    cs:__imp_CoCreateGuid
0x180058c67  mov     rcx, [rbp+0C8h]; this
0x180058c6e  test    eax, eax
0x180058c70  js      loc_180058FC1
0x180058c76  mov     r8d, 27h ; '''; cchMax
0x180058c7c  lea     rdx, [rbp+0C0h+sz]; lpsz
0x180058c80  lea     rcx, [rbp+0C0h+pguid]; rguid
0x180058c84  call    cs:__imp_StringFromGUID2
0x180058c8a  lea     rax, [rbp+0C0h+sz]
0x180058c8e  inc     rdi
0x180058c91  cmp     [rax+rdi*2], si
0x180058c95  jnz     short loc_180058C8E
0x180058c97  mov     r8, rdi
0x180058c9a  lea     rdx, [rbp+0C0h+sz]
0x180058c9e  lea     rcx, [rbp+0C0h+lpSubKey]
0x180058ca2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180058ca7  lea     rbx, [r13+10h]
0x180058cab  mov     rcx, rbx; SRWLock
0x180058cae  call    cs:__imp_AcquireSRWLockExclusive
0x180058cb4  mov     qword ptr [rbp+0C0h+pguid.Data1], rbx
0x180058cb8  lea     rcx, [r13+18h]
0x180058cbc  call    ?clear@?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@QEAAXXZ; WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>::clear(void)
0x180058cc1  lea     rcx, [r13+50h]
0x180058cc5  call    ?clear@?$vector@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@V?$allocator@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@@2@@std@@QEAAXXZ; std::vector<std::shared_ptr<PerFolderRootInfo const>>::clear(void)
0x180058cca  lock inc dword ptr [r13+68h]
0x180058ccf  mov     [rsp+1C0h+var_170], rsi
0x180058cd4  xor     edx, edx
0x180058cd6  lea     rcx, [rsp+1C0h+var_170]
0x180058cdb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180058ce0  lea     rdx, [rbp+0C0h+lpSubKey]
0x180058ce4  cmp     qword ptr [rbp+0C0h+var_B0+8], 7
0x180058ce9  cmova   rdx, [rbp+0C0h+lpSubKey]; lpSubKey
0x180058cee  mov     [rsp+1C0h+lpdwDisposition], rsi; lpdwDisposition
0x180058cf3  lea     rax, [rsp+1C0h+var_170]
0x180058cf8  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180058cfd  mov     [rsp+1C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180058d02  mov     [rsp+1C0h+samDesired], 20006h; samDesired
0x180058d0a  mov     [rsp+1C0h+dwOptions], esi; unsigned int
0x180058d0e  xor     r9d, r9d; lpClass
0x180058d11  xor     r8d, r8d; Reserved
0x180058d14  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180058d19  call    cs:__imp_RegCreateKeyExW
0x180058d1f  mov     rcx, [rbp+0C8h]; this
0x180058d26  test    eax, eax
0x180058d28  jnz     loc_180058FD6
0x180058d2e  mov     [rsp+1C0h+var_148], r14
0x180058d33  lea     rax, [rsp+1C0h+hKey]
0x180058d38  mov     [rbp+0C0h+var_140], rax
0x180058d3c  lea     rax, [rbp+0C0h+lpSubKey]
0x180058d40  mov     [rbp+0C0h+var_138], rax
0x180058d44  mov     [rbp+0C0h+var_130], 1
0x180058d48  lea     rdx, [rbp+0C0h+var_D0]
0x180058d4c  mov     rcx, r15
0x180058d4f  call    ?FolderType@?$consume_Windows_Internal_Storage_IPerFolderRootInfo@UIPerFolderRootInfo@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::FolderType(void)
0x180058d54  mov     rcx, [rax]
0x180058d57  cmp     rcx, qword ptr cs:FOLDERTYPEID_Invalid.Data1
0x180058d5e  jnz     loc_180058DF9
0x180058d64  mov     rax, [rax+8]
0x180058d68  cmp     rax, qword ptr cs:FOLDERTYPEID_Invalid.Data4
0x180058d6f  jnz     loc_180058DF9
0x180058d75  lea     rdx, ?FolderTypeValue@Details@@3QBGB; "FolderType"
0x180058d7c  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180058d81  call    cs:__imp_RegDeleteValueW
0x180058d87  lea     rdx, [rbp+0C0h+var_D0]
0x180058d8b  mov     rcx, r15
0x180058d8e  call    ?PropertyProviderClsid@?$consume_Windows_Internal_Storage_IPerFolderRootInfo@UIPerFolderRootInfo@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::PropertyProviderClsid(void)
0x180058d93  mov     rcx, [rax]
0x180058d96  cmp     rcx, qword ptr cs:GUID_NULL.Data1
0x180058d9d  jnz     loc_180058E43
0x180058da3  mov     rax, [rax+8]
0x180058da7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180058dae  jnz     loc_180058E43
0x180058db4  lea     rdx, ?PropertyProviderValue@Details@@3QBGB; "PropertyProvider"
0x180058dbb  mov     rcx, [rsp+1C0h+var_170]; hKey
0x180058dc0  call    cs:__imp_RegDeleteValueW
0x180058dc6  mov     rcx, [rsp+1C0h+var_170]; HKEY
0x180058dcb  test    r12, r12
0x180058dce  jz      loc_180058E8D
0x180058dd4  mov     r9, r12; unsigned __int16 *
0x180058dd7  lea     r8, ?RegisteredAppIDValue@Details@@3QBGB; "RegisteredAppID"
0x180058dde  xor     edx, edx; unsigned __int16 *
0x180058de0  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180058de5  mov     rcx, [rbp+0C8h]; this
0x180058dec  test    eax, eax
0x180058dee  js      loc_180058F6D
0x180058df4  jmp     loc_180058E9A
0x180058df9  lea     rdx, [rbp+0C0h+var_D0]
0x180058dfd  mov     rcx, r15
0x180058e00  call    ?FolderType@?$consume_Windows_Internal_Storage_IPerFolderRootInfo@UIPerFolderRootInfo@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::FolderType(void)
0x180058e05  mov     r8d, 27h ; '''; cchMax
0x180058e0b  lea     rdx, [rbp+0C0h+sz]; lpsz
0x180058e0f  mov     rcx, rax; rguid
0x180058e12  call    cs:__imp_StringFromGUID2
0x180058e18  lea     r9, [rbp+0C0h+sz]; unsigned __int16 *
0x180058e1c  lea     r8, ?FolderTypeValue@Details@@3QBGB; "FolderType"
0x180058e23  xor     edx, edx; unsigned __int16 *
0x180058e25  mov     rcx, [rsp+1C0h+var_170]; HKEY
0x180058e2a  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180058e2f  mov     rcx, [rbp+0C8h]; this
0x180058e36  test    eax, eax
0x180058e38  js      loc_180058F82
0x180058e3e  jmp     loc_180058D87
0x180058e43  lea     rdx, [rbp+0C0h+var_D0]
0x180058e47  mov     rcx, r15
0x180058e4a  call    ?PropertyProviderClsid@?$consume_Windows_Internal_Storage_IPerFolderRootInfo@UIPerFolderRootInfo@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_IPerFolderRootInfo<winrt::Windows::Internal::Storage::IPerFolderRootInfo>::PropertyProviderClsid(void)
0x180058e4f  mov     r8d, 27h ; '''; cchMax
0x180058e55  lea     rdx, [rbp+0C0h+sz]; lpsz
0x180058e59  mov     rcx, rax; rguid
0x180058e5c  call    cs:__imp_StringFromGUID2
0x180058e62  lea     r9, [rbp+0C0h+sz]; unsigned __int16 *
0x180058e66  lea     r8, ?PropertyProviderValue@Details@@3QBGB; "PropertyProvider"
0x180058e6d  xor     edx, edx; unsigned __int16 *
0x180058e6f  mov     rcx, [rsp+1C0h+var_170]; HKEY
0x180058e74  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180058e79  mov     rcx, [rbp+0C8h]; this
0x180058e80  test    eax, eax
0x180058e82  js      loc_180058F97
0x180058e88  jmp     loc_180058DC6
0x180058e8d  lea     rdx, ?RegisteredAppIDValue@Details@@3QBGB; "RegisteredAppID"
0x180058e94  call    cs:__imp_RegDeleteValueW
0x180058e9a  lea     rdx, [rbp+0C0h+var_D0]
0x180058e9e  mov     rcx, r15
0x180058ea1  call    ?AppPath@?$consume_WindowsUdk_Storage_DestinationList_IAutomaticDestinationListLoadOptions@UIAutomaticDestinationListLoadOptions@DestinationList@Storage@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_Storage_DestinationList_IAutomaticDestinationListLoadOptions<winrt::WindowsUdk::Storage::DestinationList::IAutomaticDestinationListLoadOptions>::AppPath(void)
0x180058ea6  nop
0x180058ea7  mov     rcx, rax; this
0x180058eaa  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180058eaf  mov     r9, rax; unsigned __int16 *
0x180058eb2  lea     r8, ?PathValue@Details@@3QBGB; "Path"
0x180058eb9  xor     edx, edx; unsigned __int16 *
0x180058ebb  mov     rcx, [rsp+1C0h+var_170]; HKEY
0x180058ec0  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180058ec5  mov     rcx, [rbp+0C8h]; this
0x180058ecc  test    eax, eax
0x180058ece  js      loc_180058F58
0x180058ed4  lea     rcx, [rbp+0C0h+var_D0]
0x180058ed8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180058edd  nop
0x180058ede  lea     rcx, [rsp+1C0h+var_170]
0x180058ee3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180058ee8  nop
  ... truncated ...
```
