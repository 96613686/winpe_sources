# Windows::UsoDatabase::UsoDatabase(std::filesystem::path const &)

- ea: `0x1401901cc`
- end: `0x140190cac`
- name: `??0UsoDatabase@Windows@@QEAA@AEBVpath@filesystem@std@@@Z`
- size: `2784`
- prototype: `__int64 __fastcall(Windows::UsoDatabase *__hidden this, const struct std::filesystem::path *)`
- caller_count: `3`
- callee_count: `32`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401672e0`
- `0x14029a2d0`
- `0x14029a3b0`

## callees

- `0x14002cd5c`
- `0x140040184`
- `0x1400413a8`
- `0x140043354`
- `0x1400447ac`
- `0x14004519c`
- `0x140045404`
- `0x140057920`
- `0x140057a20`
- `0x140058e38`
- `0x14011916c`
- `0x1401192c4`
- `0x14012d7d8`
- `0x140150f10`
- `0x14016ccd0`
- `0x14018c578`
- `0x14018c5bc`
- `0x14018c648`
- `0x14018c7a8`
- `0x14018c854`
- `0x14018ca5c`
- `0x14018cc00`
- `0x14018d304`
- `0x14018d4b4`
- `0x14018ede0`
- `0x14018fb74`
- `0x1401901cc`
- `0x140190e60`
- `0x140379070`
- `0x1403790d8`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401904e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140190849`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401904e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140190849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401904ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401905a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140190837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140190910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401904ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401905a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140190837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140190910`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14019059d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140190906`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x14019059d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140190906`
- `winsqlite3!sqlite3_busy_timeout` at `0x14019068f`
- `winsqlite3!sqlite3_busy_timeout` at `0x140190a0f`
- `winsqlite3!sqlite3_busy_timeout` at `0x14019068f`
- `winsqlite3!sqlite3_busy_timeout` at `0x140190a0f`
- `winsqlite3!sqlite3_initialize` at `0x140190486`
- `winsqlite3!sqlite3_initialize` at `0x1401907ef`
- `winsqlite3!sqlite3_initialize` at `0x140190486`
- `winsqlite3!sqlite3_initialize` at `0x1401907ef`
- `winsqlite3!sqlite3_exec` at `0x140190656`
- `winsqlite3!sqlite3_exec` at `0x140190656`

## string_xrefs

- `0x140190b9a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140190bb4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140190c1e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140190c9a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140190bf7`: `rename`
- `0x140190c73`: `rename`
- `0x140190bdd`: `remove`
- `0x140190c59`: `remove`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
Windows::UsoDatabase *__fastcall Windows::UsoDatabase::UsoDatabase(
        Windows::UsoDatabase *this,
        const struct std::filesystem::path *a2)
{
  Windows::UsoDatabase *v3; // r15
  const WCHAR *v4; // rsi
  __int64 v5; // rax
  _QWORD *System; // rax
  __int64 (__fastcall *v7)(__int64, Windows::UsoDatabase **, __int128 *); // rbx
  int *traits_2_unsigned_short; // rax
  const char *v9; // r9
  __int64 v10; // r11
  __int64 v11; // rax
  _QWORD **v12; // rax
  _QWORD *v13; // rbx
  volatile signed __int32 *v14; // rdi
  volatile signed __int32 *v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD **v18; // rax
  volatile signed __int32 *v19; // rdi
  int v20; // eax
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  struct sqlite3 *v23; // rsi
  DWORD v24; // edi
  char *v25; // rcx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rax
  __int64 v28; // rdx
  const WCHAR *v29; // rdx
  const WCHAR *v30; // rcx
  __int64 v31; // rdx
  DWORD v32; // eax
  const char *v33; // r9
  __int16 *v34; // rax
  const char *v35; // r9
  __int64 v36; // r11
  __int64 v37; // rax
  int v38; // eax
  unsigned __int64 v39; // r9
  int v40; // eax
  unsigned __int64 v41; // r9
  bool v42; // zf
  void (__fastcall **v43)(_QWORD, _QWORD); // rax
  __int64 (__fastcall *v44)(_QWORD *, Windows::UsoDatabase **, unsigned __int64); // rdi
  unsigned __int64 v45; // rax
  __int64 *v46; // rax
  __int64 v47; // rdx
  void (__fastcall ***v48)(_QWORD, __int64); // rcx
  char v49; // cl
  __int64 v50; // rdx
  int v51; // eax
  unsigned __int64 v52; // r9
  __int64 v53; // rdx
  struct sqlite3 *v54; // r13
  DWORD LastError; // edi
  const WCHAR *v56; // rcx
  unsigned __int64 v57; // rax
  unsigned __int64 v58; // rax
  __int64 v59; // rdx
  const WCHAR *v60; // rdx
  const WCHAR *p_lpExistingFileName; // rcx
  __int64 v62; // rdx
  DWORD v63; // eax
  const char *v64; // r9
  __int16 *v65; // rax
  const char *v66; // r9
  __int64 v67; // r11
  __int64 v68; // rax
  char *traits_1_unsigned_char; // rax
  const char *v70; // r9
  __int64 v71; // r11
  char *v72; // rax
  int busy; // eax
  unsigned __int64 v74; // r9
  void (__fastcall **v75)(_QWORD *, __int64); // rax
  void (__fastcall *v76)(_QWORD *, __int64); // rdi
  unsigned __int64 DatabaseSizeInBytes; // rax
  __int64 *v78; // rax
  __int64 v79; // rdx
  void (__fastcall ***v80)(_QWORD, __int64); // rcx
  Windows::UsoDatabase *v81; // rsi
  volatile signed __int32 *v82; // rdi
  int v84; // [rsp+20h] [rbp-148h]
  char v85[8]; // [rsp+30h] [rbp-138h] BYREF
  Windows::UsoDatabase *v86; // [rsp+38h] [rbp-130h] BYREF
  __int128 v87; // [rsp+40h] [rbp-128h] BYREF
  __int128 v88; // [rsp+50h] [rbp-118h] BYREF
  _QWORD *v89; // [rsp+60h] [rbp-108h]
  Windows::UsoDatabase *v90; // [rsp+68h] [rbp-100h]
  _BYTE v91[32]; // [rsp+70h] [rbp-F8h] BYREF
  _BYTE v92[32]; // [rsp+90h] [rbp-D8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+B0h] [rbp-B8h] BYREF
  volatile signed __int32 *v94; // [rsp+B8h] [rbp-B0h]
  unsigned __int64 v95; // [rsp+C8h] [rbp-A0h]
  _QWORD v96[12]; // [rsp+D0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v3 = this;
  v90 = this;
  *(_QWORD *)this = &Windows::UsoDatabase::`vftable';
  v4 = (const WCHAR *)((char *)this + 8);
  std::wstring::wstring((char *)this + 8, a2);
  *((_QWORD *)v3 + 5) = 0;
  *((_DWORD *)v3 + 12) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  *((_QWORD *)v3 + 9) = 0;
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(80);
  *(_QWORD *)v5 = v5;
  *(_QWORD *)(v5 + 8) = v5;
  *(_QWORD *)(v5 + 16) = v5;
  *(_WORD *)(v5 + 24) = 257;
  *((_QWORD *)v3 + 8) = v5;
  *((_BYTE *)v3 + 80) = 0;
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 12) = 0;
  v89 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl'::`2'::impl) )
  {
    System = (_QWORD *)SystemInterface::Providers::GetSystem(&v88);
    v7 = *(__int64 (__fastcall **)(__int64, Windows::UsoDatabase **, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, LPCWSTR *))(*(_QWORD *)*System + 40LL))(
                                                                                                 *System,
                                                                                                 &lpExistingFileName)
                                                                                + 176LL);
    traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                       L"store",
                                       &dword_14041D13C,
                                       0);
    if ( traits_2_unsigned_short == &dword_14041D13C
      || (v11 = ((char *)traits_2_unsigned_short - (char *)L"store") >> 1, v11 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v9);
    }
    *(_QWORD *)&v87 = L"store";
    *((_QWORD *)&v87 + 1) = v11;
    v12 = (_QWORD **)v7(v10, &v86, &v87);
    v13 = *v12;
    *v12 = 0;
    v89 = v13;
    if ( v86 )
      (**(void (__fastcall ***)(Windows::UsoDatabase *, __int64))v86)(v86, 1);
    v14 = v94;
    if ( v94 )
    {
      if ( _InterlockedExchangeAdd(v94 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    v15 = (volatile signed __int32 *)*((_QWORD *)&v88 + 1);
  }
  else
  {
    v16 = (_QWORD *)SystemInterface::Providers::GetSystem(&lpExistingFileName);
    v17 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v16 + 40LL))(*v16, &v88);
    v18 = (_QWORD **)(*(__int64 (__fastcall **)(_QWORD, Windows::UsoDatabase **))(*(_QWORD *)*v17 + 184LL))(*v17, &v86);
    v13 = *v18;
    *v18 = 0;
    v89 = v13;
    if ( v86 )
      (**(void (__fastcall ***)(Windows::UsoDatabase *, __int64))v86)(v86, 1);
    v19 = (volatile signed __int32 *)*((_QWORD *)&v88 + 1);
    if ( *((_QWORD *)&v88 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v88 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    v15 = v94;
  }
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174>::GetImpl'::`2'::impl) )
  {
    memset(v96, 0, 0x58u);
    std::wstring::wstring(v91, a2);
    v86 = (Windows::UsoDatabase *)v91;
    LOBYTE(v96[0]) = 0;
    std::wstring::wstring(&v96[1], v91);
    memset(&v96[5], 0, 48);
    Windows::UsoDatabaseLockPerStore::InitStaticMembers((Windows::UsoDatabaseLockPerStore *)v96);
    std::wstring::~wstring(v91, v50);
    Windows::UsoDatabaseLockPerStore::lock((Windows::UsoDatabaseLockPerStore *)v96);
    v51 = sqlite3_initialize();
    v52 = (unsigned __int16)v51 | 0x87AF0000;
    if ( v51 <= 0 )
      v52 = (unsigned int)v51;
    if ( (v52 & 0x80000000) != 0LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)v52,
        v84);
    v86 = v3;
    if ( (int)Windows::UsoDatabase::TryOpenDatabase_::_2_::_lambda_1_::operator()(&v86) < 0 )
    {
      v54 = (struct sqlite3 *)*((_QWORD *)v3 + 5);
      if ( v54 )
      {
        LastError = GetLastError();
        Windows::SqliteDatabaseClose(v54);
        SetLastError(LastError);
      }
      *((_QWORD *)v3 + 5) = 0;
      v56 = v4;
      if ( *((_QWORD *)v4 + 3) > 7u )
        v56 = *(const WCHAR **)v4;
      v57 = _std_fs_remove(v56, v53);
      try
      {
        v58 = HIDWORD(v57);
        if ( (_DWORD)v58 )
          std::filesystem::_Throw_fs_error("remove", (unsigned int)v58, v4);
        std::wstring::wstring(&lpExistingFileName, v4);
        *(_QWORD *)&v87 = L".bak";
        *((_QWORD *)&v87 + 1) = 4;
        v88 = v87;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v92, &v88);
        std::filesystem::path::replace_extension(
          (std::filesystem::path *)&lpExistingFileName,
          (const struct std::filesystem::path *)v92);
        std::wstring::~wstring(v92, v59);
        v60 = v4;
        if ( *((_QWORD *)v4 + 3) > 7u )
          v60 = *(const WCHAR **)v4;
        p_lpExistingFileName = (const WCHAR *)&lpExistingFileName;
        if ( v95 > 7 )
          p_lpExistingFileName = lpExistingFileName;
        if ( !MoveFileExW(p_lpExistingFileName, v60, 3u) )
        {
          v63 = GetLastError();
          if ( v63 )
            std::filesystem::_Throw_fs_error("rename", v63, &lpExistingFileName, v4);
        }
        std::wstring::~wstring(&lpExistingFileName, v62);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x34D,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
          v64);
        v13 = v89;
        v3 = v90;
      }
      v86 = v3;
      if ( (int)Windows::UsoDatabase::TryOpenDatabase_::_2_::_lambda_1_::operator()(&v86) < 0 )
      {
        v65 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"Corruption",
                           &word_14041D12E,
                           0);
        if ( v65 == &word_14041D12E || (v68 = ((__int64)v65 - v67) >> 1, v68 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v66);
        *(_QWORD *)&v87 = v67;
        *((_QWORD *)&v87 + 1) = v68;
        v88 = v87;
        Windows::UsoDatabase::ResetDatabase(v3);
      }
    }
    traits_1_unsigned_char = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                                       "PRAGMA foreign_keys = on",
                                       byte_14041D0B1,
                                       0);
    if ( traits_1_unsigned_char == byte_14041D0B1 || (v72 = &traits_1_unsigned_char[-v71], v72 == (char *)-1LL) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v70);
    *(_QWORD *)&v87 = v71;
    *((_QWORD *)&v87 + 1) = v72;
    v88 = v87;
    Windows::SqlExec((char *)v3 + 40, &v88);
    Windows::UsoDatabase::PopulateTables(v3);
    busy = sqlite3_busy_timeout(*((_QWORD *)v3 + 5), 2000);
    v74 = (unsigned __int16)busy | 0x87AF0000;
    if ( busy <= 0 )
      v74 = (unsigned int)busy;
    if ( (v74 & 0x80000000) != 0LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35E,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)v74,
        v84);
    v42 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl'::`2'::impl) == 0;
    v75 = (void (__fastcall **)(_QWORD *, __int64))*v13;
    if ( v42 )
    {
      v78 = (__int64 *)((__int64 (__fastcall *)(_QWORD *, Windows::UsoDatabase **))v75[3])(v13, &v86);
    }
    else
    {
      v76 = v75[2];
      DatabaseSizeInBytes = Windows::UsoDatabase::GetDatabaseSizeInBytes(v3);
      v78 = (__int64 *)((__int64 (__fastcall *)(_QWORD *, Windows::UsoDatabase **, unsigned __int64))v76)(
                         v13,
                         &v86,
                         DatabaseSizeInBytes);
    }
    v79 = *v78;
    *v78 = 0;
    v80 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v3 + 7);
    *((_QWORD *)v3 + 7) = v79;
    if ( v80 )
      (**v80)(v80, 1);
    if ( v86 )
      (**(void (__fastcall ***)(Windows::UsoDatabase *, __int64))v86)(v86, 1);
    v81 = (Windows::UsoDatabase *)operator new(0x68u);
    v86 = v81;
    *(_OWORD *)v81 = 0;
    *((_DWORD *)v81 + 2) = 1;
    *((_DWORD *)v81 + 3) = 1;
    *(_QWORD *)v81 = &std::_Ref_count_obj2<Windows::UsoDatabaseLockPerStore>::`vftable';
    Windows::UsoDatabaseLockPerStore::UsoDatabaseLockPerStore((char *)v81 + 16, v96);
    *((_QWORD *)v3 + 11) = (char *)v81 + 16;
    v82 = (volatile signed __int32 *)*((_QWORD *)v3 + 12);
    *((_QWORD *)v3 + 12) = v81;
    if ( v82 )
    {
      if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
        if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
      }
    }
    Windows::UsoDatabaseLockPerStore::~UsoDatabaseLockPerStore((Windows::UsoDatabaseLockPerStore *)v96);
  }
  else
  {
    v85[0] = 0;
    Windows::UsoDatabaseLock::lock((Windows::UsoDatabaseLock *)v85);
    v20 = sqlite3_initialize();
    v21 = (unsigned __int16)v20 | 0x87AF0000;
    if ( v20 <= 0 )
      v21 = (unsigned int)v20;
    if ( (v21 & 0x80000000) != 0LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x370,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)v21,
        v84);
    v86 = v3;
    if ( (int)Windows::UsoDatabase::TryOpenDatabase_::_2_::_lambda_1_::operator()(&v86) < 0 )
    {
      v23 = (struct sqlite3 *)*((_QWORD *)v3 + 5);
      if ( v23 )
      {
        v24 = GetLastError();
        Windows::SqliteDatabaseClose(v23);
        SetLastError(v24);
      }
      *((_QWORD *)v3 + 5) = 0;
      v25 = (char *)v3 + 8;
      if ( *((_QWORD *)v3 + 4) > 7u )
        v25 = (char *)*((_QWORD *)v3 + 1);
      v26 = _std_fs_remove(v25, v22);
      try
      {
        v27 = HIDWORD(v26);
        if ( (_DWORD)v27 )
          std::filesystem::_Throw_fs_error("remove", (unsigned int)v27, (char *)v3 + 8);
        std::wstring::wstring(&lpExistingFileName, (char *)v3 + 8);
        *(_QWORD *)&v87 = L".bak";
        *((_QWORD *)&v87 + 1) = 4;
        v88 = v87;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v91, &v88);
        std::filesystem::path::replace_extension(
          (std::filesystem::path *)&lpExistingFileName,
          (const struct std::filesystem::path *)v91);
        std::wstring::~wstring(v91, v28);
        v29 = (const WCHAR *)((char *)v3 + 8);
        if ( *((_QWORD *)v3 + 4) > 7u )
          v29 = (const WCHAR *)*((_QWORD *)v3 + 1);
        v30 = (const WCHAR *)&lpExistingFileName;
        if ( v95 > 7 )
          v30 = lpExistingFileName;
        if ( !MoveFileExW(v30, v29, 3u) )
        {
          v32 = GetLastError();
          if ( v32 )
            std::filesystem::_Throw_fs_error("rename", v32, &lpExistingFileName, (char *)v3 + 8);
        }
        std::wstring::~wstring(&lpExistingFileName, v31);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x381,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
          v33);
        v13 = v89;
        v3 = v90;
      }
      v86 = v3;
      if ( (int)Windows::UsoDatabase::TryOpenDatabase_::_2_::_lambda_1_::operator()(&v86) < 0 )
      {
        v34 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"Corruption",
                           &word_14041D12E,
                           0);
        if ( v34 == &word_14041D12E || (v37 = ((__int64)v34 - v36) >> 1, v37 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v35);
        *(_QWORD *)&v87 = v36;
        *((_QWORD *)&v87 + 1) = v37;
        v88 = v87;
        Windows::UsoDatabase::ResetDatabase(v3);
      }
    }
    v38 = sqlite3_exec(*((_QWORD *)v3 + 5), "PRAGMA foreign_keys = on", 0, 0);
    v39 = (unsigned __int16)v38 | 0x87AF0000;
    if ( v38 <= 0 )
      v39 = (unsigned int)v38;
    if ( (v39 & 0x80000000) != 0LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x38D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)v39,
        0);
    Windows::UsoDatabase::PopulateTables(v3);
    v40 = sqlite3_busy_timeout(*((_QWORD *)v3 + 5), 2000);
    v41 = (unsigned __int16)v40 | 0x87AF0000;
    if ( v40 <= 0 )
      v41 = (unsigned int)v40;
    if ( (v41 & 0x80000000) != 0LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x393,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)v41,
        0);
    v42 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl'::`2'::impl) == 0;
    v43 = (void (__fastcall **)(_QWORD, _QWORD))*v13;
    if ( v42 )
    {
      v46 = (__int64 *)((__int64 (__fastcall *)(_QWORD *, Windows::UsoDatabase **))v43[3])(v13, &v86);
    }
    else
    {
      v44 = (__int64 (__fastcall *)(_QWORD *, Windows::UsoDatabase **, unsigned __int64))v43[2];
      v45 = Windows::UsoDatabase::GetDatabaseSizeInBytes(v3);
      v46 = (__int64 *)v44(v13, &v86, v45);
    }
    v47 = *v46;
    *v46 = 0;
    v48 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v3 + 7);
    *((_QWORD *)v3 + 7) = v47;
    if ( v48 )
      (**v48)(v48, 1);
    if ( v86 )
      (**(void (__fastcall ***)(Windows::UsoDatabase *, __int64))v86)(v86, 1);
    v49 = *((_BYTE *)v3 + 80);
    *((_BYTE *)v3 + 80) = v85[0];
    v85[0] = v49;
    Windows::UsoDatabaseLock::~UsoDatabaseLock((Windows::UsoDatabaseLock *)v85);
  }
  if ( v13 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v13)(v13, 1);
  return v3;
}

```

## disassembly

```asm
0x1401901cc  mov     [rsp+arg_10], rbx
0x1401901d1  mov     [rsp+arg_18], rsi
0x1401901d6  push    rdi
0x1401901d7  push    r12
0x1401901d9  push    r13
0x1401901db  push    r14
0x1401901dd  push    r15
0x1401901df  sub     rsp, 140h
0x1401901e6  mov     rax, cs:__security_cookie
0x1401901ed  xor     rax, rsp
0x1401901f0  mov     [rsp+168h+var_38], rax
0x1401901f8  mov     r13, rdx
0x1401901fb  mov     r15, rcx
0x1401901fe  mov     [rsp+168h+var_100], rcx
0x140190203  xor     r14d, r14d
0x140190206  lea     rax, ??_7UsoDatabase@Windows@@6B@; const Windows::UsoDatabase::`vftable'
0x14019020d  mov     [rcx], rax
0x140190210  lea     rsi, [rcx+8]
0x140190214  mov     rcx, rsi
0x140190217  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14019021c  nop
0x14019021d  mov     [r15+28h], r14
0x140190221  mov     [r15+30h], r14d
0x140190225  mov     [r15+38h], r14
0x140190229  mov     [r15+40h], r14
0x14019022d  mov     [r15+48h], r14
0x140190231  lea     ecx, [r14+50h]
0x140190235  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14019023a  mov     [rax], rax
0x14019023d  mov     [rax+8], rax
0x140190241  mov     [rax+10h], rax
0x140190245  lea     r12d, [r14+1]
0x140190249  mov     word ptr [rax+18h], 101h
0x14019024f  mov     [r15+40h], rax
0x140190253  mov     [r15+50h], r14b
0x140190257  mov     [r15+58h], r14
0x14019025b  mov     [r15+60h], r14
0x14019025f  mov     [rsp+168h+var_108], r14
0x140190264  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::GetImpl(void)'::`2'::impl
0x14019026b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Tailored_Download_And_Install_46151993>::__private_IsEnabled(void)
0x140190270  test    al, al
0x140190272  jz      loc_14019037E
0x140190278  lea     rcx, [rsp+168h+var_118]
0x14019027d  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140190282  nop
0x140190283  mov     rcx, [rax]
0x140190286  mov     rax, [rcx]
0x140190289  lea     rdx, [rsp+168h+lpExistingFileName]
0x140190291  mov     rax, [rax+28h]
0x140190295  call    _guard_dispatch_icall
0x14019029a  nop
0x14019029b  mov     r11, [rax]
0x14019029e  mov     rax, [r11]
0x1401902a1  mov     rbx, [rax+0B0h]
0x1401902a8  xor     r8d, r8d
0x1401902ab  lea     rdi, dword_14041D13C
0x1401902b2  mov     rdx, rdi
0x1401902b5  lea     rcx, aStore; "store"
0x1401902bc  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1401902c1  cmp     rax, rdi
0x1401902c4  jz      loc_140190BAC
0x1401902ca  lea     rcx, aStore; "store"
0x1401902d1  sub     rax, rcx
0x1401902d4  sar     rax, 1
0x1401902d7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1401902db  jz      loc_140190BAC
0x1401902e1  mov     qword ptr [rsp+168h+var_128], rcx
0x1401902e6  mov     qword ptr [rsp+168h+var_128+8], rax
0x1401902eb  movaps  xmm0, [rsp+168h+var_128]
0x1401902f0  movdqa  [rsp+168h+var_128], xmm0
0x1401902f6  lea     r8, [rsp+168h+var_128]
0x1401902fb  lea     rdx, [rsp+168h+var_130]
0x140190300  mov     rcx, r11
0x140190303  mov     rax, rbx
0x140190306  call    _guard_dispatch_icall
0x14019030b  mov     rbx, [rax]
0x14019030e  mov     [rax], r14
0x140190311  mov     [rsp+168h+var_108], rbx
0x140190316  mov     rcx, [rsp+168h+var_130]
0x14019031b  test    rcx, rcx
0x14019031e  jz      short loc_14019032F
0x140190320  mov     rax, [rcx]
0x140190323  mov     edx, r12d
0x140190326  mov     rax, [rax]
0x140190329  call    _guard_dispatch_icall
0x14019032e  nop
0x14019032f  mov     rdi, [rsp+168h+var_B0]
0x140190337  test    rdi, rdi
0x14019033a  jz      short loc_140190374
0x14019033c  or      eax, 0FFFFFFFFh
0x14019033f  lock xadd [rdi+8], eax
0x140190344  cmp     eax, 1
0x140190347  jnz     short loc_140190374
0x140190349  mov     rax, [rdi]
0x14019034c  mov     rcx, rdi
0x14019034f  mov     rax, [rax]
0x140190352  call    _guard_dispatch_icall
0x140190357  or      eax, 0FFFFFFFFh
0x14019035a  lock xadd [rdi+0Ch], eax
0x14019035f  cmp     eax, 1
0x140190362  jnz     short loc_140190374
0x140190364  mov     rax, [rdi]
0x140190367  mov     rcx, rdi
0x14019036a  mov     rax, [rax+8]
0x14019036e  call    _guard_dispatch_icall
0x140190373  nop
0x140190374  mov     rdi, qword ptr [rsp+168h+var_118+8]
0x140190379  jmp     loc_140190426
0x14019037e  lea     rcx, [rsp+168h+lpExistingFileName]
0x140190386  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14019038b  nop
0x14019038c  mov     rcx, [rax]
0x14019038f  mov     rax, [rcx]
0x140190392  lea     rdx, [rsp+168h+var_118]
0x140190397  mov     rax, [rax+28h]
0x14019039b  call    _guard_dispatch_icall
0x1401903a0  nop
0x1401903a1  mov     rcx, [rax]
0x1401903a4  mov     rax, [rcx]
0x1401903a7  lea     rdx, [rsp+168h+var_130]
0x1401903ac  mov     rax, [rax+0B8h]
0x1401903b3  call    _guard_dispatch_icall
0x1401903b8  mov     rbx, [rax]
0x1401903bb  mov     [rax], r14
0x1401903be  mov     [rsp+168h+var_108], rbx
0x1401903c3  mov     rcx, [rsp+168h+var_130]
0x1401903c8  test    rcx, rcx
0x1401903cb  jz      short loc_1401903DC
0x1401903cd  mov     rax, [rcx]
0x1401903d0  mov     edx, r12d
0x1401903d3  mov     rax, [rax]
0x1401903d6  call    _guard_dispatch_icall
0x1401903db  nop
0x1401903dc  mov     rdi, qword ptr [rsp+168h+var_118+8]
0x1401903e1  test    rdi, rdi
0x1401903e4  jz      short loc_14019041E
0x1401903e6  or      eax, 0FFFFFFFFh
0x1401903e9  lock xadd [rdi+8], eax
0x1401903ee  cmp     eax, 1
0x1401903f1  jnz     short loc_14019041E
0x1401903f3  mov     rax, [rdi]
0x1401903f6  mov     rcx, rdi
0x1401903f9  mov     rax, [rax]
0x1401903fc  call    _guard_dispatch_icall
0x140190401  or      eax, 0FFFFFFFFh
0x140190404  lock xadd [rdi+0Ch], eax
0x140190409  cmp     eax, 1
0x14019040c  jnz     short loc_14019041E
0x14019040e  mov     rax, [rdi]
0x140190411  mov     rcx, rdi
0x140190414  mov     rax, [rax+8]
0x140190418  call    _guard_dispatch_icall
0x14019041d  nop
0x14019041e  mov     rdi, [rsp+168h+var_B0]
0x140190426  test    rdi, rdi
0x140190429  jz      short loc_140190462
0x14019042b  or      eax, 0FFFFFFFFh
0x14019042e  lock xadd [rdi+8], eax
0x140190433  cmp     eax, 1
0x140190436  jnz     short loc_140190462
0x140190438  mov     rax, [rdi]
0x14019043b  mov     rcx, rdi
0x14019043e  mov     rax, [rax]
0x140190441  call    _guard_dispatch_icall
0x140190446  or      eax, 0FFFFFFFFh
0x140190449  lock xadd [rdi+0Ch], eax
0x14019044e  cmp     eax, 1
0x140190451  jnz     short loc_140190462
0x140190453  mov     rax, [rdi]
0x140190456  mov     rcx, rdi
0x140190459  mov     rax, [rax+8]
0x14019045d  call    _guard_dispatch_icall
0x140190462  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174>::GetImpl(void)'::`2'::impl
0x140190469  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174>::__private_IsEnabled(void)
0x14019046e  test    al, al
0x140190470  jnz     loc_140190754
0x140190476  mov     [rsp+168h+var_138], r14b
0x14019047b  lea     rcx, [rsp+168h+var_138]; this
0x140190480  call    ?lock@UsoDatabaseLock@Windows@@QEAAXXZ; Windows::UsoDatabaseLock::lock(void)
0x140190485  nop
0x140190486  call    cs:__imp_sqlite3_initialize
0x14019048c  movzx   r9d, ax
0x140190490  or      r9d, 87AF0000h
0x140190497  test    eax, eax
0x140190499  cmovle  r9d, eax; char *
0x14019049d  mov     rcx, [rsp+168h]; this
0x1401904a5  test    r9d, r9d
0x1401904a8  js      loc_140190BC6
0x1401904ae  mov     [rsp+168h+var_130], r15
0x1401904b3  lea     rcx, [rsp+168h+var_130]
0x1401904b8  call    _Windows__UsoDatabase__TryOpenDatabase____2____lambda_1___operator__
0x1401904bd  test    eax, eax
0x1401904bf  jns     loc_140190640
0x1401904c5  mov     rsi, [r15+28h]
0x1401904c9  test    rsi, rsi
0x1401904cc  jz      short loc_1401904E7
0x1401904ce  call    cs:__imp_GetLastError
0x1401904d4  mov     edi, eax
0x1401904d6  mov     rcx, rsi; struct sqlite3 *
0x1401904d9  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x1401904de  mov     ecx, edi; dwErrCode
0x1401904e0  call    cs:__imp_SetLastError
0x1401904e6  nop
0x1401904e7  mov     [r15+28h], r14
0x1401904eb  lea     rdi, [r15+8]
0x1401904ef  mov     rcx, rdi
0x1401904f2  cmp     qword ptr [rdi+18h], 7
0x1401904f7  jbe     short loc_1401904FC
0x1401904f9  mov     rcx, [rdi]
0x1401904fc  call    __std_fs_remove
0x140190501  shr     rax, 20h
0x140190505  test    eax, eax
0x140190507  jnz     loc_140190BD8
0x14019050d  lea     rdx, [r15+8]
0x140190511  lea     rcx, [rsp+168h+lpExistingFileName]
0x140190519  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14019051e  nop
0x14019051f  lea     rax, aBak; ".bak"
0x140190526  mov     qword ptr [rsp+168h+var_128], rax
0x14019052b  mov     qword ptr [rsp+168h+var_128+8], 4
0x140190534  movaps  xmm0, [rsp+168h+var_128]
0x140190539  movdqa  [rsp+168h+var_118], xmm0
0x14019053f  lea     rdx, [rsp+168h+var_118]
0x140190544  lea     rcx, [rsp+168h+var_F8]
0x140190549  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14019054e  nop
0x14019054f  lea     rdx, [rsp+168h+var_F8]; struct std::filesystem::path *
0x140190554  lea     rcx, [rsp+168h+lpExistingFileName]; this
0x14019055c  call    ?replace_extension@path@filesystem@std@@QEAAAEAV123@AEBV123@@Z; std::filesystem::path::replace_extension(std::filesystem::path const &)
0x140190561  nop
0x140190562  lea     rcx, [rsp+168h+var_F8]
0x140190567  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14019056c  lea     rsi, [r15+8]
0x140190570  mov     rdx, rsi
0x140190573  cmp     qword ptr [rdi+18h], 7
0x140190578  jbe     short loc_14019057D
0x14019057a  mov     rdx, [rsi]; lpNewFileName
0x14019057d  lea     rcx, [rsp+168h+lpExistingFileName]
0x140190585  cmp     [rsp+168h+var_A0], 7
0x14019058e  cmova   rcx, [rsp+168h+lpExistingFileName]; lpExistingFileName
0x140190597  mov     r8d, 3; dwFlags
0x14019059d  call    cs:__imp_MoveFileExW
0x1401905a3  test    eax, eax
0x1401905a5  jnz     short loc_1401905B5
0x1401905a7  call    cs:__imp_GetLastError
0x1401905ad  test    eax, eax
0x1401905af  jnz     loc_140190BEA
0x1401905b5  lea     rcx, [rsp+168h+lpExistingFileName]
0x1401905bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1401905c2  nop
0x1401905c3  jmp     short loc_1401905D6
0x1401905c5  xor     r14d, r14d
0x1401905c8  lea     r12d, [r14+1]
0x1401905cc  mov     rbx, [rsp+168h+var_108]
0x1401905d1  mov     r15, [rsp+168h+var_100]
0x1401905d6  mov     [rsp+168h+var_130], r15
0x1401905db  lea     rcx, [rsp+168h+var_130]
0x1401905e0  call    _Windows__UsoDatabase__TryOpenDatabase____2____lambda_1___operator__
0x1401905e5  test    eax, eax
0x1401905e7  jns     short loc_140190640
0x1401905e9  xor     r8d, r8d
0x1401905ec  lea     rdi, word_14041D12E
0x1401905f3  mov     rdx, rdi
0x1401905f6  lea     r11, aCorruption; "Corruption"
0x1401905fd  mov     rcx, r11
0x140190600  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140190605  cmp     rax, rdi
0x140190608  jz      loc_140190C16
0x14019060e  sub     rax, r11
0x140190611  sar     rax, 1
0x140190614  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140190618  jz      loc_140190C16
0x14019061e  mov     qword ptr [rsp+168h+var_128], r11
0x140190623  mov     qword ptr [rsp+168h+var_128+8], rax
0x140190628  movaps  xmm0, [rsp+168h+var_128]
0x14019062d  movdqa  [rsp+168h+var_118], xmm0
0x140190633  lea     rdx, [rsp+168h+var_118]
0x140190638  mov     rcx, r15; this
0x14019063b  call    ?ResetDatabase@UsoDatabase@Windows@@AEAAXV?$basic_zstring_view@_W@wil@@@Z; Windows::UsoDatabase::ResetDatabase(wil::basic_zstring_view<wchar_t>)
0x140190640  mov     qword ptr [rsp+168h+var_148], r14; int
0x140190645  xor     r9d, r9d
0x140190648  xor     r8d, r8d
0x14019064b  lea     rdx, aPragmaForeignK; "PRAGMA foreign_keys = on"
0x140190652  mov     rcx, [r15+28h]
0x140190656  call    cs:__imp_sqlite3_exec
0x14019065c  movzx   r9d, ax
0x140190660  or      r9d, 87AF0000h
0x140190667  test    eax, eax
0x140190669  cmovle  r9d, eax; char *
0x14019066d  mov     rcx, [rsp+168h]; this
0x140190675  test    r9d, r9d
0x140190678  js      loc_140190C04
0x14019067e  mov     rcx, r15; this
0x140190681  call    ?PopulateTables@UsoDatabase@Windows@@AEAAXXZ; Windows::UsoDatabase::PopulateTables(void)
0x140190686  mov     edx, 7D0h
0x14019068b  mov     rcx, [r15+28h]
0x14019068f  call    cs:__imp_sqlite3_busy_timeout
0x140190695  movzx   r9d, ax
0x140190699  or      r9d, 87AF0000h
0x1401906a0  test    eax, eax
  ... truncated ...
```
