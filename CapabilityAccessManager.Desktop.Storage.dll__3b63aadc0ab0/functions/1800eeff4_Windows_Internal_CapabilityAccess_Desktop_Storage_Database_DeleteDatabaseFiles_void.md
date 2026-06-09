# Windows::Internal::CapabilityAccess::Desktop::Storage::Database::DeleteDatabaseFiles(void)

- ea: `0x1800eeff4`
- end: `0x1800ef1bc`
- name: `?DeleteDatabaseFiles@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXXZ`
- size: `456`
- prototype: `void __fastcall(Windows::Internal::CapabilityAccess::Desktop::Storage::Database *this, __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800edc60`
- `0x18010b11c`

## callees

- `0x180003060`
- `0x1800e793c`
- `0x1800ed70c`
- `0x1800eeff4`
- `0x1800f44fc`
- `0x1800f610c`
- `0x1800f62d8`
- `0x1800f6448`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef134`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef02c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef0a2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef11f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef02c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef0a2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef11f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Database::DeleteDatabaseFiles(
        Windows::Internal::CapabilityAccess::Desktop::Storage::Database *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  void **StorageDatabaseFullPath; // rax
  BOOL v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  const char *v8; // r9
  const WCHAR *v9; // rcx
  BOOL v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  const char *v13; // r9
  const WCHAR *v14; // rcx
  BOOL v15; // ebx
  const char *v16; // r9
  LPCWSTR lpFileName[3]; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int64 v18; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  StorageDatabaseFullPath = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseFullPath(
                              (void **)lpFileName,
                              a2,
                              a3,
                              a4);
  if ( (unsigned __int64)StorageDatabaseFullPath[3] > 7 )
    StorageDatabaseFullPath = (void **)*StorageDatabaseFullPath;
  v5 = DeleteFileW((LPCWSTR)StorageDatabaseFullPath);
  std::wstring::~wstring(lpFileName);
  if ( !v5 && GetLastError() != 2 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x73E,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      v8);
  if ( !Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::GlobalManager::m_initState )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
      v8);
  Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(
    (void **)lpFileName,
    v6,
    v7,
    v8);
  std::wstring::operator+=(lpFileName, L"\\");
  std::wstring::operator+=(lpFileName, L"CapabilityConsentStorage.db-shm");
  v9 = (const WCHAR *)lpFileName;
  if ( v18 > 7 )
    v9 = lpFileName[0];
  v10 = DeleteFileW(v9);
  std::wstring::~wstring(lpFileName);
  if ( !v10 && GetLastError() != 2 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x746,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      v13);
  if ( !Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::GlobalManager::m_initState )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\globals.cpp",
      v13);
  Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(
    (void **)lpFileName,
    v11,
    v12,
    v13);
  std::wstring::operator+=(lpFileName, L"\\");
  std::wstring::operator+=(lpFileName, L"CapabilityConsentStorage.db-wal");
  v14 = (const WCHAR *)lpFileName;
  if ( v18 > 7 )
    v14 = lpFileName[0];
  v15 = DeleteFileW(v14);
  std::wstring::~wstring(lpFileName);
  if ( !v15 && GetLastError() != 2 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x74E,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      v16);
}

```

## disassembly

```asm
0x1800eeff4  mov     [rsp-8+arg_0], rbx
0x1800eeff9  push    rbp
0x1800eeffa  mov     rbp, rsp
0x1800eeffd  sub     rsp, 50h
0x1800ef001  mov     rax, cs:__security_cookie
0x1800ef008  xor     rax, rsp
0x1800ef00b  mov     [rbp+var_8], rax
0x1800ef00f  mov     [rbp+var_30], 0
0x1800ef016  lea     rcx, [rbp+lpFileName]; Src
0x1800ef01a  call    ?GetStorageDatabaseFullPath@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseFullPath(void)
0x1800ef01f  cmp     qword ptr [rax+18h], 7
0x1800ef024  jbe     short loc_1800EF029
0x1800ef026  mov     rax, [rax]
0x1800ef029  mov     rcx, rax; lpFileName
0x1800ef02c  call    cs:__imp_DeleteFileW
0x1800ef032  mov     ebx, eax
0x1800ef034  lea     rcx, [rbp+lpFileName]
0x1800ef038  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ef03d  test    ebx, ebx
0x1800ef03f  jnz     short loc_1800EF050
0x1800ef041  call    cs:__imp_GetLastError
0x1800ef047  cmp     eax, 2
0x1800ef04a  jnz     loc_1800EF16C
0x1800ef050  mov     eax, cs:?m_initState@GlobalManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::GlobalManager::m_initState
0x1800ef056  nop
0x1800ef057  mov     rcx, [rbp+8]; this
0x1800ef05b  cmp     eax, 1
0x1800ef05e  jb      loc_1800EF182
0x1800ef064  lea     rcx, [rbp+lpFileName]; Src
0x1800ef068  call    ?GetStorageDatabaseDirectory@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(void)
0x1800ef06d  mov     [rbp+var_30], 1
0x1800ef074  lea     rdx, asc_180122640; "\\"
0x1800ef07b  lea     rcx, [rbp+lpFileName]; Src
0x1800ef07f  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1800ef084  lea     rdx, aCapabilitycons; "CapabilityConsentStorage.db-shm"
0x1800ef08b  lea     rcx, [rbp+lpFileName]; Src
0x1800ef08f  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1800ef094  lea     rcx, [rbp+lpFileName]
0x1800ef098  cmp     [rbp+var_10], 7
0x1800ef09d  cmova   rcx, [rbp+lpFileName]; lpFileName
0x1800ef0a2  call    cs:__imp_DeleteFileW
0x1800ef0a8  mov     ebx, eax
0x1800ef0aa  mov     [rbp+var_30], 0
0x1800ef0b1  lea     rcx, [rbp+lpFileName]
0x1800ef0b5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ef0ba  test    ebx, ebx
0x1800ef0bc  jnz     short loc_1800EF0CD
0x1800ef0be  call    cs:__imp_GetLastError
0x1800ef0c4  cmp     eax, 2
0x1800ef0c7  jnz     loc_1800EF194
0x1800ef0cd  mov     eax, cs:?m_initState@GlobalManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::GlobalManager::m_initState
0x1800ef0d3  nop
0x1800ef0d4  mov     rcx, [rbp+8]; this
0x1800ef0d8  cmp     eax, 1
0x1800ef0db  jb      loc_1800EF1AA
0x1800ef0e1  lea     rcx, [rbp+lpFileName]; Src
0x1800ef0e5  call    ?GetStorageDatabaseDirectory@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetStorageDatabaseDirectory(void)
0x1800ef0ea  mov     [rbp+var_30], 2
0x1800ef0f1  lea     rdx, asc_180122640; "\\"
0x1800ef0f8  lea     rcx, [rbp+lpFileName]; Src
0x1800ef0fc  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1800ef101  lea     rdx, aCapabilitycons_0; "CapabilityConsentStorage.db-wal"
0x1800ef108  lea     rcx, [rbp+lpFileName]; Src
0x1800ef10c  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1800ef111  lea     rcx, [rbp+lpFileName]
0x1800ef115  cmp     [rbp+var_10], 7
0x1800ef11a  cmova   rcx, [rbp+lpFileName]; lpFileName
0x1800ef11f  call    cs:__imp_DeleteFileW
0x1800ef125  mov     ebx, eax
0x1800ef127  lea     rcx, [rbp+lpFileName]
0x1800ef12b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ef130  test    ebx, ebx
0x1800ef132  jnz     short loc_1800EF13F
0x1800ef134  call    cs:__imp_GetLastError
0x1800ef13a  cmp     eax, 2
0x1800ef13d  jnz     short loc_1800EF156
0x1800ef13f  mov     rcx, [rbp+var_8]
0x1800ef143  xor     rcx, rsp; StackCookie
0x1800ef146  call    __security_check_cookie
0x1800ef14b  mov     rbx, [rsp+50h+arg_0]
0x1800ef150  add     rsp, 50h
0x1800ef154  pop     rbp
0x1800ef155  retn
0x1800ef156  mov     rcx, [rbp+8]; this
0x1800ef15a  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef161  mov     edx, 74Eh; void *
0x1800ef166  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ef16c  mov     rcx, [rbp+8]; this
0x1800ef170  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef177  mov     edx, 73Eh; void *
0x1800ef17c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ef182  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef189  mov     edx, 9Ah; void *
0x1800ef18e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800ef194  mov     rcx, [rbp+8]; this
0x1800ef198  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef19f  mov     edx, 746h; void *
0x1800ef1a4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ef1aa  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800ef1b1  mov     edx, 0A7h; void *
0x1800ef1b6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
