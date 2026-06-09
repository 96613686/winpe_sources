# _Windows::UsoDatabase::BackupDatabase_::_2_::_lambda_1_::operator()

- ea: `0x14018db34`
- end: `0x14018e34f`
- name: `_Windows::UsoDatabase::BackupDatabase_::_2_::_lambda_1_::operator()`
- size: `2075`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14018d918`

## callees

- `0x1400407f8`
- `0x1400413a8`
- `0x140041b3c`
- `0x14004296c`
- `0x140043354`
- `0x1400447ac`
- `0x140045404`
- `0x1401192c4`
- `0x14016ccd0`
- `0x14018c188`
- `0x14018c578`
- `0x14018c5bc`
- `0x14018c854`
- `0x14018cc00`
- `0x14018db34`
- `0x140190144`
- `0x14019e4f4`
- `0x14019f1e0`
- `0x14019f7e0`
- `0x14019f8b0`
- `0x1401a1944`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x140379070`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14018dd75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14018e196`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14018dd75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14018e196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018dd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018e184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018dd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018e184`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14018dbd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14018dfe8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14018dbd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14018dfe8`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x14018dbe1`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x14018dffa`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x14018dbe1`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x14018dffa`
- `winsqlite3!sqlite3_shutdown` at `0x14018dd81`
- `winsqlite3!sqlite3_shutdown` at `0x14018e1a2`
- `winsqlite3!sqlite3_shutdown` at `0x14018dd81`
- `winsqlite3!sqlite3_shutdown` at `0x14018e1a2`
- `winsqlite3!sqlite3_initialize` at `0x14018dc44`
- `winsqlite3!sqlite3_initialize` at `0x14018e063`
- `winsqlite3!sqlite3_initialize` at `0x14018dc44`
- `winsqlite3!sqlite3_initialize` at `0x14018e063`
- `winsqlite3!sqlite3_open16` at `0x14018dc97`
- `winsqlite3!sqlite3_open16` at `0x14018e0b8`
- `winsqlite3!sqlite3_open16` at `0x14018dc97`
- `winsqlite3!sqlite3_open16` at `0x14018e0b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall Windows::UsoDatabase::BackupDatabase_::_2_::_lambda_1_::operator()(std::filesystem **a1)
{
  unsigned int v2; // esi
  char v3; // bl
  int v4; // eax
  struct std::error_code *v5; // r8
  std::filesystem *v6; // rbx
  bool v7; // al
  const struct std::filesystem::path *v8; // r9
  int v9; // eax
  signed int v10; // ebx
  std::filesystem *v11; // rcx
  int v12; // eax
  struct sqlite3 *v13; // rcx
  int v14; // eax
  struct sqlite3 *v15; // rbx
  DWORD v16; // edi
  int v17; // eax
  const char *v18; // r9
  __int64 v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rax
  struct std::error_code *v24; // r8
  std::filesystem *v25; // rbx
  bool v26; // al
  const struct std::filesystem::path *v27; // r9
  int v28; // eax
  signed int v29; // ebx
  std::filesystem *v30; // rcx
  int v31; // eax
  struct sqlite3 *v32; // rcx
  int v33; // eax
  struct sqlite3 *v34; // rbx
  DWORD LastError; // edi
  int v36; // eax
  const char *v37; // r9
  int v38[4]; // [rsp+20h] [rbp-118h] BYREF
  char v39[16]; // [rsp+30h] [rbp-108h] BYREF
  _BYTE v40[32]; // [rsp+40h] [rbp-F8h] BYREF
  struct sqlite3 *v41; // [rsp+60h] [rbp-D8h] BYREF
  _BYTE v42[40]; // [rsp+68h] [rbp-D0h] BYREF
  _QWORD v43[12]; // [rsp+90h] [rbp-A8h] BYREF
  _BYTE v44[32]; // [rsp+F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174>::GetImpl'::`2'::impl) )
  {
    memset(v43, 0, 0x58u);
    std::wstring::wstring(v40, *a1);
    *(_QWORD *)v39 = v40;
    LOBYTE(v43[0]) = 0;
    std::wstring::wstring(&v43[1], v40);
    memset(&v43[5], 0, 48);
    Windows::UsoDatabaseLockPerStore::InitStaticMembers((Windows::UsoDatabaseLockPerStore *)v43);
    std::wstring::~wstring(v40);
    if ( LOBYTE(v43[0]) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.h",
        (const char *)0x8007139FLL,
        v38[0]);
    v20 = v43[5];
    *(_QWORD *)v39 = v43[5];
    *(_QWORD *)&v39[8] = 0;
    if ( (unsigned int)mtx_do_lock(v43[5], 0) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v20 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v20 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v39[8] = 1;
    v22 = std::_Uhash_compare<std::filesystem::path,std::hash<std::filesystem::path>,std::equal_to<std::filesystem::path>>::operator()<std::filesystem::path>(
            v21,
            &v43[1]);
    if ( !*(_QWORD *)(std::_Hash<std::_Uset_traits<std::filesystem::path,std::_Uhash_compare<std::filesystem::path,std::hash<std::filesystem::path>,std::equal_to<std::filesystem::path>>,std::allocator<std::filesystem::path>,0>>::_Find_last<std::filesystem::path>(
                        v43[9],
                        v44,
                        &v43[1],
                        v22)
                    + 8) )
    {
      std::_Hash<std::_Uset_traits<std::filesystem::path,std::_Uhash_compare<std::filesystem::path,std::hash<std::filesystem::path>,std::equal_to<std::filesystem::path>>,std::allocator<std::filesystem::path>,0>>::insert(
        v43[9],
        v44,
        &v43[1]);
      LOBYTE(v43[0]) = 1;
    }
    if ( (*(_DWORD *)(v20 + 76))-- == 1 )
    {
      *(_DWORD *)(v20 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v20 + 16));
    }
    WakeConditionVariable((PCONDITION_VARIABLE)(v43[7] + 8LL));
    if ( !LOBYTE(v43[0]) )
    {
      v2 = -2147024726;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x188,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)0x800700AALL,
        v38[0]);
LABEL_93:
      Windows::UsoDatabaseLockPerStore::~UsoDatabaseLockPerStore((Windows::UsoDatabaseLockPerStore *)v43);
      return v2;
    }
    v25 = *a1;
    *(_QWORD *)v39 = 0;
    *(_QWORD *)&v39[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    v26 = std::filesystem::exists(v25, (const struct std::filesystem::path *)v39, v24);
    if ( *(_DWORD *)v39 )
      std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v39, v25, v27);
    if ( !v26 )
      goto LABEL_93;
    v28 = sqlite3_initialize();
    v29 = (unsigned __int16)v28 | 0x87AF0000;
    if ( v28 <= 0 )
      v29 = v28;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x190,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)(unsigned int)v29,
        v38[0]);
LABEL_62:
      v2 = v29;
      goto LABEL_93;
    }
    v41 = 0;
    v30 = *a1;
    if ( *((_QWORD *)*a1 + 3) > 7u )
      v30 = *(std::filesystem **)v30;
    v31 = sqlite3_open16(v30, &v41);
    v29 = (unsigned __int16)v31 | 0x87AF0000;
    if ( v31 <= 0 )
      v29 = v31;
    if ( v29 >= 0 )
    {
      if ( Windows::UsoDatabase::IsDatabaseCorrupt(v41) )
      {
        if ( v41 )
          Windows::SqliteDatabaseClose(v41);
        v2 = -2018574325;
        goto LABEL_93;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742>::GetImpl'::`2'::impl)
        && (v33 = Windows::UsoDatabase::CleanupRebootDeferralHistory(&v41), v29 = v33, v33 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19B,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
          (const char *)(unsigned int)v33,
          v38[0]);
        v32 = v41;
        if ( !v41 )
          goto LABEL_62;
      }
      else
      {
        v34 = v41;
        if ( v41 )
        {
          LastError = GetLastError();
          Windows::SqliteDatabaseClose(v34);
          SetLastError(LastError);
        }
        v41 = 0;
        v36 = sqlite3_shutdown();
        v29 = (unsigned __int16)v36 | 0x87AF0000;
        if ( v36 <= 0 )
          v29 = v36;
        if ( v29 >= 0 )
        {
          std::wstring::wstring(v42, *a1);
          *(_QWORD *)v39 = L".bak";
          *(_QWORD *)&v39[8] = 4;
          std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v40, v39);
          std::filesystem::path::replace_extension(
            (std::filesystem::path *)v42,
            (const struct std::filesystem::path *)v40);
          std::wstring::~wstring(v40);
          try
          {
            std::filesystem::copy(*a1, v42, 2);
            std::wstring::~wstring(v42);
          }
          catch ( ... )
          {
            *(_DWORD *)v39 = wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x1AB,
                               (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
                               v37);
            std::wstring::~wstring(v42);
            if ( v41 )
              Windows::SqliteDatabaseClose(v41);
            v2 = *(_DWORD *)v39;
            goto LABEL_93;
          }
          if ( v41 )
            Windows::SqliteDatabaseClose(v41);
          Windows::UsoDatabaseLockPerStore::~UsoDatabaseLockPerStore((Windows::UsoDatabaseLockPerStore *)v43);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A2,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
          (const char *)(unsigned int)v29,
          v38[0]);
        v32 = v41;
        if ( !v41 )
          goto LABEL_62;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)(unsigned int)v29,
        v38[0]);
      v32 = v41;
      if ( !v41 )
        goto LABEL_62;
    }
    Windows::SqliteDatabaseClose(v32);
    goto LABEL_62;
  }
  v3 = 0;
  LOBYTE(v38[0]) = 0;
  if ( (unsigned int)mtx_do_lock(&Windows::UsoDatabaseLock::s_dbMutex, 0) )
    std::_Throw_Cpp_error(5);
  v4 = dword_1405075FC;
  if ( dword_1405075FC == 0x7FFFFFFF )
  {
    dword_1405075FC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( !Windows::UsoDatabaseLock::s_dbLocked )
  {
    v3 = 1;
    Windows::UsoDatabaseLock::s_dbLocked = 1;
    LOBYTE(v38[0]) = 1;
  }
  --dword_1405075FC;
  if ( v4 == 1 )
  {
    dword_1405075F8 = -1;
    ReleaseSRWLockExclusive(&stru_1405075C0);
  }
  WakeConditionVariable(&stru_1405498B8);
  if ( !v3 )
  {
    v2 = -2147024726;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
      (const char *)0x800700AALL,
      v38[0]);
LABEL_39:
    Windows::UsoDatabaseLock::~UsoDatabaseLock((Windows::UsoDatabaseLock *)v38);
    return v2;
  }
  v6 = *a1;
  *(_QWORD *)v39 = 0;
  *(_QWORD *)&v39[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v7 = std::filesystem::exists(v6, (const struct std::filesystem::path *)v39, v5);
  if ( *(_DWORD *)v39 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v39, v6, v8);
  if ( !v7 )
    goto LABEL_39;
  v9 = sqlite3_initialize();
  v10 = (unsigned __int16)v9 | 0x87AF0000;
  if ( v9 <= 0 )
    v10 = v9;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
      (const char *)(unsigned int)v10,
      v38[0]);
LABEL_38:
    v2 = v10;
    goto LABEL_39;
  }
  v41 = 0;
  v11 = *a1;
  if ( *((_QWORD *)*a1 + 3) > 7u )
    v11 = *(std::filesystem **)v11;
  v12 = sqlite3_open16(v11, &v41);
  v10 = (unsigned __int16)v12 | 0x87AF0000;
  if ( v12 <= 0 )
    v10 = v12;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
      (const char *)(unsigned int)v10,
      v38[0]);
    v13 = v41;
    if ( !v41 )
      goto LABEL_38;
LABEL_37:
    Windows::SqliteDatabaseClose(v13);
    goto LABEL_38;
  }
  if ( Windows::UsoDatabase::IsDatabaseCorrupt(v41) )
  {
    if ( v41 )
      Windows::SqliteDatabaseClose(v41);
    v2 = -2018574325;
    goto LABEL_39;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742>::GetImpl'::`2'::impl) )
  {
    v14 = Windows::UsoDatabase::CleanupRebootDeferralHistory(&v41);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
        (const char *)(unsigned int)v14,
        v38[0]);
      v13 = v41;
      if ( !v41 )
        goto LABEL_38;
      goto LABEL_37;
    }
  }
  v15 = v41;
  if ( v41 )
  {
    v16 = GetLastError();
    Windows::SqliteDatabaseClose(v15);
    SetLastError(v16);
  }
  v41 = 0;
  v17 = sqlite3_shutdown();
  v10 = (unsigned __int16)v17 | 0x87AF0000;
  if ( v17 <= 0 )
    v10 = v17;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
      (const char *)(unsigned int)v10,
      v38[0]);
    v13 = v41;
    if ( !v41 )
      goto LABEL_38;
    goto LABEL_37;
  }
  std::wstring::wstring(v44, *a1);
  *(_QWORD *)v39 = L".bak";
  *(_QWORD *)&v39[8] = 4;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v42, v39);
  std::filesystem::path::replace_extension((std::filesystem::path *)v44, (const struct std::filesystem::path *)v42);
  std::wstring::~wstring(v42);
  try
  {
    std::filesystem::copy(*a1, v44, 2);
    std::wstring::~wstring(v44);
  }
  catch ( ... )
  {
    *(_DWORD *)v39 = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x1D3,
                       (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\database\\Database.cpp",
                       v18);
    std::wstring::~wstring(v44);
    if ( v41 )
      Windows::SqliteDatabaseClose(v41);
    Windows::UsoDatabaseLock::~UsoDatabaseLock((Windows::UsoDatabaseLock *)v38);
    return *(unsigned int *)v39;
  }
  if ( v41 )
    Windows::SqliteDatabaseClose(v41);
  Windows::UsoDatabaseLock::~UsoDatabaseLock((Windows::UsoDatabaseLock *)v38);
  return 0;
}

```

## disassembly

```asm
0x14018db34  mov     [rsp+arg_8], rbx
0x14018db39  mov     [rsp+arg_10], rsi
0x14018db3e  push    rdi
0x14018db3f  push    r14
0x14018db41  push    r15
0x14018db43  sub     rsp, 120h
0x14018db4a  mov     rax, cs:__security_cookie
0x14018db51  xor     rax, rsp
0x14018db54  mov     [rsp+138h+var_28], rax
0x14018db5c  mov     r14, rcx
0x14018db5f  xor     esi, esi
0x14018db61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174>::GetImpl(void)'::`2'::impl
0x14018db68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_WinREHistory_55819174>::__private_IsEnabled(void)
0x14018db6d  test    al, al
0x14018db6f  jnz     loc_14018DE9D
0x14018db75  mov     bl, sil
0x14018db78  mov     byte ptr [rsp+138h+var_118], bl
0x14018db7c  xor     edx, edx
0x14018db7e  lea     rcx, ?s_dbMutex@UsoDatabaseLock@Windows@@0Vmutex@std@@A; std::mutex Windows::UsoDatabaseLock::s_dbMutex
0x14018db85  call    mtx_do_lock
0x14018db8a  test    eax, eax
0x14018db8c  jnz     loc_14018E2D2
0x14018db92  mov     eax, cs:dword_1405075FC
0x14018db98  cmp     eax, 7FFFFFFFh
0x14018db9d  jz      loc_14018E2DB
0x14018dba3  cmp     cs:?s_dbLocked@UsoDatabaseLock@Windows@@0_NA, sil; bool Windows::UsoDatabaseLock::s_dbLocked
0x14018dbaa  jnz     short loc_14018DBB8
0x14018dbac  mov     bl, 1
0x14018dbae  mov     cs:?s_dbLocked@UsoDatabaseLock@Windows@@0_NA, bl; bool Windows::UsoDatabaseLock::s_dbLocked
0x14018dbb4  mov     byte ptr [rsp+138h+var_118], bl; int
0x14018dbb8  sub     eax, 1
0x14018dbbb  mov     cs:dword_1405075FC, eax
0x14018dbc1  jnz     short loc_14018DBDA
0x14018dbc3  mov     cs:dword_1405075F8, 0FFFFFFFFh
0x14018dbcd  lea     rcx, stru_1405075C0; SRWLock
0x14018dbd4  call    cs:__imp_ReleaseSRWLockExclusive
0x14018dbda  lea     rcx, stru_1405498B8; ConditionVariable
0x14018dbe1  call    cs:__imp_WakeConditionVariable
0x14018dbe7  test    bl, bl
0x14018dbe9  jnz     short loc_14018DC11
0x14018dbeb  mov     rcx, [rsp+138h]; this
0x14018dbf3  mov     esi, 800700AAh
0x14018dbf8  mov     r9d, esi; char *
0x14018dbfb  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018dc02  mov     edx, 1B0h; void *
0x14018dc07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14018dc0c  jmp     loc_14018DDC5
0x14018dc11  mov     rbx, [r14]
0x14018dc14  mov     qword ptr [rsp+138h+var_108], rsi
0x14018dc19  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x14018dc20  mov     qword ptr [rsp+138h+var_108+8], rax
0x14018dc25  lea     rdx, [rsp+138h+var_108]; struct std::filesystem::path *
0x14018dc2a  mov     rcx, rbx; this
0x14018dc2d  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x14018dc32  cmp     dword ptr [rsp+138h+var_108], esi
0x14018dc36  jnz     loc_14018E2F0
0x14018dc3c  test    al, al
0x14018dc3e  jz      loc_14018DDC5
0x14018dc44  call    cs:__imp_sqlite3_initialize
0x14018dc4a  movzx   ebx, ax
0x14018dc4d  mov     r15d, 87AF0000h
0x14018dc53  or      ebx, r15d
0x14018dc56  test    eax, eax
0x14018dc58  cmovle  ebx, eax
0x14018dc5b  test    ebx, ebx
0x14018dc5d  jns     short loc_14018DC80
0x14018dc5f  mov     rcx, [rsp+138h]; this
0x14018dc67  mov     r9d, ebx; char *
0x14018dc6a  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018dc71  mov     edx, 1B8h; void *
0x14018dc76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14018dc7b  jmp     loc_14018DDC3
0x14018dc80  mov     [rsp+138h+var_D8], rsi
0x14018dc85  mov     rcx, [r14]
0x14018dc88  cmp     qword ptr [rcx+18h], 7
0x14018dc8d  jbe     short loc_14018DC92
0x14018dc8f  mov     rcx, [rcx]
0x14018dc92  lea     rdx, [rsp+138h+var_D8]
0x14018dc97  call    cs:__imp_sqlite3_open16
0x14018dc9d  movzx   ebx, ax
0x14018dca0  or      ebx, r15d
0x14018dca3  test    eax, eax
0x14018dca5  cmovle  ebx, eax
0x14018dca8  test    ebx, ebx
0x14018dcaa  jns     short loc_14018DCE2
0x14018dcac  mov     rcx, [rsp+138h]; this
0x14018dcb4  mov     r9d, ebx; char *
0x14018dcb7  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018dcbe  mov     edx, 1BCh; void *
0x14018dcc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14018dcc8  nop
0x14018dcc9  mov     rcx, [rsp+138h+var_D8]; struct sqlite3 *
0x14018dcce  test    rcx, rcx
0x14018dcd1  jz      loc_14018DDC3
0x14018dcd7  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x14018dcdc  nop
0x14018dcdd  jmp     loc_14018DDC3
0x14018dce2  mov     rcx, [rsp+138h+var_D8]; struct sqlite3 *
0x14018dce7  call    ?IsDatabaseCorrupt@UsoDatabase@Windows@@CA_NPEAUsqlite3@@@Z; Windows::UsoDatabase::IsDatabaseCorrupt(sqlite3 *)
0x14018dcec  test    al, al
0x14018dcee  jz      short loc_14018DD0A
0x14018dcf0  mov     rcx, [rsp+138h+var_D8]; struct sqlite3 *
0x14018dcf5  test    rcx, rcx
0x14018dcf8  jz      short loc_14018DD00
0x14018dcfa  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x14018dcff  nop
0x14018dd00  mov     esi, 87AF000Bh
0x14018dd05  jmp     loc_14018DDC5
0x14018dd0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742>::GetImpl(void)'::`2'::impl
0x14018dd11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_TailoredReboot_59302742>::__private_IsEnabled(void)
0x14018dd16  test    al, al
0x14018dd18  jz      short loc_14018DD59
0x14018dd1a  lea     rcx, [rsp+138h+var_D8]
0x14018dd1f  call    ?CleanupRebootDeferralHistory@UsoDatabase@Windows@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?SqliteDatabaseClose@Windows@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::UsoDatabase::CleanupRebootDeferralHistory(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&Windows::SqliteDatabaseClose(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &)
0x14018dd24  mov     ebx, eax
0x14018dd26  test    eax, eax
0x14018dd28  jns     short loc_14018DD59
0x14018dd2a  mov     rcx, [rsp+138h]; this
0x14018dd32  mov     r9d, eax; char *
0x14018dd35  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018dd3c  mov     edx, 1C3h; void *
0x14018dd41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14018dd46  nop
0x14018dd47  mov     rcx, [rsp+138h+var_D8]; struct sqlite3 *
0x14018dd4c  test    rcx, rcx
0x14018dd4f  jz      short loc_14018DDC3
0x14018dd51  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x14018dd56  nop
0x14018dd57  jmp     short loc_14018DDC3
0x14018dd59  mov     rbx, [rsp+138h+var_D8]
0x14018dd5e  test    rbx, rbx
0x14018dd61  jz      short loc_14018DD7C
0x14018dd63  call    cs:__imp_GetLastError
0x14018dd69  mov     edi, eax
0x14018dd6b  mov     rcx, rbx; struct sqlite3 *
0x14018dd6e  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x14018dd73  mov     ecx, edi; dwErrCode
0x14018dd75  call    cs:__imp_SetLastError
0x14018dd7b  nop
0x14018dd7c  mov     [rsp+138h+var_D8], rsi
0x14018dd81  call    cs:__imp_sqlite3_shutdown
0x14018dd87  movzx   ebx, ax
0x14018dd8a  or      ebx, r15d
0x14018dd8d  test    eax, eax
0x14018dd8f  cmovle  ebx, eax
0x14018dd92  test    ebx, ebx
0x14018dd94  jns     short loc_14018DDD4
0x14018dd96  mov     rcx, [rsp+138h]; this
0x14018dd9e  mov     r9d, ebx; char *
0x14018dda1  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018dda8  mov     edx, 1CAh; void *
0x14018ddad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14018ddb2  nop
0x14018ddb3  mov     rcx, [rsp+138h+var_D8]; struct sqlite3 *
0x14018ddb8  test    rcx, rcx
0x14018ddbb  jz      short loc_14018DDC3
0x14018ddbd  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x14018ddc2  nop
0x14018ddc3  mov     esi, ebx
0x14018ddc5  lea     rcx, [rsp+138h+var_118]; this
0x14018ddca  call    ??1UsoDatabaseLock@Windows@@QEAA@XZ; Windows::UsoDatabaseLock::~UsoDatabaseLock(void)
0x14018ddcf  jmp     loc_14018E2A7
0x14018ddd4  mov     rdx, [r14]
0x14018ddd7  lea     rcx, [rsp+138h+var_48]
0x14018dddf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14018dde4  nop
0x14018dde5  lea     rax, aBak; ".bak"
0x14018ddec  mov     qword ptr [rsp+138h+var_108], rax
0x14018ddf1  mov     qword ptr [rsp+138h+var_108+8], 4
0x14018ddfa  lea     rdx, [rsp+138h+var_108]
0x14018ddff  lea     rcx, [rsp+138h+var_D0]
0x14018de04  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14018de09  nop
0x14018de0a  lea     rdx, [rsp+138h+var_D0]; struct std::filesystem::path *
0x14018de0f  lea     rcx, [rsp+138h+var_48]; this
0x14018de17  call    ?replace_extension@path@filesystem@std@@QEAAAEAV123@AEBV123@@Z; std::filesystem::path::replace_extension(std::filesystem::path const &)
0x14018de1c  nop
0x14018de1d  lea     rcx, [rsp+138h+var_D0]
0x14018de22  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14018de27  nop
0x14018de28  mov     r8d, 2
0x14018de2e  lea     rdx, [rsp+138h+var_48]
0x14018de36  mov     rcx, [r14]
0x14018de39  call    ?copy@filesystem@std@@YAXAEBVpath@12@0W4copy_options@12@@Z; std::filesystem::copy(std::filesystem::path const &,std::filesystem::path const &,std::filesystem::copy_options)
0x14018de3e  nop
0x14018de3f  lea     rcx, [rsp+138h+var_48]
0x14018de47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14018de4c  nop
0x14018de4d  mov     rcx, [rsp+138h+var_D8]; struct sqlite3 *
0x14018de52  test    rcx, rcx
0x14018de55  jz      short loc_14018DE5D
0x14018de57  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x14018de5c  nop
0x14018de5d  lea     rcx, [rsp+138h+var_118]; this
0x14018de62  call    ??1UsoDatabaseLock@Windows@@QEAA@XZ; Windows::UsoDatabaseLock::~UsoDatabaseLock(void)
0x14018de67  jmp     loc_14018E277
0x14018de6c  lea     rcx, [rsp+138h+var_48]
0x14018de74  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14018de79  nop
0x14018de7a  mov     rcx, [rsp+138h+var_D8]; struct sqlite3 *
0x14018de7f  test    rcx, rcx
0x14018de82  jz      short loc_14018DE8A
0x14018de84  call    ?SqliteDatabaseClose@Windows@@YAXPEAUsqlite3@@@Z; Windows::SqliteDatabaseClose(sqlite3 *)
0x14018de89  nop
0x14018de8a  lea     rcx, [rsp+138h+var_118]; this
0x14018de8f  call    ??1UsoDatabaseLock@Windows@@QEAA@XZ; Windows::UsoDatabaseLock::~UsoDatabaseLock(void)
0x14018de94  mov     eax, dword ptr [rsp+138h+var_108]
0x14018de98  jmp     loc_14018E2A9
0x14018de9d  xor     edx, edx; Val
0x14018de9f  lea     r8d, [rdx+58h]; Size
0x14018dea3  lea     rcx, [rsp+138h+var_A8]; void *
0x14018deab  call    memset
0x14018deb0  mov     rdx, [r14]
0x14018deb3  lea     rcx, [rsp+138h+var_F8]
0x14018deb8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14018debd  lea     rax, [rsp+138h+var_F8]
0x14018dec2  mov     qword ptr [rsp+138h+var_108], rax
0x14018dec7  mov     [rsp+138h+var_A8], sil
0x14018decf  lea     rdx, [rsp+138h+var_F8]
0x14018ded4  lea     rcx, [rsp+138h+var_A0]
0x14018dedc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14018dee1  nop
0x14018dee2  mov     [rsp+138h+var_80], rsi
0x14018deea  mov     [rsp+138h+var_78], rsi
0x14018def2  mov     [rsp+138h+var_70], rsi
0x14018defa  mov     [rsp+138h+var_68], rsi
0x14018df02  mov     [rsp+138h+var_60], rsi
0x14018df0a  mov     [rsp+138h+var_58], rsi
0x14018df12  lea     rcx, [rsp+138h+var_A8]; this
0x14018df1a  call    ?InitStaticMembers@UsoDatabaseLockPerStore@Windows@@AEAAXXZ; Windows::UsoDatabaseLockPerStore::InitStaticMembers(void)
0x14018df1f  nop
0x14018df20  lea     rcx, [rsp+138h+var_F8]
0x14018df25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14018df2a  nop
0x14018df2b  mov     rcx, [rsp+138h]; this
0x14018df33  cmp     [rsp+138h+var_A8], sil
0x14018df3b  jnz     loc_14018E305
0x14018df41  xorps   xmm0, xmm0
0x14018df44  movups  xmmword ptr [rsp+138h+var_108], xmm0
0x14018df49  mov     rdi, [rsp+138h+var_80]
0x14018df51  mov     qword ptr [rsp+138h+var_108], rdi
0x14018df56  mov     [rsp+138h+var_108+8], sil
0x14018df5b  xor     edx, edx
0x14018df5d  mov     rcx, rdi
0x14018df60  call    mtx_do_lock
0x14018df65  test    eax, eax
0x14018df67  jnz     loc_14018E31D
0x14018df6d  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x14018df74  jz      loc_14018E328
0x14018df7a  mov     bl, 1
0x14018df7c  mov     [rsp+138h+var_108+8], bl
0x14018df80  lea     rdx, [rsp+138h+var_A0]
0x14018df88  call    ??$?RVpath@filesystem@std@@@?$_Uhash_compare@Vpath@filesystem@std@@U?$hash@Vpath@filesystem@std@@@3@U?$equal_to@Vpath@filesystem@std@@@3@@std@@QEBA_KAEBVpath@filesystem@1@@Z; std::_Uhash_compare<std::filesystem::path,std::hash<std::filesystem::path>,std::equal_to<std::filesystem::path>>::operator()<std::filesystem::path>(std::filesystem::path const &)
0x14018df8d  mov     r9, rax
0x14018df90  lea     r8, [rsp+138h+var_A0]
0x14018df98  lea     rdx, [rsp+138h+var_48]
0x14018dfa0  mov     rcx, [rsp+138h+var_60]
0x14018dfa8  call    ??$_Find_last@Vpath@filesystem@std@@@?$_Hash@V?$_Uset_traits@Vpath@filesystem@std@@V?$_Uhash_compare@Vpath@filesystem@std@@U?$hash@Vpath@filesystem@std@@@3@U?$equal_to@Vpath@filesystem@std@@@3@@3@V?$allocator@Vpath@filesystem@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@Vpath@filesystem@std@@PEAX@std@@@1@AEBVpath@filesystem@1@_K@Z; std::_Hash<std::_Uset_traits<std::filesystem::path,std::_Uhash_compare<std::filesystem::path,std::hash<std::filesystem::path>,std::equal_to<std::filesystem::path>>,std::allocator<std::filesystem::path>,0>>::_Find_last<std::filesystem::path>(std::filesystem::path const &,unsigned __int64)
0x14018dfad  cmp     [rax+8], rsi
0x14018dfb1  jnz     short loc_14018DFD7
0x14018dfb3  lea     r8, [rsp+138h+var_A0]
0x14018dfbb  lea     rdx, [rsp+138h+var_48]
0x14018dfc3  mov     rcx, [rsp+138h+var_60]
0x14018dfcb  call    ?insert@?$_Hash@V?$_Uset_traits@Vpath@filesystem@std@@V?$_Uhash_compare@Vpath@filesystem@std@@U?$hash@Vpath@filesystem@std@@@3@U?$equal_to@Vpath@filesystem@std@@@3@@3@V?$allocator@Vpath@filesystem@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@Vpath@filesystem@std@@@std@@@std@@@std@@_N@2@AEBVpath@filesystem@2@@Z; std::_Hash<std::_Uset_traits<std::filesystem::path,std::_Uhash_compare<std::filesystem::path,std::hash<std::filesystem::path>,std::equal_to<std::filesystem::path>>,std::allocator<std::filesystem::path>,0>>::insert(std::filesystem::path const &)
0x14018dfd0  mov     [rsp+138h+var_A8], bl
0x14018dfd7  sub     dword ptr [rdi+4Ch], 1
0x14018dfdb  jnz     short loc_14018DFEE
0x14018dfdd  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x14018dfe4  lea     rcx, [rdi+10h]; SRWLock
0x14018dfe8  call    cs:__imp_ReleaseSRWLockExclusive
0x14018dfee  mov     rcx, [rsp+138h+var_70]
0x14018dff6  add     rcx, 8; ConditionVariable
0x14018dffa  call    cs:__imp_WakeConditionVariable
0x14018e000  cmp     [rsp+138h+var_A8], sil
0x14018e008  jnz     short loc_14018E030
0x14018e00a  mov     rcx, [rsp+138h]; this
0x14018e012  mov     esi, 800700AAh
0x14018e017  mov     r9d, esi; char *
0x14018e01a  lea     r8, aCW1SSrcOrchest_31; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14018e021  mov     edx, 188h; void *
0x14018e026  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14018e02b  jmp     loc_14018E29A
0x14018e030  mov     rbx, [r14]
0x14018e033  mov     qword ptr [rsp+138h+var_108], rsi
0x14018e038  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x14018e03f  mov     qword ptr [rsp+138h+var_108+8], rax
0x14018e044  lea     rdx, [rsp+138h+var_108]; struct std::filesystem::path *
0x14018e049  mov     rcx, rbx; this
0x14018e04c  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x14018e051  cmp     dword ptr [rsp+138h+var_108], esi
0x14018e055  jnz     loc_14018E33A
0x14018e05b  test    al, al
0x14018e05d  jz      loc_14018E29A
0x14018e063  call    cs:__imp_sqlite3_initialize
0x14018e069  movzx   ebx, ax
0x14018e06c  mov     r15d, 87AF0000h
0x14018e072  or      ebx, r15d
0x14018e075  test    eax, eax
0x14018e077  cmovle  ebx, eax
0x14018e07a  test    ebx, ebx
  ... truncated ...
```
