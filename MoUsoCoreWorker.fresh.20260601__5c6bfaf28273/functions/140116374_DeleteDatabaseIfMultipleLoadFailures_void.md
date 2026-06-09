# DeleteDatabaseIfMultipleLoadFailures(void)

- ea: `0x140116374`
- end: `0x1401170b4`
- name: `?DeleteDatabaseIfMultipleLoadFailures@@YAXXZ`
- size: `3392`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007f8ec`

## callees

- `0x14003f778`
- `0x140040184`
- `0x140041b3c`
- `0x14004296c`
- `0x140042ef4`
- `0x140043354`
- `0x1400447ac`
- `0x140045404`
- `0x140057a20`
- `0x140076f3c`
- `0x140116374`
- `0x140117fc8`
- `0x140118f6c`
- `0x140119004`
- `0x14011916c`
- `0x1401192c4`
- `0x14012d7d8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401168ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140116b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140116db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401168ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140116b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140116db3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1401168e2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140116b1c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140116da9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1401168e2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140116b1c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140116da9`

## string_xrefs

- `0x140116fe1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140117087`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1401170a1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140116578`: `AllowedUpdateManagerCtorFailures`
- `0x14011658d`: `AllowedUpdateManagerCtorFailures`
- `0x1401163ee`: `UpdateManagerCtorFailures`
- `0x140116927`: `UpdateManagerCtorFailures`
- `0x140116bed`: `UpdateManagerCtorFailures`
- `0x140116dd2`: `UpdateManagerCtorFailures`
- `0x14011701f`: `rename`
- `0x140117039`: `rename`
- `0x140117072`: `rename`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void DeleteDatabaseIfMultipleLoadFailures(void)
{
  __int64 System; // rax
  __int64 v1; // rcx
  int *traits_2_unsigned_short; // rax
  const char *v3; // r9
  int v4; // r11d
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned int SystemValueOrDefault; // esi
  volatile signed __int32 *v8; // r14
  volatile signed __int32 *v9; // r14
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 (__fastcall *v12)(__int64, __int128 *, char *); // r14
  __int16 *v13; // rax
  const char *v14; // r9
  __int64 v15; // r11
  __int64 v16; // rax
  unsigned int v17; // r15d
  volatile signed __int32 *v18; // r14
  volatile signed __int32 *v19; // r14
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  volatile signed __int32 *v22; // r14
  volatile signed __int32 *v23; // r14
  __int64 v24; // rax
  __int64 v25; // rcx
  _QWORD *v26; // rax
  struct std::error_code *v27; // r8
  volatile signed __int32 *v28; // r14
  volatile signed __int32 *v29; // r14
  bool v30; // al
  const struct std::filesystem::path *v31; // r9
  const WCHAR *p_lpNewFileName; // rdx
  const WCHAR *p_lpExistingFileName; // rcx
  DWORD LastError; // eax
  const char *v35; // r9
  __int64 v36; // rax
  __int64 v37; // rcx
  _QWORD *v38; // rax
  __int64 v39; // rax
  volatile signed __int32 *v40; // rsi
  volatile signed __int32 *v41; // rsi
  const struct std::filesystem::path *v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rcx
  _QWORD *v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rsi
  const WCHAR *v49; // rdx
  const WCHAR *v50; // rcx
  DWORD v51; // eax
  volatile signed __int32 *v52; // rsi
  volatile signed __int32 *v53; // rsi
  __int64 v54; // rax
  __int64 v55; // rcx
  _QWORD *v56; // rax
  struct std::error_code *v57; // r8
  volatile signed __int32 *v58; // r14
  volatile signed __int32 *v59; // r14
  bool v60; // al
  const struct std::filesystem::path *v61; // r9
  const WCHAR *v62; // rdx
  const WCHAR *v63; // rcx
  DWORD v64; // eax
  __int64 v65; // rax
  __int64 v66; // rcx
  void (__fastcall *v67)(__int64, __int128 *, _OWORD *, __int128 *, _DWORD *); // r14
  int *v68; // rax
  const char *v69; // r9
  __int64 v70; // r11
  __int64 v71; // rax
  __int64 v72; // rax
  const char *v73; // r9
  volatile signed __int32 *v74; // rsi
  volatile signed __int32 *v75; // rsi
  const char *v76; // r9
  __int64 *v77; // rdx
  __int64 v78; // [rsp+0h] [rbp-138h] BYREF
  unsigned int v79[4]; // [rsp+30h] [rbp-108h] BYREF
  __int128 v80; // [rsp+40h] [rbp-F8h] BYREF
  __int128 v81; // [rsp+50h] [rbp-E8h] BYREF
  char v82[16]; // [rsp+60h] [rbp-D8h] BYREF
  __int128 v83; // [rsp+80h] [rbp-B8h] BYREF
  _OWORD v84[2]; // [rsp+90h] [rbp-A8h] BYREF
  _DWORD v85[8]; // [rsp+B0h] [rbp-88h] BYREF
  char v86; // [rsp+D0h] [rbp-68h]
  LPCWSTR lpExistingFileName; // [rsp+D8h] [rbp-60h] BYREF
  volatile signed __int32 *v88; // [rsp+E0h] [rbp-58h]
  unsigned __int64 v89; // [rsp+F0h] [rbp-48h]
  LPCWSTR lpNewFileName; // [rsp+F8h] [rbp-40h] BYREF
  volatile signed __int32 *v91; // [rsp+100h] [rbp-38h]
  unsigned __int64 v92; // [rsp+110h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    System = SystemInterface::Providers::GetSystem(&v81);
    v1 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v1 + 32LL))(v1, v84);
    v79[0] = 0;
    traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                       L"UpdateManagerCtorFailures",
                                       &dword_1404141DC,
                                       0);
    if ( traits_2_unsigned_short == &dword_1404141DC
      || (v5 = ((char *)traits_2_unsigned_short - (char *)L"UpdateManagerCtorFailures") >> 1, v5 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v3);
    }
    *(_QWORD *)v82 = L"UpdateManagerCtorFailures";
    *(_QWORD *)&v82[8] = v5;
    v83 = 0u;
    *(_QWORD *)&v80 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
    v6 = -1;
    do
      ++v6;
    while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v6] );
    *((_QWORD *)&v80 + 1) = v6;
    SystemValueOrDefault = SystemInterface::Registry::GetSystemValueOrDefault(
                             v4,
                             (unsigned int)&v80,
                             (unsigned int)&v83,
                             (unsigned int)v82,
                             (__int64)v79);
    v79[0] = SystemValueOrDefault;
    v8 = (volatile signed __int32 *)*((_QWORD *)&v84[0] + 1);
    if ( *((_QWORD *)&v84[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    v9 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
    if ( *((_QWORD *)&v81 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    v10 = SystemInterface::Providers::GetSystem(&v83);
    v11 = *(_QWORD *)v10 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v10 + 8LL) + 4LL);
    v12 = *(__int64 (__fastcall **)(__int64, __int128 *, char *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v11 + 40LL))(
                                                                                 v11,
                                                                                 v84)
                                                                + 56LL);
    *(_DWORD *)v82 = 2;
    v13 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"AllowedUpdateManagerCtorFailures",
                       word_1404141A2,
                       0);
    if ( v13 == word_1404141A2 || (v16 = ((char *)v13 - (char *)L"AllowedUpdateManagerCtorFailures") >> 1, v16 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v14);
    *(_QWORD *)&v80 = L"AllowedUpdateManagerCtorFailures";
    *((_QWORD *)&v80 + 1) = v16;
    v81 = v80;
    v17 = v12(v15, &v81, v82);
    if ( v17 < 2 )
      v17 = 2;
    v18 = (volatile signed __int32 *)*((_QWORD *)&v84[0] + 1);
    if ( *((_QWORD *)&v84[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v19 = (volatile signed __int32 *)*((_QWORD *)&v83 + 1);
    if ( *((_QWORD *)&v83 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    if ( SystemValueOrDefault >= v17 )
    {
      v20 = (_QWORD *)SystemInterface::Providers::GetSystem(v84);
      v21 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v20 + 40LL))(*v20, &v81);
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*v21 + 320LL))(*v21, SystemValueOrDefault, v17);
      v22 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
      if ( *((_QWORD *)&v81 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( !_InterlockedDecrement(v22 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
      v23 = (volatile signed __int32 *)*((_QWORD *)&v84[0] + 1);
      if ( *((_QWORD *)&v84[0] + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v84[0] + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( !_InterlockedDecrement(v23 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_RecoverDatabaseOnWriteAccessFailure_31864050>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_RecoverDatabaseOnWriteAccessFailure_31864050>::GetImpl'::`2'::impl) )
      {
        try
        {
          v24 = SystemInterface::Providers::GetSystem(v84);
          v25 = *(_QWORD *)v24 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v24 + 8LL) + 4LL);
          v26 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v25 + 8LL))(v25, &v81);
          (*(void (__fastcall **)(_QWORD, LPCWSTR *))(*(_QWORD *)*v26 + 16LL))(*v26, &lpExistingFileName);
          v28 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
          if ( *((_QWORD *)&v81 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
              if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
            }
          }
          v29 = (volatile signed __int32 *)*((_QWORD *)&v84[0] + 1);
          if ( *((_QWORD *)&v84[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
              if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
            }
          }
          *(_QWORD *)v82 = 0;
          *(_QWORD *)&v82[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
          v30 = std::filesystem::exists(
                  (std::filesystem *)&lpExistingFileName,
                  (const struct std::filesystem::path *)v82,
                  v27);
          if ( *(_DWORD *)v82 )
            std::filesystem::_Throw_fs_error(
              (std::filesystem *)"exists",
              v82,
              (const struct std::error_code *)&lpExistingFileName,
              v31);
          if ( v30 )
          {
            std::wstring::wstring(&lpNewFileName, &lpExistingFileName);
            *(_QWORD *)&v80 = L".bad";
            *((_QWORD *)&v80 + 1) = 4;
            v81 = v80;
            std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v84, &v81);
            std::filesystem::path::replace_extension(
              (std::filesystem::path *)&lpNewFileName,
              (const struct std::filesystem::path *)v84);
            std::wstring::~wstring(v84);
            p_lpNewFileName = (const WCHAR *)&lpNewFileName;
            if ( v92 > 7 )
              p_lpNewFileName = lpNewFileName;
            p_lpExistingFileName = (const WCHAR *)&lpExistingFileName;
            if ( v89 > 7 )
              p_lpExistingFileName = lpExistingFileName;
            if ( !MoveFileExW(p_lpExistingFileName, p_lpNewFileName, 3u) )
            {
              LastError = GetLastError();
              if ( LastError )
                std::filesystem::_Throw_fs_error("rename", LastError, &lpExistingFileName, &lpNewFileName);
            }
            SystemValueOrDefault = 0;
            v79[0] = 0;
            std::wstring::~wstring(&lpNewFileName);
          }
          std::wstring::~wstring(&lpExistingFileName);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x29,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\ManagerIntegrity.cpp",
            v35);
          SystemValueOrDefault = v79[0];
        }
        try
        {
          if ( SystemValueOrDefault )
          {
            v36 = SystemInterface::Providers::GetSystem(v84);
            v37 = *(_QWORD *)v36 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v36 + 8LL) + 4LL);
            v38 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v37 + 8LL))(v37, &v81);
            v39 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)*v38 + 16LL))(*v38, v85);
            std::filesystem::path::parent_path(v39, &lpExistingFileName);
            std::wstring::~wstring(v85);
            v40 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
            if ( *((_QWORD *)&v81 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
                if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
              }
            }
            v41 = (volatile signed __int32 *)*((_QWORD *)&v84[0] + 1);
            if ( *((_QWORD *)&v84[0] + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
                if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
              }
            }
            *(_QWORD *)&v80 = L"bad";
            *((_QWORD *)&v80 + 1) = 3;
            std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&lpNewFileName, &v80);
            std::filesystem::path::remove_filename((std::filesystem::path *)&lpExistingFileName);
            std::filesystem::path::operator/=(&lpExistingFileName);
            std::wstring::~wstring(&lpNewFileName);
            std::filesystem::remove_all((std::filesystem *)&lpExistingFileName, v42);
            v43 = SystemInterface::Providers::GetSystem(&v83);
            v44 = *(_QWORD *)v43 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v43 + 8LL) + 4LL);
            v45 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v44 + 8LL))(v44, &v80);
            v46 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v45 + 16LL))(*v45, v82);
            v47 = std::filesystem::path::parent_path(v46, &lpNewFileName);
            v48 = v47;
            v49 = (const WCHAR *)&lpExistingFileName;
            if ( v89 > 7 )
              v49 = lpExistingFileName;
            v50 = (const WCHAR *)v47;
            if ( *(_QWORD *)(v47 + 24) > 7u )
              v50 = *(const WCHAR **)v47;
            if ( !MoveFileExW(v50, v49, 3u) )
            {
              v51 = GetLastError();
              if ( v51 )
                std::filesystem::_Throw_fs_error("rename", v51, v48, &lpExistingFileName);
            }
            std::wstring::~wstring(&lpNewFileName);
            std::wstring::~wstring(v82);
            v52 = (volatile signed __int32 *)*((_QWORD *)&v80 + 1);
            if ( *((_QWORD *)&v80 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v80 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
                if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
              }
            }
            v53 = (volatile signed __int32 *)*((_QWORD *)&v83 + 1);
            if ( *((_QWORD *)&v83 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
                if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
              }
            }
            SystemValueOrDefault = 0;
            v79[0] = 0;
            std::wstring::~wstring(&lpExistingFileName);
          }
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x34,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\ManagerIntegrity.cpp",
            v35);
          SystemValueOrDefault = v79[0];
        }
      }
      else
      {
        v54 = SystemInterface::Providers::GetSystem(v84);
        v55 = *(_QWORD *)v54 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v54 + 8LL) + 4LL);
        v56 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v55 + 8LL))(v55, &v81);
        (*(void (__fastcall **)(_QWORD, LPCWSTR *))(*(_QWORD *)*v56 + 16LL))(*v56, &lpExistingFileName);
        v58 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
        if ( *((_QWORD *)&v81 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
            if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
          }
        }
        v59 = (volatile signed __int32 *)*((_QWORD *)&v84[0] + 1);
        if ( *((_QWORD *)&v84[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
            if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
          }
        }
        *(_QWORD *)v82 = 0;
        *(_QWORD *)&v82[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
        v60 = std::filesystem::exists(
                (std::filesystem *)&lpExistingFileName,
                (const struct std::filesystem::path *)v82,
                v57);
        if ( *(_DWORD *)v82 )
          std::filesystem::_Throw_fs_error(
            (std::filesystem *)"exists",
            v82,
            (const struct std::error_code *)&lpExistingFileName,
            v61);
        if ( v60 )
        {
          std::wstring::wstring(&lpNewFileName, &lpExistingFileName);
          *(_QWORD *)&v80 = L".bad";
          *((_QWORD *)&v80 + 1) = 4;
          v81 = v80;
          std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v84, &v81);
          std::filesystem::path::replace_extension(
            (std::filesystem::path *)&lpNewFileName,
            (const struct std::filesystem::path *)v84);
          std::wstring::~wstring(v84);
          v62 = (const WCHAR *)&lpNewFileName;
          if ( v92 > 7 )
            v62 = lpNewFileName;
          v63 = (const WCHAR *)&lpExistingFileName;
          if ( v89 > 7 )
            v63 = lpExistingFileName;
          if ( !MoveFileExW(v63, v62, 3u) )
          {
            v64 = GetLastError();
            if ( v64 )
            {
              try
              {
                std::filesystem::_Throw_fs_error("rename", v64, &lpExistingFileName, &lpNewFileName);
              }
              catch ( ... )
              {
                v77 = &v78;
                wil::details::in1diag3::Log_CaughtException(
                  (wil::details::in1diag3 *)v77[39],
                  (void *)0x42,
                  (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\ManagerIntegrity.cpp",
                  v76);
                SystemValueOrDefault = v79[0];
                goto LABEL_96;
              }
            }
          }
          SystemValueOrDefault = 0;
          v79[0] = 0;
LABEL_96:
          std::wstring::~wstring(&lpNewFileName);
        }
        std::wstring::~wstring(&lpExistingFileName);
      }
    }
    v65 = SystemInterface::Providers::GetSystem(&lpExistingFileName);
    v66 = *(_QWORD *)v65 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v65 + 8LL) + 4LL);
    v67 = *(void (__fastcall **)(__int64, __int128 *, _OWORD *, __int128 *, _DWORD *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v66 + 32LL))(v66, &lpNewFileName)
                                                                                     + 64LL);
    v85[0] = SystemValueOrDefault + 1;
    v86 = 0;
    v68 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                   L"UpdateManagerCtorFailures",
                   &dword_1404141DC,
                   0);
    if ( v68 == &dword_1404141DC || (v71 = ((char *)v68 - (char *)L"UpdateManagerCtorFailures") >> 1, v71 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v69);
    *(_QWORD *)&v80 = L"UpdateManagerCtorFailures";
    *((_QWORD *)&v80 + 1) = v71;
    v83 = 0u;
    *(_QWORD *)v82 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
    v72 = -1;
    do
      ++v72;
    while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v72] );
    *(_QWORD *)&v82[8] = v72;
    v81 = v80;
    v84[0] = v83;
    v80 = *(_OWORD *)v82;
    v67(v70, &v80, v84, &v81, v85);
    if ( v86 != -1 && v86 && v86 != 1 )
      std::wstring::~wstring(v85);
    v74 = v91;
    if ( v91 )
    {
      if ( !_InterlockedDecrement(v91 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
        if ( !_InterlockedDecrement(v74 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
      }
    }
    v75 = v88;
    if ( v88 )
    {
      if ( !_InterlockedDecrement(v88 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
        if ( !_InterlockedDecrement(v75 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\mostack\\updatemanager\\ManagerIntegrity.cpp",
      v73);
  }
}

```

## disassembly

```asm
0x140116374  mov     rax, rsp
0x140116377  mov     [rax+8], rbx
0x14011637b  mov     [rax+10h], rsi
0x14011637f  mov     [rax+18h], rdi
0x140116383  mov     [rax+20h], r12
0x140116387  push    r13
0x140116389  push    r14
0x14011638b  push    r15
0x14011638d  sub     rsp, 120h
0x140116394  mov     rax, cs:__security_cookie
0x14011639b  xor     rax, rsp
0x14011639e  mov     [rsp+138h+var_20], rax
0x1401163a6  xor     edi, edi
0x1401163a8  lea     rcx, [rsp+138h+var_E8]
0x1401163ad  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1401163b2  nop
0x1401163b3  mov     rdx, [rax]
0x1401163b6  mov     rax, [rdx+8]
0x1401163ba  movsxd  rcx, dword ptr [rax+4]
0x1401163be  add     rdx, 8
0x1401163c2  add     rcx, rdx
0x1401163c5  mov     rax, [rcx]
0x1401163c8  lea     rdx, [rsp+138h+var_A8]
0x1401163d0  mov     rax, [rax+20h]
0x1401163d4  call    _guard_dispatch_icall
0x1401163d9  nop
0x1401163da  mov     r11, [rax]
0x1401163dd  mov     [rsp+138h+var_108], edi
0x1401163e1  xor     r8d, r8d
0x1401163e4  lea     r13, dword_1404141DC
0x1401163eb  mov     rdx, r13
0x1401163ee  lea     r12, aUpdatemanagerc; "UpdateManagerCtorFailures"
0x1401163f5  mov     rcx, r12
0x1401163f8  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1401163fd  cmp     rax, r13
0x140116400  jz      loc_140116FD9
0x140116406  sub     rax, r12
0x140116409  sar     rax, 1
0x14011640c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140116410  cmp     rax, rbx
0x140116413  jz      loc_140116FD9
0x140116419  mov     qword ptr [rsp+138h+var_D8], r12
0x14011641e  mov     qword ptr [rsp+138h+var_D8+8], rax
0x140116423  mov     qword ptr [rsp+138h+var_B8], rdi
0x14011642b  mov     qword ptr [rsp+138h+var_B8+8], rdi
0x140116433  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x14011643a  mov     qword ptr [rsp+138h+var_F8], rcx
0x14011643f  mov     rax, rbx
0x140116442  inc     rax
0x140116445  cmp     [rcx+rax*2], di
0x140116449  jnz     short loc_140116442
0x14011644b  mov     qword ptr [rsp+138h+var_F8+8], rax
0x140116450  movups  xmm0, xmmword ptr [rsp+138h+var_D8]
0x140116455  movdqu  xmmword ptr [rsp+138h+var_D8], xmm0
0x14011645b  movaps  xmm1, [rsp+138h+var_B8]
0x140116463  movdqa  [rsp+138h+var_B8], xmm1
0x14011646c  movaps  xmm0, [rsp+138h+var_F8]
0x140116471  movdqa  [rsp+138h+var_F8], xmm0
0x140116477  lea     rax, [rsp+138h+var_108]
0x14011647c  mov     [rsp+138h+var_118], rax
0x140116481  lea     r9, [rsp+138h+var_D8]
0x140116486  lea     r8, [rsp+138h+var_B8]
0x14011648e  lea     rdx, [rsp+138h+var_F8]
0x140116493  mov     rcx, r11
0x140116496  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAAIV?$basic_zstring_view@_W@wil@@00AEBI@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint const &)
0x14011649b  mov     esi, eax
0x14011649d  mov     [rsp+138h+var_108], eax
0x1401164a1  mov     r14, qword ptr [rsp+138h+var_A8+8]
0x1401164a9  test    r14, r14
0x1401164ac  jz      short loc_1401164E4
0x1401164ae  mov     ecx, ebx
0x1401164b0  lock xadd [r14+8], ecx
0x1401164b6  add     ecx, ebx
0x1401164b8  jnz     short loc_1401164E4
0x1401164ba  mov     rax, [r14]
0x1401164bd  mov     rcx, r14
0x1401164c0  mov     rax, [rax]
0x1401164c3  call    _guard_dispatch_icall
0x1401164c8  mov     eax, ebx
0x1401164ca  lock xadd [r14+0Ch], eax
0x1401164d0  add     eax, ebx
0x1401164d2  jnz     short loc_1401164E4
0x1401164d4  mov     rax, [r14]
0x1401164d7  mov     rcx, r14
0x1401164da  mov     rax, [rax+8]
0x1401164de  call    _guard_dispatch_icall
0x1401164e3  nop
0x1401164e4  mov     r14, qword ptr [rsp+138h+var_E8+8]
0x1401164e9  test    r14, r14
0x1401164ec  jz      short loc_140116523
0x1401164ee  mov     eax, ebx
0x1401164f0  lock xadd [r14+8], eax
0x1401164f6  add     eax, ebx
0x1401164f8  jnz     short loc_140116523
0x1401164fa  mov     rax, [r14]
0x1401164fd  mov     rcx, r14
0x140116500  mov     rax, [rax]
0x140116503  call    _guard_dispatch_icall
0x140116508  mov     eax, ebx
0x14011650a  lock xadd [r14+0Ch], eax
0x140116510  add     eax, ebx
0x140116512  jnz     short loc_140116523
0x140116514  mov     rax, [r14]
0x140116517  mov     rcx, r14
0x14011651a  mov     rax, [rax+8]
0x14011651e  call    _guard_dispatch_icall
0x140116523  lea     rcx, [rsp+138h+var_B8]
0x14011652b  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140116530  nop
0x140116531  mov     rdx, [rax]
0x140116534  mov     rax, [rdx+8]
0x140116538  movsxd  rcx, dword ptr [rax+4]
0x14011653c  add     rdx, 8
0x140116540  add     rcx, rdx
0x140116543  mov     rax, [rcx]
0x140116546  lea     rdx, [rsp+138h+var_A8]
0x14011654e  mov     rax, [rax+28h]
0x140116552  call    _guard_dispatch_icall
0x140116557  nop
0x140116558  mov     r11, [rax]
0x14011655b  mov     rax, [r11]
0x14011655e  mov     r14, [rax+38h]
0x140116562  mov     eax, 2
0x140116567  mov     dword ptr [rsp+138h+var_D8], eax
0x14011656b  xor     r8d, r8d
0x14011656e  lea     r15, word_1404141A2
0x140116575  mov     rdx, r15
0x140116578  lea     rcx, aAllowedupdatem; "AllowedUpdateManagerCtorFailures"
0x14011657f  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140116584  cmp     rax, r15
0x140116587  jz      loc_140117099
0x14011658d  lea     rcx, aAllowedupdatem; "AllowedUpdateManagerCtorFailures"
0x140116594  sub     rax, rcx
0x140116597  sar     rax, 1
0x14011659a  cmp     rax, rbx
0x14011659d  jz      loc_140117099
0x1401165a3  mov     qword ptr [rsp+138h+var_F8], rcx
0x1401165a8  mov     qword ptr [rsp+138h+var_F8+8], rax
0x1401165ad  movaps  xmm0, [rsp+138h+var_F8]
0x1401165b2  movdqa  [rsp+138h+var_E8], xmm0
0x1401165b8  lea     r8, [rsp+138h+var_D8]
0x1401165bd  lea     rdx, [rsp+138h+var_E8]
0x1401165c2  mov     rcx, r11
0x1401165c5  mov     rax, r14
0x1401165c8  call    _guard_dispatch_icall
0x1401165cd  mov     r15d, eax
0x1401165d0  mov     eax, 2
0x1401165d5  cmp     r15d, eax
0x1401165d8  cmovb   r15d, eax
0x1401165dc  mov     r14, qword ptr [rsp+138h+var_A8+8]
0x1401165e4  test    r14, r14
0x1401165e7  jz      short loc_14011661F
0x1401165e9  mov     eax, ebx
0x1401165eb  lock xadd [r14+8], eax
0x1401165f1  add     eax, ebx
0x1401165f3  jnz     short loc_14011661F
0x1401165f5  mov     rax, [r14]
0x1401165f8  mov     rcx, r14
0x1401165fb  mov     rax, [rax]
0x1401165fe  call    _guard_dispatch_icall
0x140116603  mov     eax, ebx
0x140116605  lock xadd [r14+0Ch], eax
0x14011660b  add     eax, ebx
0x14011660d  jnz     short loc_14011661F
0x14011660f  mov     rax, [r14]
0x140116612  mov     rcx, r14
0x140116615  mov     rax, [rax+8]
0x140116619  call    _guard_dispatch_icall
0x14011661e  nop
0x14011661f  mov     r14, qword ptr [rsp+138h+var_B8+8]
0x140116627  test    r14, r14
0x14011662a  jz      short loc_140116661
0x14011662c  mov     eax, ebx
0x14011662e  lock xadd [r14+8], eax
0x140116634  add     eax, ebx
0x140116636  jnz     short loc_140116661
0x140116638  mov     rax, [r14]
0x14011663b  mov     rcx, r14
0x14011663e  mov     rax, [rax]
0x140116641  call    _guard_dispatch_icall
0x140116646  mov     eax, ebx
0x140116648  lock xadd [r14+0Ch], eax
0x14011664e  add     eax, ebx
0x140116650  jnz     short loc_140116661
0x140116652  mov     rax, [r14]
0x140116655  mov     rcx, r14
0x140116658  mov     rax, [rax+8]
0x14011665c  call    _guard_dispatch_icall
0x140116661  cmp     esi, r15d
0x140116664  jb      loc_140116DFC
0x14011666a  lea     rcx, [rsp+138h+var_A8]
0x140116672  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140116677  nop
0x140116678  mov     rcx, [rax]
0x14011667b  mov     rax, [rcx]
0x14011667e  lea     rdx, [rsp+138h+var_E8]
0x140116683  mov     rax, [rax+28h]
0x140116687  call    _guard_dispatch_icall
0x14011668c  nop
0x14011668d  mov     rcx, [rax]
0x140116690  mov     rax, [rcx]
0x140116693  mov     r8d, r15d
0x140116696  mov     edx, esi
0x140116698  mov     rax, [rax+140h]
0x14011669f  call    _guard_dispatch_icall
0x1401166a4  nop
0x1401166a5  mov     r14, qword ptr [rsp+138h+var_E8+8]
0x1401166aa  test    r14, r14
0x1401166ad  jz      short loc_1401166E5
0x1401166af  mov     eax, ebx
0x1401166b1  lock xadd [r14+8], eax
0x1401166b7  add     eax, ebx
0x1401166b9  jnz     short loc_1401166E5
0x1401166bb  mov     rax, [r14]
0x1401166be  mov     rcx, r14
0x1401166c1  mov     rax, [rax]
0x1401166c4  call    _guard_dispatch_icall
0x1401166c9  mov     eax, ebx
0x1401166cb  lock xadd [r14+0Ch], eax
0x1401166d1  add     eax, ebx
0x1401166d3  jnz     short loc_1401166E5
0x1401166d5  mov     rax, [r14]
0x1401166d8  mov     rcx, r14
0x1401166db  mov     rax, [rax+8]
0x1401166df  call    _guard_dispatch_icall
0x1401166e4  nop
0x1401166e5  mov     r14, qword ptr [rsp+138h+var_A8+8]
0x1401166ed  test    r14, r14
0x1401166f0  jz      short loc_140116727
0x1401166f2  mov     eax, ebx
0x1401166f4  lock xadd [r14+8], eax
0x1401166fa  add     eax, ebx
0x1401166fc  jnz     short loc_140116727
0x1401166fe  mov     rax, [r14]
0x140116701  mov     rcx, r14
0x140116704  mov     rax, [rax]
0x140116707  call    _guard_dispatch_icall
0x14011670c  mov     eax, ebx
0x14011670e  lock xadd [r14+0Ch], eax
0x140116714  add     eax, ebx
0x140116716  jnz     short loc_140116727
0x140116718  mov     rax, [r14]
0x14011671b  mov     rcx, r14
0x14011671e  mov     rax, [rax+8]
0x140116722  call    _guard_dispatch_icall
0x140116727  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_RecoverDatabaseOnWriteAccessFailure_31864050@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_RecoverDatabaseOnWriteAccessFailure_31864050@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_RecoverDatabaseOnWriteAccessFailure_31864050> `wil::Feature<__WilFeatureTraits_Feature_Containment_RecoverDatabaseOnWriteAccessFailure_31864050>::GetImpl(void)'::`2'::impl
0x14011672e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_RecoverDatabaseOnWriteAccessFailure_31864050@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_RecoverDatabaseOnWriteAccessFailure_31864050>::__private_IsEnabled(void)
0x140116733  test    al, al
0x140116735  jz      loc_140116C01
0x14011673b  lea     rcx, [rsp+138h+var_A8]
0x140116743  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140116748  nop
0x140116749  mov     rdx, [rax]
0x14011674c  mov     rax, [rdx+8]
0x140116750  movsxd  rcx, dword ptr [rax+4]
0x140116754  add     rdx, 8
0x140116758  add     rcx, rdx
0x14011675b  mov     rax, [rcx]
0x14011675e  lea     rdx, [rsp+138h+var_E8]
0x140116763  mov     rax, [rax+8]
0x140116767  call    _guard_dispatch_icall
0x14011676c  nop
0x14011676d  mov     rcx, [rax]
0x140116770  mov     rax, [rcx]
0x140116773  lea     rdx, [rsp+138h+lpExistingFileName]
0x14011677b  mov     rax, [rax+10h]
0x14011677f  call    _guard_dispatch_icall
0x140116784  nop
0x140116785  mov     r14, qword ptr [rsp+138h+var_E8+8]
0x14011678a  test    r14, r14
0x14011678d  jz      short loc_1401167C5
0x14011678f  mov     eax, ebx
0x140116791  lock xadd [r14+8], eax
0x140116797  add     eax, ebx
0x140116799  jnz     short loc_1401167C5
0x14011679b  mov     rax, [r14]
0x14011679e  mov     rcx, r14
0x1401167a1  mov     rax, [rax]
0x1401167a4  call    _guard_dispatch_icall
0x1401167a9  mov     eax, ebx
0x1401167ab  lock xadd [r14+0Ch], eax
0x1401167b1  add     eax, ebx
0x1401167b3  jnz     short loc_1401167C5
0x1401167b5  mov     rax, [r14]
0x1401167b8  mov     rcx, r14
0x1401167bb  mov     rax, [rax+8]
0x1401167bf  call    _guard_dispatch_icall
0x1401167c4  nop
0x1401167c5  mov     r14, qword ptr [rsp+138h+var_A8+8]
0x1401167cd  test    r14, r14
0x1401167d0  jz      short loc_140116807
0x1401167d2  mov     eax, ebx
0x1401167d4  lock xadd [r14+8], eax
0x1401167da  add     eax, ebx
0x1401167dc  jnz     short loc_140116807
0x1401167de  mov     rax, [r14]
0x1401167e1  mov     rcx, r14
0x1401167e4  mov     rax, [rax]
0x1401167e7  call    _guard_dispatch_icall
0x1401167ec  mov     eax, ebx
  ... truncated ...
```
