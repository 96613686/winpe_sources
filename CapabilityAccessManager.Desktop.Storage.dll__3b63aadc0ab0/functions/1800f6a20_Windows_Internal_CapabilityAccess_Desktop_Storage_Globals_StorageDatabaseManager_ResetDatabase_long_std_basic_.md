# Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::ResetDatabase(long,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800f6a20`
- end: `0x1800f6f13`
- name: `?ResetDatabase@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1267`
- prototype: `void __fastcall(int, struct sqlite3_stmt *)`
- caller_count: `2`
- callee_count: `30`
- tags: `registry_config`

## callers

- `0x1800ed9b8`
- `0x1800edc00`

## callees

- `0x180003060`
- `0x1800043c0`
- `0x1800e67f8`
- `0x1800eabf4`
- `0x1800ec618`
- `0x1800ed544`
- `0x1800ed70c`
- `0x1800ed7a4`
- `0x1800edb4c`
- `0x1800ee24c`
- `0x1800f44fc`
- `0x1800f5f4c`
- `0x1800f62a0`
- `0x1800f62d8`
- `0x1800f6448`
- `0x1800f6584`
- `0x1800f694c`
- `0x1800f6a20`
- `0x1800f7630`
- `0x1800f8e98`
- `0x1800f9300`
- `0x1800fae48`
- `0x1800fb768`
- `0x1800fbc58`
- `0x1800ff438`
- `0x1800ffb60`
- `0x1800ffd20`
- `0x180100108`
- `0x180106ddc`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800f6bb8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800f6bb8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6a63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f6a63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6b8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6df8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6b8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f6df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6abb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800f6aa2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800f6aa2`

## string_xrefs

- `0x1800f6bed`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f6c19`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f6c43`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::ResetDatabase(
        int a1,
        struct sqlite3_stmt *a2)
{
  struct sqlite3_stmt *v2; // rdi
  unsigned __int64 RuntimeTargetSchemaVersion; // r15
  __int64 v5; // rdx
  __int64 v6; // r8
  const char *v7; // r9
  void **StorageDatabaseDirectory; // rax
  BOOL DirectoryW; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  const char *v12; // r9
  void **StorageDatabaseFullPath; // rax
  StateRepository::Database *v14; // rbx
  struct sqlite3 **v15; // rsi
  int v16; // eax
  int (*v17)(void *); // r8
  void *v18; // r9
  int v19; // eax
  volatile signed __int32 *v20; // rbx
  unsigned int v21; // r8d
  const char *v22; // r9
  int v23; // esi
  int v24; // eax
  int v25; // eax
  int v26; // r8d
  signed int v27; // eax
  int (*v28)(void *); // r8
  void *v29; // r9
  int v30; // eax
  signed int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  __int64 v35; // r8
  const char *v36; // r9
  const unsigned __int16 *v37; // rax
  int v38; // ecx
  volatile signed __int32 *v39; // rbx
  unsigned __int16 *v40; // [rsp+20h] [rbp-188h]
  int v41; // [rsp+20h] [rbp-188h]
  struct sqlite3_stmt *v42[2]; // [rsp+38h] [rbp-170h] BYREF
  StateRepository::Database *v43; // [rsp+48h] [rbp-160h] BYREF
  volatile signed __int32 *v44; // [rsp+50h] [rbp-158h]
  RTL_SRWLOCK *v45; // [rsp+58h] [rbp-150h]
  _BYTE v46[8]; // [rsp+60h] [rbp-148h] BYREF
  _BYTE v47[168]; // [rsp+68h] [rbp-140h] BYREF
  _BYTE v48[48]; // [rsp+110h] [rbp-98h] BYREF
  void *Src[4]; // [rsp+140h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v2 = a2;
  v42[1] = a2;
  wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v46);
  AcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseLock);
  v45 = &Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseLock;
  std::make_shared<StateRepository::Database,>(&v43);
  RuntimeTargetSchemaVersion = (int)Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetRuntimeTargetSchemaVersion();
  StorageDatabaseDirectory = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(
                               Src,
                               v5,
                               v6,
                               v7);
  if ( (unsigned __int64)StorageDatabaseDirectory[3] > 7 )
    StorageDatabaseDirectory = (void **)*StorageDatabaseDirectory;
  DirectoryW = CreateDirectoryW((LPCWSTR)StorageDatabaseDirectory, 0);
  std::wstring::~wstring(Src);
  if ( !DirectoryW && GetLastError() != 183 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
      v12);
  StorageDatabaseFullPath = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseFullPath(
                              Src,
                              v10,
                              v11,
                              v12);
  v14 = v43;
  v15 = (struct sqlite3 **)v43;
  if ( (unsigned __int64)StorageDatabaseFullPath[3] > 7 )
    StorageDatabaseFullPath = (void **)*StorageDatabaseFullPath;
  v16 = StateRepository::Database::Open(v43, StorageDatabaseFullPath);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
      (const char *)(unsigned int)v16,
      (int)v40);
  std::wstring::~wstring(Src);
  StateRepository::Database::SetCheckpointOnClose(v14, 0);
  if ( a1 == -2018573557 )
  {
    v19 = StateRepository::Database::Execute(v14, "REINDEX;", v17, v18);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v19,
        (int)v40);
    v20 = v44;
    if ( v44 && _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
    ReleaseSRWLockExclusive(&Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseLock);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v48);
    wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)v47);
  }
  else
  {
    if ( !ResetEvent(Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseReady) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v21, v22);
    v42[0] = 0;
    if ( *v15 )
    {
      v24 = StateRepository::Statement::Reset((StateRepository::Statement *)v42);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x665,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)(unsigned int)v24,
          (int)v40);
      v25 = StateRepository::Statement::Finalize((StateRepository::Statement *)v42);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x127,
          (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
          (const char *)(unsigned int)v25,
          (int)v40);
      v23 = StateRepository::Database::dal_prepare_v2(*v15, "VACUUM;", v26, v42, (const char **)v40);
    }
    else
    {
      v23 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x663,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)0x8007139FLL,
        (int)v40);
    }
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v23,
        v41);
    StateRepository::Statement::Reset((StateRepository::Statement *)v42);
    v27 = sqlite3_db_config(*(_QWORD *)v14, 1009, 1);
    if ( v27 > 0 )
      v27 = (unsigned __int16)v27 | 0x87AF0000;
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v27,
        v41);
    v30 = StateRepository::Database::Execute(v14, "VACUUM;", v28, v29);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v30,
        v41);
    v31 = sqlite3_db_config(*(_QWORD *)v14, 1009, 0);
    if ( v31 > 0 )
      v31 = (unsigned __int16)v31 | 0x87AF0000;
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v31,
        v41);
    v32 = StateRepository::Database::ClearCache(v14);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v32,
        v41);
    v33 = StateRepository::Database::Reset(v14);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v33,
        v41);
    v34 = StateRepository::DatabaseCacheSingleton::Clear();
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
        (const char *)(unsigned int)v34,
        v41);
    Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::PrepareProcessForDatabaseUse(
      0,
      7,
      v35,
      v36);
    StateRepository::Statement::~Statement((StateRepository::Statement *)v42);
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v37 = (const unsigned __int16 *)v2;
    else
      v37 = *(const unsigned __int16 **)v2;
    Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::ResetDatabase(
      0,
      RuntimeTargetSchemaVersion,
      0,
      byte_180122168,
      v37);
    if ( (byte_180140201 & 1) != 0 )
    {
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(struct sqlite3_stmt **)v2;
      McTemplateU0dzd_EventWriteTransfer(
        v38,
        (unsigned int)SettingsDatabaseRecoverySuccessEvent,
        RuntimeTargetSchemaVersion,
        (_DWORD)v2,
        0);
    }
    v39 = v44;
    if ( v44 )
    {
      if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
        if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
      }
    }
    ReleaseSRWLockExclusive(&Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseLock);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v48);
    wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)v47);
  }
}

```

## disassembly

```asm
0x1800f6a20  push    rbx
0x1800f6a22  push    rsi
0x1800f6a23  push    rdi
0x1800f6a24  push    r13
0x1800f6a26  push    r14
0x1800f6a28  push    r15
0x1800f6a2a  sub     rsp, 178h
0x1800f6a31  mov     rax, cs:__security_cookie
0x1800f6a38  xor     rax, rsp
0x1800f6a3b  mov     [rsp+1A8h+var_48], rax
0x1800f6a43  mov     rdi, rdx
0x1800f6a46  mov     r14d, ecx
0x1800f6a49  mov     [rsp+1A8h+var_168], rdx
0x1800f6a4e  lea     rcx, [rsp+1A8h+var_148]; this
0x1800f6a53  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x1800f6a58  nop
0x1800f6a59  lea     r13, ?m_databaseLock@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::m_databaseLock
0x1800f6a60  mov     rcx, r13; SRWLock
0x1800f6a63  call    cs:__imp_AcquireSRWLockExclusive
0x1800f6a69  mov     [rsp+1A8h+var_150], r13
0x1800f6a6e  lea     rcx, [rsp+1A8h+var_160]
0x1800f6a73  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x1800f6a78  nop
0x1800f6a79  call    ?GetRuntimeTargetSchemaVersion@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SAHXZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetRuntimeTargetSchemaVersion(void)
0x1800f6a7e  movsxd  r15, eax
0x1800f6a81  mov     [rsp+1A8h+var_178], r15d
0x1800f6a86  lea     rcx, [rsp+1A8h+Src]; Src
0x1800f6a8e  call    ?GetStorageDatabaseDirectory@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(void)
0x1800f6a93  cmp     qword ptr [rax+18h], 7
0x1800f6a98  jbe     short loc_1800F6A9D
0x1800f6a9a  mov     rax, [rax]
0x1800f6a9d  xor     edx, edx; lpSecurityAttributes
0x1800f6a9f  mov     rcx, rax; lpPathName
0x1800f6aa2  call    cs:__imp_CreateDirectoryW
0x1800f6aa8  mov     ebx, eax
0x1800f6aaa  lea     rcx, [rsp+1A8h+Src]
0x1800f6ab2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f6ab7  test    ebx, ebx
0x1800f6ab9  jnz     short loc_1800F6ACC
0x1800f6abb  call    cs:__imp_GetLastError
0x1800f6ac1  cmp     eax, 0B7h
0x1800f6ac6  jnz     loc_1800F6E37
0x1800f6acc  lea     rcx, [rsp+1A8h+Src]; Src
0x1800f6ad4  call    ?GetStorageDatabaseFullPath@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseFullPath(void)
0x1800f6ad9  nop
0x1800f6ada  mov     rbx, [rsp+1A8h+var_160]
0x1800f6adf  mov     rcx, rbx
0x1800f6ae2  mov     rsi, rbx
0x1800f6ae5  cmp     qword ptr [rax+18h], 7
0x1800f6aea  jbe     short loc_1800F6AEF
0x1800f6aec  mov     rax, [rax]
0x1800f6aef  mov     rdx, rax
0x1800f6af2  call    ?Open@Database@StateRepository@@QEAAJPEB_WW4OpenFlags@12@PEBI@Z; StateRepository::Database::Open(wchar_t const *,StateRepository::Database::OpenFlags,uint const *)
0x1800f6af7  mov     rcx, [rsp+1A8h]; this
0x1800f6aff  test    eax, eax
0x1800f6b01  js      loc_1800F6E51
0x1800f6b07  lea     rcx, [rsp+1A8h+Src]
0x1800f6b0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f6b14  xor     edx, edx; bool
0x1800f6b16  mov     rcx, rbx; this
0x1800f6b19  call    ?SetCheckpointOnClose@Database@StateRepository@@QEAAJ_N@Z; StateRepository::Database::SetCheckpointOnClose(bool)
0x1800f6b1e  cmp     r14d, 87AF030Bh
0x1800f6b25  jnz     loc_1800F6BB1
0x1800f6b2b  lea     rdx, aReindex; "REINDEX;"
0x1800f6b32  mov     rcx, rbx; this
0x1800f6b35  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800f6b3a  mov     rcx, [rsp+1A8h]; this
0x1800f6b42  test    eax, eax
0x1800f6b44  js      loc_1800F6E66
0x1800f6b4a  mov     rbx, [rsp+1A8h+var_158]
0x1800f6b4f  test    rbx, rbx
0x1800f6b52  jz      short loc_1800F6B8B
0x1800f6b54  or      edi, 0FFFFFFFFh
0x1800f6b57  mov     eax, edi
0x1800f6b59  lock xadd [rbx+8], eax
0x1800f6b5e  add     eax, edi
0x1800f6b60  jnz     short loc_1800F6B8B
0x1800f6b62  mov     rax, [rbx]
0x1800f6b65  mov     rcx, rbx
0x1800f6b68  mov     rax, [rax]
0x1800f6b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6b70  mov     eax, edi
0x1800f6b72  lock xadd [rbx+0Ch], eax
0x1800f6b77  add     eax, edi
0x1800f6b79  jnz     short loc_1800F6B8B
0x1800f6b7b  mov     rax, [rbx]
0x1800f6b7e  mov     rcx, rbx
0x1800f6b81  mov     rax, [rax+8]
0x1800f6b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6b8a  nop
0x1800f6b8b  mov     rcx, r13; SRWLock
0x1800f6b8e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f6b94  nop
0x1800f6b95  lea     rcx, [rsp+1A8h+var_98]; this
0x1800f6b9d  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800f6ba2  lea     rcx, [rsp+1A8h+var_140]; this
0x1800f6ba7  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x1800f6bac  jmp     loc_1800F6E16
0x1800f6bb1  mov     rcx, cs:?m_databaseReady@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x1800f6bb8  call    cs:__imp_ResetEvent
0x1800f6bbe  mov     rcx, [rsp+1A8h]; this
0x1800f6bc6  test    eax, eax
0x1800f6bc8  jz      loc_1800F6E7A
0x1800f6bce  mov     [rsp+1A8h+var_170], 0
0x1800f6bd7  cmp     qword ptr [rsi], 0
0x1800f6bdb  jnz     short loc_1800F6C00
0x1800f6bdd  mov     rcx, [rsp+1A8h]; this
0x1800f6be5  mov     esi, 8007139Fh
0x1800f6bea  mov     r9d, esi; char *
0x1800f6bed  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f6bf4  mov     edx, 663h; void *
0x1800f6bf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6bfe  jmp     short loc_1800F6C6A
0x1800f6c00  lea     rcx, [rsp+1A8h+var_170]; this
0x1800f6c05  call    ?Reset@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Reset(void)
0x1800f6c0a  mov     rcx, [rsp+1A8h]; this
0x1800f6c12  test    eax, eax
0x1800f6c14  jns     short loc_1800F6C2A
0x1800f6c16  mov     r9d, eax; char *
0x1800f6c19  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f6c20  mov     edx, 665h; void *
0x1800f6c25  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f6c2a  lea     rcx, [rsp+1A8h+var_170]; this
0x1800f6c2f  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x1800f6c34  mov     rcx, [rsp+1A8h]; this
0x1800f6c3c  test    eax, eax
0x1800f6c3e  jns     short loc_1800F6C54
0x1800f6c40  mov     r9d, eax; char *
0x1800f6c43  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\StateRepositor"...
0x1800f6c4a  mov     edx, 127h; void *
0x1800f6c4f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f6c54  lea     r9, [rsp+1A8h+var_170]; struct sqlite3_stmt **
0x1800f6c59  lea     rdx, aVacuum; "VACUUM;"
0x1800f6c60  mov     rcx, [rsi]; struct sqlite3 *
0x1800f6c63  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x1800f6c68  mov     esi, eax
0x1800f6c6a  mov     rcx, [rsp+1A8h]; this
0x1800f6c72  test    esi, esi
0x1800f6c74  js      loc_1800F6E85
0x1800f6c7a  lea     rcx, [rsp+1A8h+var_170]; this
0x1800f6c7f  call    ?Reset@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Reset(void)
0x1800f6c84  xor     r9d, r9d
0x1800f6c87  mov     esi, 3F1h
0x1800f6c8c  lea     r8d, [r9+1]
0x1800f6c90  mov     edx, esi
0x1800f6c92  mov     rcx, [rbx]
0x1800f6c95  call    sqlite3_db_config
0x1800f6c9a  test    eax, eax
0x1800f6c9c  jle     short loc_1800F6CA6
0x1800f6c9e  movzx   eax, ax
0x1800f6ca1  or      eax, 87AF0000h
0x1800f6ca6  mov     rcx, [rsp+1A8h]; this
0x1800f6cae  test    eax, eax
0x1800f6cb0  js      loc_1800F6E99
0x1800f6cb6  lea     rdx, aVacuum; "VACUUM;"
0x1800f6cbd  mov     rcx, rbx; this
0x1800f6cc0  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x1800f6cc5  mov     rcx, [rsp+1A8h]; this
0x1800f6ccd  test    eax, eax
0x1800f6ccf  js      loc_1800F6EAD
0x1800f6cd5  xor     r9d, r9d
0x1800f6cd8  xor     r8d, r8d
0x1800f6cdb  mov     edx, esi
0x1800f6cdd  mov     rcx, [rbx]
0x1800f6ce0  call    sqlite3_db_config
0x1800f6ce5  test    eax, eax
0x1800f6ce7  jle     short loc_1800F6CF1
0x1800f6ce9  movzx   eax, ax
0x1800f6cec  or      eax, 87AF0000h
0x1800f6cf1  mov     rcx, [rsp+1A8h]; this
0x1800f6cf9  test    eax, eax
0x1800f6cfb  js      loc_1800F6EC1
0x1800f6d01  mov     rcx, rbx; this
0x1800f6d04  call    ?ClearCache@Database@StateRepository@@QEAAJXZ; StateRepository::Database::ClearCache(void)
0x1800f6d09  mov     rcx, [rsp+1A8h]; this
0x1800f6d11  test    eax, eax
0x1800f6d13  js      loc_1800F6ED5
0x1800f6d19  mov     rcx, rbx; this
0x1800f6d1c  call    ?Reset@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Reset(void)
0x1800f6d21  mov     rcx, [rsp+1A8h]; this
0x1800f6d29  test    eax, eax
0x1800f6d2b  js      loc_1800F6EE9
0x1800f6d31  call    ?Clear@DatabaseCacheSingleton@StateRepository@@SAJXZ; StateRepository::DatabaseCacheSingleton::Clear(void)
0x1800f6d36  mov     rcx, [rsp+1A8h]; this
0x1800f6d3e  test    eax, eax
0x1800f6d40  js      loc_1800F6EFD
0x1800f6d46  mov     edx, 7; unsigned int
0x1800f6d4b  xor     ecx, ecx; unsigned int
0x1800f6d4d  call    ?PrepareProcessForDatabaseUse@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SAXII@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::PrepareProcessForDatabaseUse(uint,uint)
0x1800f6d52  nop
0x1800f6d53  lea     rcx, [rsp+1A8h+var_170]; this
0x1800f6d58  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800f6d5d  nop
0x1800f6d5e  cmp     qword ptr [rdi+18h], 7
0x1800f6d63  jbe     short loc_1800F6D6A
0x1800f6d65  mov     rax, [rdi]
0x1800f6d68  jmp     short loc_1800F6D6D
0x1800f6d6a  mov     rax, rdi
0x1800f6d6d  mov     rdx, r15; unsigned __int64
0x1800f6d70  mov     [rsp+1A8h+var_188], rax; unsigned __int16 *
0x1800f6d75  lea     r9, byte_180122168; char *
0x1800f6d7c  xor     r8d, r8d; unsigned int
0x1800f6d7f  xor     ecx, ecx; int
0x1800f6d81  call    ?ResetDatabase@CapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@SAXJ_KIPEBDPEBG@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::ResetDatabase(long,unsigned __int64,uint,char const *,ushort const *)
0x1800f6d86  test    cs:byte_180140201, 1
0x1800f6d8d  jz      short loc_1800F6DB4
0x1800f6d8f  cmp     qword ptr [rdi+18h], 7
0x1800f6d94  jbe     short loc_1800F6D99
0x1800f6d96  mov     rdi, [rdi]
0x1800f6d99  mov     dword ptr [rsp+1A8h+var_188], 0
0x1800f6da1  mov     r9, rdi
0x1800f6da4  mov     r8d, r15d
0x1800f6da7  lea     rdx, SettingsDatabaseRecoverySuccessEvent
0x1800f6dae  call    McTemplateU0dzd_EventWriteTransfer
0x1800f6db3  nop
0x1800f6db4  mov     rbx, [rsp+1A8h+var_158]
0x1800f6db9  test    rbx, rbx
0x1800f6dbc  jz      short loc_1800F6DF5
0x1800f6dbe  or      edi, 0FFFFFFFFh
0x1800f6dc1  mov     eax, edi
0x1800f6dc3  lock xadd [rbx+8], eax
0x1800f6dc8  add     eax, edi
0x1800f6dca  jnz     short loc_1800F6DF5
0x1800f6dcc  mov     rax, [rbx]
0x1800f6dcf  mov     rcx, rbx
0x1800f6dd2  mov     rax, [rax]
0x1800f6dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6dda  mov     eax, edi
0x1800f6ddc  lock xadd [rbx+0Ch], eax
0x1800f6de1  add     eax, edi
0x1800f6de3  jnz     short loc_1800F6DF5
0x1800f6de5  mov     rax, [rbx]
0x1800f6de8  mov     rcx, rbx
0x1800f6deb  mov     rax, [rax+8]
0x1800f6def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6df4  nop
0x1800f6df5  mov     rcx, r13; SRWLock
0x1800f6df8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f6dfe  nop
0x1800f6dff  lea     rcx, [rsp+1A8h+var_98]; this
0x1800f6e07  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800f6e0c  lea     rcx, [rsp+1A8h+var_140]; this
0x1800f6e11  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x1800f6e16  mov     rcx, [rsp+1A8h+var_48]
0x1800f6e1e  xor     rcx, rsp; StackCookie
0x1800f6e21  call    __security_check_cookie
0x1800f6e26  add     rsp, 178h
0x1800f6e2d  pop     r15
0x1800f6e2f  pop     r14
0x1800f6e31  pop     r13
0x1800f6e33  pop     rdi
0x1800f6e34  pop     rsi
0x1800f6e35  pop     rbx
0x1800f6e36  retn
0x1800f6e37  mov     rcx, [rsp+1A8h]; this
0x1800f6e3f  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6e46  mov     edx, 0DCh; void *
0x1800f6e4b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800f6e51  mov     r9d, eax; char *
0x1800f6e54  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6e5b  mov     edx, 0E0h; void *
0x1800f6e60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6e66  mov     r9d, eax; char *
0x1800f6e69  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6e70  mov     edx, 0E8h; void *
0x1800f6e75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6e7a  mov     edx, 0A06h; void *
0x1800f6e7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f6e85  mov     r9d, esi; char *
0x1800f6e88  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6e8f  mov     edx, 0F9h; void *
0x1800f6e94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6e99  mov     r9d, eax; char *
0x1800f6e9c  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6ea3  mov     edx, 100h; void *
0x1800f6ea8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6ead  mov     r9d, eax; char *
0x1800f6eb0  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6eb7  mov     edx, 101h; void *
0x1800f6ebc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6ec1  mov     r9d, eax; char *
0x1800f6ec4  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6ecb  mov     edx, 102h; void *
0x1800f6ed0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6ed5  mov     r9d, eax; char *
0x1800f6ed8  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6edf  mov     edx, 107h; void *
0x1800f6ee4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6ee9  mov     r9d, eax; char *
0x1800f6eec  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6ef3  mov     edx, 108h; void *
0x1800f6ef8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6efd  mov     r9d, eax; char *
0x1800f6f00  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f6f07  mov     edx, 109h; void *
0x1800f6f0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
