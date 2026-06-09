# UsageAndQualityInsights::Database::UQIDatabase::TryOpenImpl(void)

- ea: `0x18004f64c`
- end: `0x18004f93d`
- name: `?TryOpenImpl@UQIDatabase@Database@UsageAndQualityInsights@@IEAAXXZ`
- size: `753`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004f630`
- `0x1801051c8`
- `0x180105225`

## callees

- `0x1800033d0`
- `0x180003fdc`
- `0x180004dd8`
- `0x18000eee0`
- `0x1800107b0`
- `0x180019b64`
- `0x18002b258`
- `0x18002b2b0`
- `0x18002b470`
- `0x18002bcc8`
- `0x18002be38`
- `0x18004e1d8`
- `0x18004e5d4`
- `0x18004e68c`
- `0x18004ee20`
- `0x18004f4ac`
- `0x18004f64c`
- `0x18004fa5c`
- `0x18004fb50`
- `0x1800739bc`
- `0x1800c4cfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f701`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004f701`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f8d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f8d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004f6ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004f6ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004f6ba`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004f6ba`

## string_xrefs

- `0x18004f692`: `OpenDatabase for: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UsageAndQualityInsights::Database::UQIDatabase::TryOpenImpl(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // r14
  RTL_SRWLOCK *Ptr; // rdx
  struct sqlite3 **v4; // rbx
  _QWORD *DbPath; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  const char *v10; // rax
  __int128 *v11; // rcx
  struct sqlite3 *v12; // rcx
  struct sqlite3 *v13; // rax
  WINBOOL fPending; // [rsp+20h] [rbp-E0h] BYREF
  struct sqlite3 *v15; // [rsp+28h] [rbp-D8h] BYREF
  union _RTL_RUN_ONCE *v16; // [rsp+30h] [rbp-D0h]
  __int64 v17; // [rsp+38h] [rbp-C8h]
  __int128 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v20; // [rsp+58h] [rbp-A8h]
  const char *v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h]
  _QWORD Src[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v25[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v26[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v27; // [rsp+100h] [rbp+0h]
  __int128 v28; // [rsp+110h] [rbp+10h]

  fPending = 0;
  v2 = this + 5;
  if ( this[8].Ptr <= (PVOID)7 )
    Ptr = this + 5;
  else
    Ptr = (RTL_SRWLOCK *)v2->Ptr;
  UsageAndQualityInsightsTraceLogging::TraceLoggingInfo("OpenDatabase for: %ws", Ptr);
  fPending = 0;
  if ( !__std_init_once_begin_initialize(&stru_180159E80, 0, &fPending, 0) )
    __fastfail(5u);
  if ( fPending )
  {
    v16 = &stru_180159E80;
    v17 = 4;
    sqlite3_initialize();
    if ( !InitOnceComplete(&stru_180159E80, 0, 0) )
      _std_init_once_link_alternate_names_and_abort();
  }
  AcquireSRWLockExclusive(this + 3);
  v16 = (union _RTL_RUN_ONCE *)&this[3];
  v4 = (struct sqlite3 **)&this[4];
  if ( !this[4].Ptr )
  {
    v27 = 0;
    v28 = 0;
    DbPath = UsageAndQualityInsights::Database::UQIDatabase::GetDbPath(Src);
    v6 = std::operator+<wchar_t>(pExceptionObject, DbPath, L"\\");
    v7 = std::operator+<wchar_t>(v26, v6, v2);
    v8 = std::operator+<wchar_t>(v25, v7, L"_unencrypted");
    v9 = std::operator+<wchar_t>(&v21, v8, L".db");
    std::wstring::operator=(&this[10], v9);
    std::wstring::~wstring(&v21);
    std::wstring::~wstring(v25);
    std::wstring::~wstring(v26);
    std::wstring::~wstring(pExceptionObject);
    std::wstring::~wstring(Src);
    v18 = 0;
    v19 = 0;
    v20 = 15;
    LOBYTE(v18) = 0;
    if ( this[13].Ptr <= (PVOID)7 )
      v10 = (const char *)&this[10];
    else
      v10 = (const char *)this[10].Ptr;
    v21 = v10;
    v22 = (__int64)this[12].Ptr;
    to_utf8(&v21, &v18);
    v11 = &v18;
    if ( v20 > 0xF )
      v11 = (__int128 *)v18;
    v15 = 0;
    if ( (unsigned int)openDatabase(v11, &v15, 6, 0, 1) )
    {
      v13 = unique_sqlite3::get((unique_sqlite3 *)&v15);
      sqlite3_error::sqlite3_error((sqlite3_error *)Src, v13);
      sqlite3_error::sqlite3_error(pExceptionObject, Src);
      throw (sqlite3_error *)pExceptionObject;
    }
    if ( v4 == &v15 )
    {
      v12 = v15;
    }
    else
    {
      if ( *v4 )
        unique_sqlite3::release_or_terminate(*v4);
      *v4 = v15;
      v12 = 0;
    }
    if ( v12 )
      unique_sqlite3::release_or_terminate(v12);
    sqlite3_db_config_cpp(*v4);
    v21 = "PRAGMA journal_mode=WAL;";
    v22 = 24;
    sqlite3_exec_single_text_result_cpp(Src, *v4, &v21);
    std::string::~string(Src);
    UsageAndQualityInsights::Database::UQIDatabase::CreateOrUpdateDatabase(
      (UsageAndQualityInsights::Database::UQIDatabase *)this,
      *v4);
    std::string::~string(&v18);
  }
  if ( this != (RTL_SRWLOCK *)-24LL )
    ReleaseSRWLockExclusive(this + 3);
}

```

## disassembly

```asm
0x18004f64c  mov     [rsp-8+arg_8], rbx
0x18004f651  mov     [rsp-8+arg_10], rsi
0x18004f656  push    rbp
0x18004f657  push    rdi
0x18004f658  push    r14
0x18004f65a  lea     rbp, [rsp-30h]
0x18004f65f  sub     rsp, 130h
0x18004f666  mov     rax, cs:__security_cookie
0x18004f66d  xor     rax, rsp
0x18004f670  mov     [rbp+40h+var_20], rax
0x18004f674  mov     rsi, rcx
0x18004f677  mov     [rsp+140h+fPending], 0
0x18004f67f  lea     r14, [rcx+28h]
0x18004f683  cmp     qword ptr [r14+18h], 7
0x18004f688  jbe     short loc_18004F68F
0x18004f68a  mov     rdx, [r14]
0x18004f68d  jmp     short loc_18004F692
0x18004f68f  mov     rdx, r14
0x18004f692  lea     rcx, aOpendatabaseFo; "OpenDatabase for: %ws"
0x18004f699  call    ?TraceLoggingInfo@UsageAndQualityInsightsTraceLogging@@SAXPEBDZZ; UsageAndQualityInsightsTraceLogging::TraceLoggingInfo(char const *,...)
0x18004f69e  mov     [rsp+140h+fPending], 0
0x18004f6a6  xor     r9d, r9d; lpContext
0x18004f6a9  lea     r8, [rsp+140h+fPending]; fPending
0x18004f6ae  xor     edx, edx; dwFlags
0x18004f6b0  lea     rbx, stru_180159E80
0x18004f6b7  mov     rcx, rbx; lpInitOnce
0x18004f6ba  call    cs:__imp___std_init_once_begin_initialize
0x18004f6c0  test    eax, eax
0x18004f6c2  jnz     short loc_18004F6C9
0x18004f6c4  lea     ecx, [rax+5]
0x18004f6c7  int     29h; Win8: RtlFailFast(ecx)
0x18004f6c9  cmp     [rsp+140h+fPending], 0
0x18004f6ce  jz      short loc_18004F6FA
0x18004f6d0  mov     [rsp+140h+var_110], rbx
0x18004f6d5  mov     [rsp+140h+var_108], 4
0x18004f6de  call    sqlite3_initialize
0x18004f6e3  nop
0x18004f6e4  xor     r8d, r8d; lpContext
0x18004f6e7  xor     edx, edx; dwFlags
0x18004f6e9  mov     rcx, rbx; lpInitOnce
0x18004f6ec  call    cs:__imp_InitOnceComplete
0x18004f6f2  test    eax, eax
0x18004f6f4  jz      loc_18004F937
0x18004f6fa  lea     rdi, [rsi+18h]
0x18004f6fe  mov     rcx, rdi; SRWLock
0x18004f701  call    cs:__imp_AcquireSRWLockExclusive
0x18004f707  mov     [rsp+140h+var_110], rdi
0x18004f70c  lea     rbx, [rsi+20h]
0x18004f710  cmp     qword ptr [rbx], 0
0x18004f714  jnz     loc_18004F8D0
0x18004f71a  xorps   xmm0, xmm0
0x18004f71d  movups  [rbp+40h+var_40], xmm0
0x18004f721  movups  [rbp+40h+var_30], xmm0
0x18004f725  lea     rcx, [rbp+40h+Src]; Src
0x18004f729  call    ?GetDbPath@UQIDatabase@Database@UsageAndQualityInsights@@KA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UsageAndQualityInsights::Database::UQIDatabase::GetDbPath(void)
0x18004f72e  nop
0x18004f72f  lea     r8, asc_18012C1F0; "\\"
0x18004f736  mov     rdx, rax
0x18004f739  lea     rcx, [rbp+40h+pExceptionObject]
0x18004f73d  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f742  nop
0x18004f743  mov     r8, r14
0x18004f746  mov     rdx, rax
0x18004f749  lea     rcx, [rbp+40h+var_60]
0x18004f74d  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18004f752  nop
0x18004f753  lea     r8, aUnencrypted; "_unencrypted"
0x18004f75a  mov     rdx, rax
0x18004f75d  lea     rcx, [rbp+40h+var_80]
0x18004f761  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f766  nop
0x18004f767  lea     r8, aDb; ".db"
0x18004f76e  mov     rdx, rax
0x18004f771  lea     rcx, [rsp+140h+var_E0]
0x18004f776  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x18004f77b  lea     r14, [rsi+50h]
0x18004f77f  mov     rdx, rax
0x18004f782  mov     rcx, r14
0x18004f785  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004f78a  lea     rcx, [rsp+140h+var_E0]; void *
0x18004f78f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f794  nop
0x18004f795  lea     rcx, [rbp+40h+var_80]; void *
0x18004f799  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f79e  nop
0x18004f79f  lea     rcx, [rbp+40h+var_60]; void *
0x18004f7a3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f7a8  nop
0x18004f7a9  lea     rcx, [rbp+40h+pExceptionObject]; void *
0x18004f7ad  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f7b2  nop
0x18004f7b3  lea     rcx, [rbp+40h+Src]; void *
0x18004f7b7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004f7bc  xorps   xmm0, xmm0
0x18004f7bf  movups  [rsp+140h+var_100], xmm0
0x18004f7c4  mov     [rsp+140h+var_F0], 0
0x18004f7cd  mov     [rsp+140h+var_E8], 0Fh
0x18004f7d6  mov     byte ptr [rsp+140h+var_100], 0
0x18004f7db  cmp     qword ptr [r14+18h], 7
0x18004f7e0  jbe     short loc_18004F7E7
0x18004f7e2  mov     rax, [r14]
0x18004f7e5  jmp     short loc_18004F7EA
0x18004f7e7  mov     rax, r14
0x18004f7ea  mov     [rsp+140h+var_E0], rax
0x18004f7ef  mov     rax, [r14+10h]
0x18004f7f3  mov     [rsp+140h+var_D8], rax
0x18004f7f8  lea     rdx, [rsp+140h+var_100]
0x18004f7fd  lea     rcx, [rsp+140h+var_E0]
0x18004f802  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x18004f807  lea     rcx, [rsp+140h+var_100]
0x18004f80c  cmp     [rsp+140h+var_E8], 0Fh
0x18004f812  cmova   rcx, qword ptr [rsp+140h+var_100]
0x18004f818  mov     [rsp+140h+var_118], 0
0x18004f821  mov     r14d, 1
0x18004f827  mov     [rsp+140h+fPending], r14d
0x18004f82c  xor     r9d, r9d
0x18004f82f  lea     r8d, [r14+5]
0x18004f833  lea     rdx, [rsp+140h+var_118]
0x18004f838  call    openDatabase
0x18004f83d  test    eax, eax
0x18004f83f  jnz     loc_18004F902
0x18004f845  lea     rax, [rsp+140h+var_118]
0x18004f84a  cmp     rbx, rax
0x18004f84d  jz      short loc_18004F868
0x18004f84f  mov     rcx, [rbx]; struct sqlite3 *
0x18004f852  test    rcx, rcx
0x18004f855  jz      short loc_18004F85C
0x18004f857  call    ?release_or_terminate@unique_sqlite3@@CAXPEAUsqlite3@@@Z; unique_sqlite3::release_or_terminate(sqlite3 *)
0x18004f85c  mov     rax, [rsp+140h+var_118]
0x18004f861  mov     [rbx], rax
0x18004f864  xor     ecx, ecx
0x18004f866  jmp     short loc_18004F86D
0x18004f868  mov     rcx, [rsp+140h+var_118]; struct sqlite3 *
0x18004f86d  test    rcx, rcx
0x18004f870  jz      short loc_18004F877
0x18004f872  call    ?release_or_terminate@unique_sqlite3@@CAXPEAUsqlite3@@@Z; unique_sqlite3::release_or_terminate(sqlite3 *)
0x18004f877  xor     r9d, r9d
0x18004f87a  mov     r8d, r14d
0x18004f87d  mov     edx, 3EEh
0x18004f882  mov     rcx, [rbx]; struct sqlite3 *
0x18004f885  call    sqlite3_db_config_cpp
0x18004f88a  lea     rax, aPragmaJournalM; "PRAGMA journal_mode=WAL;"
0x18004f891  mov     [rsp+140h+var_E0], rax
0x18004f896  mov     [rsp+140h+var_D8], 18h
0x18004f89f  lea     r8, [rsp+140h+var_E0]
0x18004f8a4  mov     rdx, [rbx]
0x18004f8a7  lea     rcx, [rbp+40h+Src]
0x18004f8ab  call    ?sqlite3_exec_single_text_result_cpp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@2@@Z; sqlite3_exec_single_text_result_cpp(sqlite3 *,std::string_view)
0x18004f8b0  lea     rcx, [rbp+40h+Src]; void *
0x18004f8b4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004f8b9  mov     rdx, [rbx]; struct sqlite3 *
0x18004f8bc  mov     rcx, rsi; this
0x18004f8bf  call    ?CreateOrUpdateDatabase@UQIDatabase@Database@UsageAndQualityInsights@@IEAAXPEAUsqlite3@@@Z; UsageAndQualityInsights::Database::UQIDatabase::CreateOrUpdateDatabase(sqlite3 *)
0x18004f8c4  nop
0x18004f8c5  lea     rcx, [rsp+140h+var_100]; void *
0x18004f8ca  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004f8cf  nop
0x18004f8d0  test    rdi, rdi
0x18004f8d3  jz      short loc_18004F8DE
0x18004f8d5  mov     rcx, rdi; SRWLock
0x18004f8d8  call    cs:__imp_ReleaseSRWLockExclusive
0x18004f8de  mov     rcx, [rbp+40h+var_20]
0x18004f8e2  xor     rcx, rsp; StackCookie
0x18004f8e5  call    __security_check_cookie
0x18004f8ea  lea     r11, [rsp+140h+var_10]
0x18004f8f2  mov     rbx, [r11+28h]
0x18004f8f6  mov     rsi, [r11+30h]
0x18004f8fa  mov     rsp, r11
0x18004f8fd  pop     r14
0x18004f8ff  pop     rdi
0x18004f900  pop     rbp
0x18004f901  retn
0x18004f902  lea     rcx, [rsp+140h+var_118]; this
0x18004f907  call    ?get@unique_sqlite3@@QEBAPEAUsqlite3@@XZ; unique_sqlite3::get(void)
0x18004f90c  mov     rdx, rax; struct sqlite3 *
0x18004f90f  lea     rcx, [rbp+40h+Src]; this
0x18004f913  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x18004f918  nop
0x18004f919  lea     rdx, [rbp+40h+Src]
0x18004f91d  lea     rcx, [rbp+40h+pExceptionObject]
0x18004f921  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x18004f926  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x18004f92d  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18004f931  call    _CxxThrowException_0
0x18004f937  call    __std_init_once_link_alternate_names_and_abort
```
